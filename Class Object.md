---
date updated: 2021-10-21 18:10

---

Topic: #java_programming
Tags: #review #pn_2
Links: [[Inheritance]] [[Class]]
Date Created: 12-10-21

---

# Class Object

## Class Object in few words

## Class Object in details

The Class Object is the biggest [[Superclass]] there is.
![[Pasted image 20211012180148.png]]

There are a lot of methods defined in it, but we are going to focus ourselves on three:

- `String toString()`
- `boolean equals(Object obj)`
- `int hashCode()`

### Redefine `toString`

The [Java Documentation](https://docs.oracle.com/en/java/) states that we should always redefine it, it helps greatly for [[logging]], [[debugging]].

The return should be _concise_ and _meaningful_.

### Redefine `equals`

The [[Operators in Java]] `==` is almost useless to compare [[Object]] since it will only compare [[Reference|references]].

This is the reason why we want to redefine it if we need to compare [[Object]].

```java
public boolean equals(Object obj) {
  return (this == obj);
}
```

This must follow some rules, since the `equals` method implements an [[equivalence relation]] on non-null [[Object]] [[Reference]], it is:

- **Reflexive** for any non-null reference value x, x.equals(x) should return true
- **Symmetric** for any non-null reference values x and y, x.equals(y) should return true if and only if y.equals(x) returns true
- **Transitive** for any non-null reference values x, y, and z, if x.equals(y) returns true and y.equals(z) returns true, then x.equals(z) should return true
- **Consistent** for any non-null reference values x and y, multiple invocations of x.equals(y) consistently return true or consistently return false, provided no information used in equals comparisons on the objects is modified
- For any non-null reference value x, x.equals(null) should return false

```ad-important

It's truly important to redefine this and `hashCode` as both are needed for making use of Sets !

~~~java
@Override

public boolean equals(Object o) {

if (this == o)

return true;

if (o == null)

return false;

if (this.getClass() != o.getClass())

return false;

Person p = (Person) o;

return personId == p.personId && personName.equals(p.personName);

}
~~~
```

#### Example

```java
@Override
    public boolean equals(Object o) {
        if(this == o) return true;
        if(o == null || o.getClass() != this.getClass()) {
          return false; 
        }
        Counter other = (Counter)o;
        return this.counter == other.counter;
    }
```

````ad-warning

When `instanceof` is used in place of `getClass` it might break the **Symmetric** rule, meaning
```java
y.equals(x) == x.equals(y); // not true anymore
```
````

see [[instanceof vs getClass]]

### Redefine `hashCode`

An `hash` is obtained by a [[Hashing]] function.
A [[Set]] for example is a special [[Data Structures|data structure]] that allow us to use [[Set Theory]] operations.
A [[Set]] will be **unique**. `HashSet` has a [[Hash Tables|hash table]] to optimize operations on [[Set|sets]].

A great example of why we **must** redefine this [[Method]].

```java
Counter c = Counter.zero();
Set<Counter> counters = new HashSet<>();
counters.add( c ); // ajoute un élément uniquement s'il n'est pas déjà présent
counters.add( Counter.zero() ); /* ajoute le même élément (structurellement) mais l'objet créé
                                   est nouveau et se trouve à un autre emplacement mémoire. Leur hash 
                                   est différent */
counters.size(); // ==> 2  (devrait retourner 1)
counters.contains( Counter.zero() ); // ==> false !
```

```java
 @Override
    public int hashCode() {
        return Objects.hash(this.counter);
    }
```

## References

### Direct References

- <https://cavat.website/poo/docs/classes-and-objects/object/#red%c3%a9finition-du-hashcode>
- <https://cavat.website/poo/docs/classes-and-objects/object/>

### Parent References
