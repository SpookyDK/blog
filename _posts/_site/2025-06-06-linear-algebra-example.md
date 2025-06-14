
---
layout: post
title: "Linear Algebra Example"
date: 2025-06-10
categories: [blog]
---
<!-- KaTeX CSS og JS -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js"
  onload="renderMathInElement(document.body, {
    delimiters: [
      {left: '$$', right: '$$', display: true},
      {left: '$', right: '$', display: false}
    ]
  });"></script>
# 📘 Lineær Algebra – Eksamen 2025

## 1. Hvordan multiplicerer man to matricer? Hvilke størrelser skal de to matricer A og B have, så at deres produkt AB er defineret? Lille eksempel på det, fx 3×2-matrix gange to-dimensionelt vektor.

To matricer

$$
A \in \mathbb{R}^{m \times n} \quad \text{og} \quad B \in \mathbb{R}^{n \times p}
$$

kan multipliceres, hvis **antallet af søjler i $A$** er lig med **antallet af rækker i $B$**. Produktet

$$
AB \in \mathbb{R}^{m \times p}
$$

bliver da en matrix i $\mathbb{R}^{m \times p}$.

**Eksempel:**

$$
A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \\ 5 & 6 \end{bmatrix}, \quad
x = \begin{bmatrix} 7 \\ 8 \end{bmatrix}
\Rightarrow
Ax = \begin{bmatrix} 1\cdot7 + 2\cdot8 \\ 3\cdot7 + 4\cdot8 \\ 5\cdot7 + 6\cdot8 \end{bmatrix} = \begin{bmatrix} 23 \\ 53 \\ 83 \end{bmatrix}
$$

---

## 2. Gælder altid AB = BA, hvis A og B begge er n×n-matricer? (Nej, oftest ikke!)

Nej, matrixmultiplikation er **ikke kommutativ**. Dvs. generelt gælder:

$$
AB \neq BA
$$

**Undtagelser:** Det kan dog gælde, hvis:
- \( A = I \) (identitetsmatrix)
- \( A \) og \( B \) er diagonale og kommuterer
- \( A \) og \( B \) er potenser af samme matrix

---

## 3. Hvad sker, når man ganger matricen A fra venstre eller højre med identitetsmatricen I af den tilpasse størrelse? (Ingenting, man får bare igen A.)

Hvis 
$$
A = \mathbb{R}^{m \times n} \quad \text{og} \quad I
$$
har passende størrelse, så gælder:
$$
IA = A \quad \text{og} \quad AI = A
$$

---

## 4. Hvor mange løsninger kan et lineært ligningssystem Ax = b i princippet have?

Et lineært system kan have:
- **Ingen løsning** (inkonsistent)
- **Én entydig løsning**
- **Uendeligt mange løsninger**

---

## 5. Hvordan kan man undersøge, om Ax = b har løsninger og i givet fald finde dem?

Brug **Gauss-elimination** til at omskrive systemet til trappeform.

- Tjek om systemet er **konsistent**
- Brug **tilbageindsættelse** for at finde løsninger, hvis systemet har løsninger

---

## 6. Hvad er totalmatricen tilknyttet Ax = b?

Den **totalmatricen** er matrixen dannet ved at sætte højresiden $b$ sammen med koefficientmatrixen $A$:

$$
[A \mid b]
$$

---

## 7. Hvilke elementære rækkeoperationer kender du?

1. Ombytning af to rækker
2. Multiplikation af en række med en ikke-nul konstant
3. Lægge en multiplum af én række til en anden

---

## 8. Hvad er en trappeform og hvad er specielt ved en reduceret trappeform?

**Trappeform:**
- Alle nullerækker nederst
- Første ikke-nul element i en række (pivot) er længere til højre end i rækken ovenfor
- Pivotelementet er ofte 1

**Reduceret trappeform:**
- Alle pivotelementer er 1
- Alle andre elementer i pivot-søjlerne er 0

