---
publish: "true"
title: 03 Randbedingungen
---

# 3. Randbedingungen
Randbedingungen können unterteilt werden in **Lagerungen** und **Belastungen.** Beides hat einen sehr großen Einfluss auf das Ergebnis und kann bei falscher Anwendung zu komplett falschen Ergebnissen führen.
## 3.1 **Lagerungen**
  
**Lagerung** dienen vor allem dazu **Starrkörperbewegungen** zu unterbinden, der Körper soll also bei einer Belastung nicht unkontrolliert frei bewegen.
  
Zu Beginn ein paar Beispiele aus Technische Mechanik:
  
Bei Lagerungen definiert sich durch die folgenden zwei Punkte:
1. ==**Freiheitsgrad**==**: Verschiebung oder Rotation →** freigelassen oder sperren (=0)
2. ==**Geometrie:**== (Linie, Punkt, Fläche)
  
- Festlager
    
    ![[Loslager.png|Loslager.png]]
    
- Loslager
    
    ![[Festlager.png|Festlager.png]]
    
  
- feste Einspannung
    
    ![[feste_Einspannung.png|feste_Einspannung.png]]
    
- Rotationen
    
    ![[Rotation.png|Rotation.png]]
    
In ANSYS wird dies mit folgenden Randbedingungen umgesetzt:
  
`ANSYS` ==**Lagerung & Verschiebungen**==
- **==Fixed Support==** ==(Fixierte Lagerung)  
    → Alle Freiheitsgrade = 0==> [!important]  
    > Alle Verschiebungs-Freiheitsgrade werden blockiert  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✅**Wire Body/Line Body/Beam**
    
    **Topologietypen**: ✅**Body** ✅**Face** ✅**Edge** ✅**Vertex** ✅**Nodes** ==❌====**Elements**== ✅**Element Face**
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled.png|Untitled.png]]
    
    1. Kann auf so gut wie alles angewendet werden
    
      
    
    **Beispiel: Flansch**
    
    > [!important]  
    > Zusätzliche Randbedingung:  
    - Displacement ([[Praktikum 2 3. Randbedingungen|Praktikum 2 3. Randbedingungen]])  
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 1.png|Untitled 1.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 2.png|Untitled 2.png]]
    
    **max. Durchbiegung:** $u_{max}=0{,}54\,\mathrm{mm}$﻿
    
- **==Displacement==** ==(Verschiebung)==> [!important]  
    > Belastung durch Verschiebungswerte aufbringen und/oder Geometrie in bestimmte Richtung festhalten (Wert gleich Null setzen)  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✅**Wire Body/Line Body/Beam**
    
    **Topologietypen**: ✅**Body** ✅**Face** ✅**Edge** ✅**Vertex** ==❌====**Nodes**== ==❌====**Elements**== ==❌====**Element Face**==
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 3.png|Untitled 3.png]]
    
    1. Kann auf Punkte/Linien/Flächen und Körper angewendet werden
    2. Definierte durch `Components`  
        Verhalten je nach Angabe des Wertes:
        
        a) **=0**: keine Verschiebung
        
        b) **≠0**: Verschiebung aufbringen
        
        c) **Free**: keine Einschränkung
        
    
    > [!important]  
    > Für Knoten gibt es eine extra Randbedingung Nodal Displacement  
    
    **Beispiel: Flansch**
    
    > [!important]  
    > Zusätzliche Randbedingung:  
    - Fixed Support auf der Unterseite  
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 4.png|Untitled 4.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 2.png|Untitled 2.png]]
    
    **max. Durchbiegung:** $u_{max}=0{,}54\,\mathrm{mm}$﻿
    
- ==**Remote**== ==**Displacement**== ==(Externe Verschiebung)==> [!important]  
    > Externe (auf einen Punkt bezogene) Verschiebung und/oder Rotation  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✅**Wire Body/Line Body/Beam**
    
    **Topologietypen**: ==❌====**Body**== ✅**Face** ✅**Edge** ✅**Vertex** ==❌====**Nodes**== ==❌====**Elements**== ==❌====**Element Face**==
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 5.png|Untitled 5.png]]
    
    1. Kann auf Punkte/Linien/Flächen und Körper angewendet werden
    2. Randbedingung auf einen im Raum definierten Punkt
    3. Verschiebung/Rotation des Punktes
    4. Die Verschiebung/Rotation wird mittels verschiedener Verhaltensweisen auf die Fläche eingeleitet (siehe [[Praktikum 2 3. Randbedingungen|Praktikum 2 3. Randbedingungen]])
        - Rigid
        - Deformable
        - Coupled
        - Beam
    
    **Beispiel: Flansch**
    
    > [!important]  
    > Zusätzliche Randbedingung:  
    - Fixed Support auf der Unterseite  
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 6.png|Untitled 6.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 2.png|Untitled 2.png]]
    
    **max. Durchbiegung:** $u_{max}=1{,}16\,\mathrm{mm}$﻿
    
  
