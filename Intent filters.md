---
date updated: 2021-11-10 20:46
---

Topic: #android
Tags: #review #pn_2_1
Links: [[Intent]]
Date Created: 10-11-21

---

# Intent filters

## Intent filters in few words

## Intent filters in details

[[Intent filters]] are ways of allowing other apps to start an [[Activity]] (found your app) with a **defined kind of [[Intent]]**.
Indeed, Android will search in the called App's [[App Manifest]] for an [[Intent filters|Intent filter]] matching the [[Intent]] used to start an [[Activity]].
If for some reason, there are no matching [[Intent filters]], the [[Intent]] will fail, unless **explicit**.

![](https://developer.android.com/images/components/intent-filters_2x.png)

```ad-note

An [[Activity]] can still be startted if the [[Intent]] is **explicit**.

```

## References

- <https://developer.android.com/guide/components/intents-filters>
