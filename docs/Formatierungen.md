---
publish: "true"
---

# Visualisierung der Tastatur für Anleitungen

++ctrl+alt+del++

1. Inhalt mit Mauszeiger auswählen
1. Mit ++ctrl+c++ Inhalt kopieren 
1. Mit ++ctrl+v++ Inhalt einfügen 
# Bilder

Zur Anpassung der Bildgröße (hier beispielhaft mit 300px Breite):

```markdown
![[image.png|300]]
```  

# Grids

<div class="grid cards" markdown>
- :fontawesome-brands-html5: __HTML__ for content and structure
- :fontawesome-brands-js: __JavaScript__ for interactivity
- :fontawesome-brands-css3: __CSS__ for text running out of boxes
- :fontawesome-brands-internet-explorer: __Internet Explorer__ ... huh?
</div>

<div class="grid cards" markdown>
- <img src="Angewandte FEM (Strukturmechanik)/attachments/BeispielA_Aufgabenstellung.png" alt="Beispiel A">
- <img src="Angewandte FEM (Strukturmechanik)/attachments/BeispielA_Aufgabenstellung.png" alt="Beispiel A">
- <img src="Angewandte FEM (Strukturmechanik)/attachments/BeispielA_Aufgabenstellung.png" alt="Beispiel A">
- <img src="Angewandte FEM (Strukturmechanik)/attachments/BeispielA_Aufgabenstellung.png" alt="Beispiel A">
</div>
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