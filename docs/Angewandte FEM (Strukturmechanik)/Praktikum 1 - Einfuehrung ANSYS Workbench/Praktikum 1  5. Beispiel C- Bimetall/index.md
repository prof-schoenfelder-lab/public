---
publish: "true"
title: Praktikum 1  5. Beispiel C- Bimetall
---


# 5. Beispiel C: Bimetall
  
Nun wollen wir uns noch mal mit einem Beispiel beschäftigen wo wir zwei Materialien und eine neue Randbedingung (thermische Last) kennenlernen.
## 5. 1. **Aufgabenstellung**
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/BeispielC_Aufgabenstellung.png|BeispielC_Aufgabenstellung.png]]
  
### 5. 1. 1. ==Gegeben==
  
==**Material**==
**Kupfer**
- Elastizitätsmodul $E=110\,\mathrm{GPa}$﻿
- Querkontraktionszahl $\nu=0{,}34$﻿
- Temperaturausdehnungskoeffizient $\alpha=1{,}8\cdot10^{-5}\frac{1}{K}$﻿
**Stahl**
- Elastizitätsmodul $E=200\,\mathrm{GPa}$﻿
- Querkontraktionszahl $\nu=0{,}3$﻿
- Temperaturausdehnungskoeffizient $\alpha=1{,}2\cdot10^{-5}\frac{1}{K}$﻿
==**Geometrie**==
**Balken mit rechteckigem Querschnitt**
- Länge ==$L=50\,\mathrm{mm}$==﻿
- Breite ==$b=10\,\mathrm{mm}$==﻿
- Breite ==$h=1\mathrm{mm}$==﻿
==**Randbedingungen**==
- feste Einspannung auf der linken Seite (y=0)
- Temperaturgradient von ==$\Delta T=80\,\mathrm{K}$==﻿
  
### 5. 1. 2. ==Gesucht==
  
1. Die maximale Durchbiegung $u_{max}$﻿
  
## 5. 2. Lösung
  
### 5. 2. 1. Analyse hinzufügen
  

> [!important]  
> Fügen Sie eine Strukturmechanische Analyse (Static Structural) in ANSYS Workbench hinzu  
  
### 5. 2. 2. ==Materialdefinition (Workbench)==
  

> [!important]  
> Verwenden Sie dieses Mal die vorgefertigten Materialien Copper Alloy und Structural Steel (standardmäßig dabei) aus der Materialdatenbank 📚 General Materials  
  
  
### 5. 2. 3. ==Geometrieerstellung (SpaceClaim)==
  

> [!important]  
> Erstellen Sie die Geometrie in ANSYS SpaceClaim mit Hilfe der zwei nachfolgenden Hinweise.  
  
> [!important]  
> Zeichen Sie die zwei Skizzen für die jeweiligen Querschnitte und ziehen Sie diese einzeln mit dem Pull Werkzeug in die gewünschte Länge.  
  
Bevor Sie den zweiten Querschnitt ziehen müssen Sie die Option 🚫No Merge aktivieren, da ansonsten ein großer Körper entsteht und nicht zwei.  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled.png|Untitled.png]]
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 1.png|Untitled 1.png]]

> [!important]  
> Am Ende müssen Sie Design1* im Strukturbaum von SpaceClaim auswählen und unter Properties bei Share Topology → Share einstellen.  
  
Dies bewirkt, dass die Flächen an denen sich beide Körper berühren die gleiche ist. Würde dies nicht eingestellt werden, würde ANSYS Mechanical automatisch einen Kontakt generieren.  
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 2.png|Untitled 2.png]]
    
  
### 5. 2. 5. ==Materialzuweisung & Modelleinstellung (Mechanical)==
  

> [!important]  
> Weisen Sie dem in z-Richtung oberen Geometrie das Material Structural Steel zu und dem unteren Copper Alloy  

> [!important]  
> Zur besseren Wiedererkennung können Sie im Strukturbaum unter Geometry → SYS-3 die beiden Körper nach den verwendeten Materialien mit F2 benennen.  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 3.png|Untitled 3.png]]
  
**Anleitung aus dem ersten Beispiel:**
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[CleanShot_2022-10-14_at_10.02.332x.png|CleanShot_2022-10-14_at_10.02.332x.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 4.png|Untitled 4.png]]
    
  
### 5. 2. 6. ==Vernetzung (Mechanical)==
  

> [!important]  
> Vernetzen Sie das Bauteil mit den Standardeigenschaften.  
  
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 5.png|Untitled 5.png]]
    
  
### 5. 2. 7. ==Randbedingungen (Mechanical)==
  

> [!important]  
> Bringen Sie eine feste Einspannung auf der linken Seite (y=0) an.  
  
  

> [!important]  
> Bringen eine thermische Randbedingung ein, dass ein Temperaturgradient von 80K entsteht.  
  
[https://scribehow.com/embed/ANSYS_Mechanical__Temperaturdifferenz_als_Randbedingung__MtO5jtK-TAyXr6lONONbZg?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Mechanical__Temperaturdifferenz_als_Randbedingung__MtO5jtK-TAyXr6lONONbZg?skipIntro=true&removeLogo=true)
  
- 🔁 **Ergebnis zum Vergleich**:
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 6.png|Untitled 6.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 7.png|Untitled 7.png]]
    
    ![[CleanShot_2022-10-14_at_10.26.022x.png|CleanShot_2022-10-14_at_10.26.022x.png]]
    
    ![[CleanShot_2022-10-14_at_10.25.442x.png|CleanShot_2022-10-14_at_10.25.442x.png]]
    
### 5. 2. 8. ==Lösungseinstellungen (Mechanical)==
  

> [!important]  
> Lösen Sie das Gleichungssystem.  
  
### 5. 2. 9. ==Lösungsdarstellung (Mechanical)==
  

> [!important]  
> Ermitteln Sie die maximale Durchbiegung  
  
Die maximale Verschiebung beträgt 0,47mm:
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 8.png|Untitled 8.png]]
  

> [!important]  
> In der Simulation werden häufig Verschiebungen skaliert dargestellt um sich besser vorzustellen wie sich ein Körper verformt.  
  
Hier ist dies in der Legende angezeigt (Deformation Scale Factor) mit dem automatisch berechneten Wert von 5,5  
  
  
Durch Rechtsklick auf den Titelbereich links oben im Grafikfenster können wir unter `Deformation Scale Factor` den Faktor einblenden um den die Verschiebung skaliert wurde.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 9.png|Untitled 9.png]]
  
---
  
Im Symbolmenü oben im Reiter `Result` kann dieser **Skalierungsfaktor** eingestellt werden.
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 10.png|Untitled 10.png]]
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 11.png|Untitled 11.png]]
  
---
  
Durch den Klick auf die positive x-Achse im Grafikmenü gelangen wir zur Seitenansicht
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 12.png|Untitled 12.png]]
  

> [!important]  
> Stellen Sie die Durchbiegung ohne eine überhöhe Skalierung dar.  
  
Die reale Verformung bekommt man dann mit dem Wert = 1 :
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 5. Beispiel C- Bimetall/attachments/Untitled 13.png|Untitled 13.png]]
  
## Diskussion
  
Falls Sie eine analytische Lösung zu dem Problem finden könnten Sie beurteilen ob die Simulation stimmt. Manchmal findet man auch Experimente mit allen Daten die man nachrechnen kann um zu schauen ob die Simulation richtig rechnet.
