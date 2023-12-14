---
publish: "true"
title: 07 Zusammenfassung & Ausblick
---

# 7. Zusammenfassung & Ausblick
## 7. 1. Aufräumen
  
In dem Ordner in dem wir das Projekt gespeichert haben befindet sich jetzt eine `.wbpj` Datei und ein Ordner mit dem gleichen Namen. Innerhalb dieses Ordners gibt es wieder viele Unterordner.
  
![[CleanShot_2022-10-14_at_11.29.412x.png|CleanShot_2022-10-14_at_11.29.412x.png]]
![[CleanShot_2022-10-14_at_11.30.172x.png|CleanShot_2022-10-14_at_11.30.172x.png]]
  
Dies macht es relativ unpraktisch das gesamte Projekt z.B. auf einem USB-Stick mitzunehmen oder irgendwo hochzuladen. Intuitiv könnte man alle Dateien z.B. in ein zip-Archiv packen damit man eine Datei bekommt. Glücklicherweise besitzt ANSYS nativ eine solche Funktion mit dem Namen `Archiv`.
  

> [!important]  
> Speichern Sie das Projekt als Archiv  
  
[https://scribehow.com/embed/ANSYS_Workbench__als_Archiv_speichern__cBThsNGxRZKvgQsk96TjmA?skipIntro=true&removeLogo=true](https://scribehow.com/embed/ANSYS_Workbench__als_Archiv_speichern__cBThsNGxRZKvgQsk96TjmA?skipIntro=true&removeLogo=true)
  
## 7. 2. Zusammenfassung des Praktikums

> [!important]  
> In der FEM werden geometrische Objekte in Elemente (die jeweils wieder aus Knoten bestehen) diskretisiert. Mit Hilfe von Materialmodellen mit den Materialparametern und Randbedingungen kann anschließend mit der Lösung des Gleichungssystem die Verschiebungen in jedem Knoten berechnet werden. Daraus können wieder andere Größen wie Spannungen berechnet und dargestellt werden.  
  
Der Ablauf in der Simulation ist immer der folgende: ([[Praktikum 1 1. Allgemeine Hinweise zum Praktikum|Praktikum 1 1. Allgemeine Hinweise zum Praktikum]])  
  
1. Materialdefinition  
2. Geometrieerstellung  
3. Materialzuweisung & Modelleigenschaften festlegen  
4. Vernetzung  
5. Randbedingungen anbringen  
6. Lösen des Gleichungssystems  
7. Lösung darstellen  
  
  

> [!important]  
> Randbedingungen können zu Problemen bei der Auswertung führen  
([[Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft|Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft]])  
![[CleanShot_2022-10-13_at_17.53.572x.png|CleanShot_2022-10-13_at_17.53.572x.png]]
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 4. Beispiel B- einseitig eingespannter Balken mit Einzelkraft/attachments/Untitled 6.png|Untitled 6.png]]
Beispiel B: mit der Spannungsüberhöhung durch die Querschnittsveränderung an der Einspannung
  

> [!important]  
> Um das Simulationsergebnis zu überprüfen sollten analytische Gleichungen oder Experimente verwendet werden. Sollen Spannungen berechnet werden, so sollte das Netz solange verfeinert werden, bis sich die Spannungen nicht mehr signifikant ändern (Konvergenzanalyse)  
([[Praktikum 1 6. Beispiel D- Lenker|Praktikum 1 6. Beispiel D- Lenker]])  
  
**grobes Netz  
**Spannung 167MPa  
→ Spannungsgradinenten zwischen Knoten sehr groß (nicht fein genug vernetzt)
  
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 19.png|Untitled 19.png]]
`Number of Divisions = 10`  
**feines Netz  
**Spannung 144MPa
→ Spannungsgradient zwischen Knoten deutlich kleiner, Vernetzung vermutlich ausreichend
  
![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 1- Einführung ANSYS Workbench/Praktikum 1 6. Beispiel D- Lenker/attachments/Untitled 20.png|Untitled 20.png]]
`Number of Divisions = 50`
## 7. 3. Ausblick
  
Nun folgend gibt es noch Übungsaufgaben im OPAL.
  
In den nächsten Praktika behandeln wir dann folgende Themen:
  
- **Praktikum 2**: Randbedingung & Geometrieerstellung  
    _==Kennenlernen und Anwenden verschiedener Randbedingungen.  
    Geometrieerstellung in SpaceClaim==_
- **Praktikum 3**: Vernetzung  
    ==Welche Methoden gibt es, worauf sollte man achten.==
- **Praktikum 4**: Abstraktion  
    _==Vereinfachung der Modelle um Rechenzeit zu sparen==_
- **Praktikum 5**: Postprocessing  
    _==Darstellung der Ergebnisse==_
