---
publish: "true"
title: 02 Beispiel A -  Normalkraftstab unter Eigenlast
---


# 2. Beispiel A: Normalkraftstab unter Eigenlast
![[Angewandte FEM (Strukturmechanik)/attachments/BeispielA_Aufgabenstellung.png|Angewandte FEM (Strukturmechanik)/attachments/BeispielA_Aufgabenstellung.png]]
  
**BEZUG ZU DEN LETZTEN PRAKTIKA**
- **Material definieren**  
    (Praktikum 1)
- **Geometrie selbst erstellen**  
    (Praktikum 2)
- **Richtige Randbedingung anbringen  
    **(Praktikum 2)
- **Vernetzung so fein, dass kein Einfluss auf Ergebnis vorhanden**  
    (Praktikum 3)
  
### 2.1 ==Gegeben==
  
==**Material**==
**Stahl**
- Elastizitätsmodul $E=210\,\mathrm{GPa}$﻿
- Querkontraktionszahl $\nu=0{,}3$﻿
- Dichte $\rho=7850 \frac{kg}{m^3}$﻿
==**Geometrie**==
**Balken mit rechteckigem Querschnitt**
- Länge ==$L=1000\,\mathrm{mm}$==﻿
- Breite ==$b=100\,\mathrm{mm}$==﻿
- Höhe ==$h=100\mathrm{mm}$==﻿
==**Randbedingungen**==
- feste Einspannung an der Oberseite
- Belastung durch Eigengewicht (==**Gewichtskraft**== ==$g=9{,}8066\frac{m}{s}$==﻿)
  
### 2.2 ==Gesucht==
  
**für folgende Abstraktionen:**
1. **3D Vollmodell**
2. **3D Modell (Symmetrie)**
3. **2D (ebener Spannungszustand)**
4. **1D (Beam Elemente)**
  
**soll jeweils bestimmt werden** :
- Die **maximale Verschiebung in Längsrichtung** (y-Achse) $u_{y,max}$﻿
- Die **maximale Normalspannung in Längsrichtung** (y-Achse) $\sigma_{y,max}$﻿
  
### 2.3 ==**Hinweise**==
  
**ALLGEMEIN**:
- **Materialerstellung** (`**Dichte**`)
    
    **Dichte** (`Density`) kann unter `Physical Properties` hinzugefügt werden
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled.png|Untitled.png]]
    
      
    
- Denken Sie daran ihr erstelltes Material auch zuzuweisen !
  
