---
publish: "true"
title: Willkommen auf der Seite
---

Willkommen auf der Seite von Prof. Schönfelder und M.Eng. Felix Kaule!
# Visualisierung der Tastatur für Anleitungen

++ctrl+alt+del++

1. Inhalt mit Mauszeiger auswählen
1. Mit ++ctrl+c++ Inhalt kopieren 
1. Mit ++ctrl+v++ Inhalt einfügen 
# Bilder

Zur Anpassung der Größe funktioniert die `Obsidian` Variante des Bildereinfügens mit `![[image.png|300]]`  für eine Breite von 300px nicht. Hier muss die Standard `Markdown` Variante verwendet werden mit dem zusätzlichen Attribut `width`. Zusätzlich muss der Dateiname in `<` `>`  gesetzt werden wenn Leerzeichen im Pfad vorhanden sind: `<Pfad mit Leerzeichen/Datei name.png>`

```markdown
![Image title](<Pfad mit Leerzeichen/Datei name.png>){width="300"} 
```

Hier ein Beispielbild:
![Image title](<Angewandte FEM (Strukturmechanik)/attachments/BeispielA_Aufgabenstellung.png>{width="400"} 
# Content Tabs

## Grouping code blocks

=== "C"

    ``` c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```

## Grouping other content

=== "Unordered list"

    * Sed sagittis eleifend rutrum
    * Donec vitae suscipit est
    * Nulla tempor lobortis orci

=== "Ordered list"

    1. Sed sagittis eleifend rutrum
    2. Donec vitae suscipit est
    3. Nulla tempor lobortis orci

## Embedded content
!!! example

    === "Unordered List"

        ``` markdown
        * Sed sagittis eleifend rutrum
        * Donec vitae suscipit est
        * Nulla tempor lobortis orci
        ```

    === "Ordered List"

        ``` markdown
        1. Sed sagittis eleifend rutrum
        2. Donec vitae suscipit est
        3. Nulla tempor lobortis orci
        ```