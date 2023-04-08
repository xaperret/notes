---
date created: Tuesday, January 18th 2022, 6:09:14 pm
date modified: Tuesday, January 18th 2022, 7:22:06 pm
---

- Topic:
- Tags: #review #pn_2_1
- Links: [[Concurrent Programming]]
- Date Created: 18-01-22

---

# Concurrency and the Master-Slave or Boss-Worker Model

## Concurrency and the Master-Slave or Boss-Worker Model in Few Words

### On the Fly

There are multiple ways to implement this model. The first way is to create **workers** on the fly as needed. If there is a task, then a **worker** is created and the task is assigned. The boss here in this *variant* deals with **input** and **output**, **create workers** and assigns [[Task in Operating System]] to them.

![[Pasted image 20220118181453.png]]

Each slave synchronize with their boss.

### Worker Pool

In another *variant*, we create a **pool** of **workers** at the **initialization**, since there needs to be **as many** workers **as** tasks, it might cause some blocks. In this variant, all workers **wait** to be woken up to fulfill its task.

The boss insert request to be work on in a queue.

The complexity of asynchronous request and communication is managed by the boss. Therefore, this model is most suited for server.

The boss is not blocked by the workers, but he must avoid being dependent on workers. Which is why it's crucial to limit communication between boss and workers.

## Concurrency and the Master-Slave or Boss-Worker Model in Details

## References

- [[ISC-332 - Programmation système]]
