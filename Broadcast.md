---
date updated: 2021-11-11 10:22
---

Topic: #android
Tags: #review #pn_2
Links: [[The Structure of an Android Application]]
Date Created: 13-10-21

---

# Broadcast

## Broadcast in few words

A way to receive [[Intent]]. It basically listens to messages that are intended for it.

## Broadcast in details

A **broadcast** is a message that any app can receive or send, such as system notification.
It's something similar to [[Publish-Subscribe|publish-subscribe]] [[Design Pattern|design pattern]].
A [[Broadcast]] is sent when an [[Event]] happens, it can be the phone starting to charge, system booting up, ...

Apps can then **register** to **receive** specific [[Broadcast]], using what is called [[Broadcast Receiver]].

```ad-warning

Don't abuse them ! It will cause [[Memory trashing]] !

```

There can be 
- **Implicit [[Broadcast]]:** is a call for an [[Event]] instead of a call for a specific App, Because it is **vague**, it is **NOT** advised to use this. Indeed, any apps that has a static [[Broadcast Receiver]] will be **woken up** just to listen to a call that might not be useful at all.
	- `CONNECTIVITY_CHANGE` was an example of potentially bad [[Broadcast]] use, as it could be used by many apps which will each be woken up by this.
- **Explicit [[Broadcast]]**

```ad-important

For some [[Broadcast]], a [[Broadcast Receiver]] is not enough, one must schedule a [[Job]] using the `jobScheduler` to be woken up and do an action e.g. if `CONNECTIVITY_CHANGE` happens.

```

```ad-info

[[Broadcast]] might get change for performance related reason (or something else) which is the reason why it is important to check the Android documentation !

```

### Android Manifest Configuration

## References

- [[ISC_L511 - Développement mobile]]
- <https://developer.android.com/guide/components/intents-filters>
- <https://developer.android.com/guide/components/broadcasts>
