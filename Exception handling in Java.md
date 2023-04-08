---
date updated: 2021-11-13 16:34
---

Topic:
Tags: #review #pn_2_1
Links:
Date Created: 13-11-21

---

# Exception handling in Java

## Exception handling in Java in few words

## Exception handling in Java in details

An exception handling system is very useful as we can separate the logic from error handling.

```java
try {
  //something
} catch (something1) { }
} catch (something2) { }
} catch (somthing3) { }
```

We should always throw a **specific**, **context-sensitive** and **descriptive** [[Exception]].
This is ok but not great:

```java
Something getMeSomething(int id) throws RuntimeException;
```

This is much better:

```java
Something getMeSomething(int id) throws NoSuchElementException;
```

### Throwable

An [[Exception]] in Java inherits from `Throwable`. There are multiple exceptions organized around 3 [[Class|classes]] which scheme are

![[Pasted image 20211113150656.png]][^1]

- `Throwable`
- `Error`: this [[Class]] and its subclasses are unmanageable, as the problem is so bad that the program's stop is necessary.
- `Exception`: represent every exception that must be managed, except for `RuntimeException`. Usually managed with a `try/catch` block.
- `RuntimeException`: **unchecked exception**, exception that can be ignored

### Exceptions

Every [[Class]] except `RuntimeException` **must** be **managed** and **declared**.

```java
void test() throws MandatoryException {  // this means that we must use a try/catch !
    throw new MandatoryException("message");
 }
```

Two methods to deal with it:

```java
void useTest() {
   try {
     test();
   } catch ( MandatoryException e) {...}
}
```

or

```java
void useTest() {
    try {
      test();
    } catch ( MandatoryException e) {
        throw new OtherException( e.getMessage() );
    }
}
```

or

```java
void useTest() throws MandatoryException {
    test();
}
```

But at some point there needs to be another `try/catch` block that deals with it.

### Unchecked exceptions

Not every exception will crash the program or necessitate handling !

### Actually handling exceptions

```java
try {
    /* try something */
} catch (NullPointerException ex) {
  System.err.println("Error : " + ex.getMessage());
} catch (NoSuchElementException ex) {
  System.err.println("Error : " + ex.getMessage());
} catch (NullPointerException | NoSuchElementException ex) { // multiple exceptions in one block !
  System.err.println("Error : " + ex.getMessage());
} finally {
// do something whether there is an error or no error
}
```

#### Try-with-resources

A resource is an object that must be closed after the program is finished with it. The `try-with-resources` statement ensures that each resource is **closed** at the end of the statement, for [[Object]] that implements the `AutoClosable` interface.

```java
static String readFirstLineFromFile(String path) throws IOException {
    try (BufferedReader br =
                   new BufferedReader(new FileReader(path))) {
        return br.readLine();
    }
}
```

### Custom exception

It's preferable to use the existing exception, but you can absolutely create your own exception and inherits `Exception` or any other [[Class]] that might suit your use case.

## References

- <https://cavat.website/poo/docs/inconsistencies/exceptions/>
- <https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html>

[^1]: https://cavat.website/poo/docs/inconsistencies/exceptions/
