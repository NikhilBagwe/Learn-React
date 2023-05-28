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



















