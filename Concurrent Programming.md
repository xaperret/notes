---
date created: Thursday, January 13th 2022, 3:33:14 pm
date modified: Sunday, January 23rd 2022, 9:23:18 pm
---

- Topic: #concurrency
- Tags: #review #pn_2_1
- Links: [[@0 Start here]]
- Date Created: 13-01-22

---

# Concurrent Programming

## Concurrent Programming in Few Words

[[Concurrent Programming]] is a [[Programming Paradigm]] which **account**, in a program, of **multiple execution context** ([[Task in Operating System|Task]], [[Thread]], Specialized [[Process]] materialized by a [[Stack]] and private data).
switzerland
It's useful for many applications, like:

- Interaction with [[Input Output Devices|IO]]
- To launch multiple [[Task in Operating System|Task]] that have been specifically launched independently
- To use more **hardware resources**

### Difference Between Sequential Programming and Concurrent Programming

![[Pasted image 20220113161414.png]]
![[Pasted image 20220113161711.png]]

### Advantages with Concurrent Programming

- Simplify the **program structure**
- Easier **real time** programming depending on the [[Operating System]].
- **Responsiveness**, For example, if you want to use any **hardware** and still be able to do things while using them, or you need to wait for any action (mouse, keyboard, timer, GPIO, …).
- **Resource sharing**, since [[Thread]] shares the same memory and resources of the [[Process]] to which they are attached, then we can have multiple [[Thread]] in the same **address space**.
- **Economy**, allocating memory and resources for [[Process]] creation is costly, but since [[Thread]] shares the resources of the [[Process]] to which they belong, we can use [[Thread]] and **context-switch** them whenever needed.
	- Context switching between [[Thread]] is faster than between [[Process]]
- **Scalability**, by able to use **multicore architectures**, where [[Thread]] might be run in [[Parallel]] on different [[CPU]] cores, which in turns make things like big calculation faster.

### Problem with Concurrent Programming

- Access to shared resources
- Data exchange
- Order of execution
- Synchronization of [[Task in Operating System|Tasks]]
- Predict result
- Reproduce reliably
- Harder to debug. Indeed, the debugger slows down execution, meaning the result might be different.

### Implementing Concurrency

While working on a [[Operating System]]
Thanks to a dedicated library
With mechanism implemented in the programming language
see [[Comparison between different concurrency implementatiion]]

## Concurrent Programming in Details

- [[CPU Bound vs IO Bound]]
- [[Time-sharing in Operating System]]
- [[Parallelism vs Concurrency]]
- [[Organization of a program for Concurrency]]
- [[Concurrency and the POSIX Library]]
- [[Determinism and Concurrency]]
- [[Critical Resource]]
- [[Critical Section]]
- [[Mutual Exclusion]]

## References

- [[@silberschatzOperatingSystemConcepts2018]] p. 162
P
