---
date created: Friday, November 19th 2021, 2:01:06 pm
date modified: Saturday, January 15th 2022, 7:41:03 pm
---

- Topic: #android
- Tags: #review #pn_2
- Links: [[Context]] [[Activity State]]
- Date Created: 13-10-21

---

# Life-cycle

## Life-cycle in Few Words

## Life-cycle in Details

The purpose of the [[Life-Cycle]] is to insure correct resource management.

[[Application]] don't control their [[Life-Cycle]], it is the role of the [[Android Runtime]].

### Complete Cycle

1. `onCreate(…)`
   1. UI => `savedInstanceState`
   2. Initialize [[Activity|activity]]
   3. Launch [[Service]]
2. `onDestroy(…)` => **might be necessary to redefine** !

### Visible Cycle

[[Activity|Activity]] visible but no focus

1. `onStart()`
2. `onStop()` => **might be necessary to redefine** !
3. _`onRestart()`_ => **might be necessary to redefine** !

### Active Cycle

[[Activity|Activity]] at foreground, has focus. The code executed in this [[Life-Cycle]] must be efficient and fast.

1. `onResume()`
2. `onSaveInstanceState()` => `onPause()`

## References

- [[ISC_L511 - Développement mobile]]
