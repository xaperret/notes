---
date created: Wednesday, December 1st 2021, 11:58:41 am
date modified: Wednesday, December 1st 2021, 12:04:53 pm
---

- Topic: #linux #FileSystem
- Tags: #review #pn_2_1
- Links: [[Device Special File]]
- Date Created: 01-12-21

---

# Device Driver

## Device Driver in Few Words

A [[Device driver]] is a piece of code in the [[Kernel]] that deals with **input output** on an **associated piece of [[Hardware]]**.

Each [[Device driver]] provides a **fixed set** of [[API]] functions and has routines for various [[System Call]], such as `open(), close(), read(), write(), mmap(), ioctl()`.

The **advantage** of such an [[Abstraction]] is that it hides the inner workings of each piece of [[Hardware]] and allows the User or Kernel to communicate with the [[Hardware]] without having to have special implementations for each one, allowing **universality of I/O**.

## Device Driver in Details

## References

- [[@kerriskLinuxProgrammingInterface2010]] p.252
