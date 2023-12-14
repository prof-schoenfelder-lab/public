---
publish: "true"
title: 01 Geometrieerstellung in SpaceClaim
---

# 1 Geometrieerstellung in SpaceClaim
  
Wie bereits im ersten Praktikum erwähnt, wird bei der **Geometrieerstellung** in **SpaceClaim** diese **direkt erstellt (Direct Modeler)**. Die dafür verwendeten **Operationen** werden **nicht im Strukturbaum angezeigt** (anders wie z.B. bei CATIA).
  

> [!important]  
> Hinweis zu Start bei SpaceClaim  
Drücken Sie öfter ESC in SpaceClaim nachdem Sie die gewünschte Aktion mit einem Tool ausgeführt haben, um sicher zu stellen das sie das gewünschte Tool auch wirklich beendet zu haben.  
## 1.1 Navigation
  
**Navigation** in **SpaceClaim** ist analog zum Mechanical:
  
🔄 **Drehen**: `Mittlere Maustaste` + `Mausbewegung`
↔️ **Verschieben**: `Mittlere Maustaste` + `STR` + `Mausbewegung`
🔍 **Zoom**: `Mittlere Maustaste` + `SHIFT`+ `Mausbewegung` (oder Mausrad)
  
## 1.2 Grundoperationen zur Skizzenerstellung
  
**Allgemeine Hinweise zum Skizzenmodus**
  
- Zum **Skizze erstellen** in **Skizzenmodus wechseln**
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled.png|Untitled.png]]
- **Skizzenebene ändern** über Menüleiste im unteren Bereich des Grafikfenster
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 1.png|Untitled 1.png]]
- **Senkrechte Ansicht auf die Skizze** über Menüleiste im unteren Bereich des Grafikfenster
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 2.png|Untitled 2.png]]
- Maße durchwechseln mit `Tab`
- Zum **Beenden des Skizzenmodus** auf **3D Modus klicken**
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 3.png|Untitled 3.png]]
  
`Skizzenmodus` **Rechtecke erstellen mit Mittelpunkt als Startpunkt**

> [!important]  
> Durch die Option Define rectangle from center kann das Rechteck symmetrisch vom Mittelpunkt aus definiert werden  
  
> [!important]  
> Durch die Taste ALT kann zwischen den Modi gewechselt werden  
![[Skizze-Rechtecke.gif|Skizze-Rechtecke.gif]]
  
`Skizzenmodus` **Verrundungen / Phasen anbringen**

> [!important]  
> Phasen müssen durch die Option Chamber mode erstellt werden  
![[Skizze-Verrundung_Phase.gif|Skizze-Verrundung_Phase.gif]]
  
`Skizzenmodus` **Skizzenelemente mit** `**Move-Tool**` **bewegen**

> [!important]  
> Verschiedene Objekttypen in variabler Anzahl können im Skizzenmodus über das Move Tool bewegt werden  
  
> [!important]  
> Um die Bewegung von einem definierten Punkt aus zu referenzieren, kann ein Anchor-Punkt definiert werden  
  
> [!important]  
> Mit Ruler können Bewegungsoperationen bis zu einem definierten Abstand ausgeführt werden  
  
![[Skizze-Move-Ruler.gif|Skizze-Move-Ruler.gif]]
  
`Skizzenmodus` **Linien trimmen**

> [!important]  
> Linien können aber auch im 3D Modus wieder entfernt werden  
![[Skizze-Trim.gif|Skizze-Trim.gif]]
  
## 1.3 Grundoperationen zur 3D-Geometrieerstellung
  
Nachdem eine Skizze erstellt ist kann aus diesem 2D-Element durch das `Pull-Tool` ein 3D-Element erstellt werden
  
### 1.3.1 Pull
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 4.png|Untitled 4.png]]

> [!important]  
> Das Pull-Tool ist das vielfältigste aller Designtools.  
  
Aus Flächen können durch Extrusion (gerade oder entlang einer Linie) sowie Drehung um einer Achse 3D-Körper entstehen bzw. auch von vorhandener Geometrie abgezogen werden.  
  
An Kanten können Rundungen/Phasen angebracht werden.  
  
