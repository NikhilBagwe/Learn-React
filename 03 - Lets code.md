## Comments in JSX :

- Similar to how we write comments in JS.

```js
const HeaderComponent = () => {
  return(
    <div>
      {
        // Comment in JSX
      } 
      <h1>Functional Component</h1>
      <h3>Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquam, officiis!</h3>
    </div>
  )
}
```

## Is JSX, ES6+ mandatory for React ?

- No it is not mandatory.
- React is very flexible library.
- We can also use React in a particular part of a website for example footer.

## Structuring our food ordering app :

```js
const AppLayout = () => {
  return(
    {/**
    Header
      - Logo
      - Nav items on right side
      - Cart
    Body
      - Search Bar
      - Restaurant List
        - Restaurant Card
          - Image
          - Cuisine
          - Rating
          - Name
    Footer   
      - links
    */}
  )
}
```

## NOTE : Any piece of JSX expression/component must have only one parent. Use React Fragments or a 'div' element

## React.Fragments :
  
- It is a component which is exported by 'React' library.
```js
import React from "react";

const AppLayout = () => {
  return(
    <React.Fragment>
      <HeaderComponent/>
      <Body/>
    </React.Fragment>
  )
}
```
- We can also use a 'div' instead of it but the code looks ugly as another div gets added within div with id of 'root'.
- Using React.Fragment that extra div can be eliminated.
- But still our code looks ugly as we have to write <React.Fragment>.
- React.Fragment is like an empty tag so we can just write it as below.
```js
const AppLayout = () => {
  return(
    <>
      <HeaderComponent/>
      <Body/>
    </>
  )
}
```
- We cannot pass any attributes into it.

## Adding CSS using 'style' :

- style takes an JS object containing CSS styles.
```js
const styleObj = {
  backgroundColor:'red',
}
const Body = () => {
  return(
    <div style={styleObj}>
      <h1>Body</h1>
    </div>
  )
}
```



















8
