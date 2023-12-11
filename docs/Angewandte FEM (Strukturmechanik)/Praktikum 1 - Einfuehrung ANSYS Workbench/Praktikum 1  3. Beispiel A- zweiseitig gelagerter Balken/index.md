---
publish: "true"
tags:
  - Balken
---


# 3. Beispiel A: zweiseitig gelagerter Balken
  
Als einfaches Beispiel starten wir mit einem zweiseitig gelagerten Balken mit Linienlast. Dieser ist in der Geometrie leicht zu erstellen und wir können die Lösungen leicht mit analytischen Gleichungen überprüfen.
## 3. 1. **Aufgabenstellung
  ![[Angewandte FEM (Strukturmechanik)/Praktikum 1 - Einfuehrung ANSYS Workbench/Praktikum 1  3. Beispiel A- zweiseitig gelagerter Balken/attachments/_BeispielA_Aufgabenstellung.png|Angewandte FEM (Strukturmechanik)/Praktikum 1 - Einfuehrung ANSYS Workbench/Praktikum 1  3. Beispiel A- zweiseitig gelagerter Balken/attachments/_BeispielA_Aufgabenstellung.png]]
### ==Gegeben==
  
==**Material**==
**Stahl**
- Elastizitätsmodul $E=200\,\mathrm{GPa}$﻿
- Querkontraktionszahl $\nu=0{,}3$﻿
==**Geometrie**==
#Balken
**Balken mit rechteckigem Querschnitt**
- Länge ==$L=1000\,\mathrm{mm}$==﻿
- Breite ==$b=30\,\mathrm{mm}$==﻿
- Breite ==$h=30\mathrm{mm}$==﻿
==**Randbedingungen**==
- **Loslager** auf der linken Seite
- **Festlager** auf der rechten Seite
- Flächenlast ==$q_0=1000\,\mathrm{N}$==﻿
### ==Gesucht==
  
1. Die maximale Durchbiegung $u_{max}$﻿
2. Die maximale Spannung in y-Richtung $\sigma_{y,max}$﻿
  
## 3. 2. Lösung
  
Nachfolgend werden die Schritte die zur Lösung führen beschrieben.
### 3. 2. 1. Analyse hinzufügen
  

> [!important]  
> Fügen Sie eine Strukturmechanische Analyse (Static Structural) in ANSYS Workbench hinzu  
  
[https://scribehow.com/embed/ANSYS_Workbench__Strukturmechanische_Analyse_hinzufugen__UgZDeKatR3WSHGyTkgegog?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Workbench__Strukturmechanische_Analyse_hinzufugen__UgZDeKatR3WSHGyTkgegog?skipIntro=true&removeLogo=true)
Die strukturmechanische Analyse (**Static Structrural**) besteht immer aus diesen **7 Teilen** die von **oben** nach **unten nacheinander abgearbeitet** **wird**.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken/attachments/Untitled.png|Untitled.png]]
1. **Analysetyp  
    **==Anzeige des Analystyps (hier: Static Structural)==
2. **Engineering Data**  
    ==Modul:== ==ANSYS Workbench  
    ====Aufgabe:== Materialdatenbanken einbinden, Materialien hinzufügen (aus Datenbank) oder selber selber Daten eintragen
3. **Geometry  
    **==Modul:== DesignModeler (alt) oder ==SpaceClaim (neuere Version welche wir verwenden)====  
    ====Aufgabe:== Geometrie importieren oder erstellen
4. **Model**  
    ==Modul:== ==Mechanical  
    ====Aufgabe:== Bauteil Material zuweisen und Vernetzen
5. **Setup  
    **==Modul:== ==Mechanical  
    ====Aufgabe:== Modelleinstellungen (z.B. Randbedingungen)
6. **Solution  
    **==Modul:== ==Mechanical  
    ====Aufgabe:== Lösungseinstellungen und lösen des Gleichungssystems
