---
date created: Sunday, January 23rd 2022, 9:19:36 pm
date modified: Sunday, January 23rd 2022, 9:29:45 pm
---

- Topic: #concurrency
- Tags: #review #pn_2_1
- Links: [[Concurrent Programming]]
- Date Created: 23-01-22

---

# Critical Resource

## Critical Resource in Few Words

A critical resource is a resource that can't be shared but is accessed by multiple [[Thread]]s, e.g.: global variable, hardware.

What is the critical resource ?
```c
const int N = 2;
const int iterations = 100;
int global; // this one

int main(void) {...}
```

![[Critical Section#Critical Section and Critical Resource]]

## Critical Resource in Details

## References
