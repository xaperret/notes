---
theme: white
date created: Friday, April 29th 2022, 11:41:44 am
date modified: Tuesday, October 11th 2022, 7:21:21 pm
---

# Virtual Memory

![[Pasted image 20220223104844.png]]

---

The [[Virtualization of memory]] **objective** is to allow the following operations
- to Define an **addressing space** that is **independent** for each [[Process]]
- To **address** more memories than is *physically available* (e.g.: [[RAM]]).
- Share **addressing space** between [[Process]].
- Share **file content** as if [[File]]s were in memory.

---

## Conversion of a virtual address into its physical address

The conversion of a virtual address into its physical address is done by the [[Memory Management Unit]] which is a piece of [[Hardware]]

---

![Convertion](http://cui.unige.ch/~chanel/prez/presentations/sys-exploitation/1.processes/img/convert.svg)

Half the memory is dedicated to a **page number**, the other half serves as an [[Offset]] in the actual [[Page]].
The address of the **physical [[Page]]** or **physical address** is found in the table of pages' process.

---

# References

---
