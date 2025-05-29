---
layout: post
title: "INNHABIT Network Overview"
date: 2025-05-26
categories: [blog]
---
# What is INNHABIT
INNHABIT is an Entry-Exit-Tracking system, monitoring every entrance at AAU INNOVATE via Computer Vision, then sending Entry/Exit events to a Central Aggregation Server.
![SystemOverview]({{ site.baseurl }}/assets/SystemDiagramAlternate.png){: style="width:100%;" }
> #### **Goal of Networking for INNHABIT**
> - Send Entry/Exit events from Jetson to Aggregation Server
> - Store Entry/Exit events for further analysis
> - Update setting on Jetson remotely from Aggregation Server
> - Serve a Web Dashboard for detailed statics
> - Serve focused statics to existing digital signage
  
# Jetson Internal architecture
The software of the Jetson implement multiple threads each having a class and task assigned.  
A simplifyed thread description and diagram can be seen below:  
![SystemOverview]({{ site.baseurl }}/assets/ThreadDiagram.png){: style="width:100%;" }
The figure shows all main threads and the shared resourses between them.
The main program flow is a follows
> - **FrameCapturer Thread** Captures frames from camera and adds them to *frameQueue*  
> - **Detection Thread** Takes frames from **frameQueue**, runs ML and tracking, calls **Api Handler Thread** if Entry/Exit is detected. Adds image with detection and tracking to **displayQueue**, runs ML and tracking, calls **Api Hander Thread** if Entry/Exit is detected. Adds image with detection and tracking to **displayQueue**.
> - **Display Thread** Takes frames from **displayQueue** and dispays them to either an attached monitor, x11 forwarding session, or RTSP stream. 
> - **DevicePoller Thread** uses **Api Handler Thread** to poll **Aggregation server** for updated settings
> - **Api Handler Thread** handles all network communication, takes request/events from a queue, ensuring no event is skipped cause of other events stalling.
>   

### Sending Entry/Exit events
An Entry/Exit event is sent everytime it is detected that a person has entered or exited.
The sending of these event is handled by a dedicated thread *ApiHandler*.  
The flow of such and event can be seen below:
![SystemOverview]({{ site.baseurl }}/assets/network_person_event_diagram.png){: style="width:100%;" }
The Jetsons installed are only be connected to via Wi-Fi. This makes deployment more flexible and reduces installation costs.  
The Jetsons are connected to a *Word-Wide-Web* connected network, seperate from *eduroam*. Bypassing alot of issues caused by the security system around *eduroam*. The Jetsons uploads Entry/Exit events via HTTP*s* to the Aggregation server hosted with the *DNS* adress *INNHABIT.dk*.
The Jetsons uses *libcurl* for sending HTTP*s* PUT request to *INNHABIT* at designted *API* endpoints.
> #### **API endpoints for Jetson**
> - INNHABIT.dk/api/v1/events/entries
> - INNHABIT.dk/api/v1/events/exits
  
For handling the all *API* events the Jetsons software has a dedicated thread and class *ApiHandler*.
*ApiHandler* works of a queue of *API* events ensuring no events are missed or stalls the system.
*libcurl* is designed to simplify the integration of HTTP*s*, and the code for contruction and sending a HTTP*s* request with JSON body is seen below.
```c++
#ApiHandler:sendPostRequest

json ApiHandler::sendPostRequest(const std::string& endpoint, const json& data) {
    struct curl_slist* headers = nullptr;
    headers = curl_slist_append(headers, "Content-Type: application/json");

    std::string auth_header = "Authorization: Bearer " + api_key_;
    headers = curl_slist_append(headers, auth_header.c_str());

    std::string full_url = base_url_ + endpoint;
    curl_easy_setopt(curl_, CURLOPT_URL, full_url.c_str());

    std::string data_str = data.dump();
    curl_easy_setopt(curl_, CURLOPT_POSTFIELDS, data_str.c_str());

    curl_easy_setopt(curl_, CURLOPT_HTTPHEADER, headers);
    std::string response;
    curl_easy_setopt(curl_, CURLOPT_WRITEFUNCTION, writeCallback);
    curl_easy_setopt(curl_, CURLOPT_WRITEDATA, &response);

    long http_code = 0;
    CURLcode res = curl_easy_perform(curl_);
    curl_easy_getinfo(curl_, CURLINFO_RESPONSE_CODE, &http_code);

    json result;
    if (res == CURLE_OK) {
        if (http_code >= 200 && http_code < 300) {
            try {
                result = json::parse(response, nullptr, false);
                if (result.is_discarded()) {
                    ERROR("Failed to parse response as JSON");
                    result = json();
                } else {
                    last_api_success_ = true;
                }
            } catch (const json::parse_error& e) {
                ERROR("Parse error: " << e.what());
                result = json();
                last_api_success_ = false;
            }
        } else {
            ERROR("HTTP error: " << http_code << " - Response: " << response);
            result = json();
            last_api_success_ = false;
        }
    } else {
        ERROR("CURL error: " << curl_easy_strerror(res));
        result = json();
        last_api_success_ = false;
    }

    curl_slist_free_all(headers);
    return result;
}
```
The HTTP request contructed from this example looks something like:  
```c++
POST /api/v1/events/entries/ HTTP/1.1
Host: innhabit.dk
Authorization: Bearer <GoodEncryptedKeyForSpecificEntrance>
Content-Type: application/json

{
  "timestamp": "2025-05-29T12:34:56Z"
}
```

With a HTTP POST request sent to the server, what then happens when it's recieved?  
# Aggregation Server
The internal architecture is run inside a [**Docker**](https://www.docker.com/) network with multiple containers handling different parts of the system.  
The *Docker* network can be seen below: *All arrows a bi-directional*
![SystemOverview]({{ site.baseurl }}/assets/DockerDiagram.png){: style="width:100%;" }
As can be seen on the image above, the *Docker* network consists of 4 containers described below:  
### NGINX
[**NGINX**](https://nginx.org/) can be seen as the front end of the system, being the only container able of direct communication with clients.
INGINX servers client with all static resourses such as HTML and Images, thenpasses request to Gunicorn if any logic needs to be handles, such as permissions or dynamically updating charts.

