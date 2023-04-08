---
date created: Sunday, January 23rd 2022, 6:51:45 pm
date modified: Sunday, January 23rd 2022, 9:10:55 pm
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 23-01-22

---

# Reentrancy

## Reentrancy in Few Words

A [[Method]] is said to be reentrant, if it can be interrupted in the middle of its execution and called again before its first execution is finished.
This concept is link to operation where there are a single execution flow, e.g.: [[Recursive Method]], …

A **reentrant method**:
- Must not reference **static** or **global** data
- Must not return a [[pointer]] to **static** or **global** data
- Must not call a **reentrant method**.

### Modify a Method

In most cases we must change its interface, but it might be impossible to make a method **non-reentrant** [[Thread-safety|thread-safe]] (meaning it could not be called in a multi-threads environment).

```ad-caution

Some C method are not reentrant like `strtok`, `crypt`, but have a version that is marked with `_r`

```

![[Thread-safety#Reentrant Vs Thread-safe]]

## Reentrancy in Details

## References
