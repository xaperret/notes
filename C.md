---
date updated: 2021-11-30 09:35
---

Topic: #c_programming
Tags: #review #ipn_1_6
Links: [[@0 Start here]]
Date Created: 03-11-21

---

# C

## C in few words

## C in details

- [[Introduction to C Programming]]
- [[Low vs High level language]]
- [[C Imperative Style]]
- [[The Preprocessor in C]]
- [[Type in C]]
- [[Naming Conventions in C]]
- [[Operators in C]]
- [[Type Conversion in C]]
- [[Opaque Type]]
- [[Bit Fields]]

Representation in memory of data is os dependent
Signed or non signed
Little endian
Big endian
Variable -> value, address

```c
int *ptr;

ptr = &i; // dereferencing

double *d = &i; // error wrong type
```

A pointer won't necessarily be right, but unfortunately the [[C Compiler]] will not care, it will be very happy and compile, causing errors.
We therefore must be very.
Parameters are passed by value. Values are thrown once the function is done.

[[Structure in C]] can be modified inside a function, contrary to other parameters.

[[Array in C]] are almost like [[Pointers in C]]
The difference is that an array is a pointer that is constant.
The other is that `sizeof` will give the size of the amount of byte used in the array.

```c
int *ptr = &x; 
```

```c
void *ptr;
*(int *) ptr = 2;
```

malloc => écrire free quelque part.

Precompiler : replace define, remove comments, include headers, every precompiler instruction
Compiler : make assembler
Assembler : machine code
Link editor : make executable

```c
char *c = "bim"; // the string here is constant
char c[] = "bim"; // the string here is not constant
```

## References

- [[Gustedt - Modern C]]
- [[ISC-332 - Programmation système]]
