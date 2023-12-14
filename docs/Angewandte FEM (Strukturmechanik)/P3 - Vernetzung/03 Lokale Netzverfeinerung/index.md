---
publish: "true"
title: 03 Lokale Netzverfeinerung
---

# 3. Lokale Netzverfeinerung
Die lokale Netzverfeinerung hat den Vorteil, dass wir das globale Netz relativ grob halten können und nur
In diesem Abschnitt nehmen wir eine Sweep Geometrie eines Hakens als Beispiel zur Veranschaulichung unterschiedlicher Methoden der Netzverfeinerung. Je nach Methode kann das durch Sweep gewonnene Hexaeader Netz beibehalten werden oder auch nicht.
  
## 3.1 Beispiel Haken (Sweep/Hexa Mesh)
![[Angewandte FEM (Strukturmechanik)/P3 - Vernetzung/03 Lokale Netzverfeinerung/attachments/Untitled.png|Angewandte FEM (Strukturmechanik)/P3 - Vernetzung/03 Lokale Netzverfeinerung/attachments/Untitled.png]]
  

> [!important]  
> Laden Sie das Bauteil "Haken_sweepable.sdoc" ein. Verwenden Sie das Standardmaterial "Structural Steel" und führen Sie eine Sensitivitätsanalyse bis minimal 0,5mm mit der maximalen Vergleichsspannung (von-Mises) und der maxialen Verformung durch.  
  
Verwenden Sie die Methode “Sweep”, um den Körper zu vernetzen.  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Haken_sweepable.scdoc|Haken_sweepable.scdoc]]

> [!important]  
> Die Geometrie wurde in dem Fall schon vorher aufbereitet, dass Sie "gesweept" werden kann.  
  
  
- `Lösung` **Sensitivitätsanalyse (Sweep/Hexa Mesh)** $\sigma_{eqv,max}=787{,}7\,\mathrm{MPa}$﻿
    
    ![[Haken_Sensitivitaetsanalyse.png|Haken_Sensitivitaetsanalyse.png]]
    
      
    
    Erst ab einer Elementgröße von kleiner als 0,25mm verändert sich die maximale Vergleichsspannung nicht mehr. Der Rechenaufwand für so eine feine globale Vernetzung ist enorm.
    
      
    
  
Da eine so feine globale Vernetzung von 0,25mm sehr ineffektiv ist, schauen wir uns nun an wie wir die Linieneinteilung die wir zu Beginn des Praktikums kennengelernt haben nutzen können um hier eine lokale Netzverfeinerung vorzunehmen
## `Zusatz` Beispiel Haken (Adaptive Netzverfeinerung → Tetra-Mesh)
  

> [!important]  
> Wer möchte kann noch mal die adaptive Netzverfeinerung für das Modell mit dem Haken ausprobieren.  
  
❗ Stellen Sie auf ein Tetraederförmiges Netz um, da die Adaptive Netzverfeinerung sonst nicht funktioniert: Rechtsklick auf Mesh → Insert → Method → Tetrahedrons (Geometry: All Bodies)  
  
Starten Sie mit einem Netz von 4mm und rechnen Sie solange bis das Ergebnis nur noch 1% abweicht.  
Zur Erinnerung hier die Anleitung aus dem Balken Beispiel
- 🖱️`Anleitung (P3)` ==**(**====Mechanical)== **==Adaptive Netzverfeinerung==** ==(am Beispiel des Balkens)==
    
    [http://ior.ad/7jzO](http://ior.ad/7jzO)
    
      
    
  
- `Lösung` **Adaptive Netzverfeinerung** $\sigma_{eqv,max}=787{,}9\,\mathrm{MPa}$﻿
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled.png|Untitled.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 1.png|Untitled 1.png]]
    
  
## 3.2 Beispiel Haken (Sweep/Hexa Mesh mit lokaler Netzverfeinerung)
  
Wir kennen nun den Bereich der maximalen Spannung und wollen nur dort lokale das Netz verfeinern und gleichzeitig unser Netz mit Hexaeder-Elementen behalten. Im Bild unten ist gezeigt was wir erreichen wollen. **Wir wollen in dem Bereich der maximalen Spannungen die Linieneinteilung so verändern, dass das Netz kontinuierlich kleiner wird.**
  
![[Sweep-lokal-Haken.png|Sweep-lokal-Haken.png]]
  
  

> [!important]  
> Stellen Sie wieder ein Netz mit Hexaederförmigen Elementen mit einer globalen Netzgröße von 1mm ein und verfeinern Sie das Netz im Bereich der maximalen Spannung mit Hilfe der Linieneinteilung (siehe Anleitung unten)  
  
