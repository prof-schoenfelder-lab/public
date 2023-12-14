---
publish: "true"
title: 02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt
---

# 2. Beispiel A: Normalkraftstab unter Eigenlast
![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 11.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 11.png]]
==A==: Einspannung entlang Kante
==B==: Verschiebung an einem Punkt
  
**BEZUG ZU DEN LETZTEN PRAKTIKA**
- **Material definieren**  
    (Praktikum 1)
- **Geometrie selbst erstellen**  
    (Praktikum 2)
- **Richtige Randbedingung anbringen  
    **(Praktikum 2)
- **Vernetzung so fein, dass kein Einfluss auf Ergebnis vorhanden**  
    (Praktikum 3)
- **Richtige Abstraktion wählen  
    **(Praktikum 4)
  
### 2.1 ==Gegeben==
  
==**Material**==
**Stahl**
- Elastizitätsmodul $E=210\,\mathrm{GPa}$﻿
- Querkontraktionszahl $\nu=0{,}3$﻿
  
==**Geometrie**==
**Blech**
- Länge ==$L=30\,\mathrm{mm}$==﻿
- Breite ==$b=30\,\mathrm{mm}$==﻿
- Dicke ==$d=0{,}5\mathrm{mm}$==﻿
  
==**Randbedingungen**==
- feste Einspannung an einer Kante
- Verschiebung in 4mm an dem äußeren Punkt (gegenüber der Einspannung)
  
### 2.2 ==Gesucht==
  
Wir suchen:
1. Die **maximale von-Mises Vergleichsspannung**
2. Die **Gesamtverformung** des Bauteils
3. Die **Vektordarstellung** der **Hauptspannungen**
4. Die **erste Hauptspannung** (Shell Top/Bot)
5. Die **von-Mises Vergleichsspannung als Pfad** entlang der Einspannung
6. Die **Kraft** an dem **Punkt der Verschiebung**
7. Das **Moment** in der **Einspannung**
  
### 2.3 ==**Hinweise**==
  
**Geometrie**
Da das Blech nur eine geringe Dicke aufweist, ist die Abstraktion als `Shell` Element sinnvoll.

> [!important]  
> Shell Elemente haben Besonderheiten bei der Auswertung, dazu kommen wir aber später  

> [!important]  
> Wenn die Verschiebung nicht nur in einem Punkt, sondern auf der ganze Kante (gegenüber der Einspannung) wäre, könnte man es auch in 2D mit einem ebenen Verzerrungszustand abstrahieren  
Das Blech wird in **SpaceClaim** in den Grundmaßen (30mm x 30mm) als Fläche (**Surface**) modelliert.
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled.png|Untitled.png]]
  

> [!important]  
> Es muss hierbei im Workbench Projektmenü in der Geometrie nicht auf 2D eingestellt werden, da die Shell Elemente beliebig im 3D Raum liegen und es deshalb keine 2D Abstraktion ist  
  
Im **Mechanical** können Sie der Fläche später eine Dicke zuweisen.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 1.png|Untitled 1.png]]
  
### 2.4 ==Lösung==
### Vernetzung
- **Vernetzung**
    
    - 1. Schritt (`adaptive Netzverfeinerung`) um zu schauen wie die finale Spannung ist
        
        → $\sigma_{eqv-Mises,Max}=755\,\mathrm {MPa}$﻿ bei Netzgröße von **0,05mm** im Bereich der Einspannung
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 2.png|Untitled 2.png]]
        
        Adaptive Netzverfeinerung für `von-Mises Spannung`
        
    
    _==Da das Netz der adaptiven Netzverfeinerung oft nicht gut ist, habe ich selbstständig ein Netz erstellt in ähnlichen Größenordnungen der Elementgröße und von-Mises Spannungen==_
    
    - 2. Schritt (eigenes Netz mit Netzverfeinerung `Refinement`)
        
        - globale Netzgröße: 0,5mm
        - Netzverfeinerung (`Refinement` Level: 3) an Einspannung
            
            → Netzgröße: 0,125mm an Einspannung
            
        
        → $\sigma_{eqv-Mises,Max}=751{,}9\,\mathrm {MPa}$﻿ bei Netzgröße von **0,125mm** im Bereich der Einspannung
        
        > [!important]  
        > Ein noch feineres Netz wäre vermutlich genauer, aber von der Rechenzeit zu intensiv, daher habe ich es für das Praktikum dabei belassen  
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 3.png|Untitled 3.png]]
        
  
### a) **maximale von-Mises Vergleichsspannung**

