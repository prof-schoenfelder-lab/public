---
publish: "true"
title: 01 Einführung in die Vernetzung
---

# 1 Einführung in die Vernetzung
  
Wir beschäftigen uns heute mit der **Vernetzung von volumetrischen** (also 3D) **Objekten**. Zusätzlich gibt es noch Elemente die durch Abstraktion nur eine Fläche oder eine Linie darstellen, dies lernen wir aber erst im Praktikum 4 kennen.
  
Unter einem **Netz** verstehen wir die **Einteilung** einer **Geometrie** (in unserem Fall also ein Volumenkörper) **in Elemente**. Im unter gezeigten Bild besteht der Volumenkörper aus **Hexaederförmigen Elementen.** Das Hexaeder-Element besteht in diesem Fall wiederum aus **8 Knoten** (engl. Nodes). In unserem Fall hat jeder Knoten 3 Freiheitsgrade (Verschiebung in x/y/z). Je mehr Knoten und Freiheitsgrade vorkommen, umso größer ist der Rechenaufwand um das System zu lösen.
![[Einfuehrung.png|Einfuehrung.png]]
  
**In diesem Praktikum** wollen wir bezüglich der Vernetzung **zwei fundamentale Fragen beantworten**
  

> [!important]  
> Wie erstelle ich ein optimales Netz und was ist überhaupt ein optimales Netz?  
  
> [!important]  
> Wie fein muss mein Netz sein?  
  
Fangen wir nun an mit einem einfachen Beispiel aus dem ersten Praktikum.
  
## 1.1 Vernetzung mit globalen Vernetzungseinstellungen
  

> [!important]  
> Erstellen Sie das Modell "Balken mit Linienlast" nach den unten angegeben Parametern hinsichtlich Material, Geometrie und Randbedingung.  
  
❗ Achten Sie bei der Geometrieerstellung auf die Koordinatenrichtung, da die Richtungen bei der Netzerstellung referenziert werden  
  
> [!important]  
> In 3D handelt es sich hierbei um eine Flächenlast auf die obere Balkenfläche  
  
> [!important]  
> Falls Sie nicht weiter kommen, finden Sie die Anleitungen im Praktikum 1 (Beispiel A)  
  
==**Material**==
**Stahl**
- Elastizitätsmodul $E=200\,\mathrm{GPa}$﻿
- Querkontraktionszahl $\nu=0{,}3$﻿
==**Geometrie**==
**Balken mit rechteckigem Querschnitt**
- Länge ==$L=1000\,\mathrm{mm}$==﻿
- Breite ==$b=30\,\mathrm{mm}$==﻿
- Breite ==$h=30\mathrm{mm}$==﻿
==**Randbedingungen**==
- Festlager an der linken (y=0) unteren (z=0) Seite
- Loslager an der rechten (y=L) unteren (z=0) Seite
- Linienlast ==$q_0=1000\,\mathrm{N}$==﻿
  
  

> [!important]  
> Verwenden Sie die globale Elementgröße um über die Höhe des Balkens (z-Richtung) mindestens 2 Elemente zu bekommen  
  
- 📋`Anleitung (Allg)` ==**(**====Mechanical) Globale Elementgröße==
    
    ---
    
    1. ==**Im Strukturbaum**== `Klick` auf `Mesh`
        
          
        
        ---
        
    2. ==**Im Detailfenster (Mesh)**== Unter `Defaults` → `Element Size` kann die Elementgröße festgelegt werden> [!important]  
        > Die Elementgröße gibt eine Kantenlänge als Orientierung an, da diese oft durch eine Netzoptimierung oder die Anpassung an die Kantenlängen der Geometrie nicht genau eingehalten werden kann  
        
        Die Größe des unter Element Size definierten Wertes wird im Grafikfenster durch den Kreis im Cursor angezeigt
        
    
    ---
    
  
- Lösungsbeispiel für globale Vernetzung
    
    Elementgröße von 15mm
    
  
