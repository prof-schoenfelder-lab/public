---
publish: "true"
title: 06 Beispiel D- Lenker
---


# 6. Beispiel C: Lenker
  
Als letztes Beispiel wollen wir uns nun mit einer importierten Geometrie eines Fahrradlenkers beschäftigen.
## 6. 1. **Aufgabenstellung**
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled.png|Untitled.png]]
### 6. 1. 1. ==Gegeben==
  
==**Material**==
**Stahl**
- Elastizitätsmodul $E=200\,\mathrm{GPa}$﻿
- Querkontraktionszahl $\nu=0{,}3$﻿
- Temperaturausdehnungskoeffizient $\alpha=1{,}2\cdot10^{-5}\frac{1}{K}$﻿
==**Randbedingungen**==
- feste Einspannung im mittleren Teil
- jeweils auf die Auflagerpunkte
    - Kraft in Fahrtrichtung ==$F_z=-200\,\mathrm{N}$==﻿
    - Kraft in Bodenrichtung ==$F_y=-200\,\mathrm{N}$==﻿
  
### 6. 1. 2. ==Gesucht==
  
1. Die maximale Durchbiegung $u_{max}$﻿
2. Die maximale Vergleichsspannung (von Mises) $\sigma_{v}$﻿
  
## 6. 2. Lösung
  
### 6. 2. 1. Analyse hinzufügen
  

> [!important]  
> Fügen Sie eine Strukturmechanische Analyse (Static Structural) in ANSYS Workbench hinzu  
  
### 6. 2. 2. ==Materialdefinition (Workbench)==
  

> [!important]  
> Verwenden Sie dieses Mal die vorgefertigten Materialien Structural Steel (standardmäßig dabei)  
  
### 6. 2. 3. ==Geometrieerstellung (SpaceClaim)==
  

> [!important]  
> Importieren Sie die Geometrie "Lenker.scdoc"  
  
(Alternativ im OPAL:  
Praktikum → Praktikum 01 … →)  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Lenker.scdoc|Lenker.scdoc]]
  
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 1.png|Untitled 1.png]]
**Importieren einer Geometrie:**
==**Workbench Projektmenü**==: **Rechtsklick** auf `Geometry` → `Import Geometry` → `Browse`
  
### 6. 2. 5. ==Materialzuweisung & Modelleinstellung (Mechanical)==
  

> [!important]  
> Weisen Sie dem Lenker das Material Structural Steel zu  
  
> [!important]  
> Sie können im Strukturbaum auch mehrere Geometrien auswählen und im Detailfenster die Materialeigenschaften dadurch für alle gleichzeitig ändern  
  
### 6. 2. 6. ==Vernetzung (Mechanical)==
  

> [!important]  
> Vernetzen Sie das Bauteil mit den Standardeigenschaften.  
  
  
Auf den ersten Blick sieht die Vernetzung ganz gut aus, aber wenn man sich den **Rohrquerschnitt** anschaut, so sieht man dort einige Unregelmäßigkeiten.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 2.png|Untitled 2.png]]
  
- **Anleitung zur Erstellung eines besseren Netzes**
    1. Linienauswahltool wählen
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 3.png|Untitled 3.png]]
        
          
        
    2. Mit `STR` + `A` alle Linien auswählen (dies sind alle Querschnittslinien des Rohres)
        
          
        
    3. Im **Strukturbaum:** `**Rechtsklick**` auf `Mesh` → `Insert` → `Sizing`
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 4.png|Untitled 4.png]]
        
          
        
    4. Im **Detailfenster** von "Edge Sizing": `Type` auf `Number of Divisions` stellen
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 5.png|Untitled 5.png]]
        
          
        
    5. Im **Detailfenster** von "Edge Sizing": `Number of Divisions` auf `10` stellen
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 6.png|Untitled 6.png]]
        
          
        
    6. Im **Strukturbaum:** `**Rechtsklick**` auf `Mesh` → `Generate Mesh`
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 7.png|Untitled 7.png]]
        
          
        
  
So sieht das Ergebnis nach unserer Netzveränderung aus:
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 8.png|Untitled 8.png]]
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 9.png|Untitled 9.png]]
### 6. 2. 7. ==Randbedingungen (Mechanical)==
  

> [!important]  
> Bringen Sie eine feste Einspannung auf der Mantelfläche des Mittelteils an  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 10.png|Untitled 10.png]]
  

> [!important]  
> Bringen Kraft auf die Linke Seite an  
- Kraft in Fahrtrichtung ==$F_z=-200\,\mathrm{N}$==﻿
- Kraft in Bodenrichtung ==$F_y=-200\,\mathrm{N}$==﻿
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 11.png|Untitled 11.png]]

