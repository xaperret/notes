---
date updated: 2021-10-19 16:39

---

Topic: #linux
Tags: #review #pn_1_9
Links: [[GNU Linux]]
Date Created: 06-10-21

---

# File naming Convention in Linux

## File naming Convention in Linux in few words

## File naming Convention in Linux in details

The maximum amount of characters to use is **255**. We can use every character, but there are some that should be avoided such as **space**, **`. * ? / !`**.
Files starting with `.` are **hidden**.

### Exercises

Which `ls` option allow us to see **hidden files** ?

```shell
-a
```

In the folder `bash`,
List every `JPEG` files inside `images/`

```shell
ls -la ressources/images/*.jpg
```

List every **bird** images

```shell
ls -la ressources/images/bird*.jpg
```

List every `PNG` **bird** images

```shell
ls -la ressources/images/bird*.png
```

List every **cat** images with a number between 90-99

```shell
ls -la ressources/images/cat9?.*
```

## References

- [[ISC-332 - Programmation système]]
