---
date modified: Tuesday, January 18th 2022, 4:28:02 pm
sr-due: 2021-12-01
sr-interval: 24
sr-ease: 256
tags:
  - 'operating_system'
  - 'review'
  - 'pn_1_9'
date created: Sunday, January 16th 2022, 4:01:06 pm
date modified: Tuesday, January 18th 2022, 4:28:02 pm
---

- Topic: #operating_system
- Tags: #review #pn_1_9
- Links: [[Operating System]]
- Date Created: 07-10-21

---

# Process

## Process in Few Words
A Process is an [[Instance]] of an executing [[Program]], it contains :

- [[Machine Code]]
- Data in [[Virtual Memory]]
- [[File Descriptor]]
- [[Owner]] with [[Permission]]
- [[State]]
- [[Instruction Pointer]]
- [[PID]]
- [[PPID]]
- [[Page table]]

![De l'executable au processus](http://cui.unige.ch/~chanel/prez/presentations/sys-exploitation/1.processes/img/exe_to_proc.svg)

### Multitasking
A [[CPU]] core can execute one [[Process]] at a time. The one responsible for managing [[Process]] such as to make pseudo-[[Multitasking]] is the [[Operating System]].

Indeed, the illusion of **multitasking** is done by **virtualizing** the [[CPU]].

### Process and the Kernel
Process between `[ ]` belong to the kernel.

![[PNG image.png]]

### Process ID and Parent Process ID
Each [[Process]] has a **Process ID or _PID_** and a **Parent Process ID or _PPID_**, ==except for the [[Process]] 0==. It's a **positive integer that uniquely identifies** the [[Process]] on the system.

Apart from some [[Process|processes]] like `init` (PID 1) there is **no fixed relationship** between a [[Program]] and its PPID.

In [[GNU Linux]] [[Kernel]], there is a limit of 32'767 [[Process]].

### Useful Command
- [[ps]]
- [[pstree]]
- [[top]]
- [[kill]]

## Process in Details
- [[Exercise and Processes]]
- [[Address Space of a Process]]
- [[Memory Layout of a Process]]

## References
- [[ISC-332 - Programmation système]]
- [[@kerriskLinuxProgrammingInterface2010]] p. 113-115
- [[@arpaci-dusseauOperatingSystemsThree2018]] p. 25
