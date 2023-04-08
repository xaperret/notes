---
date updated: "2021-10-05T19:00:01+02:00"
---

Topic:
Tags: #review #pn_1_9
Links:
Date Created: 05-10-21

---

# Statement

## Statement in few words

> What things are supposed to do[^1]

What is concretely a statement will depend on the programming language used, but it is something allowing us to **express an action** to be carried out using the syntax provided by the programming language.
Also named **instruction**.

## Statement in details

Here is an example in C, showing the difference between [[Definition]], [[Declaration]] and **Statement**:

```c
int main(void) {
	// declaration
	int number_declared = 5;

	// In C we use the word statement not instruction
	// statements or instructions
	for(int i = 0; i < number_declared; i++) {
		printf("i is equal to %d\n", i);
	}
}
```

## References

- [Wikipedia Reference](<https://en.wikipedia.org/wiki/Statement_(computer_science)>)

### Parent References

- [[Gustedt - Modern C#Imperative programming 1]]

[^1]: [[@gustedtModern2019]] p. 11
