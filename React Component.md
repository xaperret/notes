---
date created: Wednesday, July 6th 2022, 7:20:14 pm
date modified: Friday, July 8th 2022, 5:58:50 pm
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 06-07-22

---

# React Component

## React Component in few words

A React Component is a function or a Class which optionally accepts input and returns a React element.
```javascript
function Button({ onLogin }) {

  return React.createElement(

    "div",

    { id: "login-btn", onClick: onLogin },

    "Login",

  );

}
```

### State

### Lifecycle

### UI

### Props

It's possible to pass information to a component thanks to [[React Props]]
```javascript
// in App.js
class App extends React.Component {
	render() {
		return(
			<Hello
				firstProp="a prop"	
				secondProp="another prop wow"
			/>
		)
	}
}
export default App

// and then in Hello.js
class Hello extends React.Component {
	render() {
		return(
			<h2>
				Bim, this is a prop : {this.props.firstProp} and another
				one {this.props.secondProp}
			</h2>
		)
	}
}
export default Hello
```

```javascript
<Profile
  username="tylermcginnis"
  authed={true}
  logout={() => handleLogout()}
  header={<h1>👋</h1>}
/>
```

## React Component in details

## References

- <ui.dev>
