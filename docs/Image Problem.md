---
publish: "true"
---

## Problem with images with spaces

## not working `![[file.png|300]]

![[Angewandte FEM (Strukturmechanik)/attachments/BeispielA_Aufgabenstellung.png|300]]

## working solution with `![](<file.png>){width="300"}

![Image title](<Angewandte FEM (Strukturmechanik)/attachments/BeispielA_Aufgabenstellung.png>){width="300"}

# without any space in path
filename="BeispielA.png"
![[BeispielA.png|300]]
filename="BeispielA_Aufgabenstellung.png"
![[BeispielA_Aufgabenstellung.png|300]]
filename="bikelab.png"
![[bikelab.png|50]]
# with space in folder path

![[attach ments/BeispielA_Aufgabenstellung.png|300]]

# with space and ( ) in folder path

![[attach ments (test)/BeispielA_Aufgabenstellung.png|300]]

![[bikelab.png|50]]

![[BeispielAAufgabenstellung.png|300]]