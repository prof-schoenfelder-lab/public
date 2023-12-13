---
publish: "true"
title: 04 Beispiel B- einseitig eingespannter Balken mit Einzelkraft
---

- 📋`Anleitung (Allg)` ==**(**====Mechanical) Gleichungssystem lösen==
    
    ---
    
    1. Im Strukturbaum **Rechtsklick** auf `Solution` → `Solve`
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 3. Beispiel A- zweiseitig gelagerter Balken/attachments/Untitled 5.png|Untitled 5.png]]
        
    
    ---
    # 4. Beispiel B: einseitig eingespannter Balken mit Einzelkraft
  
Um den sich immer wiederholenden Ablauf zu üben, bearbeiten wir nun ein weiteres Beispiel mit einem anderen Querschnitt, anderen Randbedingungen und einem neuen Material.
## 4. 1. **Aufgabenstellung**
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/BeispielB_Aufgabenstellung.png|BeispielB_Aufgabenstellung.png]]
  
### ==Gegeben==
  
==**Material**==
**Aluminium**
- Elastizitätsmodul $E=70\,\mathrm{GPa}$﻿
- Querkontraktionszahl $\nu=0{,}3$﻿
==**Geometrie**==
**Balken mit rechteckigem Querschnitt**
- Länge ==$L=1000\,\mathrm{mm}$==﻿
- Breite ==$b=30\,\mathrm{mm}$==﻿
- Breite ==$h=60\mathrm{mm}$==﻿
==**Randbedingungen**==
- feste Einspannung auf der linken Seite
- Einzelkraft am Ende des Balkens ==$F=1000\,\mathrm{N}$==﻿
### ==Gesucht==
  
1. Die maximale Durchbiegung $u_{max}$﻿
2. Die maximale Spannung in y-Richtung $\sigma_{y,max}$﻿
  
  
## 4. 2. Lösung
  

> [!important]  
> Zur Hilfe werden Ihnen die teilweise Tutorials aus dem Beispiel A eingeblendet.  
### 4. 2. 1. Analyse hinzufügen
  

> [!important]  
> Fügen Sie eine Strukturmechanische Analyse (Static Structural) in ANSYS Workbench hinzu  
  
