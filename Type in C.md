---
date updated: 2021-11-30 10:04
---

Topic: #c_programming
Tags: #review #pn_2_1
Links: [[C]] [[Type]]
Date Created: 24-11-21

---

# Type in C

## Type in C in few words

| Type         | Declaration                      |
| ------------ | -------------------------------- |
| Integer      | `int`                            |
| Float        | `float`                          |
| Bigger Float | `double`                         |
| Char         | `char`, Integer using 1 [[Byte]] |
| _String_     | `char*` and `char**`             |
| Void         | `void`                           |

| Modifiers  | Compatible Types | Impact                                          |
| ---------- | ---------------- | ----------------------------------------------- |
| `short`    | `int`            | Shorten the size, modifier `short` can be alone |
| `long`     | `int, double`    | Lengthen the variable size                      |
| `unsigned` | `char, int`      | Make it unsigned (positive)                     |

```ad-important

Modifiers can affect or not affect the space taken in memory. It should but sometimes depending on the implementation it won't do a difference, e.g. [[Integer Type in C]].

```

## Type in C in details

As [[Type]] is a [[Set]] of values and operations on them, in [[C]] any **value** has **a type** that is **statically typed** and **operations** on them are determined by their type.
By this definition, we can conclude that a value's type determines the result of all operations.

```c
int a = 10; // 10 is an integer, it is statically typed
```

- [[Integer Type in C]]
- [[Boolean Type in C]]
- [[Size of Var in C]]

## References

- [[ISC-332 - Programmation système]]
- [[@gustedtModern2019]] p. 52
