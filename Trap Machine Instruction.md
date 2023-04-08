---
date created: Tuesday, November 30th 2021, 7:18:47 pm
date modified: Tuesday, November 30th 2021, 7:31:02 pm
---

- Topic: #linux #operating_system
- Tags: #review #pn_2_1
- Links: [[System Call]]
- Date Created: 30-11-21

---

# Trap Machine Instruction

## Trap Machine Instruction in Few Words

A [[Trap Machine Instruction]] is an interrupt caused by something that went badly wrong (division by zero, invalid memory access)…

This event usually result in a **switch to kernel mode**. From which the [[Operating System]] will perform actions before returning to the originating [[Process]].

- User Process causing a trap are usually **not fatal**
- Kernel Process causing a trap are usually **fatal**

Usually in [[GNU Linux]] code pointed by `0x80` of the [[Systems Trap Vector]] is executed after a [[Trap Machine Instruction]] cause a **mode switch**.

## Trap Machine Instruction in Details

## References

- https://en.wikipedia.org/wiki/Trap_(computing)
