---
date updated: '2021-10-13T18:00:51+02:00'

---

Topic: #android
Tags: #review #pn_2
Links: [[Context]]
Date Created: 13-10-21

---

# Application Context

## Application Context in few words

## Application Context in details

The [[Application Context]] should only be used when we need a [[Context]] whose [[Life-Cycle]] is separated from the current _[[Activity|activity]] [[Life-Cycle]]_.
Indeed, since the [[Application Context]] [[Life-Cycle]] is linked to the [[Application]] life itself, there could be some nasty stuff happening if not careful.
So the **pro-tip** is to use it only for [[Singleton]] or to **initialize a library**.

## References

### Direct References

- <https://blog.mindorks.com/understanding-context-in-android-application-330913e32514>

### Parent References
