---
publish: "true"
title: 01 Varianten der Geometrieabstraktionen
---


# 1 Varianten der Geometrieabstraktionen
  
**ÜBERSICHT**:
  
1. **Abstraktionen im dreidimensionalen Raum**
    
      
    
    - **Abstraktion dünnwandiger Strukturen**
        
        ==**Solid (in 3D)**====→== ==**Flächen (in 3D)**== ==(mit Dickeneigenschaft)==
        
    
      
    
    - ==**Abstraktion länglicher Strukturen mit konstantem (im Vergleich zur Länge geringem) Querschnitt**==
        
        ==**Solid (in 3D)**====→== ==**Linien (in 3D)**== ==(mit Querschnitt)==
        
          
        
2. **Abstraktionen im zweidimensionalen Raum**
    
      
    
    - ==**Ausnutzung der**== \- ==**(Ergebnis exakt)**==
        
        ==**Solid (in 3D)**====→== ==**Fläche**== ==**(in 2D)**== ==(Abbildung eines Querschnitts)==
        
          
        
    - ==**Abstraktion als**== \- ==**(engl.**== \-==**)**==
        
        ==**Solid (in 3D)**====→== ==**Fläche**== ==**(in 2D)**== ==(Abbildung eines Querschnitts)==
        
          
        
    - ==**Abstraktion als**== \- ==**(engl.**== \-==**)**==
        
        ==**Solid (in 3D)**====→== ==**Fläche**== ==**(in 2D)**== ==(Abbildung eines Querschnitts)==
        
    
      
    
Weiterhin kann noch in allen oben genannten Fällen ggf. die ==**Symmetrie**== verwendet werden um das Modell weiter zu abstrahieren.
  
## 1.1 Abstraktionen im dreidimensionalen Raum
  
**Abstraktion dünnwandiger Strukturen**
==**Solid (in 3D)**====→== ==**Flächen (in 3D)**== ==(mit Dickeneigenschaft)==

> [!important]  
> Für die Abstraktion eines dünnwandigen dreidimensionalen Körpers werden sogenannte Shell Elemente verwendet, die als Flächen im dreidimensionalen-Raum liegen und denen als Eigenschaft eine Wanddicke zugewiesen werden kann  
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 1. Varianten der Geometrieabstraktionen/attachments/Untitled.png|Untitled.png]]
3D Struktur
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 1. Varianten der Geometrieabstraktionen/attachments/Untitled 1.png|Untitled 1.png]]
Abstraktion als Fläche
  
==**Abstraktion länglicher Strukturen mit konstantem (im Vergleich zur Länge geringem) Querschnitt**==
==**Solid (in 3D)**====→== ==**Linien (in 3D)**== ==(mit Querschnitt)==

> [!important]  
> Für die Abstraktion eines länglichen Körpers mit konstantem Querschnitt werden sogenannte Beam Elemente verwendet, die als Linien im dreidimensionalen-Raum liegen und denen als Eigenschaft ein Querschnitt zugewiesen werden kann.  
  
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 1. Varianten der Geometrieabstraktionen/attachments/Untitled 2.png|Untitled 2.png]]
3D Struktur
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 1. Varianten der Geometrieabstraktionen/attachments/Untitled 3.png|Untitled 3.png]]
Abstraktion als Linie  
(ohne Darstellung des Querschnitts)
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 1. Varianten der Geometrieabstraktionen/attachments/Untitled 4.png|Untitled 4.png]]
Abstraktion als Linie  
(mit Darstellung des Querschnitts)
  
  
## 1.2 Abstraktionen im zweidimensionalen Raum
  
Hierbei wird ein dreidimensionaler Körper auf eine 2D Ebene reduziert, dabei gibt es folgende drei Ansätze:
  
==**Ausnutzung der**== \- ==**(Ergebnis exakt)**==
==**Solid (in 3D)**====→== ==**Fläche**== ==**(in 2D)**== ==(Abbildung eines Querschnitts)==

> [!important]  
> Für die Ausnutzung der Rotationssymmetrie muss die Geometrie und die Randbedingung rotationssymmetrisch sein.  
  
Der dreidimensionale Körper wird dann in einer 2D Ebene mit einer Rotationsachse (in ANSYS immer die y-Achse!) gezeichnet.  
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 1. Varianten der Geometrieabstraktionen/attachments/Untitled 5.png|Untitled 5.png]]
  
==**Abstraktion als**== \- ==**(engl.**== \-==**)**==
==**Solid (in 3D)**====→== ==**Fläche**== ==**(in 2D)**== ==(Abbildung eines Querschnitts)==

> [!important]  
> Ein ebener Spannungszustand (engl. plain stress) ist erfüllt, wenn ein dreidimensionaler Körper in zwei Raumrichtungen Spannungen aufweist, in der dritten Raumrichtung jedoch keine Spannungen auftreten.  
  