**Remote Displacement** wird verwendet um Verschiebungen von einem verbundenen starren Körper aus anzubringen der aber nicht modelliert werden muss. Nachfolgend ein Beispiel zur Verdeutlichung:
  
In dem Foto ist der Versuch zur Bestimmung der Komfortsteifigkeit von Fahrradrahmen dargestellt.
![[Komfortsteifigkeit_Real.png|Komfortsteifigkeit_Real.png]]
Versuch zur Bestimmung der Komfortsteifigkeit von Fahrradrahmen
- Der ==**Rahmen**== ist mit einem ==**Gabeldummy**== und einem ==**Hinterraddummy**== verbunden. Die Dummies sind im Vergleich zum Rahmen viel steifer, so dass davon ausgegangen werden kann das sich die Dummies nicht verformen (Hinweis: Starrkörperbewegung wie in dem Fall eine Verkippung ist weiterhin möglich).
- Somit kann man um Rechenzeit zu sparen (oder weil man die Geometrie z.B. nicht hat oder nicht modellieren möchte) nun das Festlager per **Remote Displacement** auf den Rahmen übertragen.
    
    ![[RemoteDisplacement_Vereinfacht.png|RemoteDisplacement_Vereinfacht.png]]
    
    - Dabei wird zum einen der externe Punkte gewählt von dem die Freiheitsgrade definiert werden (hier das Festlager am Ende des Gabeldummies)
    - Zum anderen wird die Geometrie ausgewählt auf die diese Randbedingung wirkt (hier das Steuerrohr des Rahmens)
  
  
- ==**Frictionless Support**== ==(Reibungsfreie Lagerung)==> [!important]  
    > Lagerung auf einer Fläche (z.B. für Symmetrierandbedingung)  
    Bewegung in Flächennormale blockiert  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✅**Wire Body/Line Body/Beam**
    
    **Topologietypen**: ==❌====**Body**== ✅**Face(3D)** ✅**Edge(2D)** ==❌====**Vertex**== ==❌====**Nodes**== ==❌====**Elements**== ==❌====**Element Face**==
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 7.png|Untitled 7.png]]
    
    1. Kann auf Flächen angewendet werden
    
    **Beispiel: Flansch**
    
    > [!important]  
    > Zusätzliche Randbedingung:  
    - Fixed Support auf der Unterseite  
    - Displacement ([[Praktikum 2 3. Randbedingungen|Praktikum 2 3. Randbedingungen]])  
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 8.png|Untitled 8.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 9.png|Untitled 9.png]]
    
    **max. Durchbiegung:** $u_{max}=0{,}54\,\mathrm{mm}$﻿
    
- ==**Compression Only Support**== ==(Starres Auflager)==> [!important]  
    > Lagerung innerhalb einer Bohrung mit Kontaktrechnung  
    Fläche kann vom virtuell starren Bolzen „abheben“  
    ⚠️ sehr zeitintensiv, da nichtlineare Kontaktrechnung.  
    Eventuell bevorzugt gegenüber zylindrischer Lagerung, wenn Bohrung unter starker Belastung und keine einfache Drehachse  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ==❌====**Surface/Shell**== ==❌====**Wire Body/Line Body/Beam**==
    
    **Topologietypen**: ==❌====**Body**== ✅**Face(3D)** ✅**Edge(2D)** ==❌====**Vertex**== ==❌====**Nodes**== ==❌====**Elements**== ==❌====**Element Face**==
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 10.png|Untitled 10.png]]
    
    1. Kann auf zylindrische Flächen angewandt werden
    2. Auswahl zum Kontaktverhalten
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung:  
    - Force mit 100N in der Mitte  
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 11.png|Untitled 11.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 12.png|Untitled 12.png]]
    
    **max. Durchbiegung:** $u_{max}=3{,}99\,\mathrm{mm}$﻿
    
- ==**Cylindrical Support**== ==(Zylindrische Lagerung)==> [!important]  
    > Zylindrische Lagerung ohne Kontakt (wenig Zeitintensiv)  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✅**Wire Body/Line Body/Beam**
    
    **Topologietypen**: ==❌====**Body**== ✅**Face(3D)** ✅**Edge(2D)** ==❌====**Vertex**== ==❌====**Nodes**== ==❌====**Elements**== ==❌====**Element Face**==
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 13.png|Untitled 13.png]]
    
    1. Kann auf zylindrische Flächen angewandt werden
    2. Folgende Freiheitsgrade können gesperrt werden:
        
        - Radial
        - Tangential
        - Axial
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 14.png|Untitled 14.png]]
        
        > [!important]  
        > Werden alle drei Freiheitsgrade gesperrt ist es ein Fixed Support  
        
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung:  
    - Force mit 100N in der Mitte  
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 15.png|Untitled 15.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 16.png|Untitled 16.png]]
    
    `Radial` fixiert `Axial` fixiert `Tangetial` free  
    **max. Durchbiegung:** $u_{max}=3{,}99\,\mathrm{mm}$﻿
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 17.png|Untitled 17.png]]
    
    `Radial` fixiert `Axial` fixiert `Tangetial` fixiert = `Fixed Support`  
    **max. Durchbiegung:** $u_{max}=0{,}64\,\mathrm{mm}$﻿
    
