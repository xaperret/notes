---
date created: Tuesday, November 30th 2021, 5:14:55 pm
date modified: Tuesday, November 30th 2021, 5:22:53 pm
---

- Topic: #c_programming
- Tags: #review #pn_2_1
- Links: [[C]]
- Date Created: 30-11-21

---

# Bit Fields

## Bit Fields in Few Words

Bit Fields are the most **efficient** and **expansible** way to represent structures that would need **few data**.

This

```c
typedef struct person { 
	char *name;
	int age; 
	int isMarried; 
	int hasChildren; 
	int canDrive; 
	int speaksEnglish; 
} person_t;
```

Can be this with the use of [[Flags]]:

```c
#define IS_MARRIED (1 << 0) //0001 = 1 
#define HAS_CHILDREN (1 << 1) //0010 = 2 
#define CAN_DRIVE (1 << 2) //0100 = 4 
#define SPEAKS_ENGLISH (1 << 3) //1000 = 8

int information = HAS_CHILDREN;
information |= CAN_DRIVE;
...
```

## Bit Fields in Details

```c
if (i & IS_MARRIED) {} // one flag check 
if (i & (CAN_DRIVE|SPEAKS_ENGLISH)) {} // multiple flag check
```

## References

- [[ISC-332 - Programmation système]]
