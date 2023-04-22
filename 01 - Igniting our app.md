## Intro :

- In our browser console, we get 'window' object from JS engine using which we can perform lot of tasks.
- Similarly in React we get all it's superpowers from the React code that we import using CDN link. The React code exports lots of functions. Once imported in our code, 
  now  we can access 'React, ReactDOM' object in console.
- In this tutorial, we will learn how to make our app production ready.

## Bundlers :

- To make our app production ready, we have to perform optimization, minify files, clear console log, etc.
- Bundler helps us to do this.
- Bundlers are used to reduce the size of the code and improve the performance of the application.
- The 'create-react-app' uses Webpack and Babel as bundler. But we will use Parcel.

## Parcel :

- Parcel is a bundler which basically is a package.
- A package is a JS module. 
- To install Parcel into our project we need a Package manager. 
- We use NPM for it.

### NOTE: NPM dosen't stand for Node package manager. There no actual full name for it. 

- NPM manages all the packages that we use in our React project. Our React app is powered by multiple packages.
- NPM generates package.json file.
- Now we install Parcel as a dev dependency into our project. "npm i -D parcel" or "npm i --save-dev parcel".

### Dependency : It is a package on which our project is dependent and will need it even in production.
### devDependencies : are those packages in the package.json file that you need only for project development purposes

- Now "package-lock.json" file is generated in our project folder.

### package-lock.json :

- If you see in package.json file, parcel is installed with its version being mentioned.
```js
"devDependencies": {
    "parcel": "^2.8.3"
 }
```
- Before version number a caret symbol '^' is used. It means when in future a new version is available, our package will automatically be updated to it.
- We can also use a '~' instead of '^'.
- package-lock.json file keeps track of which exact version of given package is been used in our code as the package might get auto-updated.
- Never put it in gitignore file.
- It basically maintains the exact version of all packages to avoid the situation where " Your app runs on local but dosen't work in production".
- Also it keeps track of each and every package installed in node_modules.

### node_modules :

- A folder with name node_modules is created which contains the folder with files for Parcel along with further dependencies.
- Our project is dependent on parcel. Then parcel is depenedent on futher packages/modules also. Those are installed in node_modules.

### NOTE: We never put node_modules onto git repo because they are very heavy. We can generate everything we have in node_modules if we have package-lock.json and package.json files. So we generate node_modules onto our servers using them.

## Don't use CDN :

- In case the React version is updated, we have to update our link and do the whole process of deployment again.
- When we host our app, the node_modules are present on our server. It is easier to access files stored on our server than CDN which are stored elsewhere.
- So lets install React into our node_modules.

## Installing React into node_modules :

- We will install react as a Dependency in our project.
- "npm i react react-dom".





## video : 
















