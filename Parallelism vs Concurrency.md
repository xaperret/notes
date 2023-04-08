---
date created: Tuesday, January 18th 2022, 4:48:18 pm
date modified: Tuesday, January 18th 2022, 5:12:37 pm
---

- Topic: #concurrency
- Tags: #review #pn_2_1
- Links: [[Concurrent Programming]]
- Date Created: 18-01-22

---

# Parallelism Vs Concurrency

## Parallelism Vs Concurrency in Few Words

Concurrency and Parallelism are not the same thing.

Two [[Task in Operating System]] are [[Concurrent]] if their **execution order** in time are **undetermined**. If two [[Task in Operating System]] are running at **the same time**, this is [[Parallelism]].

[[Parallelism]] is only possible on **multicore** [[CPU]], **multi** [[CPU]] and [[Distributed Computing]].
![[Pasted image 20220118171143.png]]
[[Concurrent|Concurrency]] is a resulting property from a program, and it's a **more general** concept than [[Parallelism]].

Indeed, if we have a program where **multiple [[Thread]]** are running, if we have a mono-core architecture [[Thread]]s will be run in a way where they will be interwoven. The kernel will schedule their execution. This is **pseudo-[[Parallelism]]**.

![[Pasted image 20220118171227.png]]

If the architecture is multicore (or multi-[[CPU]]) then there can be **[[Parallelism]]**.

## Parallelism Vs Concurrency in Details

## References

- [[ISC-332 - Programmation système]]
