
---
layout: post
title: "Linear Algebra Ordbog"
date: 2025-06-10
categories: [blog]
---

# LIAL, Ordliste  
# Dansk-Engelsk  

# A  
### afbildning  
*map, transformation*  
En regel eller funktion der "flytter" en vektor fra ét rum til et andet – fx ved rotation, skalering eller forskydning.

# B  
### basisskift  
*change of basis*  
Når man udtrykker vektorer i en ny basis, f.eks. fordi det forenkler en beregning eller tilpasser til en ny geometri.

### bijektion  
*one-to-one correspondence, bijection*  
En funktion hvor hvert input svarer til ét unikt output, og hvert output dækkes.

### bijektiv funktion  
*one-to-one correspondence, bijection*  
En funktion der både er injektiv (ingen gentagelser i output) og surjektiv (alle outputs bruges).

### bijektiv  
*bijective*  
En egenskab ved funktioner: både injektiv og surjektiv, altså perfekt match mellem input og output.

### billede  
*image*  
Alle de vektorer man får ud efter en afbildning – altså resultatet af at transformere hele definitionsmængden.

### billedmængde  
*range (se også værdimængde)*  
Det sæt af outputs en funktion faktisk rammer, ofte et underrum af kodomænet.

# D  
### definitionsmængde  
*domain*  
Alle de inputværdier man må give til en funktion – altså hvor funktionen er defineret.

### delmængde  
*subset*  
En mængde hvor alle elementer også findes i en større mængde.

### determinant  
*determinant*  
Et tal der fortæller om en matrix skalerer, spejler eller vender rummet – fx hvor meget et areal/volumen ændres.

### diagonaliserbar  
*diagonalizable*  
En matrix er diagonaliserbar hvis den kan omskrives til en diagonal matrix vha. en basistransformation.

### diagonalisering  
*diagonalization*  
Processen med at omskrive en matrix til en diagonal form, ved hjælp af egenværdier og egenvektorer.

### dimension  
*dimension*  
Antallet af uafhængige retninger i et rum – fx 2 i et plan, 3 i rum. Også antal basisvektorer.

### disjunkte  
*disjoint*  
To mængder er disjunkte, hvis de ikke har noget til fælles – deres fællesmængde er tom.

### dispositionsmængde  
*codomain*  
Alle mulige outputværdier som en funktion kan antage – ikke nødvendigvis alle bliver ramt.

# E  
### echelonform  
*echelon form (se også trappeform)*  
En matrix er i echelonform, hvis dens rækker "trapper ned" med nuller foran, og pivoterne står til højre for den ovenstående.

### element  
*entry*  
Et enkelt tal eller værdi i en matrix eller vektor – også kaldet en indgang.

### egenrum  
*eigenspace*  
Alle egenvektorer (og deres linearkombinationer) der hører til en bestemt egenværdi – altså rummet af løsninger til \((A - \lambda I)x = 0\).

### egenvektor  
*eigenvector*  
En vektor som ved transformation kun bliver skaleret, ikke ændret retning – opfylder \(Av = \lambda v\).

### egenværdi  
*eigenvalue*  
Tallet \(\lambda\) som fortæller hvor meget en egenvektor skaleres ved transformation.

### endelig  
*finite*  
Betyder at noget har et begrænset antal elementer eller størrelse – modsætning til uendelig.

# F  
### foreningsmængde  
*union*  
Mængden af alle elementer fra to (eller flere) mængder – alt der optræder mindst én gang.

### fællesmængde  
*intersection*  
Det som to (eller flere) mængder har til fælles – altså de overlappende elementer.

# G  
### Gauss-elimination  
*Gaussian elimination*  
En metode til at omskrive et ligningssystem eller matrix til trappeform ved rækkeoperationer, for nemmere løsning.

# H  
### heltal  
*integer*  
Et tal uden decimaler – både positive, negative og nul: ..., -3, -2, -1, 0, 1, 2, 3, ...

### hoveddiagonal  
*main diagonal*  
Elementerne fra øverste venstre hjørne til nederste højre i en kvadratisk matrix – de hvor række- og søjleindeks er ens.

# I  
### identitetsmatrix  
*identity matrix*  
En kvadratisk matrix med 1'ere på hoveddiagonalen og 0'er ellers – fungerer som "1" i matrixmultiplikation.

### indgang  
*entry*  
Et andet ord for et element i en matrix eller vektor.

### indre produkt  
*inner product*  
Et mål for "længde og vinkel" mellem to vektorer – i Rⁿ svarer det til prikproduktet.

### injektiv  
*injective, one-to-one*  
En funktion er injektiv hvis hvert output stammer fra ét unikt input – ingen gentagelser.

### inverterbar  
*invertible (se også invertibel)*  
En matrix der har en omvendt (inverse) matrix, så \(A^{-1}A = I\). Kun muligt hvis determinanten er forskellig fra nul.

### invertibel  
*invertible (se også inverterbar)*  
Samme som ovenfor – betyder at transformationen kan "rulles tilbage".

# K  
### kanonisk basis  
*standard basis*  
En basis bestående af enhedsvektorer – fx \([1,0,0], [0,1,0], [0,0,1]\) i R³.

### karakteristisk ligning  
*characteristic equation*  
Ligningen \(\det(A - \lambda I) = 0\) som bruges til at finde egenværdier.

### karakteristisk polynomium  
*characteristic polynomial*  
Polynomiet \(\det(A - \lambda I)\), hvis rødder er egenværdierne.

