---
date modified: Tuesday, November 30th 2021, 2:34:38 pm
date created: Tuesday, November 30th 2021, 11:55:01 am
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 30-11-21

---

# Type Conversion in C

## Type Conversion in C in Few Words

## Type Conversion in C in Details

In any operation, the variables' type determines the **result type** of the operation.

- If variables have the **same type** then the **result type** is the **same**
- If variables have **different types** then the **result type** depends on the type with the **bigger [[Domain]]**

```c
int a = 10;
int b = 10.0;
float c = 20;
float d = 20.0;
// doesn't compile float e = 20f; 
float e = 20.0f;
double f = 40;
double g = 40.0;
double h = 40.;
double i = 40.f;
```

## References

- [[ISC-332 - Programmation système]]
