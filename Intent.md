---
date updated: 2021-11-24 16:45
sr-due: 2021-12-11
sr-interval: 17
sr-ease: 255
---

Topic: #android
Tags: #review #pn_2_1
Links: [[The Structure of an Android Application]]
Date Created: 13-10-21

---

# Intents

## Intents in few words

## Intents in details

An [[Intent]] is a **messaging** [[Object]], which can be used to **request an action** from another another [[App Component]] such as another **app** or an [[Activity]] or [[Service]], ....

### Usage of Intents

#### Starting an activity

We can start a new instance of an [[Activity]] by passing an [[Intent]] to `startActivity()`.
The [[Intent]] describes the **activity** and carries **data**.

#### Starting a service

We can start a [[Service]] by passing an [[Intent]] to `startService()`.
The [[Intent]] describes the **service** and carries **data**.

#### Delivering a broadcast

A [[Broadcast]] can be delivered by passing an [[Intent]] to `sendBroadcast()` or `sendOrderedBroadcast()`.

### Types of Intent

![](https://developer.android.com/images/components/intent-filters_2x.png)

There are two types of intents:

- **Explicit intents**, which specify the **action** and **which application** will satisfy the intent, something that you will use in **your own app**, as everything is known.
- **Implicit intents**, only describe the **action** to perform, which let a [[Component]] from another App to handle it. The **image** above describe such [[Intent]].

[[Intent|Intents]] can be found in the [[App Manifest]], because Android will look at it to resolve any **implicit intents** by comparing both manifest files [[Intent]]/[[Intent filters]].

### Building an Intent

An [[Intent]] [[Object]] has information that Android system uses to **determine which component to start** and

## References

- [[ISC_L511 - Développement mobile]]
- <https://developer.android.com/guide/components/intents-filters>
