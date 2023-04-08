---
date updated: 2021-10-24 15:03

---

Topic: #java_programming #oop
Tags: #review #pn_2
Links: [[Constructor]] [[Class]]
Date Created: 12-10-21

---

# Static Factory

## Static Factory in few words

A [[Factory]] is a [[Static Method]] that returns an [[Instantiation|instance]] of a [[Class]], with 5 advantages.

- **Has a name**
- **Not obligate to** return an [[Instantiation|instance]] (e.g. _if **conditions** are not met_).
- Can return a [[Subtype]] of their return [[Type]]
- [[Class]] of the returned object can **vary** as **input parameters** can **vary**.
- ...

## Static Factory in details

A [[Factory]] is a [[Static Method]] that returns an [[Instantiation|instance]] of a [[Class]], it has the advantage of **having a name** and is **not obligate to** return an [[Instantiation|instance]] (e.g. _if **conditions** are not met_).

```java
public class Counter {
    private int counter;
	
	// private constructor
    private Counter(int i) { 
        this.safeSetCounter(i);
    }

	// factory => static method
	// returns an instance where counter is = 0
    public static Counter zero() {
        return new Counter(0);
    }
	
	public static Counter startAt(int num) {
		if(num < 9999) {
			return new Counter(num);	
		}
	}
```

### Return type

There are no direct equivalents to _Design Patterns_[^1]

## References

### Direct References

- [[@blochEffectiveJava2017]] p. 5
- <https://cavat.website/poo/docs/classes-and-objects/class-creation/#construction-via-des-m%c3%a9thodes-statiques>

### Parent References

[^1]: [[@gammaDesignPatternsElements1994]]
