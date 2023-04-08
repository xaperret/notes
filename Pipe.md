---
date updated: '2021-10-07T13:13:58+02:00'

---

Topic: #operating_system
Tags: #review #pn_1_9
Links: [[Operating System]]
Date Created: 06-10-21

---

# Pipe

## Pipe in few words

[[Pipe]] is used to pass output from one end of a [[Process]], what is called the [[Standard Output]] to another _end_ of another [[Process]], which we call the [[Standard Output]].

## Pipe in details

### Examples

Use `ls -l` to list `cat*.jpg` inside the folder `images` without using **any other option to** `ls`

```shell
ls -l images/ | grep cat
```

`/mails` contains `.txt` files, retrieve only the mails from university members, sort it alphabetically, without duplicates

```shell
$ cat mails/mail*.txt | grep @unige | sort -u # one possibility
$ cat mails/mail*.txt | grep @unige | sort | uniq # the other
$ cat mails/mail*.txt | grep @unige | sort | uniq | sed s/unige.ch/hes-so.ch/
```

List the two biggest file inside /mails

```shell
du -ab mails | grep / | sort -n | head -n 2
du -ab mails | grep / | sort -n | tail -n 2
```

#### Pipes and Tubes

## References

- [[ISC-332 - Programmation système]]
- <https://askubuntu.com/questions/172982/what-is-the-difference-between-redirection-and-pipe>

### Parent References

- [[Operating System#References]]
