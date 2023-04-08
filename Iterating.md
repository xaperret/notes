---
date updated: '2021-10-10T22:50:37+02:00'

---

Topic: #java_programming
Tags: #review #pn_1_9
Links: [[Java]] [[List]] [[Collections in Java]] [[Static Array]]
Date Created: 10-10-21

---

# Iterating

## Iterating in few words

## Iterating in details

### Iterating over List and other Collections

### Iterating over Static Arrays

Here we can look at an example of how we can iterate over a given [[Static Array]].

```java
public static void main(String[] args) {
        System.out.println("for each");
        for (String arg : args) {
            System.out.println(arg);
        }
        System.out.println("for i");
        for (int i = 0; i < args.length; i += 1) {
            System.out.println(args[i]);
        }
		
		int i = 0;
 		while (i < args.length) {
 			System.out.println( args[i] );
 			i += 1;
	 	}
 
        System.out.println("declarative for each");
        List<String> test = List.of(args);
        test.forEach(arg -> System.out.println(arg));
    }
```

## References

### Parent References
