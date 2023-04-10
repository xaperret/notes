---
date updated: "2021-07-29T10:58:40+02:00"
---

Topic: #c_programming
Tags: #review #literature_note_v1
Links:
Author:

---

# The principal structure of a program

There are two things to take in consideration when writing a C program:

- **Syntactical aspects** => figure out how to make the compiler understand what we want it to do, which is done by
  - [[Gustedt - Modern C#2 1 Grammar|grammar]]
- **Semantic aspects** => figure out how to make the program does what we want it to do, which is realised by
  - Declarative parts => what things are
  - Definitions of objects => where things are
  - Statements => what things are supposed to do (see also [[Statement]])

##### 2.1 Grammar

C program is composed of different types of text elements that constitute a kind of grammar :

- **Special words** : [[directives]], [[keywords]], [[reserved]]

```c
#include <sdtio.h> // is a directive
int a = 1; // int is a keyword
return a; // return is reserved
```

- **Punctuation**:

```c
{} // block
() // for arguments
[] // for index
/* for block comments */
; // for end of line
< > //
// content can usually span over several lines if there is no ;
```

- **Comments**: When the code isn't enough clear or for definition of functions/complicated block of code

```c
// for one liner comment or
/* for multiple lines */
```

- **Literals**: Fixed values

```c
0.1 // literals
```

- **Identifiers**: Name that **we** or the **C standard** give to entities in any given program.

```c
int an_identifier = 0; // an_identifier or main, printf, size_t, ... are identifiers which we or the C standard give to entities
```

    - Data objects: variables
    ```c
    int var = 10; // data object
    ```
    - Type aliases: specify the sort of data object
    ```c
    int var = 10; // here var is an integer
    ```
    - Functions: main, printf, ...
    - Constants: EXIT_SUCCESS

- **Function**: A function is first declared

```c
int get_number_of_potatoe(int field, int size);
```

then described

```c
int get_number_of_potatoe(int field[], int size) {
	int sum = 0;

	for(int i = 0; i < size; i++) {
		sum += field[i];
	}

	return sum;
}
```

it's completely acceptable to have both in one

```c
int main(void) {
	printf("wow\n");
	return EXIT_SUCCESS;
}
```

- **Operators**: there are many which will be covered later.

##### 2.2 Declarations[^1]

Before using an identifier in a program, it needs to be declared

## References

- [[@gustedtModern2019]]
