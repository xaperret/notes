---
date created: Monday, July 11th 2022, 9:45:07 am
date modified: Monday, July 11th 2022, 10:02:25 am
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 11-07-22

---

# CORS

## CORS in few words

CORS is a mechanism that allows a website to request data from another URL.
Browsers implement a "same-origin policy" which means that they will refuse to load any content that is from another website.
We need to fix that on the server, for example using a middleware on [[NodeJS]] to respond with the proper header.
This means that the [[API]] needs to tell browsers and other entities that it can be called from other origins.

### Preflight

Server must say if the demand is allowed (e.g: PUT, PATCH, …). Indeed, the browser will ask the server if it can send it before doing it.

## CORS in details

## References

- https://www.youtube.com/watch?v=4KHiSt0oLJ0
- https://www.youtube.com/watch?v=h-WtIT6gCBk
- https://www.youtube.com/watch?v=PNtFSVU-YTI
