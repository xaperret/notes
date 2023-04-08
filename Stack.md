---
date updated: 2021-11-12 19:21
---

Topic:
Tags: #review #pn_2_1
Links:
Date Created: 12-11-21

---

# Stack

## Stack in few words

## Stack in details

A **stack** is a [[Linear List]] for which all insertions and deletions (accesses) are made at one end of the list.

This means that a **stack** is a [[LIFO]] structure.

There are two common operations to a stack which are:
![[Pasted image 20210630173247.png]][^2]

##### Push

**Push** Add a new item to the top of the stack. Generally, this means changing the address pointed by the head to this new element and making sure the new element point to the preceding element.

##### Pop

**Pop** Remove and return the topmost or youngest item. Generally, this means changing the address pointed by the head to the element pointed by the topmost item and returning its address (the address of the topmost item).

Then the topmost item will be either garbage collected or freed after its use has passed.

## References
