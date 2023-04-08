---
date updated: 2021-11-02 11:49
sr-due: 2021-12-25
sr-interval: 31
sr-ease: 250
---

Topic: #android
Tags: #review #pn_2_1
Links: [[Android App Development]]
Date Created: 13-10-21

---

# The Structure of an Application

## The Structure of an Application in few words

## The Structure of an Application in details

An Android Application has a much different [[Architecture]] than regular Desktop apps, which are usually [[Monolithic]] in nature.
Inside an App, we can have multiple components such as:

- [[Activity]]
- [[Fragment]]
- [[Service]]
- [[Content Provider]]
- [[Intent]]
- [[Broadcast]]
- [[Notification]]
- [[Widgets]]

Each component inside an App is linked together by a [[App Manifest]] which describe them and their relations, as well as [[Metadata]] on the App ([[Permission]]).

![[Pasted image 20211013155821.png]]

![Guide to app architecture | Android Developers](https://developer.android.com/topic/libraries/architecture/images/final-architecture.png)

### Separation of Concerns

What is advised by the [Android Documentation](https://developer.android.com/jetpack/guide) is to follow [[Separation of Concerns]] principle to build up your application.
Meaning keeping [[Activity]] and [[Fragment]] [[lean]].

### Drive UI from a model

By driving UI from a model, we make the **handling of the data** independent of the UI. So these become **unaffected** by the app's [[Life-Cycle]].

## References

- [[ISC_L511 - Développement mobile]]
- <https://developer.android.com/jetpack/guide>
