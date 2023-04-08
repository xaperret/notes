---
date created: Wednesday, March 16th 2022, 5:32:46 pm
date modified: Wednesday, March 16th 2022, 5:41:28 pm
---

- Topic: #operating_system
- Tags: #review #pn_2_1
- Links: [[Process]]
- Date Created: 16-03-22

---

# Memory Layout of a Process

## Memory Layout of a Process in few words

The memory allocated to a [[Process]] is composed of different parts that are named [[Segment]].
- **Text [[Segment]]**: Contains machine-language instructions, *read-only* so the [[Process]] doesn't not modify its own instructions
- **Initialized Data [[Segment]]**: Global and static variables, that are explicitly initialized.
- **Uninitialized Data [[Segment]]**: Global and static variables, that are **not** explicitly initialized.
- [[Stack]]: dynamically growing/shrinking segment containing *stack frames*, one frame being allocated for each function (storing local variables, arguments and return values).
- [[Heap]]: area from which memory can be dynamically allocated at run time

## Memory Layout of a Process in details

## References
- [[@kerriskLinuxProgrammingInterface2010]], p.115-116