- ==ℹ️ Vergleich== ==**Cylindrical Support**== ==vs== ==**Compression Only Support**== ==für starke Belastungen==
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 18.png|Untitled 18.png]]
    
    Gleiche Zugkraft für beide Randbedingungen
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 19.png|Untitled 19.png]]
    
    `Cylindrical` Rechenzeit: 8sek
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 20.png|Untitled 20.png]]
    
    `Compression Only` (Rechenzeit: 2min30sek)
    

> [!important]  
> Für zylindrische Lagerung Compression Only nur wenn Lager stark belastet wird, da Rechenzeit für Kontaktberechnung sehr hoch. Alternativ Cylindrical Support verwenden.  
- ==**Elastic Support**== ==(Elastische Lagerung)==> [!important]  
    > Einführung von Federn unter der definierten Fläche mit definierter Gesamtsteifigkeit (Anwendung im Bauwesen, Luftlager? .. )  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ==❌====**Wire Body/Line Body/Beam**==
    
    **Topologietypen**: ==❌====**Body**== ✅**Face** ✅**Edge(2D)** ==❌====**Vertex**== ==❌====**Nodes**== ==❌====**Elements**== ==❌====**Element Face**==
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 21.png|Untitled 21.png]]
    
    1. Kann auf Flächen angewandt werden
    2. Definition der Steifigkeit
    
      
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung:  
    - Standard Earth Gravity  
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 22.png|Untitled 22.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 23.png|Untitled 23.png]]
    
    **max. Durchbiegung:** $u_{max}=-0{,}023\,\mathrm{mm}$﻿
    
    > [!important]  
    > Der dickere Teil der Struktur sinkt stärker ein, da die Kraft auf die Bettung dort größer ist  
    
  
## 3.2 **Belastungen**
  
Belastungen wirken auf das Bauteil und führen zusammen mit der Lagerung schlußendlich zu einer Spannung.
  
Die Belastung wird durch zwei Punkte definiert:
1. **Belastungsart:**
    1. Kraft / Druck
    2. Moment
    3. Beschleunigung
    4. Verschiebung / Rotation
    5. Temperatur (thermische Ausdehnung)
2. ==**Geometrie:**== (Linie, Punkt, Fläche)
  
Wenn Kräfte auf eine Fläche angewendet werden, so verteilt sich die Kraft automatisch auf die Geometrie. Eine analoge Belastung würde man mit Druck erhalten wenn man die Kraft durch die Fläche teilt
![[Kraft_Flaeche.png|Kraft_Flaeche.png]]
![[Druck.png|Druck.png]]
  
  
  
Auch eine Verschiebung die einen Wert ungleich Null besitzt kann als eine Belastung verwendet werden. Dabei kann man eine äquivalente Belastung zu einer Kraftbelastung auf die gleiche Geometrie hervorrufen. Dafür muss man nur die Verschiebung in Kraftrichtung auswerten und diese dann diese statt der Kraft als Last anbringen.
![[Last_Verschiebung.png|Last_Verschiebung.png]]
![[Last_Verschiebung_Flaeche.png|Last_Verschiebung_Flaeche.png]]
  
`ANSYS` ==**Belastungen durch Trägheit**==
- **==Acceleration==** ==(Beschleunigung)==> [!important]  
    > Beschleunigung in beliebige Richtung (für alle Körper gültig)  
    
    **Abstraktion**: ✅**3D** ✅2**D**
    
    **Geometrietypen**: ✅ **All Bodies Only**
    
    **Topologietypen**: ✅ **All Bodies Only**
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 24.png|Untitled 24.png]]
    
    1. Kann **nur** auf **alle Körper** angewendet
    2. **Richtung** definiert durch `**Component**` oder `**Vector**`
    3. beliebige **Beschleunigungswerte**
    
      
    
      
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung für das Beispiel:  
    Festlager auf der linken (x=0) unteren (z=0) Kante  
    Loslager auf der rechten (x=L) unteren (z=0) Kante  
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 25.png|Untitled 25.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 26.png|Untitled 26.png]]
    
    **max. Durchbiegung** $u_{max}=1{,}19\mathrm{e{-}6}\,\mathrm{mm}$﻿
    
      
    