**ABSTRAKTIONEN**:
- **3D Vollmodell** `**Geometrieerstellung**` `**feste Einspannung**`
    - `**feste Einspannung**` Wenn Sie die ganze Fläche als feste Einspannung definieren, wird Ihre Spannung dort überhöht sein (siehe Übung 1 und [Beispiel B aus Praktikum 1](https://www.notion.so/b0d0cf992c2948ffbaf0f015bd4fb09b?pvs=21)) .
    - `**feste Einspannung**` Deswegen Fläche der Einspannung in der Ebene festhalten und nur mittleren Punkt fixieren> [!important]  
        > Achten Sie darauf das dabei die Rotation unterdrückt wird. Im einfachsten Fall erreicht man dies indem man Remote Displacement auf den Punkt setzt und alle Freiheitsgrade auf Null setzt  
        
    - `**Geometrieerstellung**` Um mittleren Punkt (auf Einspannfläche) zu bekommen, sollte der Balken im Querschnitt in 4 Teile geteilt werden.
    - `**Geometrieerstellung**` Die geviertelte Geometrie muss über `Shared Topology` wieder **verbunden** werden (damit Netz über alle Geometrien verbunden ist)
- **3D Modell (Symmetrie)** `**Geometrie unterdrücken**` `**Symmetrierandbedingung**`
    
    - `**Geometrie unterdrücken**` **Nur eins von den vier geviertelten Geometrien verwenden**
        
        Wenn Sie zuvor das Vollmodell bereits geviertelt haben, so können Sie jetzt einfach 3 Körper über Rechtsklick im Strukturbaum → `Suppress Body` unterdrücken und können somit die gleiche Geometrie verwenden
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 1.png|Untitled 1.png]]
        
    
    - `**Symmetrierandbedingung**` Fügen Sie jeweils eine Symmetrieebene ein für jede Symmetrie die Sie angenommen haben (Anleitung siehe unten)
    
    - 📋`Anleitung (Allg)` ==**(**====Mechanical)== **==Symmetrieebenen==** ==einfügen==
        
        ---
        
        1. `**Strukturbaum**`: Rechtsklick `Model` → `Insert` → `Symmetry`
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 2.png|Untitled 2.png]]
            
            ---
            
        2. `**Strukturbaum**`: Rechtsklick `Symmetry` → `Insert` → `Symmetry Region`
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 3.png|Untitled 3.png]]
            
            ---
            
        3. **Menüleiste** (Oben) **Reiter**: `**Display**`**:** `**Show**` **→** `**All Coordinate Systems**`> [!important]  
            > Hilft bei der Auswahl von Symmetry Normal (siehe Punkt 4)  
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 4.png|Untitled 4.png]]
            
            ---
            
        4. `**Strukturbaum**`: vorher erstelle `Symmetry Region` **anklicken** und im Detailfenster unter `Geometry` die Fläche (3D) oder Linie (2D) oder Punkt (1D) auswählen die in der Symmetrieebene liegt und unter `Symmetry Normal` die Normale zu dieser Ebene einstellen
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 5.png|Untitled 5.png]]
            
            ---
            
    
- **2D (ebener Spannungszustand)** `**Geometrieerstellung**` `**Ansicht mit Dicke**`
    
    - **ℹ️ Geometrieerstellung und Einstellungen für** `**ebenen Spannungszustand**` **(**`**plane stress**`**)**
        - ==**SpaceClaim**====: Geometrie erstellen==
            1. **Skizze in x-y Ebene**
                
                Neue Skizzenebene auswählen (Icon unten) und auf z-Achse klicken
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 6.png|Untitled 6.png]]
                
            2. Skizze wird nach verlassen den Skizzenmodus **...**
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 7.png|Untitled 7.png]]
                
                ... als **Surface** im Strukturbaum angezeigt (keine weitere Aktion notwendig!)
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 8.png|Untitled 8.png]]
                
        - ==**Workbench Projektmenü**====: Geometrie als 2D einstellen==
            1. ==Rechtsklick== `Geometry` → `Properties`
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 9.png|Untitled 9.png]]
                
            2. Im `Eigenschaftsfenster` (Rechts): `Analysis Type` auf `2D` stellen
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 10.png|Untitled 10.png]]
                
            3. **Rechtsklick** auf `Model` → `Update`
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 11.png|Untitled 11.png]]
                
        - ==**Mechanical**====:== **==plane stress==** ==einstellen und== **==Dicke==** ==eingeben==
            1. `Geometry` **im Stukturbaum auswählen** und **im Detailfenster** `2D Behavior` auf `plane stress` stellen`Geometry` → `Properties`
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 12.png|Untitled 12.png]]
                
            2. SYS/Surface (ggf. anderer Name) **im Strukturbaum anklicken** und im `Detailfenster` die **Dicke** über `Thickness` eingeben
                
                ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 13.png|Untitled 13.png]]
                
    
    - `**Ansicht mit Dicke**` **Elemente mit Dicke**(`Mesh` im Strukturbaum auswählen + `Vernetzen` + Menüleiste (Reiter `Display`) → **Thick Shells and Beams** aktivieren
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 14.png|Untitled 14.png]]
        