---

## 9. Hvordan kan man aflæse fra en trappeform af totalmatricen, om systemet er løseligt eller ej, og hvor mange løsninger man har hvis systemet er løseligt? Hvordan kan man se, om en variable er fri? Hvordan kan man bestemme løsninger ud fra en trappeform, hvis systemet er konsistent?

- Hvis der er en række som $0 = d$, hvor $d \neq 0$: **ingen løsning**
- Hvis antallet af pivot-søjler $<$ antal variable: **fri variable**
- Brug **tilbageindsættelse** til at finde løsninger

---

## 10. Kan du bringe følgende totalmatrix på trappeform?

$$
\left[\begin{array}{ccccc}
-1 & 2 & 3 & 4 & 5 \\
1 & 3 & 1 & 1 & 0 \\
0 & -1 & 2 & 1 & 1
\end{array}\right]
$$

**Løsning (Gauss-elimination):**

1. Byt række 1 og 2  
2. Brug række 1 til at eliminere elementet i række 2  
3. Fortsæt til trappeform

Resultatet (trappeform):

$$
\left[\begin{array}{ccccc}
1 & 3 & 1 & 1 & 0 \\
0 & 5 & 4 & 5 & 5 \\
0 & 0 & \dots & \dots & \dots
\end{array}\right]
$$

---

## 11. Hvad betyder det, at en matrix er på reduceret trappeform?

En matrix er i **reduceret trappeform**, hvis:

- Den er i trappeform
- Alle **pivotelementer** (første ikke-nul elementer i hver række) er 1
- Alle **andre elementer i pivot-søjlen** er 0

Det gør det nemt at aflæse løsninger direkte.

---

## 12. Hvordan kan man løse Ax = b vha. reduceret trappeform?

1. Sæt den **totalmatricen** op: $[A \mid b]$
2. Brug **Gauss-Jordan elimination** for at opnå **reduceret trappeform**  
3. Aflæs løsningen:  
   - Hvis systemet er entydigt løst: én løsning  
   - Hvis fri variable: uendelig mange løsninger, skriv som parameterudtryk  

---

## 13. Hvor mange løsninger har systemet Ax = 0?

Systemet $Ax = 0$ har altid **mindst én løsning**: den trivielle $x = 0$

Antal løsninger afhænger af **rangen**:
- Hvis rang $A = n$: kun triviel løsning
- Hvis rang $A < n$: uendelig mange løsninger

---

## 14. Hvornår har systemet Ax = 0 kun den trivielle løsning?
Hvis matrix $A \in \mathbb{R}^{m \times n}$ har **fuld søjlerang**, altså $\text{rang}(A) = n$, så har systemet kun løsningen:

$$
x = 0
$$

---

## 15. Hvordan defineres rangen af en matrix?

**Rangen** af en matrix $A$ er **antallet af lineært uafhængige rækker (eller søjler)**.

= antallet af **pivot-elementer** i trappeformen

---

## 16. Hvad siger sætningen om rang og løsning af systemet $Ax = b$?

Systemet $Ax = b$ er **løseligt** hvis og kun hvis:

$$
\text{rang}(A) = \text{rang}([A \mid b])
$$

Hvis løsningen findes, og $\text{rang}(A) = n$: entydig løsning  
Hvis $\text{rang}(A) < n$: uendeligt mange løsninger

---

## 17. Giv eksempler på vektorer i $\mathbb{R}^n$

Eksempel på en vektor i $\mathbb{R}^3$:

$$
v = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}
$$

Det er blot en kolonne med 3 reelle tal.

---

## 18. Hvordan defineres lineær kombination af vektorer?

En **lineær kombination** af vektorer $v_1, v_2, \dots, v_k \in \mathbb{R}^n$ er:

$$
a_1 v_1 + a_2 v_2 + \dots + a_k v_k
$$

hvor $a_i \in \mathbb{R}$

---

