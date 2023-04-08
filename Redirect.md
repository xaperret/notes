---
date updated: '2021-10-06T20:58:21+02:00'

---

Topic: #operating_system #linux
Tags: #review #pn_1_9
Links: [[Operating System]]
Date Created: 06-10-21

---

# Redirect

## Redirect in few words

It is used to pass output from a specific **stream** to another place than the **default** [[Standard Output]] or [[Standard Error]] [[IO Stream]].

```shell
$ cat file.txt > bim.txt
```

This example will make the [[Operating System]] redirect the [[Standard Output]] to another **stream**.

[[cat]] -> `bim.txt`

Another way to look at redirection is to see
[[cat]] [[Process]] [[Standard Output]] -> [[File System]]

## Redirect in details

When using `>` or `>>` the [[Kernel]] redirects the stream to the desired resource.

## References

- <https://askubuntu.com/questions/172982/what-is-the-difference-between-redirection-and-pipe>

### Parent References

- [[Operating System#References]]
