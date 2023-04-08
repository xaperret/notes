---
date created: Wednesday, March 16th 2022, 7:22:06 pm
date modified: Wednesday, March 16th 2022, 7:29:01 pm
---

- Topic: #operating_system
- Tags: #review #pn_2_1
- Links: [[Page]]
- Date Created: 16-03-22

---

# Page default

## Page default in few words

A page default happens when the [[Memory Management Unit]] cannot satisfy a page's demand because it isn't referenced in the [[Page table]].

There are three possibilities :
- Illegal access to memory, the [[Kernel]] will shutdown the [[Process]] by `SIGSEG` (segmentation fault).
- [[Page]] is present in the **physical memory**, *[[minor page default]]*. The solution is to update the [[Page table]].
- [[Page]] isn't present in **physical memory**, *[[major page default]]*.

## Page default in details

## References

- <http://cui.unige.ch/~chanel/prez/presentations/sys-exploitation/1.processes/#/1/9>
