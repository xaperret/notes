---
date created: Tuesday, November 30th 2021, 5:25:13 pm
date modified: Tuesday, November 30th 2021, 5:26:11 pm
---

- Topic: #linux
- Tags: #review #pn_2_1
- Links: [[System Call]]
- Date Created: 30-11-21

---

# Wrapper Function in Linux

## Wrapper Function in Linux in Few Words

A Function that is specific for a [[System Call]] and allows higher abstraction.

## Wrapper Function in Linux in Details

When making a system call, we indirectly call the [[System Call Function - syscall]]. But we can also call it directly, to do some awesome stuff.

Fortunately, there are *Wrapper Functions* around [[System Call Function - syscall]] that allows us to reduce the amount of code to write to execute a [[System Call]].

Here without a *Wrapper Function*

![[System Call Function - syscall#Examples]]

Here, with the **appropriates** *Wrapper Functions*:

```c
#include <unistd.h> 
#include <sys/types.h>
#include <signal.h>

int main(int argc, char *argv[]) { 
	pid_t pid; 
	pid = getpid(); 
	kill( pid, SIGHUP);
}
```

## References

- [[ISC-332 - Programmation système]]
