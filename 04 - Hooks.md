## Export React components :

- There are 2 ways to export 

### 1. export default comp_name :

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
- A hacky way is to put multiple comps. into a obj and default export that obj.
- But a file can have multiple components in it. For that we use 2nd method.

### 2. export keyword :

- Mention export keyword at start of defining the functional component.
```js
export const Title = () => (
  <a className="logo" href="/">
    Food Fire
  </a>
);
```
- Here we export the comp. by name, so while importing it we have to extract it.
- It is called as Named import.

```js
// Named import
import {Title} from "./components/Title";
```

- We can use both export methods into a single file also.

















0
