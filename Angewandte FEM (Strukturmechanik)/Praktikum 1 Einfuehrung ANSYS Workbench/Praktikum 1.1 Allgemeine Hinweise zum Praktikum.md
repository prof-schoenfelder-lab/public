---
share: "true"
---

# 1. Allgemeine Hinweise zum Praktikum

## 1. 1. Kurzeinleitung Finite-Elemente-Methode (FEM)

Im folgenden ist die Vorgehensweise der Finiten-Elemente-Methode an Hand des Workflows in ANSYS Workbench grob skizziert.


**Geometrie**


![[1-1 Geometrie.png|200x200]]
- zunächst wird ein **Bauteil erstellt** oder **eingeladen** (z.B. aus Catia)
- es können dabei auch **mehrere Bauteile** verwendet werden

**Material**

- Es kann auf eine **Materialdatenbank** zurückgegriffen werden oder aber auch **eigene Materialien** mit den jeweiligen Parametern definiert werden

---
**Vernetzung**
![[1-1 Vernetzung.png|200]]
- Das Bauteil (in dem Beispielfall ein dreidimensionaler Körper) wird nun mit **Elementen** vernetzt
- Elemente bestehen aus **Knoten** (in diesem Fall besteht ein 3D Element aus 8 Eckknoten). Jeder Knoten besitzt Freiheitsgrade (in unserem Falle sind es Verschiebungen)
- Je mehr Elemente (und somit auch Knoten) verwendet werden, desto genauer ist das Ergebnis

---
**Randbedingungen**

![[1-1 Randbedingungen.png|200]]

- Randbedingungen (z.B. Verschiebungen, Kräfte, Druck) **werden meist auf geometrischen Objekten** (Körper, Flächen, Kanten und Punkten) **angebracht**.

---
**Übertragen Randbedingungen auf Knoten**

![[1-1 Randbedingungen Knoten.png|200]]

- Die **Randbedingungen** werden dann auf die **Freiheitsgrade der Knoten** in dem Bereich der geometrischen Objekte **übertragen**.

<aside> ➡️ Wird automatisch vom Programm durchgeführt

</aside>

---
**Lösen Gleichungssystem**

![[1-1 Loesung Gleichungssystem.png|200]]

- Durch das Lösen des Gleichungssstems wird die Lösung der noch offenen Freiheitsgrade jedes Knotens bestimmt.

<aside> ➡️ Wird automatisch vom Programm durchgeführt

</aside>

---
**Darstellung** (3D)

![[1-1 Loesungsdarstellung.png|200]]

- Nach dem Lösen können verschiedene Ergebnisse in verschiedenen Formen dargestellt werden.

## 1. 2. ANSYS auf dem eigenen Computer installieren

Sie können ANSYS auf ihrem eigenen Computer installieren, mit Windows10 und neuerdings auch unter Linux mit Ubuntu 20.04. Für den Mac muss der Umweg über [Parallels](www.parallels.com) mit der Windowsversion erfolgen. Sie benötigen aber VPN für den Zugang zum Lizenzserver.
   
1. **VPN-Client installieren** (Für Zugang zum Lizenzserver)
	1. **Anleitung** und **Download** unter [https://itsz.htwk-leipzig.de/serviceangebote-dienste/vpn-zugriff-auf-das-hochschulnetz/](https://itsz.htwk-leipzig.de/serviceangebote-dienste/vpn-zugriff-auf-das-hochschulnetz/)
2. **Software ANSYS (Version 2022R2)** installieren
	1. Download unter Server2/Lehre/Kaule/ANSYS2022R2_Windows ⚠️ VPN muss aktiviert sein
	2. iso Dateien als Laufwerk einbinden und von dort aus die Installation starten
	3. Standardinstallation (automatische Auswahl der Komponenten)
	4. notwendige verfügbare Festplattenkapazität > 30 GB
	5. Lizenzserver während Installation angeben: [**ansys.htwk-leipzig.de**](http://ansys.htwk-leipzig.de/)


> [!WARNING] **Auftretende Fehler bzw. Hinweise:**
> ANSYS CDs vom Server2 erst runterladen und dann erst mounten (sonst können bei der Installation Dateien nicht richtig gelesen werden, vor allem per VPN von zuhause)

