---
date created: Tuesday, November 30th 2021, 4:04:40 pm
date modified: Tuesday, November 30th 2021, 4:15:25 pm
---

- Topic: #linux
- Tags: #review #pn_2_1
- Links: [[System Call]]
- Date Created: 30-11-21

---

# System Call Function - Syscall

## System Call Function - Syscall in Few Words

This function simply saves the [[CPU]] [[State]] by saving the [[Register|Registers]] and then call the given [[System Call]] corresponding to `<sys/syscall.h>`.

## System Call Function - Syscall in Details

The function `syscall`

1. Save CPU state ([[Register]])
2. Launch an interruption that changes the [[CPU]] mode
3. Give control to the kernel
4. Kernel makes the requested operation
5. Once operation done, Kernel gives back control
6. Mode is now **User**
7. Restore [[CPU]] state by restoring the [[Register|registers]].

```c
long syscall(long number, …)
```

The function takes a number specifying the [[System Call]] and a list of variable arguments depending on the chosen [[System Call]].

These numbers are written as [[Constant]] and can be found `<sys/syscall.h>`.

### Examples

```c
#include <unistd.h>
#include <sys/syscall.h>
#include <sys/types.h>
#include <signal.h>

int main() { 
	pid_t pid;
	pid = syscall(SYS_getpid); // get pid of process
	syscall(SYS_kill, pid, SIGHUP); // kill the process
}
```

## References

- [[ISC-332 - Programmation système]]
- `man 2 syscall`
