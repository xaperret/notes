---
date updated: 2021-10-19 16:46

---

Topic: #operating_system #linux
Tags: #review #pn_1_9
Links: [[Operating System]]
Date Created: 06-10-21

---

# Group

## Group in few words

## Group in Linux in details

The purpose of a [[Group]] is to **restrict access** to [[Directory]], resources or [[Peripheral]]. A [[User in Linux]] can be part of one or multiple [[Group]].

### Exercise

With `whoami` get your login information

```shell
➜  ~ whoami
xavierperret
➜  ~ 
```

With `groups` get your groups

```shell
➜  ~ groups
xavierperret sudo
➜  ~ 
```

Get the combination of both last command and get the user id with `id`

```shell
➜  ~ id
uid=1000(xavierperret) gid=1000(xavierperret) groups=1000(xavierperret),27(sudo)
➜  ~ 
```

## References

- [[ISC-332 - Programmation système]]
