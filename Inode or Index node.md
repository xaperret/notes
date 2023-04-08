---
date created: Thursday, November 25th 2021, 1:15:52 pm
date modified: Wednesday, December 1st 2021, 5:47:54 pm
---

- Topic: #linux
- Tags: #review #pn_2_1
- Links: [[File]] [[File System]]
- Date Created: 25-11-21

---

# Inode

## Inode in Few Words

An [[Inode or Index node]] is used to provide information about [[Data block]] and it is identified by its **i-node number**, a **unique number**.

Each [[Data block]] has a [[Inode or Index node]], or one could say each [[File]] has an i-node. But it's possible to have multiple links pointing to the same i-node, which will point to a group of [[Data block]] that represents our [[File]].

The first number in front of each row is that **unique number** that identifies each [[Inode or Index node]].

```shell
➜  ~ ls -li
total 108
28836308 drwxr-xr-x 3 xavierp xavierp  4096 Nov 19 13:54  Android
32900407 drwxr-xr-x 3 xavierp xavierp  4096 Nov 25 14:01  AndroidStudioProjects
26479966 drwxr-xr-x 6 xavierp xavierp  4096 Nov 19 13:48  Apps
26476551 drwxr-xr-x 2 xavierp xavierp  4096 Nov 18 22:18  Desktop
26479922 drwxr-xr-x 3 xavierp xavierp  4096 Nov 30 21:41  Documents
26479919 drwxr-xr-x 2 xavierp xavierp  4096 Nov 30 21:48  Downloads
26480070 drwxr-xr-x 4 xavierp xavierp  4096 Nov 19 15:39  go
26480107 -rw-r--r-- 1 root    root     1923 Nov 21 15:57  grub
28052226 drwxr-xr-x 4 xavierp xavierp  4096 Nov 19 12:38  Insync
```

- [[File Type]]
- [[Owner]], **UID**
- [[Group]], **GID**
- [[Permission]], owner, group, other
- Timestamps
	- last access to the file `ls -lu`
	- last modification of the file `ls -l`
	- last status change `ls -lc`
- Number of [[Hard Link]]
- Size of the file in [[Byte|bytes]]
- Number of blocks allocated to the [[File]], in 512 [[Byte|bytes]]
- Pointers to the [[Data block]] of the [[File]]

![[Pasted image 20211201171651.png]]

An [[Inode or Index node]] can be linked by several [[File Link]] meaning we can arrive to the same [[Inode or Index node]] with different path.

[[Inode or Index node]] is a list of index, meaning it will point to several places of the data block.

## Inode in Details

![[Pasted image 20211201174750.png]]

Inode could also represent:
- a [[Pipe]]
- a [[Device]]

## References

- [[ISC-332 - Programmation système]]
- [[@kerriskLinuxProgrammingInterface2010]] p. 256
