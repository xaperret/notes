---
date updated: 2021-11-24 21:13
---

Topic: #c_programming
Tags: #review #pn_2_1
Links: [[C]]
Date Created: 24-11-21

---

# The Preprocessor in C

## The Preprocessor in C in few words

```c
#include <stdio.h> // this include the HEADERS of standards libraries

#define PI 3.14 // this will make the precompiler change every PI to 3.14
```

## The Preprocessor in C in details

As mentioned in the section[[Compilation in C|c]], [[Compilation in C]] is a multi-step operation that takes one or more piece of [[Source Code]] and transforms it into an [[Executable]] for the specified target.
[[The Preprocessor in C]] is the first one to act.
It takes everything that start with a **hashtag** and does the appropriate action.
This is also a way for us to add [[Constant]] that aren't really [[Constant]] but more like [[Literal]] that would have taken steroids.

## References

- [[ISC-332 - Programmation système]]