7. **Results  
    **==Modul:== ==Mechanical  
    ====Aufgabe:== Ergebnisse auswerten und darstellen
**Die folgenden Zellstatus sind möglich**

> [!important]  
> Die Komponente ist aktuell.  
  
> [!important]  
> Eine Aktualisierung ist notwendig (nach Änderung der globalen Daten).  
  
> [!important]  
> Erfordert Aufmerksamkeit. Eine Änderung der Eingabe kann notwendig sein.  
  
> [!important]  
> Eine Aktualisierung ist notwendig (nach Änderung der lokalen Daten).  
  
> [!important]  
> Die Eingabe wird unterdrückt.  
  
### 3. 2. 2. ==Materialdefinition (Workbench)==
  
Von ANSYS Workbench ist standardmäßig immer das Material **Structural Steel** mit einem Elastizitätsmodul $E=200\,\mathrm{GPa}$﻿ und einer Querkontraktion $\nu=0{,}3$﻿ definiert. Zum Zwecke der Übung wollen wir nun trotzdem ein eigenes Material definieren.
  

> [!important]  
> Erstellen Sie ein Material mit den [[Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken|Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken]]  
**Stahl**
- Elastizitätsmodul $E=200\,\mathrm{GPa}$﻿
- Querkontraktionszahl $\nu=0{,}3$﻿
[https://scribehow.com/embed/ANSYS_Workbench__Linear_Elastisches_Material_hinzufugen__WV52z8uaRNGFwMvVUu0R5Q?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Workbench__Linear_Elastisches_Material_hinzufugen__WV52z8uaRNGFwMvVUu0R5Q?skipIntro=true&removeLogo=true)
  
### 3. 2. 3. ==Geometrieerstellung (SpaceClaim)==
  
Zur Erstellung der Geometrie benutzen wir das Programm ==**SpaceClaim**==. Das Programm ist dafür gemacht schnell und flexibel eine Geometrie zu erstellen bzw. zu verändern. In dem kurzen YouTube Video wird dies recht gut verdeutlicht.
[https://youtu.be/ctI-tMc8U7M](https://youtu.be/ctI-tMc8U7M)
  
Anders als bei CATIA oder Inventor wird die Geometrie nicht durch Skizzen und Bedingungen bestimmt, sondern kann immer durch Operationen (wie z.B. ziehen, drehen, skalieren) dynamisch verändert werden.
  

> [!important]  
> Erstellen Sie die Geometrie mit der Skizze und den Parametern aus der Aufgabenstellung  
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken/attachments/BeispielA_Aufgabenstellung.png|BeispielA_Aufgabenstellung.png]]
**Balken mit rechteckigem Querschnitt**
- Länge ==$L=1000\,\mathrm{mm}$==﻿
- Breite ==$b=30\,\mathrm{mm}$==﻿
- Breite ==$h=30\mathrm{mm}$==﻿
[https://scribehow.com/embed/SpaceClaim__Rechteckprofil_Balken_erstellen__32o8UKi8Qfmip6oXaHdpFA?skipIntro=true&removeLogo=true](https://scribehow.com/embed/SpaceClaim__Rechteckprofil_Balken_erstellen__32o8UKi8Qfmip6oXaHdpFA?skipIntro=true&removeLogo=true)
### 3. 2. 5. ==Materialzuweisung & Modelleinstellung (Mechanical==
  
Nachdem die notwendigen **Materialien** definiert (in ==**Workbench Projektmenü**==) und die **Geometrie** des Modells (in ==**SpaceClaim**==) erstellt wurden, werden die nächsten Schritte im Programm **ANSYS Mechanical** durchgeführt. Dazu beginnen wir mit der Zuweisung des Materials.
  

> [!important]  
> Öffnen Sie zunächst das Programm Mechanical  
  
**Mechanical öffnen**
![[CleanShot_2022-10-12_at_15.10.012x.png|CleanShot_2022-10-12_at_15.10.012x.png]]
- `Rechtsklick` auf `Model` und dann `Klick` auf `Edit…`
  
  

> [!important]  
> Weisen Sie nun dem Geometrie das Material zu  
  
[https://scribehow.com/embed/ANSYS_Mechanical__Material_zuweisen__I_Hqji9UTluDUeV5b4s5zw?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Material_zuweisen__I_Hqji9UTluDUeV5b4s5zw?skipIntro=true&removeLogo=true)
  
  
### 3. 2. 6. ==Vernetzung (Mechanical)==
  
Die Ergebnisse der FEM werden in den **Knoten** von Elementen ermittelt. Dafür muss nun das Modell mit **Elementen** vernetzt werden. Standardmäßig gibt Ihnen das Programm ein Netz vor.
Mit dem Parameter **Resolution** kann die Vernetzung über eine Skala verfeinert werden. Dies hilft besonders zu Beginn, da man oft keine Ahnung hat welche Netzgröße (also z.B. 1mm) die richtige ist. Genau werden dir dies in einem späteren Praktikum behandeln.
  
  

> [!important]  
> Vernetzen Sie das Bauteil und erhöhen Sie die Resolution auf 5  
  
[https://scribehow.com/embed/ANSYS_Mechanical__Netzgrosse_uber_Resolution__yKnW8y6yTwCGQIWGqVZioA?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Netzgrosse_uber_Resolution__yKnW8y6yTwCGQIWGqVZioA?skipIntro=true&removeLogo=true)
  

> [!important]  
> Die Resolution ist auf 5 erhöht worden, damit wir mehr als ein Element über den Querschnitt bekommen. Jetzt haben wir insgesamt 4 Elemente im Querschnitt.  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken/attachments/Untitled 1.png|Untitled 1.png]]
  
### 3. 2. 7. ==Randbedingungen (Mechanical)==
  
Nun wird definiert an welchen Stellen die Geometrie “festgehalten” wird (also gelagert) und unter welcher Belastung (hier Kraft) die Geometrie steht.
  
In unserem Fall haben wir zwei Lagerungen:
- **Festlager** an der linken Seite **unten**
- **Loslager** an der rechten Seite **unten**
  
und eine Belastung:
- Flächenlast ==$q_0=1000\,\mathrm{N}$==﻿ **oben**
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken/attachments/BeispielA_Aufgabenstellung.png|BeispielA_Aufgabenstellung.png]]
  
