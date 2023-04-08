---
date updated: 2021-11-10 10:01
tags:
  - '#java_programming'
  - '#review'
  - '#pn_2_1'
---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Java]] [[Anonymous Class in Java]]
Date Created: 09-11-21

---

# Functional Interface in Java

## Functional Interface in Java in few words

```java
@FunctionalInterface
interface interfaceName {
abstract-method;
}
```

## Functional Interface in Java in details

When an [[Interfaces in Java]] only contains an [[Abstract Method]] it is converted to [[Functional Interface in Java|Functional Interface]].

So **this:**

```java
JButton myButton = new JButton("click me");
myButton.addActionListener(new ActionListener() {
    @Override
    public void actionPerformed(ActionEvent ev) {
        System.out.println("Someone has clicked on the button");
    }
});
```

Becomes **this:**

```java
JButton myButton = new JButton("click me");
myButton.addActionListener(ev -> System.out.println("Someone has clicked on the button"));
```

Considering **this:**

```java
@FunctionalInterface // explicitly tell the compiler that this is a functional interface
public interface Hello {
  void greetings();
}
```

We can, instead of **this:**

```java

Hello h = new Hello() {
  public void greetings() { System.out.println("Hi guys!"); }
};
h.greetings();
```

We can write, **this:**

```java
Hello h = () -> System.out.println("Hi guys!");
h.greetings();
Test t = (i) -> return i + i;
TestApp.g();
```

### Examples

```java
public class TestApp {
    public static String g(Test t) {
        return t.f(0) + t.f(1);  
    }
    public static void main(String[] args) {
        String test = g( ... );
        System.out.println( test );
    }
}
```

```java
public static void main(String[] args) {
        String test = TestApp.g( i -> String.valueOf(2*i+1) );
        System.out.println( test );
    }
```

### Important Functional Interfaces

| java.util.function | Signature      | Usage               |
| ------------------ | -------------- | ------------------- |
| [[FunctionTR]]     | `T -> R`       | `R apply(T t)`      |
| [[ConsumerT]]      | `T -> ()`      | `void accept(T t)`  |
| [[SupplierT]]      | `() -> T`      | `T get()`           |
| [[PredicateT]]     | `T -> boolean` | `boolean test(T t)` |
| [[Runnable]]       | `() -> ()`     | `void run()`        |

## References

- <https://cavat.website/poo/docs/particular-types/anonymous/#interfaces-fonctionnelles-et-lambdas>