- **1D (Beam Elemente)** `**Geometrieerstellung**` `**Ansicht mit Profil**` `**Spannungen darstellen**`
    
    - 🖱️`Anleitung (P4-BspA)` ==**(**====SpaceClaim)== **==Beam==** ==mit Profil erstellen (1D Abstraktion)==
        
        [http://ior.ad/7kX3](http://ior.ad/7kX3)
        
    
    - `**Ansicht mit Profil**` **Elementdarstellung des BEAM-Profils**
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 15.png|Untitled 15.png]]
        
    
    - 📋`Anleitung (Allg)` ==**(**====Mechanical)== \- ==(1D) Spannungen darstellen==
        
        ---
        
        1. `Strukturbaum`: **Rechtsklick** `Solution` → `Insert` → `Beam Tool` → `Beam Tool`
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 16.png|Untitled 16.png]]
            
            ---
            
        2. `Strukturbaum`: Rechtsklick `Beam Tool` → `Insert` → `Beam Tool` → `Stress` →
            
            ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 17.png|Untitled 17.png]]
            
            > [!important]  
            > Direct = Normalspannungen  
              
            > [!important]  
            > Min/Max Bending = Min/Max Biegespannung  
              
            > [!important]  
            > Min/Max Combined= Min/Max Summe aus Normal + Biegespannungen  
            
            ---
            
    
  
  
### 2.4 ==Lösung==
  
**Analytische Lösung:**
$u_{y,max}=0{,}0001833\,\mathrm{mm}$﻿
$\sigma_{y,max}=0{,}07701\,\mathrm{MPa}$﻿
  
**Simulation**
- **3D Vollmodell** `**Lösung**`
    
    Elementgröße = 25mm
    
    - ==**Randbedingungen**==
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 18.png|Untitled 18.png]]
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 19.png|Untitled 19.png]]
        
          
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 20.png|Untitled 20.png]]
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 21.png|Untitled 21.png]]
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 22.png|Untitled 22.png]]
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 23.png|Untitled 23.png]]
        
    
    ✅ $u_{y,max}=0{,}000183\,\mathrm{mm}$﻿
    
    ✅ $\sigma_{y,max}=0{,}0775\,\mathrm{MPa}$﻿
    
- **3D Modell (Symmetrie)** `**Lösung**`
    
    Elementgröße = 25mm
    
    - ==**Randbedingungen**== > [!important]  
        > Durch die Symmetrieebenen, muss keine weitere fixierte Lagerung vorgenommen werden  
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 24.png|Untitled 24.png]]
        
    - ==**Symmetrieebenen für Viertelsymmetrie  
          
        Die Symmetrie-Randbedingung sorgt dafür, dass sich die Geometrie aus der Symmetriebene nicht herausbewegen kann. Dadurch wird die Symmetriebedingung also erfüllt.**==
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 25.png|Untitled 25.png]]
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 26.png|Untitled 26.png]]
        
    
    ✅ $u_{y,max}=0{,}000183\,\mathrm{mm}$﻿
    
    ✅ $\sigma_{y,max}=0{,}0775\,\mathrm{MPa}$﻿
    
- **2D (ebener Spannungszustand)** `**Lösung**`
    
    Elementgröße = 25mm
    
    - **==Randbedingungen==**
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 27.png|Untitled 27.png]]
        
        ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 4- Abstraktionen/Praktikum 4 2. Beispiel A- Normalkraftstab unter Eigenlast/attachments/Untitled 28.png|Untitled 28.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/02 Beispiel A -  Normalkraftstab unter Eigenlast/attachments/Untitled 29.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/02 Beispiel A -  Normalkraftstab unter Eigenlast/attachments/Untitled 29.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/02 Beispiel A -  Normalkraftstab unter Eigenlast/attachments/Untitled 30.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/02 Beispiel A -  Normalkraftstab unter Eigenlast/attachments/Untitled 30.png]]
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/02 Beispiel A -  Normalkraftstab unter Eigenlast/attachments/Untitled 31.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/02 Beispiel A -  Normalkraftstab unter Eigenlast/attachments/Untitled 31.png]]
        
    
    ✅ $u_{y,max}=0{,}000183\,\mathrm{mm}$﻿
    
    ✅ $\sigma_{y,max}=0{,}0772\,\mathrm{MPa}$﻿
    
    > [!important]  
    > Hier hätte man ebenfalls eine Halbsymmetrie verwenden können  
    