Um die Koordinaten besser einzuschätzen empfiehlt sich das Koordinatensystem einzublenden:
- 📋`Anleitung (Allg)` ==**(**====Mechanical) Koordinatensystem im Grafikfenster anzeigen==
    1. Menüleiste oben auf Reiter `Display` klicken
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken/attachments/Untitled 2.png|Untitled 2.png]]
        
          
        
        ---
        
          
        
    2. auf `Show` → `All Coordinate Systems` klicken
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken/attachments/Untitled 3.png|Untitled 3.png]]
        
          
        
        ---
        
          
        
    3. im Grafikfenster wird nun das Koordinatensystem angezeigt
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken/attachments/Untitled 4.png|Untitled 4.png]]
        
  
Da wir nun bestimmte Geometrien auswählen müssen empfiehlt es sich vorher kurz über die **Navigation** zu sprechen:
  
**Rotation**: `mittlere Maustaste gedrückt` halten **+** `Mausbewegung`
![[CleanShot_2022-10-13_at_14.59.56.gif|CleanShot_2022-10-13_at_14.59.56.gif]]
  
**Bewegung**: `STR` **+** `mittlere Maustaste gedrückt` halten
![[CleanShot_2022-10-13_at_15.03.43.gif|CleanShot_2022-10-13_at_15.03.43.gif]]
  
**Zoom**: `SHIFT` **+** `mittlere Maustaste gedrückt` halten
![[CleanShot_2022-10-13_at_15.07.46.gif|CleanShot_2022-10-13_at_15.07.46.gif]]
  