- **==Standard Earth Gravity==** ==(Erdanziehungskraft)==> [!important]  
    > Beschleunigung der Erdanziehungskraft in beliebige Richtung (für alle Körper gültig)  
    
    **Abstraktion**: ✅**3D** ✅2**D**
    
    **Geometrietypen**: ✅ **All Bodies Only**
    
    **Topologietypen**: ✅ **All Bodies Only**
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 27.png|Untitled 27.png]]
    
    1. Kann **nur** auf **alle Körper** angewendet
    2. **Erdbeschleunigung** mit $9,8066\mathrm{\frac{m}{s^2}}$﻿
    3. Richtung definiert durch **globale Koordinatenachsen**
    
      
    
      
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung für das Beispiel:  
    Festlager auf der linken (x=0) unteren (z=0) Kante  
    Loslager auf der rechten (x=L) unteren (z=0) Kante  
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 28.png|Untitled 28.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 29.png|Untitled 29.png]]
    
    **max. Durchbiegung** $u_{max}=1{,}59\mathrm{e{-}5}\,\mathrm{mm}$﻿
    
      
    
- **==Rotational Velocity==** ==(Rotationsgeschwindigkeit)==> [!important]  
    > Beschleunigung der Erdanziehungskraft in beliebige Richtung (für alle Körper gültig)  
    
    **Abstraktion**: ✅**3D** ✔️**2D (Axialsymmetrie in Richtung der y-Achse)**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✅**Wire Body/Line Body/Beam**
    
    **Topologietypen**: ✅**Bodies** ❌==**Face**== ==❌====**Edge**== ==❌====**Vertex**== ==❌====**Nodes**== ==❌==**==Elements==** ==❌==**==Element Face==**
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 30.png|Untitled 30.png]]
    
    1. Kann **auf alle Körper** oder **einzelne Körper** angewendet werden
    2. **Richtung** und **Ursprung** definiert durch `Component` oder `Vector`  
          
        Betrag als `Konstante`, `Tabelle` oder `Funktion`
    
    > [!important]  
    > Berechnung der Fliehkraft aus:  
    @import url('https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css')𝐹=m ω2 r𝐹=m\,\omega^2\,rF=mω2r﻿  
    
      
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung für das Beispiel:  
    Festlager auf der linken (x=0) unteren (z=0) Kante  
    Loslager auf der rechten (x=L) unteren (z=0) Kante  
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 31.png|Untitled 31.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 32.png|Untitled 32.png]]
    
    **max. Durchbiegung** $u_{max}=2{,}46\mathrm{e{-}10}\,\mathrm{mm}$﻿
    
      
    
  
`ANSYS` ==**Belastungen durch Kräfte & Momente**==
- ==**Pressure**== ==(Druck)==> [!important]  
    > Druck auf eine Fläche  
    
    **Abstraktion**: ✅**3D** ❌==**2D**==
    
    **Geometrietypen**: ✅**Solid** ❌==**Surface/Shell**== ==❌====**Wire Body/Line Body/Beam**==
    
    **Topologietypen**: ❌==**Bodies**== ✅**Face** ✅**Edge** ✅**Vertex** ❌**==Nodes==** ==❌==**==Elements==** ==❌==**==Element Face==**
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 33.png|Untitled 33.png]]
    
    1. Kann **nur auf Flächen, Kanten und Punkte** angewendet werden
    2. Gemäß Definition in Voreinstellung **senkrecht auf der gewählten Fläche** (Voreinstellung, kann jedoch geändert werden)
    3. **Druck**: **positiver** Wert  
        **Zug**: **negativer** Wert
    
      
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung für das Beispiel:  
    Fixed Support auf der Unterseite  
    
    - Hinweise zur Vernetzung Geometriebeispiel "Box"
        
        1. Netzgröße auf `0,5mm` stellen
        2. **Im Strukturbaum**: Rechtsklick `Mesh` → `Insert` → `Method`
            1. **Im Detailfenster**: `Geometry` Alle Körper auswählen
            2. **Im Detailfenster**: `Method` auf `Multizone`
        
        - **Ergebnis zur Kontrolle**: Netz
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 34.png|Untitled 34.png]]
            
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 35.png|Untitled 35.png]]
    
      
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 36.png|Untitled 36.png]]
    
    **max. Durchbiegung:** $u_{max}=0{,}1065\mathrm{mm}$﻿
    
      
    
- ==**Hydrostatic Pressure**== ==(Hydrostatischer Druck)==> [!important]  
    > linear ansteigende verteile Drucklast (z.B. für gefüllte Behälter)  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ==❌====**Wire Body/Line Body/Beam**==
    
    **Topologietypen**: ❌==**Body**== ✔️**Face(3D)** ✔️**Edge(2D)** ❌==**Vertex**== ❌**==Nodes==** ==❌==**==Elements==** ==❌==**==Element Face==**
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 37.png|Untitled 37.png]]
    
    1. Nur auf **Flächen (3D)** bzw. **Kanten (2D)**
    2. Dichte des Mediums
    3. Definiert durch `Vector` oder `Components`
    4. Freie Oberfläche (ohne Druck)
    
      
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung für das Beispiel:  
    Fixed Support auf der Unterseite  
      
    > [!important]  
    > Koordinaten und Komponenten können abweichen, je nachdem wie Sie die Box modelliert haben. Es soll dabei der Boden der Box ausgewählt sein.  
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 38.png|Untitled 38.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 39.png|Untitled 39.png]]
    
    **max. Durchbiegung** $u_{max}=3{,}66\mathrm{e{-}8}\,\mathrm{mm}$﻿
    
