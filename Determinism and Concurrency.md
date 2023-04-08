---
date created: Sunday, January 23rd 2022, 6:31:27 pm
date modified: Sunday, January 23rd 2022, 6:44:48 pm
---

- Topic: #concurrency
- Tags: #review #pn_2_1
- Links: [[Concurrent Programming]]
- Date Created: 23-01-22

---

# Determinism and Concurrency

## Determinism and Concurrency in Few Words

Oftentimes it the programmer is careless, a result of a concurrent program can be non-deterministic. And unfortunately, even if he is, there are times when it is inevitable , and we need to write code in a way that this non-deterministic result is handled correctly.

When switching context, information kept in the register are saved, meaning we can arrive in a situation where two [[Thread]] that are sharing resources and are running concurrently, fight over those shared resources.

That fight resulting in an unexpected outcome, or non-deterministic behavior.

```ad-tldr

**Concurrence** is a situation where multiple [[Thread]] are reading and writing on a shared resources, meaning the final outcome depends on timing.

```

### Important Properties

- [[Atomicity]]
- [[Reentrancy]]
- [[Thread-safety]]

## Determinism and Concurrency in Details

## References