Die kleineste globale Netzeinteilung, die uns zwei Elemente über die Höhe erzeugt wären im Bereich von `15mm`. Dies erzeugt uns jedoch auch Elemente in x-Richtung die wir nicht brauchen, weil wir dort keine große Änderung erwarten. Weiterhin man vielleicht auch gerne in Längsrichtung die Elementgröße unabhängig variieren.
  
Um dies also genauer einzustellen benötigen wir eine Einteilung der Geometrielinien was im folgenden beschrieben wird
## 1.2 Vernetzung mittels Linieneinteilung
Wir wenden nun eine Methode an mit dessen Hilfe wir die Elementeinteilung entlang der Körperkanten definieren können.

> [!important]  
> Fügen Sie folgende Linieneinteilung ein (Anleitung siehe unten):  
- alle Linien in x-Richtung (Number of DIvisions: 1)  
- alle Linien in y-Richtung (Number of DIvisions: 5)  
- alle Linien in z-Richtung (Number of DIvisions: 2)  
- 📋`Anleitung (Allg)` ==**(**====Mechanical)== **==Linieneinteilung==**
    
    ---
    
    1. **Wählen Sie das** **`Linien-Auswahltool`** aus
        
          
        
        ---
        
    2. ==**Im Grafikfenster**==`Klicken` Sie die **die Linien an**, auf der die Einteilung vornehmen wollen.
        
        > [!important]  
        > Ggf. notwendige Mehrfahrauswahl kann im Single Select Mode mit der Taste STR bei der Auswahl erfolgen  
        
          
        
          
        
        ---
        
    3. ==**Im Strukturbaum**== `Rechtsklick` auf `Mesh` → `Insert` → `Sizing`
        
          
        
        ---
        
    4. ==**Im Detailfenster**== zwei Varianten der Einteilung möglich:
        
        **Variante a**) feste Einteilung (**Number of Divisions**)
        
        → Elementgröße wird automatisch berechnet
        
        **Variante b**) feste Elementgröße (**Element Size**)
        
        → gilt nur als Richtwert für die Einteilung
        
        Die Größe des unter Element Size definierten Wertes wird im Grafikfenster durch den Kreis im Cursor angezeigt
        
    
    ---
    
  
Erzeugen Sie anschließend das Netz durch **Rechtsklick** auf `Mesh` → `Generate Mesh`. Das Netz sollte dann so aussehen.
  
Es wurde nun ein Netz mit **Hexaeder-Elementen** und den von uns definierten Kanteneinteilungen erstellt.
Die Einteilung in **z-Richtung (Höhe des Balkens)** mussten wir auf mindestens 2 stellen, da sonst die Elemente mit den Los und Festlager zusätzlich mit einer Kraft belastet werden, wodurch es zu einer Fehlermeldung in ANSYS kommt.
In y-Richtung haben wir keine weitere Einteilung vorgenommen und entlang der Balkenlänge (y-Richtung) haben wir "nur" 5 Elemente verwendet.
  
Vergleichen wir nun die Ergebnisse für die Durchbiegung und Spannung:
**maximale Durchbiegung**
- analytisch $u_{max}=0,965\,\mathrm{mm}$﻿
- Simulation $u_{max}=0,968\,\mathrm{mm}$﻿
**und die maximale Spannung**
- analytisch $\sigma_{max}=27{,}78\,\mathrm{MPa}$﻿
- Simulation $\sigma_{max}=27{,}29\,\mathrm{MPa}$﻿
- ℹ️ Vollständige Analytische Lösung
    
    **Durchbiegung**
    
    Für den Fall des zweiseitig gelagerten Balkens mit Linienlast können wir die Durchbiegung berechnen nach:
    
    $u_{max}=\frac{5\,q\,L^4}{384\,E\,I}=\frac{5\cdot1000\,\mathrm{N}\,(1000\,\mathrm{mm})^3}{384\cdot200000\,\mathrm{MPa}\cdot67500\,\mathrm{mm}^4}=0{,}965\,\mathrm{mm}$
    
      
    
    **Maximale Spannung**
    
    Die maximale Biegespannung kann folgend berechnet werden:
    
    $\sigma_{max}=M_{Max}\frac{\frac{h}{2}}{I}$
    
    Mit dem maximalen Biegemoment zu:
    
    $M_{Max}=\frac{q\,L}{8}=\frac{1000N\cdot1000\,\mathrm{mm}}{8}=125000\,\mathrm{Nmm}$
    
    Kann die maximale Biegespannung berechnet werden:
    
    $\sigma_{max}=M_{Max}\frac{\frac{h}{2}}{I}=125000\,\mathrm{mm}\frac{(30\,\mathrm{mm})/2}{67500\,\mathrm{mm}^4}=27{,}78\,\mathrm{MPa}$
    
  
