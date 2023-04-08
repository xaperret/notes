---
date created: Tuesday, July 5th 2022, 3:20:46 pm
date modified: Wednesday, July 6th 2022, 5:08:27 pm
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 05-07-22

---

# React

## React in few words

### What is React

React is a library for building user interfaces.

### What is new with React (2022)

[[React Hook]] is a new way to write and update [[React Component]].

### What is special with React

#### Composition and UI

It's possible to do [[Composition]] with UI.
Meaning that if two functions returns each part of an interface, it's possible to combine them in order to have a complete UI by using [[Composition]].

#### Unidirectional Dataflow

Instead of having the State of an Application living inside the [[DOM]], in react it lives inside a [[React Component]].

![[Pasted image 20220705153120.png]]

**The UI is a function of the State !**
Meaning when the State changes, the UI changes too !

#### Declarative UI

In [[React]] we specify only how the **UI should look like,** not how it gets updated.

#### Just JavaScript

[[React]] tries not to rewrite stuff that has already been written in [[JavaScript]] like maps.

## React in details

### The React Ecosystem

It's possible to write a [[React]] app just with an `index.html` file but it isn't really the best idea in the world.

#### [[JSX]]

Not supported by browser atm (2022). But really great way to use, so worth preparing your dev environment for it.
For example, by using [[Babel]].

#### Babel

Babel is a [[JavaScript]] compiler that allows you to transform your [[JavaScript]] code into something that is fully usable by a modern browser.
If you use something typically not supported by browser like JSX, that allows for [[HTML]] syntax inside [[JavaScript]] code, then you need Babel.

#### Webpack

Is a module bundler.

#### React Router

[[React]] doesn't come with a router. It renders specific component based on the position of the user, e.g `mywebsite.com/bim` will not show the same stuff as `mywebsite.com/boum`

#### Styled-components

Is a way to style different component directly inside your definitions of your [[React Component]].

#### Redux

Is an ecosystem to make state changes more predictable.
Has a store where all the State are stored.
Best to let this alone for [[React]] beginners.

### An introduction to NPM

Usually, to use package you will add them in your [[HTML]], but it's not a very good way to do things.
Instead, one can use NPM to install, update and manage packages you use in your application.
```shell
node -v
npm -v
```

Then you need to initialize your project
```shell
npm init
```

To install package, just do
```shell
npm i package_name
# or
npm install package_name
```
This does two things
- adds package_name to `node_modules`
- adds package_name to dependencies in `package.json`

It's possible to add option when installing so that you can separate packages, e.g.
```shell
npm i package_name --save-dev # this puts the package_name inside the dev dep.
```

All information can then be found inside a `package.json` file.

#### Scripts

```
"scripts": {
	"start": "webpack-dev-server --open",
	"build": "NODE_ENV='production' webpack",
}
```

#### Publish

```shell
npm login
npm publish
```

#### Versioning

v.1.2.3
- 1 is the **major**
- 2 is the **minor**
- 3 is the **patch**
- `^` before allows us to specify that we want the newest version with the same major
- `~` before allows us to specify that we want the newest version with the same major and minor
- exact version by just writing the version number without any special characters.

- ### Webpack

Webpack adds scripts tag and update them accordingly and make the necessary transformation (like processing sass).

Webpack needs the entry point to build the dependency tree.

#### Loaders

They allow Webpack to process more files type.

## References

- <ui.dev/c/react/>, Which I highly recommend
- <ui.dev/c/react/why-i-love-react>
- …
