---
publish: "true"
title: 02 Geometrieaufbereitung für hexaederförmige Vernetzung
---

# 2. Geometrieaufbereitung für hexaederförmige Vernetzung
  
Standardmäßig können folgende Volumen von ANSYS **standardmäßig mit hexaeader Elementen vernetzt** werden:
  
**HEXAEDER**
**SWEEP GEOMETRIEN**
  
**ZYLINDER**
**HOHLZYLINDER**

> [!important]  
> Zylinder bzw. Hohlzylinder vernetzen am besten wenn diese geviertelt werden  
  
Um diese Aussage zu prüfen schauen wir uns dies noch mal am Beispiel es Vollzylinders genauer an
## 2.1 Beispiel: **Vollzylinder**
  

> [!important]  
> Erstellen Sie einen Vollzylinder mit Durchmesser 20mm und Höhe 20mm. Erstellen Sie dann ein automatisches Netz mit der Elementgröße von 1mm und prüfen Sie die Elementqualität (siehe Anleitung darunter)  
- 📋`Anleitung (Allg)` ==**(**====Mechanical)== **==Elementqualität anzeigen (Mesh Metrics)==**
    
    ---
    
    1. ==Im Strukturbaum== `Mesh` auswählen
        
          
        
    2. ==Im Detailfester (Mesh)== Unter `Quality` > `Mesh Metrics` auf `Element Quality` stellen
        
          
        
    3. ==Im Detailfester (Mesh)== Unter `Quality` > `Mesh Metrics` werden nun Min/Max/Mittel und Standardabweichung angezeigt
        
          
        
    4. ==Im Mesh Metrics Fenster== wird ein Histogramm angezeigt
        
          
        
    5. ==Im Mesh Metrics Fenster== Durch Anklicken eines Balkens im Histogramm werden im Grafikfenster die zugehörigen Elemente angezeigt
        
    
    ---
    
  
  
  
**Elementqualität** (Mittel): 0,88
⚠️ ==**Teilweise niedere Elemente (Wedge)**==
## 2.2 Beispiel: **Vollzylinder (geschnitten)**

> [!important]  
> Schneiden Sie nun die Geometrie in Viertel und prüfen Sie erneut die Elementqualität  
- 🖱️`Anleitung (P3)` ==**(**====SpaceClaim) Geometrie== **==schneiden==** ==für Vernetzung (Zylinder)==
    
    [http://ior.ad/7jIf](http://ior.ad/7jIf)
    
  
**Vollzylinder (geviertelt)**
![[Angewandte FEM (Strukturmechanik)/P3 - Vernetzung/02 Geometrieaufbereitung für hexaederförmige Vernetzung/attachments/Untitled 3.png|Angewandte FEM (Strukturmechanik)/P3 - Vernetzung/02 Geometrieaufbereitung für hexaederförmige Vernetzung/attachments/Untitled 3.png]]
**Elementqualität** (Mittel): 0,97
==**✅ Komplett Heaxederförmige Elemente**==
  
  

> [!important]  
> Die Elementqualität gibt ein Maß aus wie gut das Aspektverhältnis (Verhältnis von Volumen zur Kantenlänge) für die unterschiedlichen Elemente ist, wobei 1 der beste Wert und 0 der schlechteste Wert ist.  
  
Die Anzeige der Elementqualität dient nur als Orientierung und in unserem Fall auch gut um zwei Netze miteinander zu vergleichen.  
  
Man sollte darauf achten, dass die Elemente in dem Bereich den man auswerten möchte nicht zu stark verzerrt sind, wobei für Hexaeader Elemente eine schlechte Qualität vertretbarer ist, als bei Tetraeader Elementen.  
  
## 2.3 Beispiel: Biegeteil (automatische Vernetzung)

> [!important]  
> Laden Sie das Bauteil "Biegeteil.sdoc" ein und erzeugen zunächst ein automatisches Netz mit der globalen Elementgröße von 1mm und geben Sie sich dazu die Elementqualität aus  
  
Biegeteil.scdoc
  
  
- **Lösung**: **Standardnetz (**Elementqualität (Mittel): 0,73)
    
## 2.4 Beispiel: Biegeteil (geschnitten)

> [!important]  
> Verbessern Sie nun das Netz indem Sie die Geometrie nach den oben aufgeführten Prinzipien schneiden.  
  
Verwenden Sie wieder eine globale Elementgröße von 1mm und vergleichen Sie ihre Ergebnisse mit Hilfe der Elementqualität  
  
- **Lösung: Geschnitten (**Elementqualität (Mittel): 0,98)
    
      
    
  
  
## 2.5 Beispiel: Biegeteil (Method: MultiZone)
  
ANSYS bietet eine Methode an, die oft auch zu guten Ergebnissen führt. Diese trennt Geometrien an ihren Außenbereichen automatisch und versucht dann mit hexaeder Elementen zu vernetzen. Für einfache Geometrien kann dies gut funktionieren.
  
  

> [!important]  
> Verwenden sie die Methode MultiZone zur Erzeugung eines Netzes (siehe Anleitung unten).  
  
Verwenden Sie wieder eine globale Elementgröße von 1mm und vergleichen Sie ihre Ergebnisse mit Hilfe der Elementqualität  
  
- 📋`Anleitung (Allg)` ==**(**====Mechanical)== **==Methode: Multi Zone==** ==(für Hexa Mesh)==
    
    ---
    
    1. **Wählen** Sie mit dem `**Körperauswahltool**` **den Körper aus,** auf der Sie die Methode anwenden wollen. > [!important]  
        > Mit STR + A können Sie schnell alle Körper auswählen  
        
          
        
        ---
        
    2. ==Im Strukturbaum== Rechtsklick auf`Mesh` → `Insert` → `Method`
        
          
        
    3. ==Im Detailfester== Unter `Definition` die `Methode` `MultiZone` auswählen
        
          
        
    
    ---
    
  
- **Lösung:** **Multi Zone (**Elementqualität (Mittel): 0,96)
    
  
  
Im nächsten Abschnitt wollen wir uns die Methode Sweep genauer anschauen ...