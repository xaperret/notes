---
date updated: 2021-10-24 15:47

---

Topic: #operating_system
Tags: #review #pn_2_1
Links: [[Process]]
Date Created: 20-10-21

---

# Program

## Program in few words

## Program in details

A [[Program]] is **a [[File]]** containing information that describe **how to build a [[Process]] when needed**.

- _Binary format identification_, **Metadata** about the **format** of the executable file for the [[Kernel]]. Without this, the [[Kernel]] couldn't know how to interpret the rest of the information found in the [[Program]] [[File]].
- _[[Machine-language]] instructions_, Encode the algorithm of the program
- _Program entry-point address_, Location of the starting instruction
- _Data_, [[Literal in Java|Literals]] and values for [[Variable|variables]]
- _Symbol and relocation tables_, Locations and Names for [[Function|functions]] and [[Variable|variables]].
- _Shared-library and dynamic-linking information_, Fields listing the shared libraries and pathname of the [[Dynamic Linker]] to use to load these libraries.
- _Other information_, Any helpful information to build a [[Process]]

## References

- [[@kerriskLinuxProgrammingInterface2010]] p. 113-114