[https://scribehow.com/embed/ANSYS_Mechanical__zweite_Analyse_hinzufugen__EaJV3kUETtiuGm3hsjwEmw?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__zweite_Analyse_hinzufugen__EaJV3kUETtiuGm3hsjwEmw?skipIntro=true&removeLogo=true)
  
### 4. 2. 2. ==Materialdefinition (Workbench)==

> [!important]  
> Erstellen Sie ein Material mit den Materialparametern aus der Aufgabenstellung  
**Aluminium**
- Elastizitätsmodul $E=70\,\mathrm{GPa}$﻿
- Querkontraktionszahl $\nu=0{,}3$﻿
  
**Anleitung aus dem ersten Beispiel:**
[https://scribehow.com/embed/ANSYS_Workbench__Linear_Elastisches_Material_hinzufugen__WV52z8uaRNGFwMvVUu0R5Q?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Workbench__Linear_Elastisches_Material_hinzufugen__WV52z8uaRNGFwMvVUu0R5Q?skipIntro=true&removeLogo=true)
### 4. 2. 3. ==Geometrieerstellung (SpaceClaim)==

> [!important]  
> Erstellen Sie die Geometrie [[Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft|Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft]]Skizze und den Parametern aus der Aufgabenstellung  

> [!important]  
> Stellen Sie diesmal eine Höhe von h=60mm in z-Richtung ein.  
**Balken mit rechteckigem Querschnitt**
- Länge (y) ==$L=1000\,\mathrm{mm}$==﻿
- Breite (x) ==$b=30\,\mathrm{mm}$==﻿
- Höhe (z) ==$h=60\mathrm{mm}$==﻿
  
  
**Anleitung aus dem ersten Beispiel:**
[https://scribehow.com/embed/SpaceClaim__Rechteckprofil_Balken_erstellen__32o8UKi8Qfmip6oXaHdpFA?skipIntro=true&removeLogo=true](https://scribehow.com/embed/SpaceClaim__Rechteckprofil_Balken_erstellen__32o8UKi8Qfmip6oXaHdpFA?skipIntro=true&removeLogo=true)
  
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/Untitled.png|Untitled.png]]
    
  
### 4. 2. 5. ==Materialzuweisung & Modelleinstellung (Mechanical)==

> [!important]  
> Weisen Sie nun dem Geometrie das Material zu  

> [!important]  
> Verwenden Sie das neu angelegte Material Aluminium!  
  
**Anleitung aus dem ersten Beispiel:**
[https://scribehow.com/embed/ANSYS_Mechanical__Material_zuweisen__I_Hqji9UTluDUeV5b4s5zw?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Material_zuweisen__I_Hqji9UTluDUeV5b4s5zw?skipIntro=true&removeLogo=true)
### 4. 2. 6. ==Vernetzung (Mechanical)==
  

> [!important]  
> Vernetzen Sie das Bauteil und erhöhen Sie die Resolution auf 5  
  
**Anleitung aus dem ersten Beispiel:**
[https://scribehow.com/embed/ANSYS_Mechanical__Netzgrosse_uber_Resolution__yKnW8y6yTwCGQIWGqVZioA?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Netzgrosse_uber_Resolution__yKnW8y6yTwCGQIWGqVZioA?skipIntro=true&removeLogo=true)
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/Untitled 1.png|Untitled 1.png]]
    
  
### 4. 2. 7. ==Randbedingungen (Mechanical)==

> [!important]  
> Bringen Sie eine feste Einspannung auf der linken (y=0mm) des Balkens an  
**Anleitung aus dem ersten Beispiel:**
[https://scribehow.com/embed/ANSYS_Mechanical__Festlager_anbringen__bI6QsEsaTc2aZonh_EykUg?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Festlager_anbringen__bI6QsEsaTc2aZonh_EykUg?skipIntro=true&removeLogo=true)
  

> [!important]  
> Anders als Festlager bei dem wir die Linie auf der Unterseite festgehalten haben, wird bei der festen Einspannung die gesamte Fläche in alle Richtungen festgehalten  
  

> [!important]  
> Bringen eine Kraft auf der oberen (z=60mm) rechten (y=1000mm) Kante des Balkens mit dem Wert F=1000N in negativer z-Richtung an.  
  
**Anleitung aus dem ersten Beispiel:**
[https://scribehow.com/embed/ANSYS_Mechanical__Kraft_auf_Flache__VPxNV40fQOWw9iYwOXVn7A?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Kraft_auf_Flache__VPxNV40fQOWw9iYwOXVn7A?skipIntro=true&removeLogo=true)
  
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/Untitled 2.png|Untitled 2.png]]
    
  
### 4. 2. 8. ==Lösungseinstellungen (Mechanical)==

> [!important]  
> Lösen Sie das Gleichungssystem.  
  
**Anleitung aus dem ersten Beispiel:**
  
  
### 4. 2. 9. ==Lösungsdarstellung (Mechanical)==
  

> [!important]  
> Ermitteln Sie die maximale Durchbiegung in z-Richtung.  
  
**Anleitung aus dem ersten Beispiel:**
[https://scribehow.com/embed/ANSYS_Mechanical__Verschiebungsdarstellung_als_Pfad__UyGbknLTTTiPaS_VZEqzAw?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Verschiebungsdarstellung_als_Pfad__UyGbknLTTTiPaS_VZEqzAw?skipIntro=true&removeLogo=true)
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/Untitled 3.png|Untitled 3.png]]
    
    $u_{z,max}=8{,}8\,\mathrm{mm}$﻿
    
  

> [!important]  
> Ermitteln Sie die maximale Spannung in y-Richtung.  
  
**Anleitung aus dem ersten Beispiel:**
[https://scribehow.com/embed/ANSYS_Mechanical__Normalspannungen_darstellen__LGs8E2FARVqnVGQK07Zk6g?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Normalspannungen_darstellen__LGs8E2FARVqnVGQK07Zk6g?skipIntro=true&removeLogo=true)
  
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/Untitled 4.png|Untitled 4.png]]
    
    $\sigma_{y,max}=64{,}6\,\mathrm{MPa}$﻿
    
  
  
## 4. 3. Diskussion
  
Das Flächenträgheitsmoment ergibt sich zu
$I=\frac{b\,h^3}{12}=\frac{30\,\mathrm{mm}\,(60\,\mathrm{mm})^3}{12}=540000\,\mathrm{mm}^4$
  
**Durchbiegung**
Für den Fall des eingespannten Balkens mit Einzellast können wir die **Durchbiegung** berechnen nach:
$u_{max}=\frac{F\,L^3}{3\,E\,I}=\frac{1000\,\mathrm{N}\,(1000\,\mathrm{mm})^3}{3\cdot70000\,\mathrm{MPa}\cdot540000\,\mathrm{mm}^4}=8{,}8\,\mathrm{mm}$

> [!important]  
> Dieser Wert stimmt gut mit dem Wert aus unserer Simulation mit @import url('https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css')umax,Simulation=8,8 mmu_{max,Simulation}=8{,}8\,\mathrm{mm}umax,Simulation​=8,8mm﻿ überein.  
  
