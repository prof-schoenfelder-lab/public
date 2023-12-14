---
publish: "true"
title: 01 Einleitung
---

# Versagenskriterium
  
In Prüfversuchen zur Bestimmung von Materialkennwerten werden Bauteile z.B. im Zugversuch nur in einer Richtung belastet. In der Realität haben Bauteile aber Spannungen in alle Raumrichtung (Spannungstensor).
  

> [!important]  
> Welche Spannung muss ich also auswerten um Sie mit meinem Werkstoffkennwert zu vergleichen?  
  
Das hängt vom Werkstoff und dem **Versagenskriterium** ab:
- **Stahl** / **Aluminium** und viele andere Metalle brechen `duktil`. Bevor das Bauteil also komplett versagt (Bruch) treten **plastischen Verformungen** auf. Der plastische Anteil wird durch den Deviatorischen Anteil des Spannungstensors bestimmt. Die `von Mises Vergleichsspannung` berücksichtigt genau diesen Anteil und ist deshalb die Spannung die zum Vergleich mit dem Werkstoffkennwert verwendet wird.
- **Glas** / **Keramiken** / **Silizium** sind Beispiele für `spröd` brechende Materialien. Beim Versagen des Bauteils tritt dabei **keine plastische Verformung** auf. Es kommt dabei direkt zur **Ausbreitung von Rissen** die zum Versagen führen. Hierbei ist ein anderes Versagenskriterium zu verwenden. Dies kann z.B. das `Hauptspannungskriterium` sein.
  
# Beispiele für Post-Processing
  
Im folgenden werden Beispiele für die Ergebnisdarstellung aufgezeigt:
  
## Skalierung der Verformung ( Deformation Scale Factor )
Oft sind Verformungen so klein, dass die normale Darstellung keinen Einblick über die Verformung gibt. Standardmäßig stellt ANSYS ein `Auto Scale` ein. Dies führt bei zu kleinen Verschiebungen zur Vergrößerung und bei zu großen auch zur Verkleinerung. Eingestellt werden kann dies im Reiter `Result`:
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled.png|Untitled.png]]
Über Rechtsklick auf die Legende kann der `Deformation Scale Factor` ausgewählt werden und ist dann in der Legende sichtbar.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 1.png|Untitled 1.png]]
Ein Beispiel ist zum Beispiel der Verformung eines Fahrradrahmens bei der Komfortsteifigkeit (700N auf den Sattel) zeigt sich das Bild der Verformung erst durch eine Überhöhung um den Faktor 1000 (selbstgewählter Wert)
![[Scale-1.png|Scale-1.png]]
`Deformation Scale Factor = 1`
![[Scale-1000.png|Scale-1000.png]]
`Deformation Scale Factor = 1000`
  
## Min / Max / Probe
Zur Anzeige des `Minimum` & `Maximum` gibt es einen Button im Reiter `Result`.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 2.png|Untitled 2.png]]
  
Mit Hilfe des Buttons `Probe` können Werte im beliebigen Bereich angezeigt werden
![[Min_Max_Probe.png|Min_Max_Probe.png]]
  
Im Fenster `Graphics Annotations` werden diese dann aufgelistet (und können dort ebenfalls gelöscht werden):
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 3.png|Untitled 3.png]]
  
## Section Planes (Schnittebenen)
Dies sind Schnittebenen die dazu genutzt werden können um in das innere des Modells zu schauen. Dies ist zum Beispiel nützlich um die Vernetzung in die Tiefe des Bauteils zu bewerten. Die Darstellungen stammen hier aus einem [[Praktikum 3 3. Lokale Netzverfeinerung|Praktikum 3 3. Lokale Netzverfeinerung]].
Klicken Sie dafür zunächst auf `Section Plane` (Menüleiste Home) und ziehen sie anschließend im Geometriefenster eine Linie wo Sie schneiden wollen.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 4.png|Untitled 4.png]]
  
![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/01 Einleitung/attachments/Untitled 8.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/01 Einleitung/attachments/Untitled 8.png]]
Anschließend können wir nun in die Schnittebene schauen und sehen das nur auf der einen Seite leicht in die Tiefe feiner vernetzt wurde.
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 5.png|Untitled 5.png]]
Um den Schnitt wieder zu deaktivieren klicken Sie auf die `Box` im Fenster Section Planes.
Sollte das Fenster nicht vorhanden sein, können Sie dies in der **Menüleiste** im Reiter `Home` unter `Manage`
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 6.png|Untitled 6.png]]
Unter dem Punkt `Section Planes` aufrufen.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 7.png|Untitled 7.png]]
Das Fenster bildet oft ein Reiter zusammen mit dem Detailfenster
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 3. Lokale Netzverfeinerung/attachments/Untitled 8.png|Untitled 8.png]]
## Element-Darstellung
In der Darstellung (vor allem bei Spannungen) kann es sinnvoll sein, die Elemente darzustellen um neben dem Ergebnis auch die Netzgröße zu beurteilen.
![[no_mesh.png|no_mesh.png]]
`Edges` = `No Wireframe`
![[mesh.png|mesh.png]]
`Edges` = `Show Elements`
Man erkennt hier, das die maximale Spannung nur in wenigen Knotenpunkten vorherrscht und somit das Netz oft nicht fein genug ist.
Als Gegenbeispiel bei einem sehr feinen Netz:
![[mesh_fine.png|mesh_fine.png]]
`Edges` = `Show Elements` (fine mesh) mit `High Resolution` (beste Qualität) gespeichert
![[mesh_fine_enhanced_quality.png|mesh_fine_enhanced_quality.png]]
`Edges` = `Show Elements` (fine mesh) mit `enhanced Resolution` (mittlere Qualität) gespeichert
  

