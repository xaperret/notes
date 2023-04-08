---
date created: Thursday, January 13th 2022, 3:33:15 pm
date modified: Sunday, January 23rd 2022, 12:10:37 pm
---

- Topic: #concurrency
- Tags: #review #pn_2_1
- Links: [[Concurrent Programming]]
- Date Created: 13-01-22

---

# Thread

## Thread in Few Words

A [[Thread]] is a basic unit of [[CPU]] utilization, it is by this definition a task that **execute** itself **independently** from other task. A [[Thread]] who belongs to the same [[Process]] as others [[Thread]] will share the following information with them:

- code section
- data section
- stuff related to the [[Operating System]]

Therefore, [[Thread]]s from the **same process** will **share the same addressing space**. A [[Thread]] itself has a few unique elements

- unique ID, that is on [[GNU Linux]] x64 an `unsigned long int`
- Program Counter
- Register Set

The ID, [[Program Counter]] and [[Register]] Set are called **the execution context**.

A [[Process]] usually has only one **[[Thread]] of control**, but it can have **more**.

![[Pasted image 20220115185426.png]]

## Thread in Details

- [[Thread Vs Process]]
- [[Relation Between Thread and Process]]
- [[State of a Process or Thread]]

## References

- [[@silberschatzOperatingSystemConcepts2018]] p. 160
