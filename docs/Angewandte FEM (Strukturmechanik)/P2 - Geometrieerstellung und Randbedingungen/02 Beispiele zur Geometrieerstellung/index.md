---
publish: "true"
title: 02 Beispiele zur Geometrieerstellung
---

# 2. Beispiele zur Geometrieerstellung

> [!important]  
> Legen Sie im Datenlaufwerk D:\ ein Ordner an und speichern Sie Ihr Projekt zum zweiten Praktikum dort.  
  
Wir wollen nun die zuvor gesehen Methoden zur Geometrieerstellung in SpaceClaim an ein paar Beispielen anwenden. Falls Sie nicht weiter kommen sind für die komplexeren Geometrien Nachklick-Anleitungen vorhanden, die einen möglichen Lösungsweg aufzeigen.
  
Fügen Sie für jede neue Geometrieerstellung eine neue Komponente `Geometry` hinzu, die Sie später mit einer Analyse verknüpfen können.

> [!important]  
> Es empfiehlt sich die Geometrien untereinander zu ordnen, weil rechts daneben dann die Analysen hinzufügen werden.  
  
![[WorkbenchMenu-GeometrieKomponente.gif|WorkbenchMenu-GeometrieKomponente.gif]]
## 2.1 Balken
![[Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/02 Beispiele zur Geometrieerstellung/attachments/Untitled.png|Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/02 Beispiele zur Geometrieerstellung/attachments/Untitled.png]]

> [!important]  
> Erstellen Sie die Geometrie "Balken" mit den oben angegeben Maßen in SpaceClaim.  
  
### Vernetzung
1. Netzgröße auf `1mm` stellen
  
## 2.2 Box
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 2. Beispiele zur Geometrieerstellung/attachments/Untitled.png|Untitled.png]]

> [!important]  
> Erstellen Sie die Geometrie "Box" mit den oben angegeben Maßen in SpaceClaim. Konstruieren Sie das Modell in der gleiche Ebene und Richtung um später in den Randbedingungen die gleichen Koordinaten verwenden zu können.  
### Hinweise
- Um eine **bessere Vernetzung zu generieren**, wird empfohlen zwei Körper zu erstellen (Wände und Unterteil)
  
## 2.3 Verschraubung
![[Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/02 Beispiele zur Geometrieerstellung/attachments/Untitled 1.png|Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/02 Beispiele zur Geometrieerstellung/attachments/Untitled 1.png]]

> [!important]  
> Erstellen Sie die Geometrie "Verschraubung" mit den oben angegeben Maßen in SpaceClaim.  
  
Wenn Sie nicht weiterkommen finden Sie weiter unten ein Tutorial wo alle Abläufe dargestellt sind.  
### Hinweise
- **Skizze auf z-x Ebene**:  
    Rechteck mittig ausrichten über `Define rectangle from center`
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 2. Beispiele zur Geometrieerstellung/attachments/Untitled 1.png|Untitled 1.png]]
---
- **Extrudieren in beide Richtungen gleichzeitig**:  
    Beim `Pull` Operation `Pull in Both Sides` auswählen
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 2. Beispiele zur Geometrieerstellung/attachments/Untitled 2.png|Untitled 2.png]]
---
- **Erstellung von zwei Körpern**:  
    Wenn Schraube modelliert wird auf `No merge` klicken damit zwei Extra Körper erstellt werden
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 2. Beispiele zur Geometrieerstellung/attachments/Untitled 3.png|Untitled 3.png]]
  
---
- **Damit sich beide Körper das gleiche Netz teilen:**  
    `Design` im Strukturbaum auswählen → unter `Properties` → `Share Topology` → `Share`
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 2. Beispiele zur Geometrieerstellung/attachments/Untitled 4.png|Untitled 4.png]]
  
- 🖱️`Anleitung (P2)` ==**(**====SpaceClaim) Geometrie "==**==Verschraubung"==** ==erstellen (3D)==
    
    [http://ior.ad/7ipk](http://ior.ad/7ipk)
    
  
  
  
## 2.3 Bimetall
![[Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/02 Beispiele zur Geometrieerstellung/attachments/Untitled 3.png|Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/02 Beispiele zur Geometrieerstellung/attachments/Untitled 3.png]]

> [!important]  
> Erstellen Sie die Geometrie "Bimetall" mit den oben angegeben Maßen in SpaceClaim.  
### Hinweise
- **Erstellung von zwei Körpern**:  
    Wenn zweiter Körper erstellt wird, beim der `Pull` Operation die Option `No Merge` aktivieren
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 2. Beispiele zur Geometrieerstellung/attachments/Untitled 3.png|Untitled 3.png]]
  
- **Damit sich beide Körper das gleiche Netz teilen:**  
    `Design` im Strukturbaum auswählen → unter `Properties` → `Share Topology` → `Share`
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 2. Beispiele zur Geometrieerstellung/attachments/Untitled 4.png|Untitled 4.png]]
  
  
## 2.4 Flansch
![[Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/02 Beispiele zur Geometrieerstellung/attachments/Untitled 2.png|Angewandte FEM (Strukturmechanik)/P2 - Geometrieerstellung und Randbedingungen/02 Beispiele zur Geometrieerstellung/attachments/Untitled 2.png]]

> [!important]  
> Erstellen Sie die Geometrie "Flansch" mit den oben angegeben Maßen in SpaceClaim.  
  
Wenn Sie nicht weiterkommen finden Sie weiter unten ein Tutorial wo alle Abläufe dargestellt sind.  
- 🖱️`Anleitung (P2)` ==**(**====SpaceClaim) Geometrie "==**==Flansch==**=="== ==erstellen (3D)==
    
    [http://ior.ad/7ipX](http://ior.ad/7ipX)
    
## 2.5 Drehmechanismus
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 2. Beispiele zur Geometrieerstellung/attachments/Untitled 5.png|Untitled 5.png]]

> [!important]  
> Erstellen Sie die Geometrie "Drehmechanismus" mit den oben angegeben Maßen in SpaceClaim.  
  
Verwenden Sie dafür die Komponente Geometry im Workbench Projekmenü.  
  
  
Im nachfolgenden Abschnitt beschäftigen wir uns mit den Randbedingungen.
  
◀️ [[P2 - Geometrieerstellung und Randbedingungen|P2 - Geometrieerstellung und Randbedingungen]]
  
[[Praktikum 2 3. Randbedingungen|Praktikum 2 3. Randbedingungen]] ➡️
  
  
==Praktikum erstellt von:== Felix Kaule======Links:== [[❓FAQ|❓FAQ]]
  
==Hochschule für Technik, Wirtschaft und Kultur Leipzig  
Fakultät Ingenieurwissenschaften  
Karl-Liebknecht-Str. 134  
04277 Leipzig==