- ==**Force**== ==(Kraft)==> [!important]  
    > Anbringen einer Kraft auf eine Geometrie  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✅**Wire Body/Line Body/Beam**
    
    **Topologietypen**: ❌==**Body**== ✅**Face** ✅**Edge** ✅**Vertex** ❌**==Nodes==** ==❌==**==Elements==** ==❌==**==Element Face==**
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 40.png|Untitled 40.png]]
    
    1. Kann auf Punkte/Linien und Flächen angewendet werden
    2. Richtung und Betrag definiert durch `Component` oder `Vector`  
          
        Betrag kann als `Konstante`, `Tabelle` oder `Funktion` angegeben werden
    
    > [!important]  
    > Für Flächen (Area):  
    Wird als Druck aufgebracht, basierend auf der selektierten Gesamtfläche  
      
    > [!important]  
    > Für Kanten (Edge):  
    Für die Selektion mehrerer Kanten wird die Kraft entlang aller Kanten gleichverteilt  
      
    > [!important]  
    > Für Punkte (Vertex):  
    Für die Selektion mehrerer Punkte wird die Kraft zwischen allen Punkten aufgeteilt  
      
    > [!important]  
    > Für Punkte (Vertex):  
    Das Anbringen einer Einzelkraft an einem Punkt führt zu Singularitäten und sollte vermieden werden!  
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung für das Beispiel:  
    Fixed Support auf der Unterseite  
    
    ![[Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/03 Randbedingungen/attachments/Untitled 1.png|Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/03 Randbedingungen/attachments/Untitled 1.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 41.png|Untitled 41.png]]
    
    **max. Durchbiegung:** $u_{max}=0{,}0015\mathrm{mm}$﻿
    
      
    
  