### kofaktor  
*cofactor*  
Et tal man får ved at tage determinanten af en mindre matrix (minor), ganget med \((-1)^{i+j}\).

### kofaktorudvidelse  
*cofactor expansion*  
En metode til at beregne determinanter ved at ekspandere langs en række eller søjle med kofaktorer.

### koordinatvektor  
*coordinate vector*  
En vektor der viser, hvordan en vektor er sammensat ud fra en valgt basis.

### korollar  
*corollary*  
En sætning der følger direkte af en anden sætning eller bevis – altså en slags "konsekvens".

# L  
### ledende koefficient  
*leading entry*  
Den første ikke-nul værdi i en række i en matrix – bruges til at finde pivoter.

### lemma  
*lemma*  
En hjælpesætning der bruges som del af et større bevis.

### linearkombination  
*linear combination*  
En sum af vektorer ganget med skalarer – fx \(2v_1 + 3v_2\).

### lineær (u)afhængig  
*linearly (in)dependent*  
Vektorer er uafhængige hvis ingen kan skrives som kombination af de andre – ellers er de afhængige.

### lineær (u)afhængighed  
*linear (in)dependence*  
Egenskaben af et vektorsæt – om det er muligt at udtrykke én som en kombination af de andre.

# M  
### mindste kvadraters metode  
*method of least squares*  
En metode til at finde den bedste (mindst fejlagtige) løsning til et overbestemt system – f.eks. i regression.

### underdeterminant  
*minor*  
Det man får ved at fjerne én række og én søjle fra en matrix og tage determinanten af det resterende.

### mængde  
*set*  
En samling af unikke elementer – fx {1, 2, 3}.

# N  
### nullitet  
*nullity*  
Dimensionen af nulrummet – altså hvor mange frie variable der er i løsningen af \(Ax = 0\).

### nulrum  
*null space*  
Mængden af alle vektorer \(x\) der opfylder \(Ax = 0\). Et underrum af definitionsmængden.

### nulvektor  
*zero vector*  
En vektor hvor alle indgange er nul – længde 0 og ingen retning.

# P  
### pivotindgang  
*pivot entry*  
Den første ikke-nul værdi i en række i en matrix – bruges til rækkeoperationer og trappeform.

### pivotsøjle  
*pivot column*  
En søjle der indeholder en pivot – typisk en vigtig søjle ifm. løsning af ligninger.

# R  
### rang  
*rank*  
Antallet af uafhængige rækker eller søjler i en matrix – afgør matrixens "styrke".

### regulær matrix  
*invertible matrix*  
En matrix der har en invers – kun mulig hvis rang = antal rækker (fuld rang).

### række  
*row*  
En vandret linje i en matrix.

### rækkereduktion  
*row reduction*  
Processen med at bruge rækkeoperationer til at bringe en matrix på echelonform eller reduceret echelonform.

# S  
### skalarprodukt  
*scalar product*  
Et tal man får ved at tage indre produkt af to vektorer – bruges fx til projektion og vinkelberegning.

### singulær matrix  
*singular matrix*  
En matrix der **ikke** har en invers – typisk fordi determinanten er 0.

### spænd  
*span*  
Alle mulige linearkombinationer af et vektorsæt – definerer et underrum.

### standardbasis  
*standard basis (se også kanonisk basis)*  
De vektorer der peger i én og kun én retning – fx \([1,0], [0,1]\) i R².

### surjektiv  
*surjective, onto*  
En funktion hvor hvert output i kodomænet bliver ramt af mindst ét input.

### sætning  
*theorem*  
En matematisk påstand der er blevet bevist ud fra aksiomer og tidligere sætninger.

### søjle  
*column*  
En lodret linje i en matrix.

### søjlerum  
*column space*  
Mængden af alle linearkombinationer af en matrix' søjler – samme som billedmængde.

# T  
### totalmatrix  
*augmented matrix (se også udvidet koefficientmatrix)*  
En matrix der indeholder både koefficienter og resultatled fra et ligningssystem.

### transponering  
*transpose*  
Man bytter rækker og søjler i en matrix – altså spejler over hoveddiagonalen.

### trappeform  
*echelon form (se også echelonform)*  
En form hvor nuller er flyttet ned og til venstre i matrixen – giver trinvis struktur.

### triangulær matrix  
*triangular matrix*  
En matrix hvor alle elementer under eller over hoveddiagonalen er nul – enten øvre eller nedre triangulær.

### triviel løsning  
*trivial solution*  
Den simple løsning \(x = 0\) til ligningen \(Ax = 0\).

# U  
### uendelig  
*infinite*  
Ikke endeligt – noget uden grænse, fx en uendelig løsningsmængde.

### udvidet koefficientmatrix  
*augmented matrix (se også totalmatrix)*  
En matrix der inkluderer både koefficienterne og resultatleddene fra et ligningssystem.

### undermatrix  
*submatrix*  
En mindre matrix man får ved at fjerne rækker og/eller søjler fra en større matrix.

### underrum  
*subspace*  
Et rum inden for et større vektor rum, som også opfylder regler for lukkethed under addition og skalering.

# V  
### vectorspænd  
*vector span*  
Alle mulige linearkombinationer af et givet vektorsæt – definerer hvilket rum de "udspænder".

### værdimængde  
*image/range (se også billedmængde)*  
Det sæt af outputværdier som en funktion faktisk rammer – samme som billedmængde.
