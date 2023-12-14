---
publish: "true"
title: 04 Fahrradrahmen
---

# 4. Fahrradrahmen
  
Hier wollen wir nun die `Geometrieaufbereitung` und einfache `Randbedingungen` an einem realen Beispiel anwenden. Dafür verwenden wir einen Trekking Rahmen von Bergamont, den wir in der Simulation hinsichtlich der Steifigkeit untersuchen wollen. Da für die Gesamtsteifigkeit kleine Details nicht wichtig sind, können wir alle Bohrungen und kleinen Details entfernen, wodurch unser Netz deutlich einfacher sein sollte.
![[Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/04 Fahrradrahmen/attachments/Untitled 6.png|Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/04 Fahrradrahmen/attachments/Untitled 6.png]]
  
## 4. 1 Geometrieaufbereitung
  

> [!important]  
> Laden Sie im OPAL die Datei TrekkingRahmen_01_Original.step unter Praktikum / Praktikum 02 - Geometrieerstellung & Randbedingungen runter und fügen Sie diese Datei in SpaceClaim hinzu  
  
> [!important]  
> Führen Sie für die Geometrieaufbereitung folgende Schritte aus:  
  
1. Entfernung aller nicht relevanten Bohrungen / Einzelteile  
2. Verbindung aller übrigen Einzelteile zu einem Gesamtteil  
  
**Hinweis zur Verbindung aller Teile:**
- Dies erfolgt mit dem Tool `Combine` (Reiter `Design`), wobei mit `STR` Teile zusammengeführt werden können
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled.png|Untitled.png]]
    
- Falls Sie mit der Geometrieaufbereitung nicht weiterkommen finden Sie im OPAL auch ein bereits aufbereitetes Modell des Rahmens
## 4. 2 Komfortsteifigkeit vereinfacht
  

> [!important]  
> Überführen Sie die aufbereitete Geometrie in ANSYS Mechanical Modell  
  
### Material & Vernetzung
  

> [!important]  
> Verwenden Sie dieses Mal die vorgefertigten Materialien Aluminium Alloy aus der Materialdatenbank 📚 General Materials und vernetzen Sie die Geometrie mit einer Elementgröße von 10mm  
**Hinweis zur Vernetzung**
- Da wir nur die Steifigkeit untersuchen, reicht ein relativ grobes Netz mit `10mm` aus
- Die Einstellung für die Elementgröße finden Sie durch das Auswählen von `Mesh` im Strukturbaum und dem Detailfenster unter `Defaults` → `Element Size`
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 1.png|Untitled 1.png]]
  
  
- `LÖSUNG` So sollte die Vernetzung aussehen
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 2.png|Untitled 2.png]]
    
  
### Randbedingungen
Wir wollen nun schauen wie der Rahmen sich verformt, wenn z.B. eine Person von 70kg auf dem Sattel sitzt. In dem Fall haben wir nur den Rahmen, wir versuchen aber alle Randbedingungen auf diesen anzubringen mit folgenden Überlegungen:
  
1. **Belastung von 700N** auf den **Sattel** _(entspricht ca. 70kg)_
2. **Starrkörperbewegungen** sollen unterbunden werden
  

> [!important]  
> Finden Sie Randbedingungen die die oberen Bedingungen erfüllen. Legen Sie die Randbedingungen dabei so aus, dass Sie ungefähr dem entsprechen wenn Sie sich auf das Fahrrad setzen mit angezogener Hinterradbremse. Verwenden Sie hierbei zunächst weder Remote-Displacement noch Remote-Force.  
  
> [!important]  
> Je nachdem wie Sie die Kraft einleiten wird dies ein großen Einfluss auf das Ergebnis haben  
  
- `LÖSUNG` Verschiebung
    
      
    **Variante 1:  
    **- **feste Einspannung** Hinterachse  
    - **Loslager** Unterseite Steuerrohr  
    - **Kraft** auf Oberseite Sitzrohr
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 3.png|Untitled 3.png]]
    
    **Variante 2:  
    **- **feste Einspannung** Hinterachse  
    - **Loslager** Unterseite Steuerrohr  
    - **Kraft auf** Innenfläche Sitzrohr (oberer Teil)
    
    ![[2.png|2.png]]
    
- `LÖSUNG` Verschiebung Animation
    
    **Variante 1:  
    **- **feste Einspannung** Hinterachse  
    - **Loslager** Unterseite Steuerrohr  
    - **Kraft** auf Oberseite Sitzrohr
    
    ![[Komfortsteifigkeit_V1.gif|Komfortsteifigkeit_V1.gif]]
    
    **Variante 2:  
    **- **feste Einspannung** Hinterachse  
    - **Loslager** Unterseite Steuerrohr  
    - **Kraft auf** Innenfläche Sitzrohr (oberer Teil)  
    
    ![[Komfortstefigkeit_v2.gif|Komfortstefigkeit_v2.gif]]
    
  