Dies tritt auf bei dünnwandige Strukturen, weil sich hier das Material in Wanddickenrichtung ungehindert ausdehnen kann und deshalb keine Spannungen entstehen.  
  
Als weitere Bedingung muss die Belastung noch in der Ebene erfolgen.  
  
→ In der Abstraktion wird die dritte Raumrichtung (die der dünnen Wanddicke) nicht berücksichtigt und das Bauteil nur in 2D betrachtet  
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 1. Varianten der Geometrieabstraktionen/attachments/Untitled 6.png|Untitled 6.png]]
  
==**Abstraktion als**== \- ==**(engl.**== \-==**)**==
==**Solid (in 3D)**====→== ==**Fläche**== ==**(in 2D)**== ==(Abbildung eines Querschnitts)==

> [!important]  
> Ein ebener Verzerrungszustand (engl. plain strain) ist erfüllt, wenn ein dreidimensionaler Körper in zwei Raumrichtungen Dehnungen (Verzerrungen in Normalenrichtung) aufweist, in der dritten Raumrichtung jedoch keine Dehnungen auftreten.  
  
Dies tritt auf bei lange Strukturen (mit konstantem Querschnitt), weil sich hier das durch das "viele" Material in Richtung der Länge die Dehnung blockiert wird und deshalb keine Dehnungen in dieser Richtung entstehen.  
  
Als weitere Bedingung muss die Belastung noch in der Ebene erfolgen.  
  
→ In der Abstraktion wird deshalb die dritte Raumrichtung (in der der Körper sehr lang ist) nicht berücksichtigt und das Bauteil nur in 2D im Querschnitt betrachtet  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 1. Varianten der Geometrieabstraktionen/attachments/Untitled 7.png|Untitled 7.png]]
## 1.3 Beispiele für Abstraktionen im zweidimensionalen Raum
  
Wir schauen uns nun ein Beispiel an um zu verdeutlichen, dass es nicht nur auf die Geometrie, sondern auch auf die Randbedingung ankommt, um zu entscheiden ob eine Abstraktion möglich ist oder nicht.
  
![[Aufgabe.png|Aufgabe.png]]
  
Gegeben ist ein Zylinder mit ==Innendruck== ==$p_i$==﻿ und ==Aussendruck== ==$p_a$==﻿==.==

> [!important]  
> Erfüllt das Beispiel die die Anforderung für eine Abstraktion in 2D als Rotationssymmetrie und als ebener Spannungszustand ?  
![[Beispiel1.png|Beispiel1.png]]

> [!important]  
> Sowohl die Rotationssymmetrie als auch der ebene Spannungszustand wäre hier möglich, da Geometrie und Randbedingung die Bedingung erfüllen.  
  
Nun ändern wir das Beispiel und führen eine ==**punktuelle Kraft F**== ein und orüfen erneut:
![[Beispiel2.png|Beispiel2.png]]

> [!important]  
> Sowohl die Rotationssymmetrie als auch der ebene Spannungszustand sind hier nicht möglich, da die Randbedingung in beiden Fällen nicht angebracht werden kann  
  
Würde nun statt der ==**punktuelle Kraft F eine Kraft entlang des gesamten oberen Ringes anliegen:**==
![[Beispiel3.png|Beispiel3.png]]

> [!important]  
> Wäre es im ebene Spannungszustand immer noch nicht möglich die Randbedingung anzubringen, da diese nur an der Oberseite anliegt und nicht wie z.B. der Aussendruck über die gesamte Mantelfläche.  
  
> [!important]  
> Bei der Rotationssymmetrie kann die Kraft aber nun als punkt in der oberen rechten Ecke angebracht werden.  
  
## 1.4 **Ausnutzung der Symmetrie**
  
Die letzte Form der Abstraktion ist die Ausnutzung von **Symmetrien** der **Geometrie** **und** **Randbedingung.**
  
Für unser letztes Beispiel mit dem **3D-Modell** sehen die möglichen Symmetrien dann so aus:
![[Ebenensymmetrie.png|Ebenensymmetrie.png]]
Symmetrien des 3D Modells

> [!important]  
> Ergänzung: Die sinnvollste Abstraktion (mit dem geringsten Rechenaufwand) für genau dieses Beispiel wird vermutlich die Rotationssymmetrie sein.  
  
Für unsere **2D Abstraktionen** sind natürlich ebenfalls Symmetrien zu nutzen wenn möglich:
![[2D-Symmetrie.png|2D-Symmetrie.png]]
  
Nachfolgend schauen wir uns nun an wie die ganzen Abstraktionen in ANSYS umzusetzen sind.