**Ansicht an Achsen orientieren**: Auf Achsen im Koordinatensystem rechts unten klicken
![[CleanShot_2022-10-13_at_15.22.05.gif|CleanShot_2022-10-13_at_15.22.05.gif]]
Fangen wir nun mit der Lagerung an:
  

> [!important]  
> Bringen Sie das Festlager auf der linken (y=0mm) unteren Seite (z=0) des Balkens an  
  
[https://scribehow.com/embed/ANSYS_Mechanical__Festlager_anbringen__bI6QsEsaTc2aZonh_EykUg?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Festlager_anbringen__bI6QsEsaTc2aZonh_EykUg?skipIntro=true&removeLogo=true)

> [!important]  
> Wir haben nun eingestellt das sie die untere Linie auf der linken Seite in alle drei Raumrichtungen nicht bewegen kann (=Festlager)  
  
Nun wiederholen wir das gleiche für die Rechte Seite, nur das wir hier die Bewegung in y-Richtung frei lassen (also hier nicht den Wert 0 eintragen)
  

> [!important]  
> Bringen Sie das Loslager auf der rechten (y=1000mm) unteren Seite (z=0) des Balkes an (siehe Bild rechts)  
  
**Hierzu gibt es kein Tutorial**, da sich im Vergleich zum Festlager nur die Geometrie (untere Linie rechts) und die Komponenten die Null gesetzt werden sollen ändern (hier nur x und z). So sollte das Detailfenster dann aussehen:
  
![[CleanShot_2022-10-13_at_15.59.012x.png|CleanShot_2022-10-13_at_15.59.012x.png]]
  

> [!important]  
> Bei dem Loslager kann sich also die untere Seite des Balkens frei in Balkenrichtung (=y-Richtung) bewegen  
  
Als nächstes bringen wir die Kraft als Belastung auf
  

> [!important]  
> Bringen eine Kraft auf der oberen Fläche (z=30mm) des Balkens mit F=1000N in negativer z-Richtung an.  
  
  
[https://scribehow.com/embed/ANSYS_Mechanical__Kraft_auf_Flache__VPxNV40fQOWw9iYwOXVn7A?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Kraft_auf_Flache__VPxNV40fQOWw9iYwOXVn7A?skipIntro=true&removeLogo=true)
  
Durch die Auswahl `Static Structural` im Strukturbaum kann man im Grafikfenster noch mal die Übersicht über alle Verschiebungen sehen
![[CleanShot_2022-10-13_at_16.25.292x.png|CleanShot_2022-10-13_at_16.25.292x.png]]
![[file.png|file.png]]
  
### 3. 2. 8. ==Lösungseinstellungen (Mechanical)==
Zu Beginn sind erst einmal keine Lösungseinstellungen notwendig.
  

> [!important]  
> Lösen Sie das Gleichungssystem.  
  
- 📋`Anleitung (Allg)` ==**(**====Mechanical) Gleichungssystem lösen==
    
    ---
    
    1. Im Strukturbaum **Rechtsklick** auf `Solution` → `Solve`
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken/attachments/Untitled 5.png|Untitled 5.png]]
        
    
    ---
    
  

> [!important]  
> Glückwunsch! Sie haben ihre erste Finite-Elemente Simulation gelöst. Jetzt schauen wir uns mal die Ergebnisse an …  
### 3. 2. 9. ==Lösungsdarstellung (Mechanical)==
  
Zunächst wollen wir uns die Durchbiegung (also die Verschiebung in Kraft-Richtung = z-Richtung) anschauen
  

> [!important]  
> Stellen Sie die Gesamtverschiebung und die Verschiebung in z-Richtung dar  
  
