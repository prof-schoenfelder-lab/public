---
publish: "true"
title: 03 Beispiel B -  Si-Ingot unter Eigenlast
---


# 3. Beispiel B: Si-Ingot unter Eigenlast
  
Bei der Kristallisation von Silizium wird im Czochralski-Verfahren ein zylindrischer Silizium Ingot aus der Schmelze gezogen. Zu Beginn wird die Orientierung mit einem Impfkristall vorgegeben und dann Schrittweise der Durchmesser erhöht. Das führt dazu, dass der Ingot an einem sogenannten Dünnhals hängt. Die Belastung die dabei entstehen wollen wir nun bewerten.
  
![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled.png]]
  
**BEZUG ZU DEN LETZTEN PRAKTIKA**
- **Material definieren**  
    (Praktikum 1)
- **Geometrie erstellen  
    **(Praktikum 2)
- **Richtige Randbedingung anbringen  
    **(Praktikum 2)
- **Netz mit Hexa Elementen**  
    (Praktikum 3)
  
### 3.1 ==Gegeben==
  
==**Material**==
**Silizium (monokristallin)**
- Siehe [[Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast|Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast]]
  
==**Geometrie**==
**Si-Ingot**
- Gesamtlänge ==$L=1650\,\mathrm{mm}$==﻿
- Durchmesser Kristall ==$d_{Kristall}=300\,\mathrm{mm}$==﻿
- Länge Kristall ==$L_{Kristall}=1400\,\mathrm{mm}$==﻿
- Durchmesser Dünnhals ==$d_{Dünnhals}=15\,\mathrm{mm}$==﻿
- Länge Dünnhals ==$L_{Dünnhals}=100\,\mathrm{mm}$==﻿
- Länge Übergangsbereich zwischen Dünnhals Kristall ==$L_{Übergang}=150\,\mathrm{mm}$==﻿
  
==**Randbedingungen**==
- feste Einspannung an der Oberseite
- Belastung durch Eigengewicht (==**Gewichtskraft**== ==$g=9{,}8066\frac{m}{s}$==﻿)
  
### 3.2 ==Gesucht==
  
**für folgende Abstraktionen:**
1. **3D Viertelmodell**
2. **2D (Rotationssymmetrie)**
  
  
**soll jeweils bestimmt werden** :
- Die **maximale Verschiebung in Längsrichtung** (y-Achse) $u_{y,max}$﻿
- Die **maximale Normalspannung in Längsrichtung** (y-Achse) $\sigma_{y,max}$﻿
  
### 3.3 ==**Hinweise**==
  
**ALLGEMEIN**:
- **Materialerstellung Silizium (100)**
    
    **Silizium (100)** ist **anisotrop** und kann über `Orthotropic Elasticity` (siehe Werte unten)  
    **Dichte (**`**Density**`**)** eingefügt nicht vergessen !
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled.png|Untitled.png]]
    
    > [!important]  
    > Werte in MPa!  
    
      
    
- Denken Sie daran ihr erstelltes Material auch zuzuweisen !
- Vernetzung für Hexa-Elemente in Lösungen dargestellt
  
