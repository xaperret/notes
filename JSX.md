---
date created: Thursday, July 7th 2022, 6:37:34 pm
date modified: Thursday, July 7th 2022, 7:20:38 pm
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 07-07-22

---

# JSX

## JSX in few words

### Variable

If we have a variable `name`:

```javascript
return (
	<div>Hello, {name}</div>
);
```

We can add more logic

```javascript
if(name == "bim") {
	return (
		<div>Hello, {name}</div>
	);
} else {
	return (
		<div> Hello, pif</div>
	);
}
```

or simply
```javascript
return (
	<div>Hello, {name == "bim"? "boum" : "bam"}</div>
);
```

### React Fragment

By encapsulating the [[HTML]] code inside a [[React Fragment]] it's possible not to have to encapsulate the code in a `div`.

## JSX in details

## References
