---
date created: Tuesday, January 18th 2022, 7:06:04 pm
date modified: Friday, January 21st 2022, 11:21:37 am
---

- Topic:
- Tags: #review #pn_2_1
- Links: [[Concurrent Programming]]
- Date Created: 18-01-22

---

# Concurrency and the Peer Model

## Concurrency and the Peer Model in Few Words

In the **peer model,** there are no **principal [[Thread]]**. They are hierarchically equals.

Each **peer ([[Thread]])** deal with any *data* **input or output**.

![[Pasted image 20220118190614.png]]

The peer model is well adapted to applications where there are a **fixed number** of input or that they are **well-defined** and **easy to share**, e.g.: matrix multiplication, image analysis.

**A fixed number of input** means that we don't need a boss.

Without *boss*, *workers* must synchronize together to access **input**.

Similarly to [[Concurrency and the Master-Slave or Boss-Worker model]] we should **limit dependencies** between boss and workers.

## Concurrency and the Peer Model in Details

## References