## 19. Hvornår siges en mængde af vektorer at være lineært afhængige/uafhængige?

- **Afhængige:** En vektor kan skrives som lineær kombination af de andre  
- **Uafhængige:** Ingen vektor kan skrives som lineær kombination af de andre

Formelt:  
$$
a_1 v_1 + \dots + a_k v_k = 0 \quad \Rightarrow \quad a_1 = \dots = a_k = 0
$$

---
## 20. Hvad er søjlerummet for en matrix?

**Søjlerummet** (column space) for matrix $A \in \mathbb{R}^{m \times n}$ er:

$$
\text{Col}(A) = \{ Ax \mid x \in \mathbb{R}^n \} \subseteq \mathbb{R}^m
$$

= mængden af alle lineære kombinationer af søjlerne i $A$

## 21. Hvordan udregner man determinanter af 2×2 og 3×3-matricer?

- **2×2 matrix:**

$$
\det\begin{bmatrix} a & b \\ c & d \end{bmatrix} = ad - bc
$$

- **3×3 matrix:**

Brug sarrus-reglen eller kofaktorudvikling:

$$
\det\begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix}
= aei + bfg + cdh - ceg - bdi - afh
$$

---

## 22. Hvad betyder kofaktorudvidelse?

Kofaktorudvidelse (Laplace-udvikling) betyder at bestemme determinanten af en matrix ved at:

- Udvikle langs en række eller søjle:

$$
\det(A) = \sum_{j=1}^{n} (-1)^{i+j} a_{ij} \cdot \det(A_{ij})
$$

hvor $A_{ij}$ er undermatricen uden række $i$ og søjle $j$.

---

## 23. Hvad sker med $\det(A)$, når man bytter to rækker eller søjler?

- Når man bytter to **rækker** eller **søjler** i $A$, så ændrer determinanten **fortegn**:

$$
\det(\text{byttet } A) = -\det(A)
$$

---

## 24. Hvad sker med $\det(A)$, når man lægger et multiplum af én række til en anden?

- Determinanten **ændrer ikke værdi**:

$$
\det(A) = \det(A + \lambda \cdot \text{anden række})
$$

Gælder også for søjler.

---

## 25. Hvad gælder for determinanter under transponering og multiplikation?

- 
$$
\det(A^T) = \det(A)
$$
- 
$$
\det(AB) = \det(A) \cdot \det(B)
$$

---

## 26. Hvis $A$ er inverterbar, hvad er $\det(A^{-1})$?

$$
\det(A^{-1}) = \frac{1}{\det(A)}
$$

Fordi:

$$
\det(I) = \det(A A^{-1}) = \det(A) \cdot \det(A^{-1}) = 1
$$

---

## 27. Antag at $S$ er symmetrisk og inverterbar. Vis at $S^{-1}$ også er symmetrisk.

Hvis $S = S^T$, og $S$ er inverterbar:

- Tag transponatet: 

$$
(S^{-1})^T = (S^T)^{-1} = S^{-1}
$$

- Altså: $S^{-1} = (S^{-1})^T$, dvs. **symmetrisk**

---

## 28. Hvad er en ortogonal matrix $U$?

En kvadratisk matrix $U$ er **ortogonal**, hvis:

$$
U^{-1} = U^T \quad \text{eller} \quad U^T U = I
$$

Det betyder, at søjlerne i $U$ er **ortonormale**.

---

## 29. Er produktet $U_1 U_2$ af to ortogonale matricer igen ortogonal?

Ja!

- Hvis $U_1$ og $U_2$ er ortogonale:

$$
(U_1 U_2)^T (U_1 U_2) = U_2^T U_1^T U_1 U_2 = U_2^T I U_2 = U_2^T U_2 = I
$$

Altså er $U_1 U_2$ ortogonal.

---

## 30. Hvad forstår vi ved en linearkombination af vektorerne $v_1, ..., v_k$?

