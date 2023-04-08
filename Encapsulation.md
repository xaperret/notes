---
date updated: '2021-10-12T11:08:20+02:00'

---

Topic: #oop
Tags: #review #pn_2
Links: [[Java]] [[Object-Oriented Programming]]
Date Created: 12-10-21

---

# Encapsulation

## Encapsulation in few words

## Encapsulation in details

A good encapsulation is done by a focus on an object's **behavior** rather than **structure**.
An **example** of that is the usage of `getter` and `setter`, which should be discouraged because they are often **meaningless**, **dangerous** and **unhelpful**.

```java
public class BadCounter {
    private int counter;

    public void setCounter(int i){ 
        this.counter = i; 
    }
    public int getCounter() {
        return this.counter;
    }
}
```

This example here shows a counter. The problem with this counter is that all the logic has to be added on the outside of the [[Class]] which makes the whole concept of [[Object-Oriented Programming]] **meaningless** and utterly **useless**.

## References

### Direct References

- <https://cavat.website/poo/docs/classes-and-objects/class-creation/#encapsulation>

### Parent References

- [[Java#References]]
- [[Object-Oriented Programming#References]]
