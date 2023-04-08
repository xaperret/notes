---
date updated: '2021-10-10T23:23:08+02:00'

---

Topic: #java_programming
Tags: #review #pn_1_9
Links: [[Java]]
Date Created: 10-10-21

---

# Class Creation

## Class Creation in few words

## Class Creation in details

```java
package Semaine2;

public class Serpent {
    private String body = "*"; // field
    private String head = ">>>"; // private is the visibility
    final int minSize = 4;

    private boolean canGetSmaller() {
        return body.length() - 1 <= 0 ? false : true;
    }

    public void bigger() {
        this.body = this.body.concat("*");
    }

    public boolean smaller() {
        if (!canGetSmaller()) {
            return false;
        }
        StringBuilder newBody = new StringBuilder(this.body);
        newBody.deleteCharAt(body.lastIndexOf("*"));
        this.body = newBody.toString();
        return true;
    }

    public String toString() {
        return body.length() >= this.minSize ? body + this.head : body;
    }

    Serpent() { // builder
    }
}
```

```java
public String toString() {
        final String tooMuchDigits = ("0000" + this.counter);
        final String fourDigits = tooMuchDigits.substring( tooMuchDigits.length()-4, tooMuchDigits.length() );
        return "Counter(" + fourDigits + ")";
    }
```

### Private member

```java
public class Counter {
    private int counter;

    public void click() {
        this.safeSetCounter(this.counter + 1);
    }
    private void safeSetCounter(int i) {
        this.counter = i % 10000;
    }
    public void reset() {
        this.counter = 0;
    }
    public int value() {
        return this.counter;
    }
    private static String toFourDigits(int i) {
        final String tooMuchDigits = ("0000" + i);
        return tooMuchDigits.substring( tooMuchDigits.length()-4, tooMuchDigits.length() );
    }
    public String toString() {
        return "Counter(" + toFourDigits(this.counter) + ")";
    }
}
```

### Builder

```java
public class Counter {
    private int counter;
    public Counter() {
        this.counter = 0; // inutile, pour la démo uniquement
    }
    public void click() {
        this.counter = (this.counter + i) % 10000;
    }
    public void reset() {
        this.counter = 0;
    }
    public int value() {
        return this.counter;
    }
}
```

### Static Builder

```java
public class Counter {

    private int counter;

    private Counter(int i) {
        this.safeSetCounter(i);
    }

    public void click() {
        this.safeSetCounter(this.counter + 1);
    }

    private void safeSetCounter(int i) {
        this.counter = i % 10000;
    }

    public void reset() {
        this.counter = 0;
    }

    public int value() {
        return this.counter;
    }

    public static Counter zero() {
        return new Counter(0);
    }

    /**
     * Returns a new Counter with de defined value included between 0 and 9999. Throws an IllegalArgumentException
     * if the value is out of the range
     *
     * @param value the initial value between 0 and 9999
     * @return a counter with the given value set
     * @throws IllegalArgumentExcpetion if value is not included in the specific range
     */
    public static Counter withValue(int value) {
        if (value < 0 || value > 9999) {
            /* Nous préférons retourner une exception si l'utilisateur fait une bêtise */
            throw new IllegalArgumentException("Value must be between 0 and 9999");
        }
        return new Counter(value);
    }

    private String toFourDigits(int i) {
        final String tooMuchDigits = ("0000" + this.counter);
        return tooMuchDigits.substring( tooMuchDigits.length()-4, tooMuchDigits.length() );
    }

    public String toString() {
        return "Counter(" + toFourDigits(this.counter) + ")";
    }
}
```

## References

- <https://cavat.website/poo/docs/poo-basics/poo-intro/>

### Parent References

- [[Java#References]]
