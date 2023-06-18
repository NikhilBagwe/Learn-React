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
- Question : Can we use React fragment inside a React fragment ????

## Adding CSS using 'style' :

- In React we cannot use the normal way to add styling to out component i.e using inline CSS using 'style' attribute.
- Since, we are using JSX, it is like writing HTML inside JS. So we have a different way of adding styles to our app.
- In JSX component, 'style' attribute takes an JS object containing CSS styles or we can write this obj inside it directly. 
- eg: style={{backgroundColor:'red',}}
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

## Adding CSS using 'className' :

- Another way to add CSS is to give the JSX element a className and write CSS inside 'index.css' file.

## Config Driven UI System Design :

- The whole UI of the website is driven by the configs send from the backend API.
- Lets take example of Swiggy. It may have different offers running in different cities. But it cannot have different website for each city.
- So here we control the UI of the single website using the config, and display it differently to the user based on its location.

## Props :

- Shorthand for  Properties.
- Basically we pass some data into our Functional Component using props.
  
```js
const RestaurantCard = (props) => {
  return(
    <div>
      <h1>{props.restaurant.data?.name}</h1>
    </div>
  )
}

const Body = () => {
  return(
    <div>
      {RestaurantCard(restaurantList[0])}
      <RestaurantCard restaurant = {restaurantList[0]}>
    </div>
  )
}
```
- Props are similar to passing an argument into a JS function and are received as parameters into the function.
- We can pass multiple props.
- We can also destructure the props so to avoid writing 'props.restaurant..'
  
```js
const RestaurantCard = ({ restaurant }) => {
  const {name, cuisines} = restaurant.data // we can further destructure the 'restaurant' obj
  
  return(
    <div>
      <h1>{name}</h1>
    </div>
  )
}










8
