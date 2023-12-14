---
publish: "true"
title: 03 Ablauf der Parametrisierung
---

# Varianten der Parametrisierung
  
Insgesamt gibt es zwei wesentliche Methoden zur Parametrisierung. Die erste ist die Verwendung des `Move` und `Pull` Tools in SpaceClaim. Diese ist sehr flexibel und kann auch mit eingeladenen CAD Dateien funktionieren. Allerdings gibt es hier auch einige Probleme die auftreten können. Die zweite Variante ist die Geometrieerstellung mit Hilfe eines Skriptes.
Wir fangen zunächst mit der ersten Variante an:
## Variante a) `Move` & `Pull`
  
Mit Hilfe des `Move` Tools können Objekte in eine definierte Raumrichtung bewegt werden. Durch die Verwendung der `Ruler` Option kann dies auf ein relatives Objekt gesetzt werden. Dies kann verwendet werden um aus dieser Operation einen Parameter zu erstellen. Im folgenden ein Beispiel zur Definition des Parameters der Höhe eines Blocks mit Hilfe des Pull Tools.
1. **Fläche auswählen** die sich verschieben soll durch den Parameter
2. `Move` **Tool auswählen**
3. **Richtung wählen** in welche die Fläche verschoben werden soll (meist normal zur Fläche)
4. `Ruler` **auswählen**
5. **Referenz** für Ruler auswählen (in unserem Fall die Unterseite)
6. `P` anklicken
7. Der Parameter erscheint im Reiter `Groups`
![[Move.gif|Move.gif]]
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled.png|Untitled.png]]
Anschließend empfiehlt es sich den Parameter entsprechend umzubenennen
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 1.png|Untitled 1.png]]
  
Im `Workbench Projektmenü` erscheint nach dem Erstellen des Parameters das `Parameter Set`
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 2.png|Untitled 2.png]]
  
Nach dem Doppelklick auf das `Parameter Set` finden wir unseren neu erstellen Parameter hier wieder
Analog kann mit Hilfe des Pull Tools z.B. eine Kantenverrundung oder ein Bohrungsdurchmesser definiert werden:
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 3.png|Untitled 3.png]]
## Probleme mit Variante a)
Die Variante mit Verwendung des `Move` und `Pull` Tools kann es zu Problemen kommen wenn Geometrien dadurch entfernt werden und dadurch dann auch die Parameter verschwinden. In nachfolgenden Beispiel wurde z.B. der Abstand der Bohrung von der Oberseite als Parameter mit Hilfe des `Move` Tools definiert. Wird die Höhe aber so stark geändert, dass die Bohrung verschwindet, so ist auch der Parameter verschwunden. Wird die Höhe wieder auf den Ausgangswert gestellt, so kommt diese auch nicht wieder.
  
![[Move_Problem.gif|Move_Problem.gif]]
## Variante b) Scripting
  
Die zweite Variante ist mit Hilfe eines Python Skriptes. Dabei muss man keine großen Programmierkenntnisse haben, da SpaceClaim dies großteils alleine ausführt.
Dabei wird meist die Geometrie komplett neu erstellt und dabei die Parameter gesetzt. Das Skript wird automatisch aufgezeichnet und man ändert im nachhinein nur die Parameter ab die man haben möchte.
  
Im folgenden wird dies in einem Beispiel gezeigt:
  
1. In der Kopfleiste über `File` → `New` → `Script` erstellen wir ein neues Skript
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 4.png|Untitled 4.png]]
    
      
    
2. Auf der rechten Seite erscheint der `Skript Editor`. Wenn der Rote Kreis dunkelgrau hinterlegt ist, so ist die Aufnahme Funktion aktiviert. Sämtliche Geometrieerstellung wird nun automatisch aufgezeichnet.
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 5.png|Untitled 5.png]]
    
      
    
3. Nun erstellen wir den Block und im Skript Editor sollte sich schrittweise das Skript mit aufbauen
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 6.png|Untitled 6.png]]
    
      
    
4. Durch erneutes Klick auf den **roten Button** beenden wir die Skript-Aufnahme (dieser ist dann nicht mehr dunkelgrau hinterlegt)
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 7.png|Untitled 7.png]]
    
      
    
5. Nun suchen wir die Stelle an der wir den Parameter einsetzen wollen. In dem Fall war das der Wert beim Extrudieren in diesem Fall hier 16.65.
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 8.png|Untitled 8.png]]
    
      
    
6. Diesen Wert ersetzen wir nun mit einem eigenen Parameter.
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 9.png|Untitled 9.png]]
    
      
    
7. Am Beginn des Skripts initialisieren wir den Parameter (hier im Beispiel mit dem Wert 30)
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 10.png|Untitled 10.png]]
    
      
    
8. Wenn wir das Skript jetzt so ausführen würden, würde er die Geometrie immer erweitern. Um dies zu verhindern müssen wir zum Beginn des Skriptes folgenden Code einfügen
    
    ```
    ClearAll()
    ```
    
      
    