[https://scribehow.com/embed/ANSYS_Mechanical__Verschiebungsdarstellung_als_Pfad__UyGbknLTTTiPaS_VZEqzAw?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Verschiebungsdarstellung_als_Pfad__UyGbknLTTTiPaS_VZEqzAw?skipIntro=true&removeLogo=true)
Zur besseren Darstellung stellen wir das Einheitensystem noch auf mm um:
Klicken Sie zur Umstellung der Einheiten unten in der blauen Leiste auf `Metric (...)` und wählen Sie `Metric (mm, t, N, s, mV, mA)` aus
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken/attachments/Untitled 6.png|Untitled 6.png]]
  
So sollte das finale Ergebnis aussehen: Wir haben eine maximale Durchbiegung von $0{,}967\,\mathrm{mm}$﻿
![[file2.png|file2.png]]
  
  
  

> [!important]  
> Ermitteln Sie die maximale Spannung in y-Richtung und ermitteln Sie den Ort der maximalen Spannung.  
  
[https://scribehow.com/embed/ANSYS_Mechanical__Normalspannungen_darstellen__LGs8E2FARVqnVGQK07Zk6g?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Normalspannungen_darstellen__LGs8E2FARVqnVGQK07Zk6g?skipIntro=true&removeLogo=true)
So sollte das finale Ergebnis aussehen: Die maximale Normalspannung liegt bei $27{,}789\,\mathrm{MPa}$﻿
![[file3.png|file3.png]]
  
  
## 3. 3. Diskussion
  
  
Prüfen wir nun also die Ergebnisse mit Hilfe der analytischen Gleichungen für die bekannten Biegefälle.
  
Das Flächenträgheitsmoment ergibt sich zu
$I=\frac{b\,h^3}{12}=\frac{30\,\mathrm{mm}\,(30\,\mathrm{mm})^3}{12}=67500\,\mathrm{mm}^4$
  
**Durchbiegung**
Für den Fall des zweiseitig gelagerten Balkens mit Linienlast können wir die Durchbiegung berechnen nach:
$u_{max}=\frac{5\,q\,L^3}{384\,E\,I}=\frac{5\cdot1000\,\mathrm{N}\,(1000\,\mathrm{mm})^3}{384\cdot200000\,\mathrm{MPa}\cdot67500\,\mathrm{mm}^4}=0{,}965\,\mathrm{mm}$

> [!important]  
> Dieser Wert stimmt gut mit dem Wert aus unserer Simulation mit @import url('https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css')umax,Simulation=0,967 mmu_{max,Simulation}=0{,}967\,\mathrm{mm}umax,Simulation​=0,967mm﻿ überein. Bei einer Verschiebung von @import url('https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css')≈1mm\approx 1 \mathrm{mm}≈1mm﻿ ist eine Abweichung von @import url('https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css')1μm1 \mathrm{\mu m}1μm﻿ akzeptabel, da es ein Tausendstel der Ergebnisgröße ist.  
  
**Maximale Spannung**
Die maximale Biegespannung kann folgend berechnet werden:
$\sigma_{max}=M_{Max}\frac{\frac{h}{2}}{I}$
Mit dem maximalen Biegemoment zu:
$M_{Max}=\frac{q\,L}{8}=\frac{1000N\cdot1000\,\mathrm{mm}}{8}=125000\,\mathrm{Nmm}$
Kann die maximale Biegespannung berechnet werden:
$\sigma_{max}=M_{Max}\frac{\frac{h}{2}}{I}=125000\,\mathrm{mm}\frac{(30\,\mathrm{mm})/2}{67500\,\mathrm{mm}^4}=27{,}78\,\mathrm{MPa}$

> [!important]  
> Auch dieser Wert stimmt gut mit Wert aus unserer Simulation mit @import url('https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css')σmax,Simulation=27,789 MPa\sigma_{max,Simulation}=27{,}789\,\mathrm{MPa}σmax,Simulation​=27,789MPa﻿ überein.  
  
**Weiter geht es auf der nächsten Seite mit einem weiteren Beispiel**