Die Änderung von Durchmesser zylindrischer Objekte (also auch Bohrungen).  
  
> [!important]  
> Über einen Anchor-Punkt kann der Referenzpunkt der Bewegung definiert werden.  
  
Mit der Option Ruler kann ein Abstand definiert werden.  
  
Mit der Option UpTo kann die Bewegung bis zu einem bestimmten Punkt definiert werden.  
  
`Pull-Tool` **Punkt ziehen** (Linienerstellung)

> [!important]  
> Wird ein Punkt gezogen, so entsteht eine Linie  
  
> [!important]  
> Die Richtung kann an Hand des Koordinatensystems oder geometrischen Objekten definiert werden  
![[Pull-Punkt.gif|Pull-Punkt.gif]]
  
`Pull-Tool` **Punkt ziehen mit** **`UpTo`** (Linienerstellung)

> [!important]  
> Mit UpTo können Bewegungsoperationen bis zu einem definierten Punkt ausgeführt werden  
![[Pull-Punkt-UpTo.gif|Pull-Punkt-UpTo.gif]]
  
`Pull-Tool` **Punkt ziehen mit** `**Ruler**` (Linienerstellung)

> [!important]  
> Mit Ruler können Bewegungsoperationen bis zu einem definierten Abstand ausgeführt werden  
![[Pull-Punkt-Ruler.gif|Pull-Punkt-Ruler.gif]]
  
`Pull-Tool` **Linie ziehen** (Flächenerstellung)

> [!important]  
> Wird eine Linie gezogen, so entsteht eine Fläche  
  
> [!important]  
> Mit dem drücken der Leertaste kann der Wert direkt geändert werden  
![[Pull-Linie2.gif|Pull-Linie2.gif]]
  
`Pull-Tool` **Fläche** **ziehen** (Volumenerstellung)

> [!important]  
> Wird eine Linie gezogen, so entsteht eine Fläche  
  
> [!important]  
> Mit dem drücken der Leertaste kann der Wert direkt geändert werden  
![[Pull-Flaeche.gif|Pull-Flaeche.gif]]
  
`Pull-Tool` **Fläche** **anschrägen**

> [!important]  
> Selektierte Flächen können über eine definierte Grundfläche in einem Winkel angeschrägt werden  
![[Pull-Flaeche-Draft.gif|Pull-Flaeche-Draft.gif]]
  
`Pull-Tool` **Fläche um Achse rotierten** (Volumenerstellung)

> [!important]  
> Durch Selektion der Fläche und der Rotationsachse kann ein 3D-Rotationskörper entstehen  
  
> [!important]  
> Mit dem drücken der Leertaste kann der Wert direkt geändert werden  
![[Pull-Flaeche-Rotation.gif|Pull-Flaeche-Rotation.gif]]
  
`Pull-Tool` **Fläche entlang Linien sweepen** (Volumenerstellung)

> [!important]  
> Durch Selektion der Fläche und einer vorher definierten Linie entsteht ein 3D Körper  
![[Pull-Flaeche-Sweep.gif|Pull-Flaeche-Sweep.gif]]
  
`Pull-Tool` **Körper skalieren**

> [!important]  
> Selektierte Körper können durch Angabe des Referenzpunktes skaliert werden  
![[Pull-Scale-Body.gif|Pull-Scale-Body.gif]]
  
`Pull-Tool` **3D** **Kantenverrundung an einzelnen Kanten**

> [!important]  
> Selektierte Kanten können das Ziehen verrundet werden  
![[Pull-3D-Radien-Einzelln.gif|Pull-3D-Radien-Einzelln.gif]]
  
`Pull-Tool` **3D** **Kantenverrundung an allen Kanten einer Fläche**

> [!important]  
> Durch Doppelklick auf eine Linie werden alle der Fläche zugehörigen Linien ausgewählt. Durch Wiederholung des Doppelklick werden alle weiteren "Linien-Flächen" ausgewählt.  
  
> [!important]  
> Anschließend können die selektierten Kanten durch ziehen verrundet werden  
![[Pull-3D-Radien-AlleKanten.gif|Pull-3D-Radien-AlleKanten.gif]]
  
  
`Pull-Tool` **3D** **Kantenphase an einzelnen Kanten**