9. Der komplette Code sieht in meinem Fall dann so aus
    
    - Code
        
        ```
        # Python Script, API Version = V17
        ClearAll()
        
        hoehe = 30
        
        # Set Sketch Plane
        sectionPlane = Plane.Create(Frame.Create(Point.Create(MM(0), MM(15), MM(15)), 
        	Direction.DirX, 
        	Direction.DirY))
        result = ViewHelper.SetSketchPlane(sectionPlane, Info1)
        # EndBlock
        
        # Set Sketch Plane
        selection = Selection.Create(Axis1)
        result = ViewHelper.SetSketchPlane(selection, Info2)
        # EndBlock
        
        # Sketch Rectangle
        point1 = Point2D.Create(MM(-15),MM(-15))
        point2 = Point2D.Create(MM(15),MM(-15))
        point3 = Point2D.Create(MM(15),MM(15))
        result = SketchRectangle.Create(point1, point2, point3)
        # EndBlock
        
        # Solidify Sketch
        mode = InteractionMode.Solid
        result = ViewHelper.SetViewMode(mode, Info3)
        # EndBlock
        
        # Extrude 1 Face
        selection = Selection.Create(Face1)
        options = ExtrudeFaceOptions()
        options.ExtrudeType = ExtrudeType.Add
        result = ExtrudeFaces.Execute(selection, MM(hoehe), options, Info4)
        # EndBlock
        ```
        
    
      
    
10. Durch das Play Button auf der rechten Seite wird nun das Modell immer neu erstellt
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 11.png|Untitled 11.png]]
    
      
    
11. Um nun den Parameter in das Workbench Parameter Set zu bekommen fehlen noch zwei Schritte. Zunächst müssen wir das Skript als Gruppe speichern. Dafür klicken wir auf den kleinen Pfeil nach unten und stellen dabei `Publish as Group` ein.
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 12.png|Untitled 12.png]]
    
      
    
12. Anschließen klicken wir auf das Symbol und veröffentlichen das Skript als Gruppe. (Mit OK bestätigen)
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 13.png|Untitled 13.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 14.png|Untitled 14.png]]
    
      
    
13. Im Reiter `Groups` mit Rechtsklick auf `Group` → `Create Script Parameter`
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 15.png|Untitled 15.png]]
    
      
    
14. Den Parameter entsprechend umbenennen (in dem Fall zu `Hoehe`) und Wert eintragen (hier `30`)
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 16.png|Untitled 16.png]]
    
      
    
15. Im Skript den Wert durch `Parameters.Hoehe` ersetzen (wenn man `Parameters.` schreibt werden alle vorhandenen Parameter vorgeschlagen).
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 17.png|Untitled 17.png]]
    
      
    
16. Der Parameter ist nun im `Workbench Parameter Set` zu finden
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 18.png|Untitled 18.png]]
    
  
# Named Selections
Werden Randbedingungen auf Geometrien angewendet, die sich durch die Parameterisierung verändern, so muss eine Named Selection erstellt werden.
  
In unserem Fall z.B. durch eine parametrisierte Verrundung der oberen Fläche
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 19.png|Untitled 19.png]]
  
Wir wollen eine Randbedingung auf die obere Fläche anbringen. Dazu wählen wir diese aus und klicken im Reiter `Groups` auf `Create NS`
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 20.png|Untitled 20.png]]
  
Anschließend kann diese sinnvoll umbenannt werden:
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 21.png|Untitled 21.png]]
  
Im `Mechanical` muss in der entsprechenden Randbedingung (oder auch für Post-Processing Auswertung) die Scoping Method auf `Named Selection` gestellt werden und unter `Named Selection` die vorher in Space Claim erstellte Named Selection ausgewählt werden (in unserem Fall also `Flaeche_oben`.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 22.png|Untitled 22.png]]
  
  
# weitere Input Parameter
Neben den geometrischen Parametern in SpaceClaim können auch andere Input-Parameter der Simulation verwendet werden. Ein gutes Beispiel dafür ist zum Beispiel die Netzgröße. Um den Parameter zu erstellen im Detailfenster auf die leere Box neben den Wert klicken bis ein `P` erscheint.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 23.png|Untitled 23.png]]
  
# Output Parameter
Dies sind Parameter die wir berechnen wollen. Dies könnte z.B. die maximale Verformung oder Spannung sein. In unserem Fall wählen wir die maximale Verformung aus. Wieder über das Detailfenster auf den leeren Kasten klicken bis ein `P` erscheint.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 24.png|Untitled 24.png]]
  
# Workbench Parameter Set
Im Parameter Set können Sie nun beliebig viele Parametervariationen durchrechnen und sich das Output Ergebnis ausgeben lassen. Wollen Sie das Ergebnis für den jeweiligen Parameter später noch mal abrufen wollen müssen Sie ein Haken bei `Retain` setzen
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 25.png|Untitled 25.png]]
Anschließend den entsprechenden DesignPoint auswählen und rechtsklick auf `Set as Current`. Dadurch wird der jeweilige DesignPoint geladen und man kann z.B. im Mechanical sich das Modell anschauen.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 26.png|Untitled 26.png]]
  
# Optimierung / Parameterkorrelation
Ohne näher darauf einzugehen gibt es im Workbench Projektmenü unter dem Punkt `Design Exploration` noch die Möglichkeit u.a. eine Optimierung oder eine Parameterkorrelation durchzuführen.
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 5- Post-Processing & Parametrisierung/Praktikum 5 3. Ablauf der Parametrisierung/attachments/Untitled 27.png|Untitled 27.png]]
![[2D-Symmetrie 2.png|2D-Symmetrie 2.png]]