**ABSTRAKTIONEN**:
- **3D Modell (Viertelsymmetrie)** `**Geometrie unterdrücken**` `**Symmetrierandbedingung**`
    
    - **`Geometrie erstellen`** **3D**
        - Erstellen Sie **jeweils einen Zylinder** für den **Dünnhals** und den **Kristall** und verbinden Sie beide Teile mit der Funktion `**Blend**`
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled 1.png|Untitled 1.png]]
            
        - Viertel Sie anschließend die Geometrie. Verwenden Sie nur ein Viertel der Geometrie für die Simulation
        - Für eine bessere Vernetzung ist es auch empfehlenswert den Dünnhals / Übergangsbereich und Kristall jeweils aufzuteilen (`Split Body`) und dann mit `Shared Topology` wieder zu verbinden
    
    - `**Symmetrierandbedingung**` Fügen Sie jeweils eine Symmetrieebene ein für jede Symmetrie die Sie angenommen haben (Anleitung siehe unten)
    
    - 📋`Anleitung (Allg)` ==**(**====Mechanical)== **==Symmetrieebenen==** ==einfügen==
        
        ---
        
        1. `**Strukturbaum**`: Rechtsklick `Model` → `Insert` → `Symmetry`
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 2.png|Untitled 2.png]]
            
            ---
            
        2. `**Strukturbaum**`: Rechtsklick `Symmetry` → `Insert` → `Symmetry Region`
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 3.png|Untitled 3.png]]
            
            ---
            
        3. **Menüleiste** (Oben) **Reiter**: `**Display**`**:** `**Show**` **→** `**All Coordinate Systems**`> [!important]  
            > Hilft bei der Auswahl von Symmetry Normal (siehe Punkt 4)  
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 4.png|Untitled 4.png]]
            
            ---
            
        4. `**Strukturbaum**`: vorher erstelle `Symmetry Region` **anklicken** und im Detailfenster unter `Geometry` die Fläche (3D) oder Linie (2D) oder Punkt (1D) auswählen die in der Symmetrieebene liegt und unter `Symmetry Normal` die Normale zu dieser Ebene einstellen
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 5.png|Untitled 5.png]]
            
            ---
            
    
- **2D (Rotationssymmetrie)** `**Geometrieerstellung**` `**Ansicht mit Dicke**`
    
    - ℹ️ **Geometrieerstellung aus 3D Modell** für 2D Abstraktionen
        
        Wenn wir bereits ein 3D Modell haben, können wir einfach in dem 3D Modell die Fläche markieren die wir in 2D verwenden wollen und diese mit `STR` + `C` kopieren und mit `STR` + `V` einfügen. Im Strukturbaum erscheint das Surface und der Body kann ggf. gelöscht werden.
        
        > [!important]  
        > Die Ebene muss allerdings in der x-y Ebene liegen und für Rotationssymmetrie muss die y-Achse die Rotationsachse sein. Falls die Fläche nicht so liegt, kann sie ggf. durch Rotation in diese Ebene bewegt werden.  
        
    
    - **ℹ️ Geometrieerstellung und Einstellungen für Rotationssymmetrie (**`**axis-symmetric**`**)**
        - ==**SpaceClaim**====: Geometrie erstellen==
            1. **Skizze in x-y Ebene**
                
                Neue Skizzenebene auswählen (Icon unten) und auf z-Achse klicken
                
                > [!important]  
                > Die y-Achse muss ist die Rotationsachse sein  
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 6.png|Untitled 6.png]]
                
            2. Skizze wird nach verlassen den Skizzenmodus **...**
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 7.png|Untitled 7.png]]
                
                ... als **Surface** im Strukturbaum angezeigt (keine weitere Aktion notwendig!)
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 8.png|Untitled 8.png]]
                
        - ==**Workbench Projektmenü**====: Geometrie erstellen==
            1. ==Rechtsklick== `Geometry` → `Properties`
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 9.png|Untitled 9.png]]
                
            2. Im `Eigenschaftsfenster` (Rechts): `Analysis Type` auf `2D` stellen
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 10.png|Untitled 10.png]]
                
            3. **Rechtsklick** auf `Model` → `Update`
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 11.png|Untitled 11.png]]
                
        - ==**Mechanical**====:== ==**axissymmetric**== ==einstellen==
            1. `Geometry` **im Stukturbaum auswählen** und **im Detailfenster** `2D Behavior` auf `Axissymmetric` stellen
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled 2.png|Untitled 2.png]]
                
    
      
    
  
  
### 3.4 ==Lösung==
  
  
**Simulation**
- **3D Modell (Viertel)** `**Lösung**`
    
    - ==**Vernetzung (aufwendig)**==> [!important]  
        > Ggf. Netz noch mal entfernen (Rechtsklick Mesh → Clear Generated Data) und dann neu vernetzen, falls Vernetzung nicht klappt  
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled 3.png|Untitled 3.png]]
        
        1. **Sweep** Method auf Übergangsbereich
            
            Rechtsklick `Mesh` → `Insert` → `Method` → Detailfenster `Method=Sweep` und mittleren Körper auswählen
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled 4.png|Untitled 4.png]]
            
              
            
        2. **Edge Sizing** im Übergangsbereich mit **Bias**
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled 5.png|Untitled 5.png]]
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled 6.png|Untitled 6.png]]
            
              
            
        3. **Edge Sizing** auf allen Kanten in z oder y- Richtung (Symmetriekanten) mit `Number of Divisions`
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled 7.png|Untitled 7.png]]
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled 8.png|Untitled 8.png]]
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled 9.png|Untitled 9.png]]
            
              
            
        4. **Edge Sizing** auf Kristall (y-Richtung)
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled 10.png|Untitled 10.png]]
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 3. Beispiel B- Si-Ingot unter Eigenlast/attachments/Untitled 11.png|Untitled 11.png]]
            
              
            
        5. **Edge Sizing** auf Dünnhals (y-Richtung)
            
            ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 12.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 12.png]]
            
            ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 13.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 13.png]]
            
              
            
    - ==**Randbedingungen**== > [!important]  
        > Durch die Symmetrieebenen, muss keine weitere fixierte Lagerung vorgenommen werden  
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 14.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 14.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 15.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 15.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 16.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 16.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 17.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 17.png]]
        
    - ==**Symmetrieebenen für Viertelsymmetrie**==
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 18.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 18.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 19.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 19.png]]
        
    
    $u_{y,max}=0{,}0098\,\mathrm{mm}$﻿
    
    $\sigma_{y,max}=13{,}935\,\mathrm{MPa}$﻿
    
