---
date created: Friday, November 19th 2021, 1:59:42 pm
date modified: Thursday, December 2nd 2021, 1:18:07 pm
---

- Topic: #operating_system #linux
- Tags: #review #pn_2_1
- Links: [[IO Stream]]
- Date Created: 21-10-21

---

# File Descriptor

## File Descriptor in Few Words

It's a unique identifier for a [[File]] or [[IO resource]], such as a [[Pipe]] or [[Network socket]].

The [[Kernel]] maintains a table of each [[File descriptor]] and the associated [[Pipe]] for each [[Process]]. It contains information such as :

- Input or Output

![[Pasted image 20211202130940.png]]

![[Pasted image 20211202133438.png]]

Two [[Process]] can share the same entry in the [[Kernel]].

Each [[Process]] and [[File]] have an existence in the [[Kernel]].

Example of [[File descriptor]]:

- Stdin, 0
- Stdout, 1
- Stderr, 2

## File Descriptor in Details

### Writing a File

makes the file pointer move

### Opening a new [[File descriptor]]
- An element is added to the [[File descriptor]] list
- A descriptor is associated 

## References

- <https://en.wikipedia.org/wiki/File_descriptor>