## 4. 2 Lenkkopfsteifigkeit
  
Nun wollen wir mit dem gleichen Modell (gleiches Material/Geometrie/Vernetzung) und wollen nur andere Randbedingungen anbringen. Dafür empfiehlt es sich, eine neue Analyse (`Static Structural`) auf die Komponente `Model` der vorherigen Analyse zu ziehen. Dadurch werden alle Teile bis zu den Randbedingungen übernommen (_es ist also z.B. keine separate Vernetzung notwendig_).
![[neueAnalyse.gif|neueAnalyse.gif]]
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 4.png|Untitled 4.png]]
Die neue Analyse erscheint dann unter der vorherigen im Strukturbaum. Mit `F2` können die Analysen im Strukturbaum auch noch umbenannt werden (wie in dem Fall zu `Komfortsteifigkeit` und `Lenkkopfsteifigkeit`).
  
Bei der Lenkkopfsteifigkeit wird das Hinterrad fixiert und im Abstand von `1000mm` von der Mitte des Steuerrohrs entfernt eine Kraft von `100N` senkrecht zum Fahrrad eingeleitet (in unserem Fall in die globale x-Richtung)
  

> [!important]  
> Finden Sie Randbedingungen die die oberen Bedingungen erfüllen. Zum Vergleich können Sie sich die Gesamtverformung in der unteren Animation als Vergleich ansehen.  
  
Zur besseren Einbringung der Kraft empfiehlt es sich ein neues Koordinatensystem im Mittelpunkt des Steuerrohrs zu definieren:
- `Hinweis` Koordinatensystem im Steuerrohr erstellen
    
    Die Innenwand des Steuerrohrs auswählen
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 5.png|Untitled 5.png]]
    
    und im Strukturbaum Rechtsklick auf `Coordinate Systems` → `Insert` → `Coordinate System`
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 6.png|Untitled 6.png]]
    
    → Koordinatensystem umbenennen in `Steuerrohr_KOS`
    
    Im Detailfenster unter Principal Axis → Define By → Geometry Selection
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 7.png|Untitled 7.png]]
    
    Mit dem `Flächenauswahltool` die Innenwand des Steuerrohrs auswählen und mit `Apply` bestätigen
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 8.png|Untitled 8.png]]
    
      
    
    Das neue Koordinatensystem liegt nun im Zentrum des Steuerrohrs
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 9.png|Untitled 9.png]]
    
      
    
  
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 10.png|Untitled 10.png]]
Die maximale Verformung liegt hier bei `2,6mm`
  
- `LÖSUNG` **Randbedingungen**
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 11.png|Untitled 11.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 12.png|Untitled 12.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 13.png|Untitled 13.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Untitled 14.png|Untitled 14.png]]
    
      
    
- `LÖSUNG` **Verschiebung Animation**
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 4. Fahrradrahmen/attachments/Lenkkopfsteifigkeit.gif|Lenkkopfsteifigkeit.gif]]
    
      
    
  
  
## 4. 3 Komfortsteifigkeit verbessert `Zusatzaufgabe`
  
Setzen Sie die Komfortsteifigkeit analog der realen Randbedingungen um und Vergleichen Sie die Lösung mit der Variante die Sie oben verwendet haben:
- Der **Gabeldummy** besitzt ein **gelenkige Lagerung**
    - ==$dy_F=460mm$==﻿
    - ==$dx_F=210mm$==﻿
- Der **Hinterraddummy** besitzt eine **zylindrische Lagerung**
    - ==$dy_R=390mm$==﻿
![[Komoforsteifigkeit_komplett.png|Komoforsteifigkeit_komplett.png]]
Randbedingungen bei der Komfortsteifigkeit
  
  
  
◀️ [[P2 - Geometrieerstellung und Randbedingungen|P2 - Geometrieerstellung und Randbedingungen]]
[[Praktikum 2 5. Zusammenfassung & Ausblick|Praktikum 2 5. Zusammenfassung & Ausblick]][[Praktikum 2 5. Zusammenfassung & Ausblick|Praktikum 2 5. Zusammenfassung & Ausblick]]
==Praktikum erstellt von:== Felix Kaule======Links:== [[❓FAQ|❓FAQ]]
  
==Hochschule für Technik, Wirtschaft und Kultur Leipzig  
Fakultät Ingenieurwissenschaften  
Karl-Liebknecht-Str. 134  
04277 Leipzig==