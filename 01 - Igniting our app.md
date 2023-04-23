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
- Parcel is a beast. It does a lot of things for us BTS.
- Provides HMR - Hot Module Reloading i.e. Parcel keeps a track of all the files we are updating in real-time and reloads the server automatically. It does this by using File Watcher Algorithm which is written in C++.
- Parcel even does Image optimization for us. 
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
- When we host our app, the node_modules are present on our server. It is easier to access files stored on our server than CDN which are stored elsewhere on third-party servers.
- So lets install React into our node_modules.

## Installing React into node_modules :

- We will install react as a Dependency in our project.
- "npm i react react-dom".

## Igniting our app using Parcel :

- npx (Node Package Execute) - means to execute something using npm
- Execute cmd : npx parcel index.html - "index.html" is the entry point
- This command will execute our code and host it on localhost server.
- On editing file, the server will even reload our page.
- "dist" folder is created which stores the minified, faster development version of our project and serves it on the server. It stores the development build.
- A folder with name ".parcel-cache" is created, which is used by parcel to do it's things(minify files, HMR, etc). It is a separate space used by parcel.
- To build a production build : "npx parcel build index.html"
- When we use Parcel to build our project, we need to remove {"main": "App.js",} i.e entry point of our app from package.json as we provide the new entry point in our build command itself. Or else parcel will throw error.
- After running the build command, Parcel will create 3 main files inside "dist" folder which are html, css, js. It will bundle, minified, clean console.logs all of your code into this 3 files.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Home</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width" />
  </head>

  <body>
    <div id="root">Not rendered</div>
    <script type="module" src="App.js"></script>
  </body>
</html>

```

```js
import React from 'react'
import ReactDOM from 'react-dom'

// creating a Nested React element
const heading1 = React.createElement('h1', {
    id:'title'
  }, 'Heading 1')
  const heading2 = React.createElement('h2', {
    id:'title'
  }, 'Heading 2')

  // Passing multiple children into an React element
  const container = React.createElement('div', {
    id: 'container'
  }, [heading1, heading2])

  const root = ReactDOM.createRoot(document.getElementById('root'))
  
  root.render(container)
```

### But we might encounter a error : Browser scripts cannot have imports or exports. For that add "<script type="module" src="App.js"></script>"

- We have to tell browser that we are using a module, not a normal script file. We cannot import/export scripts
- Now everything will work as expected. Parcel will do everything for you from compiling to hosting.

## Flow of our app after deploying on production :

- node_modules folder is on server.
- When client/user machine sends a request to server, the server ships the production build to the user.
- node_modules are not sent to client.
- Production build already contains the node_modules in minified form.
- Now the most heaviest thing for our website is the "media" i.e images, videos, etc.
- For us, Parcel even does Image optimization for us. 




## video : 1.49.20
















