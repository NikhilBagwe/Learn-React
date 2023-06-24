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












0
