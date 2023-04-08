---
date modified: Tuesday, November 30th 2021, 7:13:30 pm
date created: Friday, November 19th 2021, 2:01:21 pm
---

- Topic: #operating_system
- Tags: #review #pn_2_1
- Links: [[System Call]]
- Date Created: 18-11-21

---

# An Example Of System Call

## An Example Of System Call in Few Words

## An Example Of System Call in Details

Looking for C Dynamic Libraries, Linking them with the code

```shell
➜  s2 git:(master) strace ./main test.txt 
execve("./main", ["./main", "test.txt"], 0x7ffe186be768 /* 65 vars */) = 0
brk(NULL)                               = 0x55a03d5ec000
arch_prctl(0x3001 /* ARCH_??? */, 0x7ffe474e85d0) = -1 EINVAL (Invalid argument)
access("/etc/ld.so.preload", R_OK)      = -1 ENOENT (No such file or directory)
openat(AT_FDCWD, "/etc/ld.so.cache", O_RDONLY|O_CLOEXEC) = 3
newfstatat(3, "", {st_mode=S_IFREG|0644, st_size=92282, ...}, AT_EMPTY_PATH) = 0
mmap(NULL, 92282, PROT_READ, MAP_PRIVATE, 3, 0) = 0x7f3e1f453000
close(3)                                = 0
openat(AT_FDCWD, "/lib/x86_64-linux-gnu/libc.so.6", O_RDONLY|O_CLOEXEC) = 3
read(3, "\177ELF\2\1\1\3\0\0\0\0\0\0\0\0\3\0>\0\1\0\0\0\240\206\2\0\0\0\0\0"..., 832) = 832
pread64(3, "\6\0\0\0\4\0\0\0@\0\0\0\0\0\0\0@\0\0\0\0\0\0\0@\0\0\0\0\0\0\0"..., 784, 64) = 784
pread64(3, "\4\0\0\0 \0\0\0\5\0\0\0GNU\0\2\0\0\300\4\0\0\0\3\0\0\0\0\0\0\0"..., 48, 848) = 48
pread64(3, "\4\0\0\0\24\0\0\0\3\0\0\0GNU\0+H)\227\201T\214\233\304R\352\306\3379\220%"..., 68, 896) = 68
newfstatat(3, "", {st_mode=S_IFREG|0755, st_size=1983576, ...}, AT_EMPTY_PATH) = 0
mmap(NULL, 8192, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_ANONYMOUS, -1, 0) = 0x7f3e1f451000
pread64(3, "\6\0\0\0\4\0\0\0@\0\0\0\0\0\0\0@\0\0\0\0\0\0\0@\0\0\0\0\0\0\0"..., 784, 64) = 784
mmap(NULL, 2012056, PROT_READ, MAP_PRIVATE|MAP_DENYWRITE, 3, 0) = 0x7f3e1f265000
mmap(0x7f3e1f28b000, 1486848, PROT_READ|PROT_EXEC, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x26000) = 0x7f3e1f28b000
mmap(0x7f3e1f3f6000, 311296, PROT_READ, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x191000) = 0x7f3e1f3f6000
mmap(0x7f3e1f442000, 24576, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x1dc000) = 0x7f3e1f442000
mmap(0x7f3e1f448000, 33688, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_ANONYMOUS, -1, 0) = 0x7f3e1f448000
close(3)                                = 0
mmap(NULL, 8192, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_ANONYMOUS, -1, 0) = 0x7f3e1f263000
arch_prctl(ARCH_SET_FS, 0x7f3e1f452580) = 0
mprotect(0x7f3e1f442000, 12288, PROT_READ) = 0
mprotect(0x55a03ce8b000, 4096, PROT_READ) = 0
mprotect(0x7f3e1f49c000, 8192, PROT_READ) = 0
munmap(0x7f3e1f453000, 92282)           = 0
```

Actual program