**Kräfte** werden durch das Programm (ANSYS) automatisch auf die **Geometrie** aufgeteilt (genauer gesagt auf die darunter liegenden Knoten verteilt). In dem unteren Beispiel wirkt die Kraft F auf die Fläche. Somit wird die Kraft ==**F**== also auf **16** **Knoten verteilt, so dass auf jeden Knoten die Kraft** **$\frac{1}{16}F$**﻿ **wirkt.**
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 3. Randbedingungen/attachments/Untitled 42.png|Untitled 42.png]]
![[Untitled 43.png|Untitled 43.png]]
![[Untitled 44.png|Untitled 44.png]]
![[Untitled 45.png|Untitled 45.png]]
- ==**Remote**== ==**Force**== ==(Externe Kraft)==> [!important]  
    > Eine externe Kraft ist eine Kraft die von einem definiertem Punkt im Raum ausgeht und dadurch ein zusätzliches Moment erzeugt. Dies kann genutzt werden, um eine Kraft die an einem Starrkörper (der nicht modelliert werden muss) angreift, zu ersetzen.  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✅**Wire Body/Line Body/Beam**
    
    **Topologietypen**: ❌==**Body**== ✔️**Face (3D)** ✅**Edge** ✅**Vertex**
    
    **Betrag als Konstante** `**Constant**`**:** ✅
    
    **Betrag als Tabelle** `**Tabular**`**:** ✅ **Lastschritt** ✅ **zeitlich** ❌ ==**örtlich**==
    
    **Betrag als Funktion** `**Function**`**:** ✅ **zeitlich** ❌ ==**örtlich**==
    
    ![[Untitled 46.png|Untitled 46.png]]
    
    1. Kann auf Punkte/Linien und Flächen angewendet werden
    2. Angabe einer Kraft auf einen definierten Punkt
    3. Definiert durch `Component` oder `Vector`
    4. Die Kraft wird mittels verschiedener Verhaltensweisen auf die Fläche eingeleitet:
        - Rigid (starr)> [!important]  
            > Geometrie kann sich nicht verformen  
            
        - Deformable (verformbar)> [!important]  
            > Geometrie kann sich verformen  
            
        - Coupled (gekoppelt)> [!important]  
            > Geometrie verhälts ich analog der Freiheitsgrade des Remotepunktes  
            
        - Beam (Balken)> [!important]  
            > Geometrie wird zum Remotepunkte durch ein Balkenelement mit definiertem Material und Radius verbunden  
            
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung für das Beispiel:  
    Fixed Support auf der Unterseite  
      
    > [!important]  
    > Koordinaten und Komponenten können abweichen, je nachdem wie Sie die Box modelliert haben.  
      
    Der externe Punkt (3) soll dabei mittig über einer äußere Kante der Fläche (1) im Abstand von 5mm nach oben (z-Richtung) liegen und die Kraft quer dazu angreifen (siehe Bilder unten)  
    
      
    
    ![[Untitled 47.png|Untitled 47.png]]
    
    externe Kraft auf obere Fläche (1) mit externen Punkt (2) über der Box in x-Richtung (3)
    
    **Verschiedene Verhaltensweisen (4)**
    
    ![[Untitled 48.png|Untitled 48.png]]
    
    Verhalten = **Rigid**
    
    > [!important]  
    > Rigid Fläche (1) bleibt steif, verformt sich also nicht  
    
    ![[Untitled 49.png|Untitled 49.png]]
    
    Verhalten = **Deformable**
    
    > [!important]  
    > Deformable Fläche (1) kann sich verformen  
    
    ![[Untitled 50.png|Untitled 50.png]]
    
    Verhalten = **Coupled**
    
    > [!important]  
    > Coupled Fläche (1) verhält sich in den Freiheitsgraden analog wie der externe Punkte.  
    
    > [!important]  
    > Der Unterschied zwischen Coupled und Rigid wird noch mal klar, wenn man sich beide in der Seitenansicht anschaut. Bei Rigid kommt es durch die starre Verbindung zur Verkippung der Fläche, wobei im Fall Coupled nur die Freiheitsgrade gekoppelt sind und dadurch nur die seitliche Bewegung ausgeführt wird.  
    
    ![[Untitled 51.png|Untitled 51.png]]
    
    **Seitenansicht**  
    Verhalten = **Rigid**
    
    ![[Untitled 52.png|Untitled 52.png]]
    
    **Seitenansicht**  
    Verhalten = **Coupled**
    
    ![[Untitled 53.png|Untitled 53.png]]
    
    Verhalten = Beam(steel 0,1mm)
    
    > [!important]  
    > Beam (0,1mm) Die Flächen (1) sind mit Masselosen Balkenelementen verbunden. Durch die geringe Steifigkeit (Radius 0,1mm) des Balkens bleibt die Fläche (1) flexibel und verformt vor allem dort wo der Hebelarm am größten ist.  
    
    ![[Untitled 54.png|Untitled 54.png]]
    
    Verhalten = Beam(steel 10mm)
    
    ![[Untitled 55.png|Untitled 55.png]]
    
    Verhalten = Beam(steel 1mm)
    
    > [!important]  
    > Beam (1mm) Durch die erhöhte Steifigkeit (Radius 1mm) des Balkens verformen nun auch die anderen Flächen stärker, die Lösung nähert sich immer mehr dem Rigid Verhalten an.  
    
    > [!important]  
    > Beam (10mm) Durch die sehr große Steifigkeit (Radius 10mm) der Balken, verhalten sich die Flächen wie im Fall Rigid.  
    
    **Ein Anwendungsbeispiel**
    
    ![[Untitled 56.png|Untitled 56.png]]
    
    Quelle: [Coval](https://www.coval-germany.com/Produkte/ultraflache-sauggreifer-fur-einebeschadigungsfreie-handhabung-reihe-vpsc-3395.htm)
    
    Stellen Sie sich vor Sie haben eine sehr dünne Platte die sich auf Grund des Eigengewichts bereits verformt. Jetzt würden Sie mit einem Sauggreifer aus weichem Kunststoff diese Platte ansaugen und anschließend nach oben bewegen. Durch einen weichen Kunststoff würde der Sauggreifer sich stark verformen und dies nicht stark auf die Platte weitergeben. Würden sie ein sehr steifes Material verwenden, so würde dies die Platte dazu zwingen im Bereich der Ansaugung sehr steif (Rigid) zu verhalten.
    
      
    
  
Die Remote Force funktioniert analog zur Remote Displacement. Dafür erneut die Erklärung am Beispiel der Komfortsteifigkeit.
  
![[Komfortsteifigkeit_Real2.png|Komfortsteifigkeit_Real2.png]]
  
- Die Kraft wird hierbei mittels eines Satteldummies auf das Sitzrohr übertragen. Wir gehen wieder davon aus, dass der Satteldummy steif ist und abstrahieren somit die Last mit Remote Force
    
    ![[RemoteForce.png|RemoteForce.png]]
    
  
- ==**Bearing Load**== ==(Bolzenlast)==> [!important]  
    > Erzeugt eine sinusförmige Druckverteilung in der Bohrungsfläche wobei die maximale Amplitude in Richtung der gewählten Kraft zeigt.  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ❌==**Surface/Shell**== ==❌====**Wire Body/Line Body/Beam**==
    
    **Topologietypen**: ❌==**Body**== ✅**Face** ✔️**Edge (2D)** ❌==**Vertex**== ❌**==Nodes==** ==❌==**==Elements==** ==❌==**==Element Face==**
    
    ![[Untitled 57.png|Untitled 57.png]]
    
    1. Kann auf zylindrische Flächen angewandt werden
    2. Richtung und Betrag definiert durch `Component` oder `Vector`  
        
    
    ![[Untitled 58.png|Untitled 58.png]]
    
- ==**Bolt Pretension**== ==(Schraubenvorspannkraft)==> [!important]  
    > Berechnung der Verformung von Schrauben infolge der Vorspannkraft  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✔️==**Wire Body**==**/Line Body/**==**Beam**==
    
    **Topologietypen**: ✅**Body** ✅**Face** ❌==**Edge**== ❌==**Vertex**== ❌**==Nodes==** ==❌==**==Elements==** ==❌==**==Element Face==**
    
    ![[Untitled 59.png|Untitled 59.png]]
    
    1. Kann auf Mantelflächen eines Schraubenzylinders angewandt werden
    2. Typischer weise wird die Vorspannkraft verwendet
    
    **Beispiel:**
    
    Wir benötigen hier noch eine Randbedingung welche die Verformung des Bauteils nicht beeinträchtigt. Dafür gibt es sogenannte Weak Springs (schwache Federn), die dann automatisch von außen am Bauteil anliegen und es dadurch festhalten.
    
    Diese werden über `Analysis Settings` eingeschaltet (siehe Bild unten)
    
    > [!important]  
    > Dies sollte man nur im äußersten Notfall tun, da hierbei Energie im Gesamtsystem verloren geht (selbst wenn man dies im nachhinein prüfen kann).  
      
    > [!important]  
    > Die bessere Lösung wäre das System zu schneiden und die Symmetrien auszunutzen, dies werden wir in einem späteren Praktikum durchführen.  
    
    ![[Untitled 60.png|Untitled 60.png]]
    
    ![[Untitled 61.png|Untitled 61.png]]
    
    ![[Untitled 62.png|Untitled 62.png]]
    
    **max. Durchbiegung:** $u_{max}=0{,}0108\mathrm{mm}$﻿
    
      
    
- ==**Moment**== ==(Moment)==> [!important]  
    > Anbringen eines Moments auf eine Geometrie  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✅**Wire Body/Line Body/Beam**
    
    **Topologietypen**: ❌==**Body**== ✔️**Face (3D)** ✅**Edge** ✅**Vertex** ❌**==Nodes==** ==❌==**==Elements==** ==❌==**==Element Face==**
    
    ![[Untitled 63.png|Untitled 63.png]]
    
    1. Kann auf Punkte/Linien und Flächen angewendet werden
    2. Definition mittels `Component`
    3. Das Moment wird mit verschiedenen Verhaltensweisen auf die Fläche eingeleitet (siehe [[Praktikum 2 3. Randbedingungen|Praktikum 2 3. Randbedingungen]]):  
        - Rigid (starr)  
        - Deformable (verformbar)  
        - Coupled (gekoppelt)  
        - Beam (Balken)
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung für das Beispiel:  
    Fixed Support auf der Unterseite  
    
    ![[Untitled 64.png|Untitled 64.png]]
    
    ![[Untitled 65.png|Untitled 65.png]]
    
    **max. Durchbiegung:** $u_{max}=8{,}6\mathrm{e{-}5}\,\mathrm{mm}$﻿
    
      
    
- ==**Line Pressure**== ==(Liniendruck)==> [!important]  
    > Anbringen einer Linienlast auf eine Geometrie  
    
    **Abstraktion**: ✅**3D** ❌==**2D**==
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✅**Wire Body/Line Body/Beam**
    
    **Topologietypen**: ❌==**Body**== ❌==**Face**== ✅**Edge** ❌==**Vertex**== ❌**==Nodes==** ==❌==**==Elements==** ==❌==**==Element Face==**
    
    ![[Untitled 66.png|Untitled 66.png]]
    
    1. Kann auf Punkte/Linien und Flächen angewendet werden
    2. Definition mittels `Component`, `Vector` oder `Tangetial`
    
    **Beispiel:**
    
    > [!important]  
    > Zusätzliche Randbedingung für das Beispiel:  
    Fixed Support auf der Unterseite  
    
    ![[Untitled 67.png|Untitled 67.png]]
    
    ![[Untitled 68.png|Untitled 68.png]]
    
    **max. Durchbiegung:** $u_{max}=0{,}107\,\mathrm{mm}$﻿
    
  
`ANSYS` ==**Thermische Belastung**==
- **==Thermal Condition==** ==(Thermische Bedingung)==> [!important]  
    > Thermische Randbedingung z.B. für Verformungen von Bimetallen  
    
    **Abstraktion**: ✅**3D** ✅**2D**
    
    **Geometrietypen**: ✅**Solid** ✅**Surface/Shell** ✅**Wire Body/Line Body/Beam**
    
    **Topologietypen**: ✅**Body** ❌==**Face**== ❌==**Edge**== ❌==**Vertex**== ❌**==Nodes==** ==❌==**==Elements==** ==❌==**==Element Face==**
    
    ![[Untitled 69.png|Untitled 69.png]]
    
    1. Kann auf Körper angewendet werden
    2. Eingabe von Temperaturgradienten
    
    **Beispiel: Bimetall**
    
    > [!important]  
    > Material aus Datenbank: Aluminum Alloy und Structural Steel  
    
    ![[Untitled 70.png|Untitled 70.png]]
    
    ![[Untitled 71.png|Untitled 71.png]]
    
    **max. Durchbiegung:** $u_{max}=0{,}033\,\mathrm{mm}$﻿
    
  
  
## 3.3. Die 3 Möglichkeiten Randbedingungen anzubringen
  
Hier wird noch mal aufgezeigt wie Randbedinungen angebracht werden können:
  
- **Variante A**: ==**Im Strukturbaum**== **Rechtsklick** auf `Static Structural`
    
    ![[Untitled 72.png|Untitled 72.png]]
    
- **Variante B**: ==**Im Geometriefenster**== **Rechtsklick** auf `die Geometrie`> [!important]  
    > Vorher muss Static Structural im Strukturbaum ausgewählt sein  
    
    ![[Untitled 73.png|Untitled 73.png]]
    
- **Variante C**: ==**Menüleiste**== **Rechtsklick** auf `die Geometrie`> [!important]  
    > Vorher muss Static Structural im Strukturbaum ausgewählt sein  
      
    > [!important]  
    > Vorteil: Die Randbedingungen sind thematisch zusammengefasst  
    
    ![[Untitled 74.png|Untitled 74.png]]
    
## 3.4. Geometrieselektion
  
Da Randbedingungen werden wie bereits erwähnt entweder von Geometrien auf Knoten übertragen oder direkt auf diese angewandt.
Zur Auswahl stehen in der Menüleiste ==**Geometrien (Punkte/Linien/Flächen/Volumen)**== oder ==**Knoten**== ==und== ==**Elemente**==
![[Untitled 75.png|Untitled 75.png]]
  
Die **Geometrieselektion** kann **vor der Einbringung der Randbedingung** erfolgen oder **nach Einbringung der Randbedingung eingefügt** oder **ergänzt werden**
  
![[Untitled 76.png|Untitled 76.png]]
![[Untitled 77.png|Untitled 77.png]]
  
## 3.4. Richtungsdefinition (z.B. bei Kräften)
  
**Vektorielle Größen** wie **Kräfte** können auf zwei verschiedene Arten angewandt werden:
- Kraftrichtung mittels Vektor `Vector` definieren
- Kraftrichtung mittels Komponente `Component` definieren
  
### 3.4.1. **Kraftrichtung mittels Vektor definieren**
**Betrag** und **Richtung** müssen eingegeben werden. Die **Richtung** kann mittels folgender Geometrien definiert werden werden:
- zwei Punkte
- eine Linie
- eine Flächennormale
- Achse einer Bohrung
![[Untitled 78.png|Untitled 78.png]]
  
![[Untitled 79.png|Untitled 79.png]]
  
### 3.4.2. **Kraftrichtung mittels Komponente definieren**
Kraft wird im definierten Koordinatensystem in den jeweiligen Komponenten angegeben. Ein negatives Vorzeichen im Betrag führt zur Richtungsänderung um 180°.
![[Untitled 80.png|Untitled 80.png]]
## 3.5. Variationen von Randbedingungen innerhalb von einem Modell
  
Wollen Sie innerhalb von einem Modell zwei verschiedene Versionen mit unterschiedlichen Randbedingungen, aber gleichem Material und Vernetzung haben, so können Sie eine neue Analyse auf die bereits vorhandene ziehen:
![[WorkbenchMenu-Analysen-verknuepfen.gif|WorkbenchMenu-Analysen-verknuepfen.gif]]
  
![[Untitled 81.png|Untitled 81.png]]
Nach dem Öffnen von **Mechanical** finden sich die Analysen **untereinander im** **Strukturbaum** wieder
![[Mechanical-RB-Post-kopieren.gif|Mechanical-RB-Post-kopieren.gif]]
Sie können per Drag&Drop auch Randbedingungen (aber auch Lösungsdarstellungen) von einem in die andere Analyse ziehen
  
  
  
  
◀️ [[P2 - Geometrieerstellung und Randbedingungen|P2 - Geometrieerstellung und Randbedingungen]]
[[Praktikum 2 4. Fahrradrahmen|Praktikum 2 4. Fahrradrahmen]][[Praktikum 2 4. Fahrradrahmen|Praktikum 2 4. Fahrradrahmen]]
  
==Praktikum erstellt von:== Felix Kaule======Links:== [[❓FAQ|❓FAQ]]
  
==Hochschule für Technik, Wirtschaft und Kultur Leipzig  
Fakultät Ingenieurwissenschaften  
Karl-Liebknecht-Str. 134  
04277 Leipzig==