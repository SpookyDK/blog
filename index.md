---
layout: home
title: A place of experimentation
---

Microcontrollers to 3D rendering and blinking lights.

---

## Latest Posts

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a> – {{ post.date | date: "%Y-%m-%d" }}
    </li>
  {% endfor %}
</ul>

