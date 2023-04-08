---
theme: white
date created: Friday, April 29th 2022, 11:41:44 am
date modified: Wednesday, October 12th 2022, 7:05:44 pm
---

# Virtualization of memory

[[GNU Linux]] and most modern [[Kernel]] provide [[Virtual memory management]].

---

## Memory access

The CPU can only access
- [[Register]]
- [[RAM]] (*main memory*)

Any data stored on disk **must be first transferred** into *main memory* before it can be used.

---

## Memory protection

- **User** [[Process]] **must be** **restricted** to only access memory that **belongs** to them
- The [[Operating System]] has
	- **unrestricted** access to main memory
	- **unrestricted** access to the entire CPU instruction set

---

## Privilege levels

To provide **memory protection**, there are CPU modes :
1. **Privileged mode**
2. **User mode**

[[System Call]] allow mode switch

---

## Address space

[[Address Space]] or [[Address Space of a Process]] is the range of addresses that can be addressed or accessed by the CPU

---

## Address space

There are two types of address space :
- Virtual : that can be accessed by the CPU
- Physical : **in RAM** that can be accessed by the CPU

---

## Address space

### Examples

- IA-32, protected mode:
	- 32 bit virtual address space (4GB)
	- 32 bit physical address space (4GB)
- X86-64 (or AMD64), long mode:
	- 48 bit virtual address space (256TB)
	- 40 bit physical address space (1TB)

---

## Process address space

Process address space is an **abstraction** created by the [[Operating System]]

![[Pasted image 20221012190530.png]]

---

[[GNU Linux]] is exploiting a property common to most programs : **locality** for its [[Virtual memory management]].

---

## Locality

Locality can be :
- **Spatial locality**: tendency of a program to reference memory addresses that are near those recently accessed (because of **sequential** instruction & **sequential** processing of [[Data Structures]]).
- **Temporal locality**: tendency of a program to access the same memory addresses in the future/recent past

---

A [[Virtual memory scheme]] splits the memory used by each program into small, fixed-size units called [[Page]].
The [[RAM]] is divided into a series of [[page frame]] of the same size.

![Virtualisation](http://cui.unige.ch/~chanel/prez/presentations/sys-exploitation/1.processes/img/virtualization.svg)

---

## References

- <http://cui.unige.ch/~chanel/prez/presentations/sys-exploitation/>

---
