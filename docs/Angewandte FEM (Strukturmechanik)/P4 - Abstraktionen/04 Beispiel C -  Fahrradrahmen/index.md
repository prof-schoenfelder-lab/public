---
publish: "true"
title: 04 Beispiel C -  Fahrradrahmen
---

# Geometrie
Wir schauen uns nun den vereinfachten Fahrradrahmen im Vergleich mit `BEAM` und `SOLID` Elementen an. An diesem Beispiel können wir gut und Vor- und Nachteile der BEAM Modellierung erkennen. Zunächst schauen wir uns an wie die BEAM Abstrahierung hier erfolgt ist.
![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/04 Beispiel C -  Fahrradrahmen/attachments/Untitled 1.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/04 Beispiel C -  Fahrradrahmen/attachments/Untitled 1.png]]
Solid
![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/04 Beispiel C -  Fahrradrahmen/attachments/Untitled 2.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/04 Beispiel C -  Fahrradrahmen/attachments/Untitled 2.png]]
Beam
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled.png|Untitled.png]]
Solid (Schnittansicht) [Detail Steuerrohr]
In der Realität berühren sich die Rohre an den Außenflächen und werden dort verschweißt (Schweißnähte sind hier nicht mit modelliert). In dem `SOLID` Modell wird dies genau so abgebildet (siehe Abbildung links in der Schnittansicht des Steuerrohrs).
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 1.png|Untitled 1.png]]
Beam [Detail Steuerrohr]
  
Beim `BEAM` Modell wird jedoch nur eine Linie betrachtet und dieser ein Querschnitt gegeben. Somit wird bei der Modellierung die Mittellinien der Rohre bis zum Schnittpunkt verlängert. In dem Fall Steuerrohrs für das BEAM Modell (siehe Abbildung links) ist dies deutlich zu sehen. Es kommt somit zu einer Überschneidung der Rohre.
  
Weiterhin gibt es bei der BEAM Modellierung noch zwei Sachen zu beachten:
1. **Veränderliche Querschnitte**  
    Profile die sich über die Länge verändern (z.B. Veränderung der Wanddicke oder des Profils über das Rohr) sind nicht möglich. Sie müssten dafür die Linie teilen und für jeden Abschnitt einen eigenen Querschnitt vergeben
2. **Nicht standardisierte Profile  
    **Bei Verwendung von Profilen die nicht standardmäßig von ANSYS unterstützt werden, sind Zusatzfeatures wie die Ausgabe der Spannung auf dem Profil, nicht unterstützt.
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 2.png|Untitled 2.png]]
    
# Material
||Aluminiumlegierung  <br>( 6061 )|Stahl  <br>( 25CrMo4 )|
|---|---|---|
|Elastizitätsmodul [$\mathrm{GPa}$﻿]|69|210|
|Querkontraktion [-]|0,33|0,3|
|Streckgrenze [$\mathrm{MPa}$﻿]|250|700|
|Dichte [$\frac{kg}{m^3}$﻿]|2770|7850|
# Aufgabenstellung
  
## 1️⃣ `Beam` vs. `Solid`
Laden Sie im Opal unter `Praktikum` / `Praktikum 04 - Abstraktionen` die Geometrien des Fahrradrahmens für `Beam` ( [Fahrradrahmen_BEAM.scdoc](https://bildungsportal.sachsen.de/opal/auth/RepositoryEntry/18448121873/CourseNode/98344428551215/Praktikum%2004%20-%20Abstraktionen/2019R2_Fahrradrahmen_BEAM.scdoc) ) und `Solid` ( [Fahrradrahmen_SOLID.scdoc](https://bildungsportal.sachsen.de/opal/auth/RepositoryEntry/18448121873/CourseNode/98344428551215/Praktikum%2004%20-%20Abstraktionen/2019R2_Fahrradrahmen_SOLID.scdoc) ) runter und machen Sie jeweils eine strukturmechanische Analyse mit der [[Praktikum 2 4. Fahrradrahmen|Praktikum 2 4. Fahrradrahmen]] jeweils für Beam und für Solid. Verwenden Sie dafür die unten angegebene `Aluminiumlegierung`.
1. Vergleichen Sie die **maximale Verschiebung** für `Beam` und `Solid`
2. Vergleichen Sie die **maximale von-Mises Vergleichsspannung** für `Beam` und `Solid`
  

> [!important]  
> HinweiseAnsicht mit Profil Elementdarstellung des BEAM-Profils![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 15.png|Untitled 15.png]]BEAM Koordinatensystem in der Mitte SteuerrohrVerwenden Sie die zwei Punkte auf der Ober- und Unterseite um den Mittelpunkt des Koordinatensytems zu definieren![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 3.png|Untitled 3.png]]BEAM Spannungsdarstellung auf Profil (für Standardprofile)Im Strukturbaum Solution auswählen und im Detailfenster unter Post Processing die Beam Section Results auf Yes stellen![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 4.png|Untitled 4.png]]  
Anschließend Spannungen wie gewohnt unter Stress einfügen![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 5.png|Untitled 5.png]]  
  
  
### Lösung
- Vernetzung> [!important]  
    > Bei BEAM Elementen mit Einzellasten an den Knoten reicht bereits 1 Element über die Länge des Rohres  
    
    `BEAM`
    
    - 38 Knoten (228 Freiheitsgrade)
    
    1. Alle Linien auswählen
    2. `Insert` → `Sizing`
    3. im Detailfenster unter Type: `Number of Divisons = 1`
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 6.png|Untitled 6.png]]
    
    `SOLID`
    
    - 120345 Knoten (481380 Freiheitsgrade)
    
    globale Netzeinstellung `10mm`
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 7.png|Untitled 7.png]]
    
    lokale Netzverfeinerung im Bereich der maximalen Spannung (auf der Außenfläche der linken Kettenstrebe) `2mm`
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 8.png|Untitled 8.png]]
    