Die Simulation passt bereits sehr gut mit der von uns gewählten Einteilung. Oft ist jedoch keine analytische Lösung vorhanden, so dass eine Sensitivitätsanalyse durchgeführt werden muss.
## 1.3 Sensitivitätsanalyse mit Parametervariation
Bei einer Sensitivitätsanalyse werden die zu untersuchenden Größen (in unserem Fall maximale Durchbiegung und Spannung) in Abhängigkeit von der Vernetzung dargestellt
  
Für den Fall der Einteilung in y-Richtung in den Werten von 2 bis 15 sieht das folgendermaßen aus:
  
Man erkennt, dass nach einer gewissen Verfeinerung des Netztes, sich das Ergebnis nicht mehr signifikant ändert, es ist also eine ausreichende Netzgröße gefunden worden.
Zur Erstellung dieser Graphen ist die Parametervariation in ANSYS Workbench sehr praktisch. Wie dies funktioniert wird im folgenden Tutorial beschrieben:

> [!important]  
> Zur Reduzierung der Rechenzeit wird empfohlen nicht alle Designpunkte wie oben von 2 bis 15 Einteilungen zu rechnen, sondern nur eine kleine Auswahl  
- 🖱️`Anleitung (P3)` ==**(**====Mechanical)== **==Sensitivitätsanalyse mit einer Parametervariation==** ==(am Beispiel der Linieneinteilung am Balken)==
    
    [http://ior.ad/7jzp](http://ior.ad/7jzp)
    
      
    
  
## 1.4 Adaptive Vernetzung
  
Eine weitere Lösungsvariante um eine optimale Netzgröße zu finden ist die **adaptiven Vernetzung**. Dabei wird ein relativ grobes Standardnetz aus Ausgang verwendet. Anschließend wir ein Ergebnis (z.B. die maximale Spannung) ausgewählt und definiert ab wieviel Prozent Änderung das Netz nicht mehr angepasst werden soll. Anschließend verfeinert ANSYS das Netz automatisch solange bis die vorher eingestellte Änderung erreicht ist.
  
Im folgenden Tutorial wird der Lösungsweg aufgezeigt:
- 🖱️`Anleitung (P3)` ==**(**====Mechanical)== **==Adaptive Netzverfeinerung==** ==(am Beispiel des Balkens)==
    
    [http://ior.ad/7jzO](http://ior.ad/7jzO)
    
      
    
  
Im Vergleich zur Variante die wir davor händisch mit der Linieneinteilung erstellt haben, ist das von ANSYS erstellte Netz ist nun **lokal verfeinert** und besteht **nun nicht mehr aus Hexaederförmigen Elementen**, **sondern aus Tetraederförmigen Elementen.**
Die Tetraeder Elemente sind bei der lokale Netzverfeinerung von Volumenkörpern notwendig um einen Übergang zwischen großen und kleineren Elementen zu erzeugen.
  
Übersicht über die dreidimensionalen Elementtypen
  
Neben Tetraeder gibt es noch pyramidenförmige Elemente und das Dreiecksprisma, welches eine niedere Form des Hexaeders darstellt.
Zu Vergleich noch mal ein Netz mit hexaeder Elementen der Kantenlänge 15mm
  

> [!important]  
> Tetraederförmige Elementen sind, wenn möglich zu vermeiden und stattdessen hexaederförmige Elemente zu verwenden, da diese robuster und effizienter sind. Bei komplexen Geometrien ist aber oft nur eine Vernetzung mit tetraeder Elementen möglich  
  
Im Folgenden schauen wir uns an, wie wir hexaederförmige Elemente auf etwas komplexerer Geometrien erstellen können.