En **linearkombination** af vektorer $v_1, ..., v_k$ er:

$$
a_1 v_1 + a_2 v_2 + \dots + a_k v_k
\quad \text{hvor } a_i \in \mathbb{R}
$$

Det er en måde at danne nye vektorer ud fra givne vektorer.

## 31. Hvad er $\text{span}\{v_1, \dots, v_k\}$?

Det er mængden af alle linearkombinationer af $v_1, \dots, v_k$:

$$
\text{span}\{v_1, \dots, v_k\} = \left\{ \sum_{i=1}^k a_i v_i \mid a_i \in \mathbb{R} \right\}
$$

Span er altså et underrum bestående af alle vektorer, man kan danne ved linearkombination.

---

## 32. Hvornår siger vi, at vektorerne $v_1, \dots, v_k$ er lineært uafhængige?

De er lineært uafhængige, hvis:

$$
c_1 v_1 + \dots + c_k v_k = 0 \Rightarrow c_1 = \dots = c_k = 0
$$

Dvs. den eneste linearkombination, der giver nulvektoren, er den trivielle.

---

## 33. Hvad er et underrum $V \subseteq \mathbb{R}^n$?

Et underrum $V$ er en delmængde af $\mathbb{R}^n$, som opfylder:

- $0 \in V$
- Lukket under addition: $u, v \in V \Rightarrow u + v \in V$
- Lukket under skalering: $c \in \mathbb{R}, v \in V \Rightarrow c \cdot v \in V$

---

## 34. Hvad er nulrummet til en givet matrix $A$?

Nulrummet er mængden af løsninger til $Ax = 0$:

$$
\text{Nul}(A) = \{ x \in \mathbb{R}^n \mid Ax = 0 \}
$$

Det er et underrum af $\mathbb{R}^n$.

---

## 35. Hvad er søjlerummet til en givet matrix $A$?

Søjlerummet er mængden af alle linearkombinationer af søjlerne i $A$:

$$
\text{Col}(A) = \text{span}\{\text{søjlerne i } A\}
$$

Det er et underrum af $\mathbb{R}^m$, hvor $A$ er $m \times n$.

---

## 36. Hvad er rang af en matrix?

Rangen af $A$ er dimensionen af søjlerummet:

$$
\text{rang}(A) = \dim(\text{Col}(A))
$$

Det er også antal ledende 1-taller i en reduceret trappeform.

---

## 37. Hvad er en basis af et underrum $V \subseteq \mathbb{R}^n$?

En basis er en mængde vektorer:

- Som **spænder over** $V$
- Som er **lineært uafhængige**

$$
\text{Basis } \Rightarrow \text{minimalt sæt, der genererer } V
$$

---

## 38. Hvad kan man sige om søjlerne i en inverterbar $n \times n$-matrix?

De danner en basis for $\mathbb{R}^n$:

$$
A \text{ inverterbar } \Leftrightarrow \text{søjlerne i } A \text{ er lineært uafhængige og spænder over } \mathbb{R}^n
$$

---

## 39. Hvornår er to vektorer $v$ og $w$ ortogonale?

Hvis deres indre produkt er 0:

$$
v \cdot w = 0 \Rightarrow v \perp w
$$

---

## 40. Hvad er formlen for den ortogonale projektion af \(x\) på \(\text{span}\{v_1, \dots, v_k\}\), hvis de er ortogonale?

Projektionen \(P x\) er givet ved:

$$
P x = \sum_{j=1}^k \frac{v_j \cdot x}{v_j \cdot v_j} v_j
$$

Gælder kun hvis \(v_j\)'erne er parvist ortogonale (ortogonal mængde).

## 41. Hvad er en ortonormalbasis af \(\mathbb{R}^n\)?

En ortonormalbasis er en basis hvor vektorerne både er

- **Ortogonale:** $v_i \cdot v_j = 0$ for $i \neq j$  
- **Normerede:** $\|v_i\| = 1$

