---
date updated: '2021-10-14T09:22:03+02:00'

---

Topic: #operating_system
Tags: #review #pn_2
Links: [[Operating System]]
Date Created: 14-10-21

---

# JOBS

## JOBS in few words

## JOBS in details

By default, each [[Process]] launched from the [[Shell]] will run in the **foreground**, to launch a [[Process]] in the **background** within the [[Shell]] you can simply add `&` at the end of the command.
To stop it, `CTRL-Z` within the [[Process]] [[Standard Input]] or use [[kill]] command with the `TSTP` [[Signal|signal]].

```shell
➜  ~ vim banane 
# CTRL-Z is pressed inside vim
[1]  + 84794 suspended  vim banane
➜  ~ fg   
```

Then restart it with [[bg]].
Then put it in the **foreground** with [[fg]]

```shell
➜  ~ gedit # start gedit
^Z # suspend it with CTRL+Z
[1]  + 226487 suspended  gedit
➜  ~ bg # make it continue
[1]  + 226487 continued  gedit
➜  ~ fg # make it come back in the terminal
[1]  + 226487 running    gedit
^Z # suspend it again
[1]  + 226487 suspended  gedit
➜  ~ kill -s SIGCONT 226487 # make it continue but without bg
➜  ~ fg # make it come back again on the foreground
[1]  + 226487 continued  gedit
^C # interrupt it with sigint 
➜  ~ 
```

### Exercises

Launch `gedit` from the terminal in the **background**

```shell
➜  ~ gedit &
[1] 73779
                                                    
```

Pause it

```shell
➜  ~ kill -s TSTP 73779
[1]  + 73779 suspended  gedit   
```

Relaunch it with kill

```shell
➜  ~ kill -s CONT 73779
```

## References


- [[ISC-332 - Programmation système]]