- **1D (Beam Elemente)** `**Lösung**`
    
    Elementgröße = 25mm
    
    - ==**Randbedingungen**==> [!important]  
        > Das Problem mit der Querkontraktionsunterdrückung haben wir hier nicht, da wir den Balken ja nur im Schwerpunkt (entlang der Linie) festhalten können  
        
        ![[Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/02 Beispiel A -  Normalkraftstab unter Eigenlast/attachments/Untitled 32.png|Angewandte FEM (Strukturmechanik)/P4 - Abstraktionen/02 Beispiel A -  Normalkraftstab unter Eigenlast/attachments/Untitled 32.png]]
        
    
    ✅ $u_{y,max}=0{,}000183\,\mathrm{mm}$﻿
    
    ✅$\sigma_{y,max}=0{,}0769\,\mathrm{MPa}$﻿$\sigma_{y,max}=0{,}0772\,\mathrm{MPa}$﻿ (`Direct Stress`)
    
  
### 2.5 ==Diskussion==
  
**Analytisch**
**3D Vollmodell**
**3D Modell (Symmetrie)**
**2D (ESZ)**
1**D (Beam)**
  
$u_{y,max}=0{,}0001833\,\mathrm{mm}$﻿
$u_{y,max}=0{,}000183\,\mathrm{mm}$﻿
$u_{y,max}=0{,}000183\,\mathrm{mm}$﻿
$u_{y,max}=0{,}000183\,\mathrm{mm}$﻿
$u_{y,max}=0{,}000183\,\mathrm{mm}$﻿
  
$\sigma_{y,max}=0{,}07701\,\mathrm{MPa}$﻿
$\sigma_{y,max}=0{,}0775\,\mathrm{MPa}$﻿
$\sigma_{y,max}=0{,}0775\,\mathrm{MPa}$﻿
$\sigma_{y,max}=0{,}0772\,\mathrm{MPa}$﻿
$\sigma_{y,max}=0{,}0769\,\mathrm{MPa}$﻿
  
Alle Abstraktionen haben die Verschiebung (exakt) und die Spannung (sehr genau) wiedergegeben.
  
Der Sinn der Abstraktion ist in der Einsparung von Rechenzeit, durch Reduzierung der Elementanzahl (und dabei auch weniger Freiheitsgrade). Schauen wir uns also mal die Anzahl der Elemente (bei gleicher Netzgröße von 25mm) für die verschiedenen Abstraktionen an:
  
**3D (Vollmodell)**
**3D Modell (Viertelsymmetrie)**
**2D (ESZ) (Vollmodell)**
**2D (ESZ) (Halbsymmetrie)**
1**D (Beam)**
  
**640 (mit 24 Freiheitsgraden)**
**160 (mit 24 Freiheitsgraden)**
**160 (mit 8 Freiheitsgraden)**
**80 (mit 8 Freiheitsgraden)**
**40 (mit 6 Freiheitsgraden)**
  

> [!important]  
> Das 3D Modell ist in ANSYS Workbench vermutlich das einfachste zu erstellende Modell, mit dem man immer zur Lösung kommt. Sobald man eine Abstraktion wählt, muss man prüfen ob diese überhaupt anwendbar ist und dann die Besonderheiten bei der Erstellung beachten.  
  
Haben Sie jedoch ein sehr großes 3D Modell, welches viele Minuten oder gar Stunden rechnet, so lohnt es sich zu prüfen ob man durch Abstraktion nicht deutlich Rechenzeit sparen kann, gerade wenn Sie eine Parametervariation durchführen wollen.  