Dvs. vektorerne er ortogonale og har længde 1.

---

## 42. Hvad kan man sige om søjlerne i en ortogonal \(n \times n\)-matrix \(U\)?

Søjlerne i \(U\) danner en ortonormalbasis for $\mathbb{R}^n$

Det betyder også:

$$
U^T U = U U^T = I
$$

---

## 43. Hvad er en egenværdi af en \(n \times n\)-matrix \(A\)?

Et tal \(\omega\), sådan at der findes en ikke-nul vektor $v \in \mathbb{R}^n$ med

$$
A v = \omega v
$$

Vektoren $v$ kaldes en egenvektor til egenværdien $\omega$.

---

## 44. Hvordan kan jeg bestemme egenværdierne af \(A\)?

Egenværdierne er nulpunkterne til det karakteristiske polynomium:

$$
\det(A - \omega I) = 0
$$

Løsning af denne ligning giver egenværdierne $\omega$

---

## 45. Hvad er egenrummet af $A$ til egenværdien $\omega$?

Egenrummet er mængden af alle egenvektorer til $\omega$ plus nulvektoren:

$$
\text{Nul}(A - \omega I) = \{ v \mid (A - \omega I)v = 0 \}
$$

---

## 46. Hvordan kan jeg bestemme egenvektorer $v$ til egenværdien $\omega$?

Løs det homogene ligningssystem:

$$
(A - \omega I) v = 0
$$

Alle løsninger $v \neq 0$ er egenvektorer til $\omega$.

---

## 47. Hvornår kaldes en $n \times n -matrix  A$ diagonaliserbar?

Hvis den er similær med en diagonal matrix $D$, dvs. hvis der findes en inverterbar matrix $P$, så

$$
A = P D P^{-1}
$$

---

## 48. Hvis $A = P D P^{-1}$ er en diagonalisering af $A$, hvad er indgangene i $D$ og $P$?

- Diagonalen i $D$ indeholder egenværdierne til $A$.
- Søjlerne i $P$ er egenvektorer til $A$, i samme rækkefølge som egenværdierne i $D$.

---

## 49. Er alle kvadratiske matricer diagonaliserbare?

Nej, ikke alle er diagonaliserbare.

---

## 50. Hvornår er en kvadratisk matrix \(A\) diagonaliserbar?

Hvis og kun hvis for hver egenværdi stemmer den algebraiske multiplicitet overens med den geometriske multiplicitet.

## 51. Hvad ved man om symmetriske matricer?

En symmetrisk matrix $S$ er altid diagonaliserbar — faktisk er $S$ endda ortogonalt diagonaliserbar, dvs. der findes en diagonal matrix $D$ og en ortogonal matrix $U$ sådan at

$$
S = U D U^T
$$

(hvor $U^T = U^{-1}$, fordi $U$ er ortogonal).

---

## 52. Hvad er en mindste kvadraters løsning til $Ax = b$?

En vektor $\hat{x}$, sådan at

$$
|b - A \hat{x}| \leq \|b - A x\| \quad \text{for alle } x
$$

Dvs. $\hat{x}$ minimerer den kvadrerede afstand mellem $b$ og $A x$.

---

## 53. Hvordan kan man bestemme mindste kvadraters løsninger?

$\hat{x}$ er mindste kvadraters løsning til $Ax = b$ hvis og kun hvis $\hat{x}$ løser normalligningen:

$$
A^T A \hat{x} = A^T b
$$

---

## 54. Er mindste kvadraters løsninger entydige?

Ikke altid. De er entydige hvis og kun hvis $A$ har fuld rang, eller ækvivalent hvis $A^T A$ er inverterbar.

---

## 55. Hvornår giver det mening at bruge mindste kvadraters metoden?

Når man ikke har nogen grund til at tro, eller ikke er sikker på, at det oprindelige system $Ax = b$ er konsistent.

---

