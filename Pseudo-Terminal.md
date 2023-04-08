---
date updated: 2021-10-19 16:09

---

Topic: #operating_system
Tags: #review #pn_2_1
Links: [[Terminal vs Pseudo-Terminal]]
Date Created: 19-10-21

---

# Pseudo-Terminal

## Pseudo-Terminal in few words

## Pseudo-Terminal in details

In dumb words, a [[Pseudo-Terminal]] is a tube that a [[program]] **to communicate with another [[Program]]** in a way that mimics a **communication with a [[Terminal]]**, because this tube makes the communication behaves **like a [[Terminal]]**.

![[Pasted image 20211019155942.png]]
In better words, a [[Pseudo-Terminal]] is a **[[virtual device]]** that provides **an [[interprocess communication channel]]**

![[Pasted image 20211019150129.png]]

### Master and Slave devices

So there are

- _master side_ or _master pseudo-terminal device_
- _slave side_

The [[Pseudo-Terminal]] or TTY or IPC makes both sides think the data is coming from a [[Terminal]]. They also will output data like they are outputting data to a [[Terminal]].

![[Pasted image 20211019160425.png]]

### Communication between programs

## References

- [[@kerriskLinuxProgrammingInterface2010]] p. 1375-1376
- <https://www.gnu.org/software/libc/manual/html_node/Pseudo_002dTerminals.html#:~:text=A%20pseudo%2Dterminal%20is%20a,is%20called%20the%20slave%20side>
- <http://www.rkoucha.fr/tech_corner/pty_pdip.html>
