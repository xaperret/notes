---
date updated: 2021-10-19 16:35

---

Topic: #operating_system #linux
Tags: #review #pn_1_9
Links: [[Operating System]]
Date Created: 06-10-21

---

# Move through Linux

## Move through Linux in few words

Using [[pwd]], [[ls]] and [[cd]].

## Move through Linux in details

The root is represented by **`/`**.
Folders are separated by **`/`**.
Every path who does not begun by `/` is **in the current folder**.
The **current directory** is represented by `.`.
The **parent directory** is represented by `..`.
The **home directory** is represented by `~`.

### Exercises

Where are you ?

```shell
pwd
```

Go to `/tmp`

```shell
cd /tmp
```

Check that you are at `/tmp`

```shell
pwd
```

List the content of the folder

```shell
ls
```

Come back

```shell
cd
```

Go into folder bash (cloned repo)

```shell
cd bash/
```

List content of `/tmp` from here

```shell
ls /tmp
```

What does `cd ~/././././bash` do ?
This make you go into the folder `bash`

What does `ls ~/./bash/../bash/../.` do ?
This list the content of the **home** directory.

How to list the `home` directory ?

```shell
ls ~
```

## References

- [[ISC-332 - Programmation système]]
