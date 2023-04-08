---
date created: Friday, March 18th 2022, 10:35:41 am
date modified: Friday, March 18th 2022, 12:10:53 pm
---

- Topic: #operating_system
- Tags: #review #pn_2_1
- Links: [[Page default]]
- Date Created: 18-03-22

---

# major page default

## major page default in few words

When a major page default happens, the missing page must be loaded, by:
- Saving the CPU state and put it in wait
- Releasing pages if there aren't enough physical memory available
- Load the missing page from disk
- Update the [[Page table]]'s [[Process]]
- Load the CPU state and restart from the instruction that caused the [[major page default]]

When a [[Page]] is **freed** from physical memory then
- It already exists on the disk and hasn't been modified (bit dirty page = 0)
- It has been modified and is transferred to the swap to keep modifications

## major page default in details

## References
