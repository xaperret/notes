---
date created: Tuesday, November 30th 2021, 5:29:58 pm
date modified: Tuesday, November 30th 2021, 5:47:17 pm
---

- Topic: #linux
- Tags: #review #pn_2_1
- Links: [[System Call]]
- Date Created: 30-11-21

---

# Checking System Call Error

## Checking System Call Error in Few Words

To check for errors, we use the global variable `errno` and then we can test for errors using standards errors code from `errno.h`.

There isn't really 1000 ways to do this, it's important to know that since it's a **global variable** then `errno` could have its content **overwritten** because a [[System Call]] could have been called in the meantime.

Therefore, it is **extremely** indispensable to check for errors. One method could be to

1. Check given function for possible error code
2. Use [[Control Structures]] to test for error code found in `errno`

In pseudocode:

```c
system_call();
switch(errno) {
	case possible_error_for_system_call1:
		...
		break;
	case possible_error_for_system_call2:
		...
		break;
	case possible_error_for_system_call3:
		...
		break;
}
```

## Checking System Call Error in Details

- [[Error Return Convention in C]]

### Return an error with `strerror`

```c
if( num < 0 ) { printf(stderr, "An error has occured: %s\n", strerror(errno)); }
```

### Print an error message with `perror`


## References

- [[ISC-332 - Programmation système]]
