---
date updated: "2021-10-06T16:21:09+02:00"
---

Topic: #operating_system #linux
Tags: #review #pn_1_9
Links: [[Operating System]]
Date Created: 06-10-21

---

# rm

## rm in few words

Delete the indicated file

## rm in details

### Exercises

- Why can't you delete `backup` ?
  - Because, it's not **empty** and it's a **folder**, which means we must do it **recursively**.
- Delete `backup/mybird.jpg`
  - `rm backup/mybird.jpg`
- Delete `backup` in one command
  - `rm -rf backup/`
- Try to delete `images/bird00.jpg` what happened ?
  - Could do it but it said write-protected because as a user I had

```shell
----rw-r-- 1 xavierperret xavierperret 17 Oct  6 15:05 images/bird00.jpg
```

- Because the user didn't have the right to "write", a warning appeared, but the file is still removable. To make it non-removable

```shell
➜  ressources git:(master) ✗ chmod u-x images
➜  ressources git:(master) ✗ rm images/bird01.jpg
rm: cannot remove 'images/bird01.jpg': Permission denied
```

- Copy `images` to `images-backup`, what happens ?

```shell
➜  ressources git:(master) ✗ cp images/ images-backup
cp: -r not specified; omitting directory 'images/'
➜  ressources git:(master) ✗
```

- We must do it recursively !

## References

- [[ISC-332 - Programmation système]]

### Parent References

- [[Operating System#References]]
