---
date created: Friday, January 21st 2022, 11:26:52 am
date modified: Friday, January 21st 2022, 11:33:16 am
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 21-01-22

---

# Concurrency and the Pipeline Model

## Concurrency and the Pipeline Model in Few Words

This model is valid for:

- Long input stream
- The process can be decomposed into sub-threads, through which each data needs to go through
- Each step can process one data at one instant in time
- A thread wait on data from the previous one and then transmit data to the next one
![[Pasted image 20220121112809.png]]

The advantage of this way of doing is that the throughput is improved since each step is processed concurrently.

To have the best performance, it is important to divide the work fairly between the different steps.

The throughput is limited by the **slowest** step.

## Concurrency and the Pipeline Model in Details

## References
