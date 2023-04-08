---
date updated: 2021-11-02 11:55
sr-due: 2021-12-24
sr-interval: 30
sr-ease: 251
---

Topic: #android
Tags: #review #pn_2_1
Links: [[Android's Ecosystem]]
Date Created: 13-10-21

---

# Android Runtime

## Android Runtime in few words

## Android Runtime in details

The [[Android Runtime]] is composed of the [[ART]] and **core Java libraries**.
Each Android App has its own [[Process]] with its own instance of the [[Java Machine]].
Applications aren't using the standard [[Java Machine]] to **compile and execute**, but another compiler called [[ART]].
Previously, Google used [[Dalvik]] but they dropped for the better performing [[ART]].
This [[Virtual Machine]] is a bit different than the [[Java Machine]] in that it is aware of CPU and memory constraint.
Furthermore, each instance are **protected** which avoid that a bug shutdown the whole system.

## References

- <https://www.techentice.com/dalvik-vs-art-android-drop-dalvik-efficient-art/>
- [[ISC_L511 - Développement mobile]]
