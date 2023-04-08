---
date updated: 2021-10-21 09:10
tags:
  - '#operating_system'
  - '#linux'
  - '#review'
  - '#pn_1_9'

---

Topic: #operating_system #linux
Tags: #review #pn_1_9
Links: [[Operating System]] [[Redirect]] [[Pipe]]
Date Created: 06-10-21

---

# IO Stream

## IO Stream in few words

## IO Stream in details

[[UNIX]] [[Process]] uses [[IO Stream]] to read and write data, therefore each program has 3 [[IO Stream]]:

| [[File descriptor]] | Purpose             | POSIX name    | stdio stream |
| :-----------------: | ------------------- | ------------- | ------------ |
|          0          | [[Standard Input]]  | STDIN_FILENO  | _stdin_      |
|          1          | [[Standard Output]] | STDOUT_FILENO | _stdout_     |
|          2          | [[Standard Error]]  | STDERR_FILENO | _stderr_     |

![[Pasted image 20211006203605.png]]

What is inputted or outputted can be a variety of things, e.g.: [[File]], [[Device]], [[Terminal]] Window, [[Standard Output]] from another [[Process]].

### Input Stream

By default, the **Input Stream** of a [[Process]] is associated to the [[Keyboard]] of the [[Terminal]].

```shell
$ cat # waits for user input
$ cat > bim.txt
```

We can use `<` to redirect something to the **Input Stream**

```shell
cat < livre.txt
```

### Output Stream

By default, the **Stream Output** or [[Standard Output]] is the terminal. For example, `echo` is outputting whatever we tell it to the terminal.
`1>` allows us to redirect the [[Standard Output]]

### Error Stream

By default, it's also redirected to the terminal, but we can redirect it !
`2>` will allow us to redirect the [[Standard Error]] to any [[Standard Input]].

### Exercises

Store the file list of `images/` with their **attributes** inside a file named `result`

```shell
$ ls -lha images/ > result
```

Copy a file to the file `result` without using [[cp]]

```shell
$ cat afile > result
$ cat afile >> result
```

One will append `>>` the other squash the file `>`.

Use `ls -R /tmp` to list recursively the content of `/tmp` and redirect the [[Standard Output]] and [[Standard Error]] to different files.

```shell
$ ls -R /tmp 1> noerror 2> error
```

# References

- [[ISC-332 - Programmation système]]
- <https://ryanstutorials.net/linuxtutorial/piping.php>
- [[@wardHowLinuxWorks2021]] _2.2.3 Standard Input and Standard Output_
