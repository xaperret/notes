---
date updated: '2021-10-13T17:59:05+02:00'

---

Topic: #android
Tags: #review #pn_2
Links: [[Activity]]
Date Created: 13-10-21

---

# Context

## Context in few words

## Context in details

The [[Context]] **holds** the **current** [[State]] of the [[Application]].
It can help us get **information** regarding [[Activity]] and [[Application]]
Another way that it might be used is to access [[Resources]], databases, shared preferences, etc...
Both [[Activity]] and [[Application]][[Class]] [[Inheritance|extends]] [[Context]].

There are two types of [[Context]]:

- [[Application Context]],
  - i.e. [[Context]] is here an instance of the [[Application]] its in
  - e.g. `getApplicationContext()`
- [[Activity Context]],
  - i.e. [[Context]] is here an instance of the [[Activity|activity]]
  - e.g. `getContext()`

### Access a Context

- From [[Activity]] or [[Service]] `this`
- From [[Broadcast]] `onReceived()`
- From [[Content Provider]] `this.getContext()`

## References

### Direct References

- <https://blog.mindorks.com/understanding-context-in-android-application-330913e32514>

### Parent References