- **2D (ebener Spannungszustand)** `**Lösung**`
    
    Elementgröße = 25mm
    
    - ==**Vernetzung**==
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 20.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 20.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 21.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 21.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 22.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 22.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 23.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 23.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 24.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 24.png]]
        
    - **==Randbedingungen==**
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 25.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 25.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 26.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 26.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 27.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 27.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 28.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/03 Beispiel B -  Si-Ingot unter Eigenlast/attachments/Untitled 28.png]]
        
    
    $u_{y,max}=0{,}0098\,\mathrm{mm}$﻿
    
    $\sigma_{y,max}=14{,}621\,\mathrm{MPa}$﻿
    
    > [!important]  
    > Hier weichen die y-Spannung etwas vom 3D Modell ab (vermutlich liegt das am Netz)  
    
      
    
      
    
### 3.5 ==Diskussion==
  
Will man nun die Spannung im Dünnhals für einen Ingot bestimmen, so kann man dies eigentlich auch relativ leicht analytisch berechnen:
  
$\sigma=\frac{F}{A}=\frac{m g}{A}=\frac{240{,}23kg\cdot9{,}8066\frac{m}{s}}{\frac{\pi}{4} {0{,}015m}^2}=13,33\mathrm{MPa}$
  
**3D (Viertel):** $\sigma_{y,max}=13{,}935\,\mathrm{MPa}$﻿
**2D (Rotationssymmetrie):** $\sigma_{y,max}=14{,}668\,\mathrm{MPa}$﻿
  
  

> [!important]  
> Das wirkt doch so zerbrechlich, warum wirken da nur 14 MPa? Gefühlt geht das bei dem kleinsten Windhauch doch sicher kaputt.  
  
Nur 14MPa wirken an dem Dünnhals trotz des enormen Größe und Gewichts von 240kg des Kristalls und dem geringem Durchmesser von 15mm des Dünnhalses.
Kritisch wird es, wenn zum Beispiel der untere Bereich des Kristalls leicht ausgelenkt wird und dadurch am Dünnhals eine Biegung entsteht. Um diesen Sachverhalt zu lösen, bräuchten wir allerdings das 3D Vollmodell.
  