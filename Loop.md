---
date updated: "2021-10-10T12:02:50+02:00"
---

Topic: #java_programming
Tags: #review #pn_1_9
Links: [[Control Structures]]
Date Created: 10-10-21

---

# Loops

## Loop in few words

## Loop in details

### _Pre Conditional_ Loop

The verification of the **condition** is done before going into a [[Loop]]

```java
while (condition) {
	// repeat while true
}
```

### _Post Conditional_ Loop

```java
do {
	// do once
	// verify then
} while (condition);
```

### Iterative Loop

```java
for(init; check condition; iterate) {
	// do this while condition true
}
```

### Iterator Loop

When we want to loop over [[Collections in Java]]

```java
for(type identifier: collection) {
	// identifier will be one different element of collection each loop
	// collection is of type Collection<type>
	// identifier is of type type
	// this does not stop until every element has been looped over
}
```

#### [[Declarative language|Declarative Style]]

Another way to do it but in a declarative style.

```java
collection.forEach(do stuff in here);
```

### Exercises

Write a loop that stimulate the behavior of `while` with `do while`.
Then do the reverse.

```java
public class Loop {
	public static void whileWithDoWhile(int i) {
		if(i < 5) {
			do {
				System.out.println(i);
				i++;
			} while(i < 5)
		}
	}

	public static void doWhileWithWhile(int i) {
		System.out.println(i);
		i++;
		while {
			System.out.println(i);
			i++;
		} while(i < 5)
	}
}
```

## References

- <https://cavat.website/poo/docs/syntaxe/structures/#les-boucles>

### Parent References

- [[Java#References]]
