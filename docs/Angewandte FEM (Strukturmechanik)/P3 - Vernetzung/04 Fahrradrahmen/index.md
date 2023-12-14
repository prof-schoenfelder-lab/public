---
publish: "true"
title: 04 Fahrradrahmen
---

# 4. Fahrradrahmen
Wir verwenden nun eine abgewandelte Variante des Fahrradrahmens aus dem letzten Praktikum um die gelernten Methoden zur Vernetzung zu üben.
Dazu verwenden wir zunächst den **Rahmen ohne Schweißnähte** (analog wie das Modell im zweiten Praktikum verwendet wurde).
  
![[Angewandte FEM (Strukturmechanik)/P3 - Vernetzung/04 Fahrradrahmen/attachments/Untitled 1.png|Angewandte FEM (Strukturmechanik)/P3 - Vernetzung/04 Fahrradrahmen/attachments/Untitled 1.png]]
  
## 4. 1 Vernetzung ohne Schweißnähte

> [!important]  
> Diese Aufgabe dient nur der Verdeutlichung, dass eine Netzverfeinerung immer höhere Spannung generiert, wenn eine Geometrie ohne Kantenverrundung verwendet wird. Bei einem realen Bauteil sollten Sie also immer die Kanten abrunden.  
  

> [!important]  
> Laden Sie im OPAL folgende Datei runter Praktikum \ Praktikum 03 - Vernetzung \ 2019R2_Solid_Gesamtrahmen.scdoc und fügen Sie diese zu einer neuen strukturmechanischen Analyse hinzu.  
  
> [!important]  
> Vernetzen Sie den Rahmen nach den erlernten Methoden  
  
> [!important]  
> Verwenden Sie die [[Praktikum 2 4. Fahrradrahmen|Praktikum 2 4. Fahrradrahmen]] und prüfen Sie ob die Vernetzung für Bewertung der von-Mises Spannung ausreicht  
**Zur Erinnerung die Randbedingungen für die Lenkkopfsteifigkeit:**
Bei der Lenkkopfsteifigkeit wird das Hinterrad fixiert und im Abstand von `1000mm` von der Mitte des Steuerrohrs entfernt eine Kraft von `100N` senkrecht zum Fahrrad eingeleitet (in unserem Fall in die globale x-Richtung)
  
- Lösung mit `**Tetrateder**` Elementen `**ohne Schweißnähte**`
    
    **Vernetzung**:
    
    1. globale Vernetzung
    2. lokale Vernetzung mit `Refinement` (höchste Stufe) im Bereich der Schweißnaht
    
      
    
    > [!important]  
    > zu kleine Netzgrößen sind hier nicht empfohlen, da sonst die Lösung zu lange dauert!  
    
      
    
    **Spannung und Verformung in Abhängigkeit von der Vernetzung**
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 4. Fahrradrahmen/attachments/Untitled.png|Untitled.png]]
    
    von Mises Spannung für globale Netzgröße von 10mm und Refinement Stufe 3 an der Kante
    
    ![[tetra_stress_ohne.png|tetra_stress_ohne.png]]
    
    ![[tetra_disp_ohne.png|tetra_disp_ohne.png]]
    
    > [!important]  
    > Die maximale Verformung ändert sich nur minimal, die Spannung nimmt bei kleinerer Vernetzung jedoch immer mehr zu und würde auch keinen Grenzwert erreichen. Es ist also eine Verrundung der Kante notwendig.  
    
      
    
      
    
## 4. 2 Vernetzung mit Schweißnähten
  

> [!important]  
> Kopieren Sie die Analyse und fügen Sie mit SpaceClaim Schweißnähte an kritischen Stellen hinzu durch eine Kantenverrundung von 5mm hinzu und vernetzen Sie diese entsprechend.  
  
Berechnen Sie anschließend die von-Mises-Spannung (Randbedingungen bleiben gleich).  
  
- Lösung mit `**Tetrateder**` Elementen **`mit Schweißnähten`**
    
    Kantenverrundung von 5mm am Steuerrohr
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 4. Fahrradrahmen/attachments/Untitled 1.png|Untitled 1.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 4. Fahrradrahmen/attachments/Untitled 2.png|Untitled 2.png]]
    
    von Mises Spannung für globale `Vernetzung von 5mm` und lokale Netzverfeinerung an der Schweißnaht mit `Refinement 3`
    
    ![[tetra_stress_beide.png|tetra_stress_beide.png]]
    
    ![[tetra_disp_beide.png|tetra_disp_beide.png]]
    
      
    
    > [!important]  
    > Diesmal bleibt die Spannung im Bereich von 42MPa  
    
- Zusatz: Vergleich aller Schweißnähte
    
    → Kantenverrundung zusätzlich an allen Bereichen wo eine Schweißnaht wäre
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 4. Fahrradrahmen/attachments/Untitled 3.png|Untitled 3.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 4. Fahrradrahmen/attachments/Untitled 4.png|Untitled 4.png]]
    
    ![[Notion/Angewandte FEM in der Strukturmechanik/Praktikum 3- Vernetzung/Praktikum 3 4. Fahrradrahmen/attachments/Untitled 5.png|Untitled 5.png]]
    
      
    
  
## 4. 3 Diskussion
  
In der Festigkeitsbewertung von Schweißnähten werden diese je nach Bewertungskonzept anders als hier abstrahiert. Die Darstellung der Schweißnähte als Verrundung dient somit nur der Verdeutlichung des Effekts der unendlich scharfen Kante.
