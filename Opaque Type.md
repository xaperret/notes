---
date created: Tuesday, November 30th 2021, 4:26:04 pm
date modified: Tuesday, November 30th 2021, 5:14:25 pm
---

- Topic: #c_programming
- Tags: #review #pn_2_1
- Links: [[Type in C]]
- Date Created: 30-11-21

---

# Opaque Type

## Opaque Type in Few Words

[[Opaque Type]] are any [[Type]] that is deemed *incomplete*, meaning its implementation is **hidden** from the user. The only **visible** element being the [[Identifier]].

```c
// in not_tnt.h
typedef struct not_tnt not_tnt;
// here put function defs

// in not_tnt.c
struct not_tnt {
	int amount_of_tnt;
}
```

## Opaque Type in Details

We could use different [[Header]] files to hide our implementation also.

```ad-info

Using Opaque Type could discourage users to use our stuff if their work depends on our **internal implementation**.

```

Here's another way to implement it

```c
// in fruit.h
typedef banana;
```

```c
// in fruit.c
typedef struct kiwi {
	int weight;
	char *color;
} kiwi;

typedef struct kiwi* banana;
```

## References

- [[@seacordEffectiveIntroductionProfessional2020]] p.188