```shell
brk(NULL)                               = 0x55a03d5ec000
brk(0x55a03d60d000)                     = 0x55a03d60d000
openat(AT_FDCWD, "test.txt", O_RDONLY)  = 3
newfstatat(3, "", {st_mode=S_IFREG|0664, st_size=49, ...}, AT_EMPTY_PATH) = 0
read(3, "Ceci est la balade, la balade de"..., 4096) = 49
newfstatat(1, "", {st_mode=S_IFCHR|0620, st_rdev=makedev(0x88, 0x1), ...}, AT_EMPTY_PATH) = 0
write(1, "\n", 1
)                       = 1
write(1, "char: C\n", 8char: C
)                = 8
write(1, "char: e\n", 8char: e
)                = 8
write(1, "char: c\n", 8char: c
)                = 8
write(1, "char: i\n", 8char: i
)                = 8
write(1, "char:  \n", 8char:  
)                = 8
write(1, "char: e\n", 8char: e
)                = 8
write(1, "char: s\n", 8char: s
)                = 8
write(1, "char: t\n", 8char: t
)                = 8
write(1, "char:  \n", 8char:  
)                = 8
write(1, "char: l\n", 8char: l
)                = 8
write(1, "char: a\n", 8char: a
)                = 8
write(1, "char:  \n", 8char:  
)                = 8
write(1, "char: b\n", 8char: b
)                = 8
write(1, "char: a\n", 8char: a
)                = 8
write(1, "char: l\n", 8char: l
)                = 8
write(1, "char: a\n", 8char: a
)                = 8
write(1, "char: d\n", 8char: d
)                = 8
write(1, "char: e\n", 8char: e
)                = 8
write(1, "char: ,\n", 8char: ,
)                = 8
write(1, "char:  \n", 8char:  
)                = 8
write(1, "char: l\n", 8char: l
)                = 8
write(1, "char: a\n", 8char: a
)                = 8
write(1, "char:  \n", 8char:  
)                = 8
write(1, "char: b\n", 8char: b
)                = 8
write(1, "char: a\n", 8char: a
)                = 8
write(1, "char: l\n", 8char: l
)                = 8
write(1, "char: a\n", 8char: a
)                = 8
write(1, "char: d\n", 8char: d
)                = 8
write(1, "char: e\n", 8char: e
)                = 8
write(1, "char:  \n", 8char:  
)                = 8
write(1, "char: d\n", 8char: d
)                = 8
write(1, "char: e\n", 8char: e
)                = 8
write(1, "char: s\n", 8char: s
)                = 8
write(1, "char:  \n", 8char:  
)                = 8
write(1, "char: j\n", 8char: j
)                = 8
write(1, "char: o\n", 8char: o
)                = 8
write(1, "char: u\n", 8char: u
)                = 8
write(1, "char: r\n", 8char: r
)                = 8
write(1, "char: s\n", 8char: s
)                = 8
write(1, "char:  \n", 8char:  
)                = 8
write(1, "char: h\n", 8char: h
)                = 8
write(1, "char: e\n", 8char: e
)                = 8
write(1, "char: u\n", 8char: u
)                = 8
write(1, "char: r\n", 8char: r
)                = 8
write(1, "char: e\n", 8char: e
)                = 8
write(1, "char: u\n", 8char: u
)                = 8
write(1, "char: x\n", 8char: x
)                = 8
write(1, "char: .\n", 8char: .
)                = 8
write(1, "char: \n", 7char: 
)                 = 7
read(3, "", 4096)                       = 0
write(1, "\n", 1
)                       = 1
write(1, "End-Of-Life", 11End-Of-Life)             = 11
exit_group(0)                           = ?
+++ exited with 0 +++
➜  s2 git:(master) 
```

We can see that a [[System Call]] can have multiple arguments, some that might be related to the [[Process]] who is at the origin of the request:

```c
openat(AT_FDCWD, "test.txt", O_RDONLY)  = 3
newfstatat(3, "", {st_mode=S_IFREG|0664, st_size=49, ...}, AT_EMPTY_PATH) = 0
read(3, "Ceci est la balade, la balade de"..., 4096) = 49
newfstatat(1, "", {st_mode=S_IFCHR|0620, st_rdev=makedev(0x88, 0x1), ...}, AT_EMPTY_PATH) = 0
write(1, "char: \n", 7char: 
)                 = 7
```

## References
