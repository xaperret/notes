---
date updated: '2021-10-08T10:51:34+02:00'

---

Topic: #java_programming
Tags: #review #pn_1_9
Links: [[Java]]
Date Created: 08-10-21

---

# Java without OOP

## Java without OOP in few words

## Java without OOP in details

The keyword `static` makes any [[Function]] or [[Variable]] **unrelated** to any [[Instantiation]], meaning it is not linked to any [[Object]] therefore **static**.
Concretely, this means that a class like this

```java
public class HelloWorld {
	public static bim(String name) {
		return "bim in the face of " + name;
	}
}
```

can be use like so

```java
System.out.println(HelloWorld.bim("Tartampion"));
```

Here's another example

```java
public class HelloWorld {
  public static double sumThreeTerms(double d1, double d2, double d3) {
    return d1 + d2 + d3;
  }
  public static double doubleThat(double d) {
    return 2.0 * d;
  }
  public static void main(String[] args) {

    System.out.println( doubleThat(sumThreeTerms(1.0, 2.0, 3.0)) ); // shows 12.0

  }
}
```

## References

- <https://cavat.website/poo/>

### Parent References

- [[Java#References]]