## 56. Hvad, hvis jeg udregner en mindste kvadraters løsning $\hat{x}$ til et system $Ax = b$, som faktisk er konsistent?

Så er enhver mindste kvadraters løsning $\hat{x}$ også en almindelig løsning til $Ax = b$, dvs.

$$
A \hat{x} = b
$$

---

## 57. Hvad er et lineært programmeringsproblem på kanonisk form?

Maksimer

$$
c^T x
$$

under bibetingelserne

$$
A x \leq b, \quad x \geq 0
$$

---

## 58. Hvordan kan bibetingelser som $a_i^T x \geq b_i$ eller $a_i^T x = b_i$ omskrives i et lineært programmeringsproblem på kanonisk form?

- $a_i^T x \geq b_i$ omskrives som $-a_i^T x \leq -b_i$
- $a_i^T x = b_i$ omskrives som to uligheder: $a_i^T x \leq b_i$ og $a_i^T x \geq b_i$

---

## 59. Hvad, hvis man vil minimere $c^T x$: kan man stadigvæk opstille et lineært programmeringsproblem på kanonisk form?

Ja, minimere $c^T x$ kan omskrives til maksimering af $-c^T x$.

---

## 60. Kender du to situationer, hvor man ikke finder en optimal løsning til et lineært programmeringsproblem?

1. Feasibility set $F$ er tomt (ingen løsninger).
2. $c^T x$ er ubegrænset på $F$ (ingen maksimum).

---

## 61. Hvis $F$ ikke er tom og $c^T x$ er begrænset på $F$, hvor i $F$ ligger de optimale løsninger?

Mindst én optimal løsning findes i et ekstremalpunkt (hjørnepunkt) af den konvekse mængde $F$

---

## 62. Skitser mængden $F$ af alle vektorer $x = (x_1, x_2)$, der opfylder

$$
0 \leq x_1 \leq 2, \quad 0 \leq x_2 \leq 2, \quad x_1 + x_2 \leq 3
$$

Hvilke punkter i $F$ ville du afprøve som mulige optimale løsninger i den grafiske metode?

Svar: De mulige optimale løsninger ligger i hjørnerne af $F$:

$$
(0,0), (2,0), (0,2), (2,1), (1,2)
$$


---

## 63. Hvordan opstiller man en initial simplextableau (begyndelsessimplextableau) for et lineært programmeringsproblem på kanonisk form?

- Tilføj slack-variabler for at omskrive uligheder til ligheder.
- Antal slack-variabler svarer til antallet af uligheder.
- Objektfunktionen tilføjes som sidste række i tableau.

---

## 64. Beskriv algoritmen i simplexmetoden i tilfælde, hvor alle indgange i $b$ er positive!

- Vælg indgangsvariabel (variabel med mest negativ koefficient i objektfunktionen).
- Bestem udgangsvariabel via minimum ratio test.
- Udfør pivotering.
- Gentag indtil ingen negative koefficienter i objektfunktionen.
- Optimal løsning aflæses i tableau.

---

## 65. Kan man gøre noget, hvis $b$ har en eller flere negative indgange?

Ja, man kan bruge en “big M” metode eller to-fase simplex til at starte med en basisløsning.

---

## 66. Hvad er det duale problem til et lineært programmeringsproblem på kanonisk form?

Hvis primalproblemet er

$$
\max c^T x \quad \text{under} \quad A x \leq b, \quad x \geq 0
$$

så er det duale problem

$$
\min b^T y \quad \text{under} \quad A^T y \geq c, \quad y \geq 0
$$

---

## 67. Hvad er udsagnet af dualitetssætningen om lineære programmeringsproblemer samt deres duale problemer?

Hvis primalproblemet har en optimal løsning, så har dualproblemet også en optimal løsning, og deres optimale værdier er ens:

$$
\max c^T x = \min b^T y
$$

Desuden, hvis enten primal eller dual har ubegrænset løsning, så er det modsatte problem ufeasible.
