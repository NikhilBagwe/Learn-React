## Export React components :

- There are 2 ways to export 

### 1. export default comp_name : Default export

- Using "default" you can only export 1 component/function from the said file.

```js
const Title = () => (
    <a className="logo" href="/">
      Food Fire
    </a>
);

export default Title
```
- To import
```js
// Default import
import Title from "./components/Title";
```
- The name while importing shouldn't necessarily be same as the name of file. It can be anything. But keep it same as good practice.
- A hacky way is to put multiple comps. into a obj and default export that obj.
- But a file can have multiple components in it. For that we use 2nd method.

### 2. export keyword : Named export

- Mention export keyword at start of defining the functional component.
```js
export const Title = () => (
  <a className="logo" href="/">
    Food Fire
  </a>
);
```
- Here we export the comp. by name, so while importing it we have to extract it.
- It is called as Named import. It is not similar to obj destructuring. It is more like extracting.

```js
// Named import
import {Title} from "./components/Title";
```

- We can use both export methods into a single file also.

### Example :

- Title.js
```js
// Title component for display logo
export const Title = () => (
);

// Header component for header section: Logo, Nav Items
const Header = () => {
};
  
export default Header
```

- App.js
```js
import Header, {Title} from "./components/Title";

// OR

import * as xyz, {Title} from "./components/Title.js";

<xyz.Header/>
```

### NOTE : While importing we can put the only name or whole name of file while with extension. Eg: from "./components/Title"  OR  from "./components/Title.js" both works.

## .js vs .jsx file extension :

- They are just different file formats.
- Both are nearly same.
- Some libraries track your React file using the extension. Sometimes the code might break. 

## Config file : config.js or constants.js

- We put all the harcoded things into our config file.
- Eg : Image URL, obj list array like 'restaurantList', etc.

## Input field not working : One way data binding

- When you add an input element in a React component using JSX, on rendering it won't work.
- You won't be able to type anything in it unlike in plain HTML it would work.
- It is happening because React uses ONE WAY DATA BINDING.
- It means while writing anything in input field, React re-renders the comp. and we somehow need to modify the variable assigned to value by using "onChange" attribute. But it still won't work.
  
```js
const Body = () => {
  let searchTxt = 'KFC'

  return (
    <>
      <div className="searchcontainer">
        <input
          type="text"
          className="search-input"
          placeholder="Search"
          value={searchTxt}
          onChange={(e) =>  searchTxt = e.target.value)}
        />
        ....
};
```
- Thus, we conclude that Local variables don't work in React. We can use them to display constant values but can't update them.
- We need a React type of variable which can be changed dynamically known as "State".

## State :

- Every component in React maintains a State.
- We can put all the variables in State.
- We use useState() hook for it. useState() hook returns a array which looks like : [variableName, setFunction to update the variable]
- Thus, we use destructuring while using it.
```js
const [searchText, setSearchText] = useState()

// searchText - is a local state variable. We can use it like a normal variable.

// OR  -  another way to write -----
const searchVar = useState()
const [searchText, setSearchText] = searchVar
```
- But React says we cannot modify a variable like 'searchText' directly.
- We can only modify the state variable by using the function provided by useState() and calling it in onChange.
- The updated code looks like :
```js
const Body = () => {
  //const searchTxt = 'KFC'
  const [searchText, setSearchText] = useState('KFC')

  return (
    <>
      <div className="searchcontainer">
        <input
          type="text"
          className="search-input"
          placeholder="Search"
          value={searchText}
          onChange={(e) =>  setSearchText(e.target.value)}
        />{searchText}
        ......
};
```
- In above code we are updating 'searchText' as well as displaying it. Thus, we successfully acheived TWO WAY DATA BINDING in React.

## Why do we need State variables ? (IMP)

- Suppose if we are using a normal local variable in our functional component and displaying it.
```js
const Comp = () => {
    let num = 10;

    return({num})
}
```
- Some function updated it's value to 11.
- In this case, React will not know that it has to update the DOM i.e UI
- Because React cannot keep track of local variables.
- React says that everytime you want your UI to be in sync with your variable use "State".
- React keeps track of all State variables.
- So whenever we update a state variable, the component automatically re-renders i.e the whole component is destroyed and created once again and this whole process happens very fast. BTS Reconcilation happens.
- React by default has One way data binding. But using state we can acheive Two way data binding.

## Hooks :

- A hook is just a normal function.
- Every hook provides us with a specific functionality.
- Eg: useState() hook exported by 'react' library is used to create State variables.











0 : 01.49.00