**Maximale Spannung**
  
Die maximale Biegespannung kann folgend berechnet werden:
$\sigma_{max}=M_{Max}\frac{\frac{h}{2}}{I}$
Mit dem maximalen Biegemoment zu:
$M_{Max}=q\,L=1000\,\mathrm{N}\cdot1000\,\mathrm{mm}=1000000\,\mathrm{Nmm}$
Die maximale Biegespannung kann folgend berechnet werden:
$\sigma_{max}=M_{Max}\frac{\frac{h}{2}}{I}=1000000\,\mathrm{Nmm}\frac{(60\,\mathrm{mm})/2}{540000\,\mathrm{mm}^4}=55{,}6\,\mathrm{MPa}$

> [!important]  
> Dieser Wert stimmt nicht gut mit Wert aus unserer Simulation mit @import url('https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css')σy,max,Simulation=64,6 MPa\sigma_{y,max,Simulation}=64{,}6\,\mathrm{MPa}σy,max,Simulation​=64,6MPa﻿ überein.  
  
**Woher kommt die Abweichung in der Spannung?**
Zunächst schauen wir uns die **Normalspannung (y-Richtung)** entlang der oberen Kante an:
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/Untitled 5.png|Untitled 5.png]]
![[CleanShot_2022-10-13_at_17.53.572x.png|CleanShot_2022-10-13_at_17.53.572x.png]]
Im Pfad sehen wir das die Normalspannung bis zur Einspannung linear ansteigt, aber an der Einspannung (bei 0mm) nicht mehr stimmt.

> [!important]  
> Schauen wir uns nun die Verschiebung in x-Richtung im Bereich der Einspannung an. Nun sehen wir, dass der Balken auf Grund der Querkontraktion seinen Querschnitt eigentlich verändern möchte, aber durch die flächige Einspannung daran gehindert wird.  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/Untitled 6.png|Untitled 6.png]]
  
Jetzt gibt es zwei Lösungen das Problem zu umgehen.
- **Lösung 1**: Querkontraktion auf Null setzen
    
    Dieser Weg soll nur verdeutlichen das wir das Problem hier beheben können. Allgemein wird unser Modell ==**dadurch aber schlechter**====,== ==**da wir nun die Querkontraktion nicht mehr berücksichtigen**====.==
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/Untitled 7.png|Untitled 7.png]]
    
    > [!important]  
    > Wir kommen mit @import url('https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css')σy,max,Simulation=56 MPa\sigma_{y,max,Simulation}=56\,\mathrm{MPa}σy,max,Simulation​=56MPa﻿ sehr nah an die analytische Lösung von @import url('https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css')σy,max,analytisch=56,6 MPa\sigma_{y,max,analytisch}=56{,}6\,\mathrm{MPa}σy,max,analytisch​=56,6MPa﻿  
    
  

> [!important]  
> Probieren Sie selber ob Sie durch Anpassung der Randbedingung der analytischen Lösung näher kommen  

> [!important]  
> Zur Lösung benötigen Sie das Node-Selection Tool. Anders als die bisher vorgestellten Auswahltools können Sie damit direkt an einem Knoten Randbedingungen anbringen.  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/Untitled 8.png|Untitled 8.png]]
- **Lösung 2:** Randbedingung anpassen
    
    Der favorisierte zweite Weg zeigt eine Möglichkeit wie wir nur das Zentrum des Querschnitts im Bereich der Einspannung festhalten und die Fläche dazu in der Einspannung sich frei bewegen kann, so dass der Querschnitt sich hier auch ändern kann.
    
    [https://scribehow.com/embed/ANSYS_Mechanical__feste_Einspannung_Spannungsuberhohung_unterdrucken_bei_Biegung__BewdkP9GSQ2pV3Sn8Ks5vg?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__feste_Einspannung_Spannungsuberhohung_unterdrucken_bei_Biegung__BewdkP9GSQ2pV3Sn8Ks5vg?skipIntro=true&removeLogo=true)
    
      
    
    Für die Normalspannung ergibt sich nun:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/Untitled 9.png|Untitled 9.png]]
    
    > [!important]  
    > Wir kommen mit @import url('https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css')σy,max,Simulation=56,1 MPa\sigma_{y,max,Simulation}=56{,}1\,\mathrm{MPa}σy,max,Simulation​=56,1MPa﻿ sehr nah an die analytische Lösung von @import url('https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css')σy,max,analytisch=56,6 MPa\sigma_{y,max,analytisch}=56{,}6\,\mathrm{MPa}σy,max,analytisch​=56,6MPa﻿  