> [!important]  
> Stahl hat duktiles Materialversagen, als müssen wir die von-Mises Vergleichsspanung auswerten  
  
In der Menüleiste im Reiter `Result` kann man das **Maximum** bzw. **Minimum** anzeigen lassen und über **Probe** auf eine Stelle im Bauteil klicken um dort die Spannung zu bestimmen
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 4.png|Untitled 4.png]]
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 5.png|Untitled 5.png]]
  
Beim `Probe` werden die Ergebnisse unten im Fenster `Graphics Annotations` angezeigt. Dort können diese auch mit **Selektion** und **Rechtsklick** wieder gelöscht werden.
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 6.png|Untitled 6.png]]
  
Wenn wie in diesem Fall die Elemente so fein sind, das durch die Elementrahmen die Darstellung behindert wird, kann man die Elemente auch ausblenden.
**Elemente ausblenden**: `Menüleiste:` Reiter (`**Result**`): `Edges` → `No WireFrame`
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 7.png|Untitled 7.png]]
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 8.png|Untitled 8.png]]
Die Spannung sieht dann wie folgt aus:
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 9.png|Untitled 9.png]]
  
  
### b) **Gesamtverformung** des Bauteils
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 10.png|Untitled 10.png]]

> [!important]  
> Bei der Darstellung der Verformung ist vor allem auf den Deformation Scale Factor zu achten. Diese sollte bei der Verwendung der Abbildung möglichst mit angegeben werden  
Durch `Rechtsklick` **auf die Infos im Grafikfenster** kann der `Deformation Scale Factor` angezeigt werden
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 11.png|Untitled 11.png]]
  
  
Unter `Edges` kann zusätzlich das unverformte Modell dargestellt werden (als WireFrame oder als transparentes Volumen)
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 12.png|Untitled 12.png]]
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 13.png|Untitled 13.png]]
  
Neben der Darstellung als `Contour-Plot` kann die Verformung auch als Vektor dargestellt werden. Diese Darstellung funktioniert bei allen vektoriellen Größen (wie z.B. auch den Hauptspannungen).
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 14.png|Untitled 14.png]]
Es empfiehlt sich oft die `proportionale Darstellung` mit der Ausrichtung an einem `Grid` (nicht den Elementen). Dafür muss man an den beiden Schiebereglern spielen bis man die Größe und Verteilung so eingestellt hat, das man etwas erkennt
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 15.png|Untitled 15.png]]
### c) **Vektordarstellung** der **Hauptspannungen**

> [!important]  
> Für sprödes Materialversagen werden die Hauptspannungen ausgewertet.  
  
Um den Vektor der Hauptspannungen zu bekommen muss `Vector Principal` ausgewählt werden.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 16.png|Untitled 16.png]]
Bei den Hauptspannungen können die Vektoren für die zweite und dritte Hauptspannung ausgeblendet werden da uns meist nur die erste (also die größte) Hauptspannung interessiert
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 17.png|Untitled 17.png]]

> [!important]  
> Die vektorielle Darstellung der ersten Hauptspannung hilft uns die Richtung und Größe der Spannung im Bauteil zu bewerten  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 18.png|Untitled 18.png]]
### d) Hauptspannung (Shell Top/Bot)
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 19.png|Untitled 19.png]]
  
