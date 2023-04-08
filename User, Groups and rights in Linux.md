---
date updated: 2021-10-19 16:47

date created: Friday, November 19th 2021, 1:59:36 pm
date modified: Wednesday, January 12th 2022, 10:15:00 am
---

Topic: #linux #operating_system

Tags: #review #pn_1_9

Links: [[Operating System]] [[User in Linux]]

Date Created: 06-10-21

---

# User, Groups and Rights in Linux

## User, Groups and Rights in Linux in Few Words

![[Pasted image 20210930131854.png]]

## User, Groups and Rights in Linux in Details

### File

| File        | Effects                                                       |
| ----------- | ------------------------------------------------------------- |
| **R**ead    | Read the file's content                                       |
| **W**rite   | Modify the file's content, if you try to delete it => Warning |
| e**X**ecute | Executer le fichier                                           |

### Directory

| Directory   | Effects                                                                      |
| ----------- | ---------------------------------------------------------------------------- |
| **R**ead    | List the files' names included in the directory not metadata                 |
| **W**rite   | Create, rename or delete files included                                      |
| e**X**ecute | Open directory, Execute files, See metadata, access files' content but not their names |

### Change Permission

As we can see on the image below permission are divided in three groups which themselves are divided into three different type of permission which are represented on **three bits**.

![[Pasted image 20210930144157.png]]

To change permission the easiest way is to do as follow `chmod GroupAddOrRemovePermission` which translate to:

```shell
$ chmod u+rw file.txt
```

which add read and write permission for the user on a file named `file.txt`.

### Exercise

Look at the content of `bird00.jpg`

`cat bird00.jpg`

Remove reading right to the user for the file `images/bird00.jpg`

`chmod u-r images/bird00.jpg`

Try to look at the content of `bird00.jpg`

```shell
  $ cat images/bird00.jpg\
  cat: images/bird00.jpg: Permission denied
```

Remove writing right to user of file `images/bird00.jpg`

`chmod u-w images/bird00.jpg`

Check changes

`ls -lh images/bird00.jpg`

```shell
➜  ressources git:(master) ✗ ls -lh images/bird00.jpg   
--w-rw-r-- 1 xavierperret xavierperret 17 Oct  6 15:05 images/bird00.jpg
➜  ressources git:(master) ✗ chmod u-w images/bird00.jpg 
➜  ressources git:(master) ✗ ls -lh images/bird00.jpg   
----rw-r-- 1 xavierperret xavierperret 17 Oct  6 15:05 images/bird00.jpg
```

Remove execution rights to `images/` folder

`chmod u-x images/`

List the content of the folder with `ls -l`

Give back the execution right to `images/` folder

`chmod u+x images/`

## References

- [[ISC-332 - Programmation système]]

### Parent References

- [[Operating System#References]]
