---
date modified: Tuesday, November 30th 2021, 8:31:27 pm
date created: Friday, November 19th 2021, 2:01:21 pm
---

- Topic: #operating_system #linux
- Tags: #review #ipn_1_6
- Links: [[Operating System]]
- Date Created: 18-11-21

---

# System Call

## System Call in Few Words

A [[System Call]] is a **controlled entry point**, that is identified thanks to a **unique number**, to the [[Kernel]], that allows [[Process]] to use the [[Kernel]]'s functionalities and services by making a request to the [[Kernel]].

![[Pasted image 20211130190016.png]]

A [[System Call]] changes the [[CPU]] [[State]] from **user mode** to **kernel mode**,[^1] so that the [[CPU]] can access **restricted [[Kernel]] memory**.

The set of [[System Call]] is **limited**, and they can generally do things like for example :

- Interaction with [[File System]]
- Interaction with data
- Creating a new [[Process]]
- Creating a [[Pipe]] to communicate with another [[Process]]

The full list can be found in the man page `syscalls(2)`.

A concrete example of a [[System Call]] would be the widely used [[C]] [[Function]] `malloc`. This function makes a **system call** to ask for **memory space** on the [[Heap]].

```ad-important

Whenever we make a [[System Call]] we should **ALWAYS** check the retrun status of the call in order to determine whether it was successful or not !

```

![[Pasted image 20211130160358.png]]

## System Call in Details

### How a System Call Works

1. Use [[Wrapper Function in Linux]] to make a [[System Call]]
2. [[Wrapper Function in Linux]] gives the necessary arguments to the [[System Call]] by copying the information on the [[Stack]] in **the specific registers**.
3. The `%eax` [[Register]] contains the **system call number** that uniquely identifies this [[System Call]]
4. [[Wrapper Function in Linux]] executes a [[Trap Machine Instruction]] `int 0x80` which switch the [[CPU modes]] into [[Kernel]] to access **restricted memory** and execute the code pointed by `0x80`

```ad-info

More recent x86-32 architectures implement the `sysenter` instruction which is a faster method to switch to Kernel mode.

```

5. Then the `system_call()` routine of the [[Kernel]] is called
	1. Saves register values onto the [[Kernel]] [[Stack]]
	2. Checks that the **number given** corresponds to a [[System Call]]
	3. If args were given, are they correct ?
	4. Call the proper system call service routine found by using the **previous correct number**
	5. Restores [[Register]] values from the [[Kernel]] [[Stack]] and places the [[System Call]] return value on the [[Stack]]
	6. Returns to the [[Wrapper Function in Linux]] & Return [[CPU]] to **user mode**.
6. If the **return value** from the [[System Call]] on the [[Stack]] indicates an error, the **global variable** `errno` is sets by the [[Wrapper Function in Linux]]. Then the [[Wrapper Function in Linux]] returns an **integer return value** indicating an **error or not**, see [[Error Return Convention in C]] for more information.

### Other Important Details About System Call

- Ways to use [[System Call]]:
	- [[Wrapper Function in Linux]]
	- [[High Level Libraries in Linux]]
- [[An Example Of System Call]]
- [[Checking System Call Error]]

## References

- [[ISC-332 - Programmation système]]
- [[@kerriskLinuxProgrammingInterface2010]] p. 43-44



































[^1]: [[CPU modes]]
