---
date updated: 2021-10-19 16:22

---

Topic: #operating_system
Tags: #review #pn_2_1
Links: [[Terminal vs Pseudo-Terminal]]
Date Created: 19-10-21

---

# Terminal

## Terminal in few words

## Terminal in details

The terminal is a type of **command-line interface**.
It sends characters between [[User]] [[Process]] and an [[I/O device]].

![[Pasted image 20211019161818.png]]

- `text` -> `terminal screen`

It is a tool to interact with the [[Shell]].

### Examples

#### `/dev/tty1`

The first virtual console. The `/dev/tty` device is the controlling [[Terminal]] of the current [[Process]].

#### `/dev/pts/0`

The first pseudoterminal device.

## References

- [[ISC-332 - Programmation système]]
- [[@wardHowLinuxWorks2021]] _3.4.7 Terminals: /dev/tty*, ..._
