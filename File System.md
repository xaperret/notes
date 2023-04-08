---
date created: Friday, November 19th 2021, 1:59:41 pm
date modified: Wednesday, December 1st 2021, 5:07:27 pm
---

Topic: #operating_system #linux

Tags: #review #pn_1_9

Links: [[Operating System]]

Date Created: 06-10-21

---

# File System

## File System in Few Words

A [[File System]] is a [[System]] that allows us to **organize and manage persistent [[Data]]** in a structured manner. This structured manner is often represented by [[File|files]] and [[Directory|directories]].

The basic unit of a [[File System]] is call a **logical block**, which is multiple contiguous physical blocks on the [[Disk]] device on which the [[File System]] sits.

![[Pasted image 20211201152803.png]]

So, a [[File System]] contains :

- [[Boot block]], the thing that contains information to boot the [[Operating System]]
- [[Superblock]], the thing that contains information about size of Inode, logical blocks and number of logical blocks
- [[Inode or Index node]] table or i-list, contains information about each [[File]] and [[Directory]]
- [[Data block]]

A [[File System]] on [[GNU Linux]] is built using `mkfs` command, it's just a frontend for [[File System|file systems]].[^1]

Examples :

- [[ext4]], with a standard 4 KiB block size
- [[fat]]
- [[tmpfs]]

## File System in Details

- [[Anatomy of a File or Directory]]
- [[Different types of File System]]
- [[File System Tree Structure]]
- [[Everything is a file]]
- [[Device Special File]]
- [[File]]
- [[Inode or Index node]]

### Useful Related Command

- [[touch]]
- [[mkdir]]
- [[mv]]
- [[cp]]
- [[rm]]
- [[rmdir]]
- [[zero]]
- [[null]]
- [[cat]]
- [[grep]]

#### Exercises Related to Said Commands

- Create backup folder
  - `mkdir backup`
- Try to copy image `images/bird00.jpg`

```shell
➜  ressources git:(master) ✗ cp images/bird00.jpg test.jpg
cp: cannot open 'images/bird00.jpg' for reading: Permission denied	
```

- Copy all dog images to backup
  - `cp images/dog* backup/`
- Create an empty file inside `backup/myimage.png`
  - `touch backup/myimage.png`
- Rename previous file to `backup/myimage.jpg`
  - `mv backup/myimage.png backup/myimage.jpg`
- Move in one command cats image with 00-09 and 90-99 number to backup
  - `mv images/cat0?.* images/cat9?.* backup/`

With `mount` find where are mounted [[File System]] [[ext4]] [[fat]] [[tmpfs]]

```shell
$ mount -l -ttmpfs,ext4,nfs
➜  ~ mount | grep ext4
/dev/mapper/data-root on / type ext4 (rw,noatime,errors=remount-ro)
```

As we can see there are multiple [[File System]] living on one [[Operating System]].

```shell
➜  ~ mount | grep fat 
/dev/sda2 on /recovery type vfat (rw,relatime,fmask=0077,dmask=0077,codepage=437,iocharset=iso8859-1,shortname=mixed,errors=remount-ro)
/dev/sda1 on /boot/efi type vfat (rw,relatime,fmask=0077,dmask=0077,codepage=437,iocharset=iso8859-1,shortname=mixed,errors=remount-ro)
```

```shell
➜  ~ mount | grep tmpfs
udev on /dev type devtmpfs (rw,nosuid,noexec,relatime,size=16325744k,nr_inodes=4081436,mode=755,inode64)
tmpfs on /run type tmpfs (rw,nosuid,nodev,noexec,relatime,size=3276960k,mode=755,inode64)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,inode64)
tmpfs on /run/lock type tmpfs (rw,nosuid,nodev,noexec,relatime,size=5120k,inode64)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,size=4096k,nr_inodes=1024,mode=755,inode64)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,size=3276956k,nr_inodes=819239,mode=700,uid=1000,gid=1000,inode64)
```

Knowing there are two types of peripheral, block, indicated in the file mode by the symbol `b`, and character list every peripheral of type `bloc`

```shell
```

With `zero`, fill a 1Mb file of zeros.

```shell
➜  ~ dd if=/dev/zero of=test bs=1024 count=1000
1000+0 records in
1000+0 records out
1024000 bytes (1.0 MB, 1000 KiB) copied, 0.00484212 s, 211 MB/s
```

Here's another way to do it.

```shell
➜  ~ dd if=/dev/zero of=test bs=1M count=1
```

`dd` write `blocks` of by default 512 bytes.

With `null`, list `/tmp` without error

```shell
➜  ~ ls -lha /tmp 1> test 2> /dev/null
```

## References

- [[@arpaci-dusseauOperatingSystemsThree2018]] p. 12
- [[@kerriskLinuxProgrammingInterface2010]] p. 254, p.256
- [[ISC-332 - Programmation système]]
- https://en.wikipedia.org/wiki/Ext4

























[^1]: deprecated method according to man
[^2]: [[User, Groups and rights in Linux]]