> [!important]  
> Selektierte Kanten können durch Einstellen der Option Chamber und anschließendem Ziehen zur Phase definiert werden  
![[Pull-3D-Phase.gif|Pull-3D-Phase.gif]]
  
`Pull-Tool` **Taschen/Bohrungen** erstellen (Geometrie ausschneiden)

> [!important]  
> Durch das ziehen von Flächen in ein Volumen hinein, wird dieses von dem anderen entfernt (z.B. für Bohrungen)  
![[Pull-3D-Cut.gif|Pull-3D-Cut.gif]]
  
`Pull-Tool` **Bohrung-/Zylinderdurchmesser ändern**

> [!important]  
> Durch das Anklicken von Mantelflächen (Bohrungen/Zylinder) können diese im Wert geändert werden  
![[Pull-3D-BohrungRadius.gif|Pull-3D-BohrungRadius.gif]]
  
### 1.3.2 Move
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 5.png|Untitled 5.png]]

> [!important]  
> Das Move-Tool dient der Bewegung/Rotation aller geometrischen Objekte (Punkte, Linien, Flächen und Volumen).  
  
  
  
> [!important]  
> Über einen Anchor-Punkt kann der Referenzpunkt der Bewegung definiert werden.  
  
Mit der Option Ruler kann ein Abstand definiert werden.  
  
Mit der Option UpTo kann die Bewegung bis zu einem bestimmten Punkt definiert werden.  
  
`Move-Tool` Bewegung eines Körpers mit `Anchor`-Punkt und `Ruler`

> [!important]  
> Standardmäßig wird der Schwerpunkt als Referenzpunkt für die Bewegung definiert, dies kann durch den Anchor Punkt geändert werden  
  
> [!important]  
> Durch Anklicken der Bewegungsrichtung kann anschließend der Betrag definiert werden bzw. mit den Optionen Ruler bzw. UpTo noch anders definiert werden.  
![[Move-3D-Anchor-Ruler.gif|Move-3D-Anchor-Ruler.gif]]
  
  
`Move-Tool` Bewegung eines Punktes und einer Linie mit `Ruler`
![[Move-3D-Linie-Point.gif|Move-3D-Linie-Point.gif]]
  
`Move-Tool` **Bewegung einer Fläche mit schräger Nachbarsfläche** (Beibehaltung des Winkels)

> [!important]  
> Das Bewegen einer Fläche mit einer schrägen Nachbarfläche antizipiert, dass der Winkel der Schräge weiterhin beibehalten werden soll.  
![[Move-3D-Flaeche.gif|Move-3D-Flaeche.gif]]
  
`Move-Tool` **Bewegung aller Linien zu einer Fläche** mit schräger Nachbarsfläche

> [!important]  
> Werden nur die Linien der Fläche selektiert (Doppelklick auf die Linien), so verändert sich der Winkel der schrägen Nachbarsfläche.  
![[Move-3D-Flaechelinien.gif|Move-3D-Flaechelinien.gif]]
  

> [!important]  
> Wie kann nun die Fläche als Quader extrudiert werden?  
  
> [!important]  
> Dafür benötigen wir wieder das Pull-Tool !  
  
⚠️ ==**Einschub**== ⚠️**`Pull`**`-Tool` **Fläche ziehen unabhängig** von schrägen Nachbarsflächen

> [!important]  
> Soll die Fläche unabhängig von den Nachbarsflächen gezogen werden, so muss neben der Fläche auch die Linie markiert werden.  
![[Pull-senkrecht-mit-schraegen-Flaechen.gif|Pull-senkrecht-mit-schraegen-Flaechen.gif]]
  
### 1.3.3 Fill
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 6.png|Untitled 6.png]]
  

> [!important]  
> Das Fill-Tool dient dem auffüllen von Geometrie an Verrundungen/Phasen Bohrungen/Taschen sowie der Weiterführung einer Geometrie zu einem Endpunkt.  
  
> [!important]  
> Viele Aktionen die mit dem Fill-Tool erledigt werden, können ebenfalls durch die Taste del (Entfernen auf der Tastatur) ausgeführt werden  
  
