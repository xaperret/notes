---
date modified: Wednesday, December 1st 2021, 11:57:19 am
date created: Thursday, November 25th 2021, 1:08:56 pm
---

- Topic: #operating_system #linux
- Tags: #review #ipn_1_6
- Links: [[Operating System]]
- Date Created: 25-11-21

---

# File

## File in Few Words

A file doesn't really exist if it's not opened. It's a [[File Link]], [[Inode or Index node]] and [[Data]].

There are file that are simulated.

- `/dev/`, links found in this folder are not regular [[File]] they are [[Peripheral]]
- `/proc/`, numbers representing [[Process]]
- `/sys/`, system information

Here we can see the type of file system

```shell
➜  ~ mount
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
sys on /sys type sysfs (rw,nosuid,nodev,noexec,relatime)
dev on /dev type devtmpfs (rw,nosuid,relatime,size=16371476k,nr_inodes=4092869,mode=755,inode64)
run on /run type tmpfs (rw,nosuid,nodev,relatime,mode=755,inode64)
```

- [[Hard Link]]
- [[Lost-Found]]

### Deletion Process

1. Delete link
2. Decrement number of link in Inode
3. Is Inode = 0
4. If yes delete data
5. If no, don't do anything

If a link is deleted but the Inode is not then it is put into [[Lost-Found]].

## File in Details

- [[Device Special File]]
- [[Inode or Index node]]

## References

- [[ISC-332 - Programmation système]]
