---
date created: Friday, November 19th 2021, 1:59:39 pm
date modified: Wednesday, December 1st 2021, 3:14:19 pm
---

Topic: #operating_system

Tags: #review #ipn_2_1

Links: [[File System]]

Date Created: 19-10-21

---

# Device Special File

## Device Special File in Few Words

A [[Device Special File]] is a type of [[File]] that represents a [[Device]] on the system and appears under `/dev/` in [[GNU Linux]].

Each [[Device]] type has a corresponding [[Device driver]], which has a set of functions for input/output and an API with fixed functions, which allows higher **[[Abstraction]]** which in turns gives us **universality of I/O**.

![[1634664486600.jpg]]

There are two types of device :

- [[Character devices]], where data is handled **character-by-character**, e.g. *terminal*, *keyboard*
- [[Block devices]], where data is handled **block by block**, whose size depends on the **device type**, but are **multiple of 512 bytes**.

## Device Special File in Details

### Creating a Device

Using `mknod` command, the [[Superuser]] can create a device file.

### Identification

Each **device file** has a

- *Major ID number*, identifies the **general class of device**, for the [[Kernel]] to **select the proper [[Device driver]]**
- *Minor ID number*, identifies a **particular device** within the **general class**

## References

- [[@kerriskLinuxProgrammingInterface2010]] p. 252-253