> [!important]  
> Die Netzdarstellung in ANSYS ist oft nicht so gut, dass man es eindeutig sieht. Im oberen Beispiel wurden die Abbildungen über den Reiter Result → Images → ImagesTo File → High Resolution - memory intensive (4:1) oder Enhanced resoultion (2:1) erzeugt wodurch das Ergebnis deutlich besser ist  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 4.png|Untitled 4.png]]
`Edges` = `Show Elements` (fine mesh) mit `Optimized for screen display ..` (schlechteste Qualität) gespeichert
## Komponenten-Darstellung
  
Vektorielle Werte (Spannungen / Verschiebungen) können mit jeder Komponente einzeln dargestellt werden, z.B. hier bei den Verschiebungen
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 5.png|Untitled 5.png]]
  
Man kann auch eine extra Koordinatensystem erzeugen, wenn die gewünschte Richtung nicht der globalen x/y/z-Richtung entspricht
## Vektor-Darstellung
  
Gleichzeitig können vektorielle Werte (Spannungen / Verschiebungen) auch als Vektor dargestellt werden. Somit wird zu dem farbcodierten Wert (z.B. der Veschiebung) gleich die Richtung mit angezeigt.
  
Dafür im Reiter `Result` den Button `Vectors` aktivieren und über die Einstellungen den gewünschten Output erzeugen.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 6.png|Untitled 6.png]]
![[Vektor.png|Vektor.png]]
  
## Original mit unverformter Geometrie
Zusätzlich zur Vektordarstellung hilf es die unverformte Geometrie mit einzublenden. Dazu hilft es ggf. den [[Praktikum 5 1. Einleitung|Praktikum 5 1. Einleitung]] hoch zu stellen um die Verformung sichtbar zu machen.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 7.png|Untitled 7.png]]
![[undeformed_wireframe.png|undeformed_wireframe.png]]
`Edges` = `Show Undeformed WireFrame`
![[undeformed_model.png|undeformed_model.png]]
`Edges` = `Show Undeformed Model`
## Animation
Eine weitere Möglichkeit die Verformung sichtbar zu machen ist die Animation. Diese ist im Fenster `graph` zu finden. Dazu gibt es viele Einstelllungsmöglichkeiten (z.B. Frameanzahl, Dauer, Legendenupdate) und Datenformat (*.mp4 , *.wmv , *.gif , *.avi)
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 8.png|Untitled 8.png]]
![[ezgif.com-gif-maker_(2).gif|ezgif.com-gif-maker_(2).gif]]
## Pfad-Darstellung
Pfade können Ergebnisse entlang einer Linie darstellen. So können z.B. Spannungen über eine definierte Länge besser zwischen Varianten verglichen werden.
Pfade können individuell erstellt werden durch Rechtsklick auf `Model` → `Insert` → `Construction Geometry` → `Path`
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 9.png|Untitled 9.png]]
  
Dabei gibt es drei Methoden zur Pfaderstellung:
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 10.png|Untitled 10.png]]
  
Der einfachste Fall ist die Darstellung eines Ergebnisses aus einer Linie per Rechtsklick direkt in ein Pfad umzuwandeln:
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 11.png|Untitled 11.png]]
## Sonderfall `Shell`
  
Bei Shell Elementen können Ober/Unterseite sowie maximale Werte aus beiden dargestellt werden.
  
## Sonderfall `Beam`
  
Bei Beam Elementen gibt es das Beam Tool zur Ergebnisdarstellung.
  
Weiterhin können für Standardprofile die Ergebnisse auch auf dem Profil dargestellt werden. Dafür muss über `Solution` im Detailfenster unter `Post Processing` die `Beam Section Results` = `Yes` gestellt werden.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 12.png|Untitled 12.png]]
Anschließend können dann Spannungen auf dem Beamprofil dargestellt werden
## Abspeichern hochaufgelöster Bilder / ohne Logo / weißer Hintergrund
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 13.png|Untitled 13.png]]
Um hochauflösende Bilder abzuspeichern sollte im Reiter `Result` unter `Images` die Option `Image to File` ausgewählt werden.
Als Resolution empfiehlt sich dann mindestens `Enhanced` zu verwenden.
Weiterhin kann hier der Hintergrund auf weiß gestellt werden und die Legende ausgeblendet werden und die Schriftart skaliert.
Weiterhin kann man das ANSYS Logo auszuschalten muss man im Workbench Projektmenü in der Menüleiste auf `Tools` → `Options` → `Appearance` → `ANSYS Logo` = `OFF`
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 1. Einleitung/attachments/Untitled 14.png|Untitled 14.png]]
![[2D-Symmetrie 2.png|2D-Symmetrie 2.png]]