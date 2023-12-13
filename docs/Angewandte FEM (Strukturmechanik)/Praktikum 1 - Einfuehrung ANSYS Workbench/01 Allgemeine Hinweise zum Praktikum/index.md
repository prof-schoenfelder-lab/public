---
publish: "true"
title: 01 Allgemeine Hinweise zum Praktikum
---


  # 1. Allgemeine Hinweise zum Praktikum
  
## 1. 1. Kurzeinleitung Finite-Elemente-Methode (FEM)
Im folgenden ist die Vorgehensweise der Finiten-Elemente-Methode an Hand des Workflows in ANSYS Workbench grob skizziert.
  
  
**Geometrie**
- zunächst wird ein **Bauteil erstellt** oder **eingeladen** (z.B. aus Catia)
- es können dabei auch **mehrere Bauteile** verwendet werden
**Material**
- Es kann auf eine **Materialdatenbank** zurückgegriffen werden oder aber auch **eigene Materialien** mit den jeweiligen Parametern definiert werden
---
**Vernetzung**
- Das Bauteil (in dem Beispielfall ein dreidimensionaler Körper) wird nun mit **Elementen** vernetzt
- Elemente bestehen aus **Knoten** (in diesem Fall besteht ein 3D Element aus 8 Eckknoten). Jeder Knoten besitzt Freiheitsgrade (in unserem Falle sind es Verschiebungen)
- Je mehr Elemente (und somit auch Knoten) verwendet werden, desto genauer ist das Ergebnis
---
**Randbedingungen**
- Randbedingungen (z.B. Verschiebungen, Kräfte, Druck) **werden meist auf geometrischen Objekten** (Körper, Flächen, Kanten und Punkten) **angebracht**.
  
---
**Übertragen Randbedingungen auf Knoten**
- Die **Randbedingungen** werden dann auf die **Freiheitsgrade der Knoten** in dem Bereich der geometrischen Objekte **übertragen**.

> [!important]  
> Wird automatisch vom Programm durchgeführt  
---
**Lösen Gleichungssystem**
- Durch das Lösen des Gleichungssstems wird die Lösung der noch offenen Freiheitsgrade jedes Knotens bestimmt.

> [!important]  
> Wird automatisch vom Programm durchgeführt  
---
**Darstellung** (3D)
- Nach dem Lösen können verschiedene Ergebnisse in verschiedenen Formen dargestellt werden.
## 1. 2. ANSYS auf dem eigenen Computer installieren
  
Sie können ANSYS auf ihrem eigenen Computer installieren, mit Windows10 und neuerdings auch unter Linux mit Ubuntu 20.04. Für den Mac muss der Umweg über [Parallels](https://www.notion.sowww.parallels.com) mit der Windowsversion erfolgen. Sie benötigen aber VPN für den Zugang zum Lizenzserver.
  
  