---
date created: Sunday, January 23rd 2022, 9:01:23 pm
date modified: Sunday, January 23rd 2022, 9:10:29 pm
---

- Topic: #concurrency
- Tags: #review #pn_2_1
- Links:
- Date Created: 23-01-22

---

# Thread-safety

## Thread-safety in Few Words

A method is said to be **thread-safe** or **MT-safe** if it can be simultaneously be called by multiple [[Thread]]s and **always** returns the same result.

In a concurrent application, any **non** thread-safe method **must** be protected. Most POSIX Threads methods are thread-safe, but some aren't.

### Reentrant Vs Thread-safe

These aren't the same thing, as a [[Reentrancy|reentrant]] method might not be thread-safe and a thread-safe might not be [[Reentrancy|reentrant]].
Because, a reentrant method **must NOT** be called by multiple [[Thread]]s.

## Thread-safety in Details

## References