> [!important]  
> Bringen Kraft auf die rechte Seite an  
- Kraft in Fahrtrichtung ==$F_z=-200\,\mathrm{N}$==﻿
- Kraft in Bodenrichtung ==$F_y=-200\,\mathrm{N}$==﻿
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 12.png|Untitled 12.png]]
  

> [!important]  
> Wenn Sie beide Mantelflächen gleichzeitig auswählen und mit nur einer Kraft-Randbedingung anbringen, so teilt sich die Kraft die Sie angeben automatisch gleichmäßig auf beide Flächen auf.  
  
Würden Sie also jeweils den Wert von 200 eintragen, kämen bei jeder Mantelfläche nur 100N an.  
  
  
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 13.png|Untitled 13.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 14.png|Untitled 14.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 15.png|Untitled 15.png]]
    
### 6. 2. 8. ==Lösungseinstellungen (Mechanical)==
  

> [!important]  
> Lösen Sie das Gleichungssystem.  
  
### 6. 2. 9. ==Lösungsdarstellung (Mechanical)==
  

> [!important]  
> Ermitteln Sie die maximale Durchbiegung.  
  
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 16.png|Untitled 16.png]]
    
    $u_{max}=3{,}3\,\mathrm{mm}$﻿
    
  
  

> [!important]  
> Ermitteln Sie die maximale von-Mises Vergleichsspannung.  
  
> [!important]  
> Die von-Mises Vergleichsspannung finden Sie unter: Rechtsklick Solution → Insert → Stress → Equivalent (von-Mises)  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 17.png|Untitled 17.png]]
  
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 18.png|Untitled 18.png]]
    
    $\sigma_{v,Max}=167{,}2\,\mathrm{MPa}$﻿
    
  
  
## 6. 3. Diskussion
  

> [!important]  
> Wie können wir nun überprüfen ob die Ergebnisse aus unserer Simulation stimmen, wenn wir keine einfache analytische Lösung haben?  
  
Dafür gibt es grundsätzlich zwei Ansätze der ==**Verifikation**== und der ==**Validierung**==
  
**==Verifikation==**: **Rechne ich richtig?**
- Hier werden Fehler im Programm/Algorithmus betrachtet. > [!important]  
    > Wir gehen davon aus, dass ANSYS als kommerzielles Produkt ohne Fehler ausgeliefert wird.  
    
- Weiterhin soll geprüft werden, ob die Diskreditierungen (also die Vernetzung) gut genug ist?> [!important]  
    > Dazu müssten wir eine Konvergenzanalyse durchführen. Wir verfeinern das Netz also solange, bis sich das Ergebnis nicht mehr signifikant ändert.  
    
  
Ein Hilfsmittel zur Verifikation ist die Checkliste die wir bereits schon kennengelernt haben
  
**==Validierung==**: **Berechne ich das Richtige?**
- Bei der Validierung betrachten wir hier vor allem den Abgleich mit der Realität, also einem Experiment bzw. einer Messung.
➡️ **VERGLEICH mit EXPERIMENT / MESSUNG**
- Wenn wir jetzt also den gleichen Fahrradlenker hätten mit einem entsprechenden Labor, könnten wir innerhalb eines Experimentes mit Hilfe von verschiedenen Messmethoden z.B. Verschiebungen, Dehnungen oder Kräfte messen.
  
  
Wir müssen uns also zunächst auf die **Konvergenzanalyse** beschränken. Wir können nun unser Netz über den Parameter `Number of Divisions` ([[Praktikum 1 6. Beispiel D- Lenker|Praktikum 1 6. Beispiel D- Lenker]]) unser Netz solange verfeinern und überprüfen wie sich unsere Ergebnisse verändern.
  
==**Edge Sizing = 10**==
$u_{max}=3{,}34\,\mathrm{mm}$﻿
$\sigma_{v,Max}=167{,}2\,\mathrm{MPa}$﻿
==**Edge Sizing = 20**==
$u_{max}=3{,}36\,\mathrm{mm}$﻿
$\sigma_{v,Max}=147{,}99\,\mathrm{MPa}$﻿
==**Edge Sizing = 40**==
$u_{max}=3{,}36\,\mathrm{mm}$﻿
$\sigma_{v,Max}=144{,}45\,\mathrm{MPa}$﻿
==**Edge Sizing = 50**==
$u_{max}=3{,}36\,\mathrm{mm}$﻿
$\sigma_{v,Max}=144{,}59\,\mathrm{MPa}$﻿
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 19.png|Untitled 19.png]]
`Number of Divisions = 10`
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 20.png|Untitled 20.png]]
`Number of Divisions = 50`