`Fill-Tool` **Fortführung von Geometrie**

> [!important]  
> Geometrien die auf einen bestimmten Endpunkt zulaufen können bis dahin gezogen werden  
![[Fill-1.gif|Fill-1.gif]]
  
`Fill-Tool` **Entfernen von Verrundungen/Phasen sowie Bohrungen/Taschen**

> [!important]  
> Das gleiche kann durch die Taste del (Entfernen auf der Tastatur) ausgeführt werden  
![[Fill-2.gif|Fill-2.gif]]
  
  
### 1.3.4 Blend
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 7.png|Untitled 7.png]]
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 8.png|Untitled 8.png]]

> [!important]  
> Das Blend Tool dient der Erstellung eines Übergangs zwischen zwei Geometrien (Flächen, Kanten bzw Kurven)  
  
`Blend Tool` **Übergang zwischen zwei Flächen** (Volumenerstellung)
![[Blend.gif|Blend.gif]]
## 1.4 Sonstiges Hinweise
### 1.4.1 Mehrere Körper erstellen
  
![[Pull-AutoMerge.gif|Pull-AutoMerge.gif]]
Beim ziehen einer Fläche, die Kontakt zu bereits vorhandener Geometrie hat, wird die neue Geometrie automatisch mit der vorhandenen Geometrie vereinigt.

> [!important]  
> Es wird also kein zweiter Körper erzeugt  
  
  
Nachfolgend sollen nun vier Varianten gezeigt werden, wie ein zweiter Körper erstellt werden kann:
  
`zweiten Körper erstellen` **Variante 1:** `**Pull**` **mit** `**No Merge**`

> [!important]  
> Bei der Pull Operation muss die Option No merge eingestellt werden  
![[Pull-NoMerge.gif|Pull-NoMerge.gif]]
  
`zweiten Körper erstellen` **Variante 2: Einteilung in Komponenten**

> [!important]  
> Im Strukturbaum muss die vorhandene Geometrie und die zu ziehende Fläche jeweils eine eigene Komponente bekommen  
![[Pull-Komponenten.gif|Pull-Komponenten.gif]]
  
`zweiten Körper erstellen` **Variante 3: Körper teilen mit** `**Plane**` **und** `**Split Body**`

> [!important]  
> Durch das erstellen einer Ebene (Plane) und Verschiebung in die gewünschte Tiefe kann anschließend mit Split Body der Körper durch die Ebene geteilt werden  
![[Split-3D-Plane.gif|Split-3D-Plane.gif]]
  
`zweiten Körper erstellen` **Variante 4: Körper teilen mit** `**Face Split**` **und** `**Pull mit der Option Cut**`

> [!important]  
> Die Fläche kann mittels Face Split geteilt werden  
  
> [!important]  
> Anschließend kann die neuentstandene Linie mit dem Pull Tool und der Option Cut in den Körper gezogen werden, wodurch ein zweiter Körper entsteht  
![[Split-SplitPlane-PullCut.gif|Split-SplitPlane-PullCut.gif]]
  
  
### 1.4.3 Planes
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 9.png|Untitled 9.png]]
Für **Skizzen** oder zum **Schneiden** von Geometrien ist es manchmal notwendig eine **Ebene** zu erzeugen. Dies kann über das `Plane` Tool erfolgen.
### 1.4.3 Symmetrie & Wiederholungen
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 10.png|Untitled 10.png]]
Zur Ausnutzung von **Spiegelsymmetrie** kann `Mirror` verwendet werden. Dabei muss zuerst die Symmetrieebene und anschließend die Geometrie ausgewählt werden
  
  
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 11.png|Untitled 11.png]]
Zur Verwendung von **Musterwiederholungen** gibt es ebenfalls verschiedene Tools
### 1.4.4 Named Selections
  
Sogenannte `Named Selections` sind eine selbstdefinierte Zusammenfassung geometrischer Objekte. Sie können im ==**Mechanical**== z.B. für **Vernetzungen** oder **Randbedingungen** verwendet werden.
  
`Named Selections` Erstellung
1. `Select Modus` aktivieren
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 12.png|Untitled 12.png]]
    