- 🖱️`Anleitung (P3)` ==**(**====Mechanical)== **==Lokale Netzverfeinerung eines Sweep/Hexa-Mesh mit Linieneinteilung und Bias==** ==(Haken Beispiel)==
    
    [http://ior.ad/7jTb](http://ior.ad/7jTb)
    
      
    
  
- `Lösung` **Netzverfeinerung Hexa/Sweep-Mesh** $\sigma_{eqv,max}=788{,}8\,\mathrm{MPa}$﻿
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 2.png|Untitled 2.png]]
    
  
## 3.3 Beispiel Haken (Tetra Mesh mit lokaler Netzverfeinerung)
  
Als letztes wollen wir nun eine allgemeingültigere Methode zur Netzverfeinerung anschauen, da es bei komplexeren Geometrien oft nicht möglich ist durch Linieneinteilung das Netz so zu verfeinern. Dazu verwenden wir die Methode `Refinement`.
  
  

> [!important]  
> Löschen Sie nun das alte Netz und verwenden Sie eine globale Elementgröße von 1mm und verfeinern Sie das Netz auf den zwei inneren Flächen (mit dem Spannungsmaxima) mit der Methode Refinement (siehe Anleitung unten).  
  
  
- 🖱️`Anleitung (P3)` ==**(**====Mechanical)== **==Lokale Netzverfeinerung Tetra-Mesh mit Refinement auf Fläche==** ==(Haken Beispiel)==
    
    [http://ior.ad/7jTk](http://ior.ad/7jTk)
    
      
    
  
- `Lösung` **Netzverfeinerung Tetra-Mesh** $\sigma_{eqv,max}=787{,}5\,\mathrm{MPa}$﻿
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 3.png|Untitled 3.png]]
    
  
Um sich die lokale Netzverfeinerung genaue anzuschauen gibt es die Möglichkeit mit `Section Plane` die Geometrie zu schneiden. Klicken Sie dafür zunächst auf `Section Plane` (Menüleiste Home) und ziehen sie anschließend im Geometriefenster eine Linie wo Sie schneiden wollen.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 4.png|Untitled 4.png]]
  
![[Angewandte FEM (Strukturmechanik)/P3 - Vernetzung/03 Lokale Netzverfeinerung/attachments/Untitled 8.png|Angewandte FEM (Strukturmechanik)/P3 - Vernetzung/03 Lokale Netzverfeinerung/attachments/Untitled 8.png]]
Anschließend können wir nun in die Schnittebene schauen und sehen das nur auf der einen Seite leicht in die Tiefe feiner vernetzt wurde.
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 5.png|Untitled 5.png]]
Um den Schnitt wieder zu deaktivieren klicken Sie auf die `Box` im Fenster Section Planes.
Sollte das Fenster nicht vorhanden sein, können Sie dies in der **Menüleiste** im Reiter `Home` unter `Manage`
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 6.png|Untitled 6.png]]
Unter dem Punkt Section Planes aufrufen.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 7.png|Untitled 7.png]]
Das Fenster bildet oft ein Reiter zusammen mit dem Detailfenster
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 8.png|Untitled 8.png]]
## 3.4 Diskussion
  
Wir haben nun vier verschiedene Möglichkeiten aufgezeigt wie wir die Netzgröße verändern können um die Spannung richtig abzubilden.
  
1. **Sweep (Hexa Mesh) -** `**global**` **feines Netz**
    
    ==**➕ Hexa Netz kann beibehalten werden**==
    
    ➖ ==**Rechenintensiv**==
    
2. **Sweep (Hexa Mesh) -** `**lokal**` **feines Netz (**`**Linieneinteilung**`**)**
    
    ==**➕ Hexa Netz kann beibehalten werden**==
    
    ==**➖ nur bei bestimmten Geometrien möglich**==
    
3. **Adaptive Netzverfeinerung (Tetra Mesh) -** `**lokal**` **feines Netz**
    
    ==**➕ führt schnell zu einem Ergebnis (muss nicht das richtige sein)**==
    
    ==**➖ Tetraeder Netz**==
    
    ==**➖ keine Kontrolle über das Netz, lokal können Fehler auftreten (immer Ergebnis prüfen!)**==
    
4. **Flächen Netzverfeinerung mit Methode** `**Refinement**` **(Tetra Mesh) -** `**lokal**` **feines Netz**
    
    ==**➖ Tetraeder Netz**==
    
    ==➕== ==**Diese Methode funktioniert unabhängig von der Geometrie**==
    
