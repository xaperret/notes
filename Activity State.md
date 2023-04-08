---
date updated: '2021-10-13T18:27:50+02:00'

---

Topic: #android
Tags: #review #pn_2
Links: [[Android App Development]] [[Activity Stack]]
Date Created: 13-10-21

---

# Activity State

## Activity State in few words

## Activity State in details

An [[Activity|Activity]] in a [[Stack]] can have four states:

- **Active**, **visible and has focus**, at the top of the [[Stack]]
- **Paused**, **visible** but doesn't have the focus[^1]
- **Stopped**, **hidden**, in memory
- **Inactive**, killed by System, not yet launched, deleted from [[Stack]]

![[Pasted image 20211013182735.png]]

## References

### Direct References

- [[ISC_L511 - Développement mobile]]
- <https://developer.android.com/guide/components/activities/activity-lifecycle>

### Parent References

[^1]: Can be killed if [[Android]] need more [[Resources]]