2. Geometrien auswählen (Linien, Flächen oder Körper)
3. Reiter `Groups` auswählen
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 13.png|Untitled 13.png]]
    
4. `Create NS` klicken und Namen vergeben
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 14.png|Untitled 14.png]]
    
### 1.4.5 Suppress/Activate for Physics
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Untitled 15.png|Untitled 15.png]]
Sollen Körper für die Bearbeitung im ==**Mechanical**== unterdrückt werden, so ist dies **im Strukturbaum** mit `Rechtsklick` auf die **Geometrie** und `Suppress for Physics` zu definieren.
  
  
## 1.5 Geometrieaufbereitung
  
**Aufgaben der Geometrieaufbereitung:**
- Vereinfachung der Geometrie zur besseren Vernetzung
    - **Entfernen** von nicht tragenden Bauteilen
    - **Entfernen** `Bohrungen` / `Phasen` / `Radien` / `Nuten` in unkritischen Bereichen
- Bauteile zusammenführen
    - Übergänge zwischen Bauteilen erstellen ( Kraftschluss herstellen )
    - ggf. Radien anbringen (z.B. Schweißnähte) → (falls Spannungsauswertung in diesem Bereich interessant)
    
Neben der Geometrieerstellung ist SpaceClaim besonders geeignet Geometrien von anderen CAD-Tools wie Catia zu importieren und diese aufzubereiten. Ziel da ist es, **Details die kleiner sind als das gewünschte Netz** und **außerhalb des als relevant betrachteten Bereichs liegen zu entfernen**. Dies können zum Beispiel Radien oder Taschen niedriger Dicke sein. Weiterhin gibt es Möglichkeiten Fehlerhafte Geometrie z.B. fehlende Fläche zu füllen.
  
Besonders nützlich erweist sich dabei die Selektionsfunktion von SpaceClaim die nach analogen Geometrien suchen lässt. Im nachfolgenden Beispiel wurden zum Beispiel alle Flächen mit gleichem Flächeninhalt selektiert und mit der Taste `DEL` (oder Alternativ der Funktion `Fill`) entfernt.
![[SpaceClaim_MultiSelect_delete.gif|SpaceClaim_MultiSelect_delete.gif]]
  
Durch eine einfache Selektion von Flächen mit der Taste `DEL` können so einfach Geometrien aufgefüllt werden.
![[SpaceClaim_Delete_Fill.gif|SpaceClaim_Delete_Fill.gif]]
  

> [!important]  
> Öffnen Sie die Datei "Modellaufbereitung.stp" in SpaceClaim und entfernen sie alle kleinen Radien und Taschen.  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 2- Geometrieerstellung und Randbedingungen/Praktikum 2 1. Geometrieerstellung in SpaceClaim/attachments/Modellaufbereitung.stp|Modellaufbereitung.stp]]

> [!important]  
> Die Datei finden Sie im OPAL und können Sie über  
  
Um nur eine Geometrie zu bearbeiten, fügen Sie für jede neue Geometrieerstellung eine neue Komponente `Geometry` hinzu, die Sie später mit einer Analyse verknüpfen können.

> [!important]  
> Es empfiehlt sich die Geometrien untereinander zu ordnen, weil rechts daneben dann die Analysen hinzufügen werden.  
  
![[Workbench_zweiteGeometrie.gif|Workbench_zweiteGeometrie.gif]]
  
Weitere Übungsbeispiele zur Geometrieerstellung finden Sie im nächsten Abschnitt.
  
◀️ [[P2 - Geometrieerstellung und Randbedingungen|P2 - Geometrieerstellung und Randbedingungen]]
  
[[Praktikum 2 2. Beispiele zur Geometrieerstellung|Praktikum 2 2. Beispiele zur Geometrieerstellung]] ➡️
  
  
==Praktikum erstellt von:== Felix Kaule======Links:== [[❓FAQ|❓FAQ]]
  
==Hochschule für Technik, Wirtschaft und Kultur Leipzig  
Fakultät Ingenieurwissenschaften  
Karl-Liebknecht-Str. 134  
04277 Leipzig==