- Verschiebung
    
    `BEAM` $u_{max}=4{,}92\,\mathrm{mm}$﻿
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 9.png|Untitled 9.png]]
    
    BEAM - maximale Verschiebung
    
    `SOLID` $u_{max}=4{,}68\,\mathrm{mm}$﻿
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 10.png|Untitled 10.png]]
    
    SOLID - maximale Verschiebung
    
- Spannung> [!important]  
    > Spannungsspitzen an Schweißnähten können im BEAM Modell nicht berücksichtigt werden  
    
    `BEAM` $\sigma_{eqv,max}=60{,}6\,\mathrm{MPa}$﻿
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 11.png|Untitled 11.png]]
    
    BEAM - maximale von Mises Spannung
    
    > [!important]  
    > Das maximum nicht in der Kerbe sondern kurz davor auf der Fläche  
    
    Mit Hilfe das BEAM Tools kann zusätzlich zwischen Normal und Biegespannung unterschieden werden. Dabei sieht man, dass 44,1MPa Biegespannung und 16,4MPa Zugspannung in dem Punkt des Maximums herrschen.
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 12.png|Untitled 12.png]]
    
    maximale Normalspannung (Direct Stress)
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 13.png|Untitled 13.png]]
    
    maximale Biegespannung
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 14.png|Untitled 14.png]]
    
    maximale Biege + Normalspannung
    
    `SOLID` $\sigma_{eqv,max}=61{,}6\,\mathrm{MPa}$﻿
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 4. Beispiel C- Fahrradrahmen/attachments/Untitled 15.png|Untitled 15.png]]
    
    SOLID - maximale von Mises Spannung
    
    > [!important]  
    > Das Maximum nicht in der Kerbe sondern kurz davor auf der Fläche  
    
  
### Diskussion
Wir konnten in unserem Fall mit dem BEAM Modell mit nur 0,0003% der Knoten im Vergleich zum SOLID Modell ähnliche Ergebnisse erzeugen. Was man mit einem Beam Modell jedoch nicht abbilden kann sind Spannungsspitzen in Schweißnähten.
  
  
## 2️⃣ `Beam` : `Aluminium` vs. `Stahl`
Verwenden Sie die `Beam` Geometrie und erstellen Sie eine strukturmechanische Simulation mit den Randbedingungen der [[Praktikum 2 4. Fahrradrahmen|Praktikum 2 4. Fahrradrahmen]] für die `Aluminiumlegierung`. Berechnen Sie nun die **maximale Verschiebung** und die **maximale von-Mises Spannung** für diesen Fall
1. Erstellen Sie nun eine neue strukturmechanische Simulation mit den Randbedingungen der [[Praktikum 2 4. Fahrradrahmen|Praktikum 2 4. Fahrradrahmen]] und verwenden Sie als Werkstoff `Stahl`. Verändern Sie anschließend die Rahmenprofile so, dass Sie den gleichen Sicherheitsfaktor wie bei dem Aluminiumrahmen haben.
2. Vergleichen Sie anschließend die zwei Rahmen hinsichtlich des **Gewichts** und der **Steifigkeit**
  
  
  
## 3️⃣ `Beam` : `Herren` vs. `Damenrad`
Laden Sie im Opal unter `Praktikum` / `Praktikum 04 - Abstraktionen` das BEAM Modell des Damenrades herrunter ( [Fahrradrahmen_BEAM_Damenrad.scdoc](https://bildungsportal.sachsen.de/opal/auth/RepositoryEntry/18448121873/CourseNode/98344428551215/Praktikum%2004%20-%20Abstraktionen/Fahrradrahmen_BEAM_Damenrad.scdoc) ). Hierbei wurde der Kontaktpunkt zwischen **Oberrohr** und und **Sitzrohr** um 300mm in Richtung des Tretlagers verschoben.
1. Passen Sie das Rohrquerschnitte des Damenrads entsprechend an um auf eine analoge Steifigkeit wie beim Herrenrad zu kommen und vergleichen Sie anschließend das Gewicht.
  