Den **Wert der ersten Hauptspannung** bekommt man durch `Maximum Principal`
  

> [!important]  
> Für Shell-Elemente kann die Spannung auf der Ober/Unterseite separat ausgegeben werden, da die Elemente nur Knoten in der Mitte verfügen und die Spannung auf den Ober/Unterseite durch die Biegung und den Abstand berechnet werden  
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 20.png|Untitled 20.png]]
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 21.png|Untitled 21.png]]
Top
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 22.png|Untitled 22.png]]
Bot
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 23.png|Untitled 23.png]]
Bot + Top
### e) **von-Mises Vergleichsspannung als Pfad** entlang der Einspannung
  
- 📋`Anleitung (Allg)` ==**(**====Mechanical)== ==**Pfad**== ==erstellen==
    
    ---
    
    1. ==Im Strukturbaum== `Rechtsklicken` auf `Model` → `Insert` → `Construction Geometry` → `Path`
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 24.png|Untitled 24.png]]
        
          
        
        ---
        
    2. ==Im Strukturbaum== erstellten **Pfad** auswählen
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 25.png|Untitled 25.png]]
        
          
        
        ---
        
    3. ==Im Detailfenster (==**==Path==**==)== Den Start und Endpunkt über `Koordinaten` oder durch `Location` mit Geometrieselektion auswählen
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 26.png|Untitled 26.png]]
        
          
        
        ---
        
    4. ==Im Detailfenster (==**==der gewünschte Ergebnisausgabe==**==)== unter `Scoping Method` → `Path` auswählen
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 27.png|Untitled 27.png]]
        
          
        
        ---
        
    5. ==Im Detailfenster (==**==der gewünschte Ergebnisausgabe==**==)== unter `Path` den **erstellen Pfad auswählen**
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 28.png|Untitled 28.png]]
        
    
    ---
    
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 29.png|Untitled 29.png]]
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 30.png|Untitled 30.png]]
  
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 31.png|Untitled 31.png]]
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 2. Beispiel A- Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 32.png|Untitled 32.png]]
### f) **Kraft** an dem **Punkt der Verschiebung**
  
- 📋`Anleitung (Allg)` ==**(**====Mechanical)== **==Kraftreaktion==** ==ausgeben==
    
    ---
    
    1. ==Im Strukturbaum== `Rechtsklicken` auf `Solution` → `Insert` → `Probe` → `Force Reaction`
        
        ![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 33.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 33.png]]
        
          
        
        ---
        
    2. ==Im Detailfenster (Force Reaction)== Unter `Boundary Condition` die Randbedingung angeben auf der die Kraft ausgelesen werden soll
        
        ![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 34.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 34.png]]
        
          
        
        ---
        
    
    ---
    
  
![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 35.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 35.png]]
![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 36.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 36.png]]
  
Zur Kontrolle, die Kraft an der Einspannung ist natürlich der gleiche Wert in die andere Richtung
![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 37.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 37.png]]
![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 38.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 38.png]]
### g) **Moment** in der **Einspannung**
  
- 📋`Anleitung (Allg)` ==**(**====Mechanical)== **==Drehmoment==** ==ausgeben==
    
    ---
    
    1. ==Im Strukturbaum== `Rechtsklicken` auf `Solution` → `Insert` → `Probe` → `Moment Reaction`
        
        ![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 39.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 39.png]]
        
          
        
        ---
        
    2. ==Im Detailfenster (Moment Reaction)== Unter `Boundary Condition` die Randbedingung angeben auf der das Moment ausgelesen werden soll
        
        ![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 40.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 40.png]]
        
          
        
        ---
        
    
    ---
    
  
  
![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 41.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 41.png]]
![[Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 42.png|Angewandte FEM (Strukturmechanik)/P5 - Post-Processing & Parametrisierung/02 Beispiel A -  Stahlblech mit Verschiebung an einem Punkt/attachments/Untitled 42.png]]