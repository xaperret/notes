---
date updated: 2021-11-24 17:33
sr-due: 2021-12-28
sr-interval: 34
sr-ease: 250
tags:
  - '#android'
  - '#review'
  - '#pn_2_1'
---

Topic: #android
Tags: #review #pn_2_1
Links: [[The Structure of an Android Application]]
Date Created: 13-10-21

---

# Activities

## Activities in few words

[[User interface]] for Android. They are stacked on top one another on a [[LIFO]] [[Stack]][^1].

## Activities in details

If an [[App Component]] is an **entry point**, then an [[Activity]] is the **entry point** for **user interaction**.
Indeed, an [[Activity]] is responsible for the **presentation layer** of a given [[Application]].
Each [[Activity]] is linked to one [[User Interface]], which is a file in XML format that describes the **look** of the given [[Activity]].
For each _screen_ we want to display, we need one [[Activity]].

An [[Activity]] uses [[Views]] to draw [[User Interface]] and manage interactivity.
An [[Activity]] is constituted by the [[Application]] [[Context]] and one [[User Interface]]

If an [[Activity]] must have some properties that are common to **existing [[Class|classes]]** you should use them, e.g.

- List of item : `ListActivity`
- Extensible List of item : `ExpandableListActivity`
- Google map : `MapActivity`
- Tabs : `TabActivity`
- Web page : `WebViewClient`
- Preference panel : `PreferenceActivity`

## References

- [[ISC_L511 - Développement mobile]]

[^1]: [[Activity Stack]]
