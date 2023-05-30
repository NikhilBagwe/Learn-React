## Intro :

- Currently we are working with modern JS and our apps are also made using it.
- But suppose our user is using a browser from 90's, our website might not load properly as Modern JS was not invented at that time and thus, bowser won't understand our website's code.
- There is a replacement code available for the modern JS functionalities which is compatible with older versions of browser. So when we write "browserlists" - (mentions which versions of browser our code must support) in our package.json, our code gets converted to that code.
- So "Babel" which is a JS library/package, is the one who converts the code using the "browserlists" provided.
- So we don't have to write polyfills.

### NOTE : 'git init' is a command which makes your folder/repo compatible with git. Also generates '.gitignore' file. You can also use all features of git in your repo now such as branching, push, pull, etc.

## Building a script in package.json :

- Writing 'npx parcel index.html' everytime is not feasible.
- So we create a script as below :
```js
"scripts" : {
  "start" : "parcel index.html",
  "build" : "parcel build index.html",
}
```
- Now you just have to write "npm run start" or just "npm start".
- Why we skipped 'npx' in our script : npx executes a package without downloading it unlike we use npm to install something into our app also run it. So npm = npx. And while executing cmd we write 'npm ' ourself. So we skip npx.

## Assigning key prop to children of a list :

- Why do we need a key? : When there are multiple children and we add a new children to the list. Thus, React has to update/rerender the DOM. React has to take a lot of efforts while updating the DOM with children not having keys. Thus, we introduce key prop to uniquely identify an children and React easily injects it at the desired location w/o much efforts.
- Read more : https://legacy.reactjs.org/docs/reconciliation.html
- As shown in the below code, each children of a list/array must have a key prop to uniquely identify it.

```js
import React from 'react'
import ReactDOM from 'react-dom/client'

// creating a Nested React element
const heading1 = React.createElement('h1', {
  id:'title',
  key:'h1'
}, 'Heading 1') 
const heading2 = React.createElement('h2', {
  id:'title', 
  key:'h2'
}, 'Heading 2')

// Passing multiple children into an React element
const container = React.createElement('div', {
  id: 'container'
}, [heading1, heading2])

const root = ReactDOM.createRoot(document.getElementById('root'))

root.render(container)
```
- Otherwise we may get error : Warning: Each child in a list should have a unique "key" prop.

## How does React.createElement() works :

- In Below code React.createElement() creates a JS object :

```js
const heading1 = React.createElement(
  "h1",
  {
    id: "title",
    key: "h1",
  },
  "Heading 1"
);

// In console we see the object : {$$typeof: Symbol(react.element),...}
```
- Then React converts the object to HTML and puts in on the DOM.

## JSX : 

- As we saw in above code, making react apps using React.createElement() will become messy for complex app design.
- Thus, we use JSX.
- People say JSX stands for "Javascript XML" even though there is no official name for it in the docs.
- Motivation behind JSX: When FB created React, there main motive was to write/update HTML using JS. So createElement API was introduced. But again for complex designs the code became lengthy, messy and less readable using createElement. Thus, finally JSX was introduced.

```js
// <h1>Heading</h1> is JSX not a string and is a perfectly valid JS code.

const heading = <h1 id="title" key="h1">Heading</h1>
```
- If you paste the above code in browser's console, it won't understand it and throw error.
- Babel understands the JSX code.
- Babel in itself is just a library which takes the above JSX code and outputs the normal code.
- It goes line by line through your code and when it sees an angular bracket '<' it understands it is JSX and thus creates the required code for it.

### NOTE : So is JSX, HTML inside JavaScript ? : Answer - False. JSX is just an HTML like syntax but not HTML. The attributes which we add to JSX elements are written in Camel case convention which is follwed by JS. Thus, JSX is valid JS.

## key vs id :

- 'id' is a concept of HTML.
- While React keeps track of 'key' while rendering DOM. It dosen't care what 'id' the element has.

## How is JSX executed ? Babel

- React.createElement gives us a JS obj, which then gets coverted to HTML.
- JSX uses React.createElement() behind the scene.
- JSX => React.createElement() => Object => HTML.
- Babel converts JSX to React.createElement then futher process happens.

```js
// JSX code
const heading = <h1>Heading</h1>

// Babel's o/p as React
const heading = React.createElement('h1', null, 'Heading')

// Check out to try it out: https://babeljs.io/
```

## Advantages of JSX :

- Readibility
- Good developer experience
- Syntactic sugar
- Less code and easy to maintain.

## Components :

- Everything is a component in React.
- 2 types : Functional component and Class based component.
- Any component's name starts with Capital letter. It's not mandatory but it is a good practice.

## Functional component :

- Functional component is nothing but just a normal JS function which returns some piece of JSX code or React element.

```js
const HeaderComp = () => {
  return <h1>Navbar</h1>
}

// OR

const HeaderComp = function () {
  return <h1>Navbar</h1>
}
```
### React element vs Component :

- They look very similar. 
- Syntax when writing and rendering them inside root is different.

```js
// React element - Just a normal JS variable. After getting parsed it is just a JS object.

const heading = (
   <h1 id="title" key="h1">
      Heading
   </h1>
)
const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(heading);



// Component - After getting parsed it is just a JS function that returns JSX code.

const HeaderComponent = () => {
  return(
    <div>
      <h1>Functional Component</h1>
      <h3>Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquam, officiis!</h3>
    </div>
  )
}
const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<HeaderComponent/>);
```

### Rendering React element inside Component :

```js
const heading = (
  <h1 id="title" key="h1">
     React Element
  </h1>
)

const HeaderComponent = () => {
  return(
    <div>
      {heading}
      <h1>Functional Component</h1>
      <h3>Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquam, officiis!</h3>
    </div>
  )
}

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<HeaderComponent/>);
```

### Rendering Component inside Component :

- Instead of curly brackets, we have write it as a tag.
- OR we can call it like a normal JS function.

```js
const Heading = () => (
  <h1 id="title" key="h1">
     React Element
  </h1>
)

const HeaderComponent = () => {
  return(
    <div>
      <Heading/>
      <h1>Functional Component</h1>
      <h3>Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquam, officiis!</h3>
    </div>
  )
}

// OR ------------------ Call it like a normal function

const HeaderComponent = () => {
  return(
    <div>
      {Heading()}
      <h1>Functional Component</h1>
      <h3>Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquam, officiis!</h3>
    </div>
  )
}
```

## Component Composition :

- When we use a component inside a component as we did above, that is called as Component Composition or Composing Components.

## Advantages of JSX :

- JSX is powerful. You can write any piece of JS code inside { } curly brackets. 
- IMP : JSX is very secure. It protects your app from Cross-site scripting attacks. It does this by "sanitizing" your JS code.



