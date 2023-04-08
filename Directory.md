---
date updated: 2021-11-25 15:49
---

Topic: #c_programming
Tags: #review #pn_2_1
Links: [[File]]
Date Created: 25-11-21

---

# Directory

## Directory in few words

## Directory in details

A [[Directory]] is a [[File Link]] and an [[Inode or Index node]] which points to a block of data containing a list of [[File Link]] and their associated [[Inode or Index node]], each item is called a _Directory Entry_.

To open a file

```c
open(".bashrc", ...) // tries to find this in the File Link list, if not found returns an error
```

## References

- [[ISC-332 - Programmation système]]
