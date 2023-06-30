## 1. What is Emmet ?

- Emmet is a free add-on/plugin for your text editor.
- It allows you to type shortcuts that are then expanded into full pieces of code.
- By using Emmet, developers type less.
- While typing the Emmet Abbreviations, you can press "Ctrl + Space" see what will be generated(Inside a pop up)

### Example :
- Generate a div with text content inside them : div{This is a div}
- To generate nested we will use ‘>’ operator : ul>li
- Generate a list 3 li’s , each li has an anchor(a) tag : ul>li*3>a

## 2. Difference between a Library and Framework ?

- You have complete control over the application's flow when you use a "Library". You get to decide when and where you want to call the library.
- You can simply insert a Image carousel made using React in an plain HTML,CSS website.
- While when using a framework, the flow is controlled by the framework itself. It provides ready to use tools, standards, templates and we have to use them only .
- When an application code uses a library, the developer writing the code is in charge of the application flow. This means the developer decides when to call the library.
- However, when we use a framework, the framework decides when to call the library. This shift in control of calling the library from the application code to the framework is an inversion of control.

### Limitations of a Framework :

- Options to tweak functionalities are limited.
- Sometimes application development becomes complex
- Have to be up-to-date with new/deprecated features in every version.

### Limitations of a Library :

- Using a library means that our code is tied to that library.
- Using several libraries might impact the performance of an application adversely because of dependency conflicts.
- Sometimes libraries are vulnerable to malicious attacks.

## 3. What is CDN? Why do we use it?

- A content delivery network is a distributed group of servers that caches content near end users.
- It is a network of interconnected servers that speeds up webpage loading for data-heavy applications
- It allows for the quick transfer of assets needed for loading Internet content, including HTML pages, JavaScript files, stylesheets, images, and videos.
- It distributes network traffic evenly across several servers, making it easier to scale rapid boosts in traffic.
- A CDN consists of multiple data centers around the world called points of presence (PoPs). Each PoP is capable of hosting and serving content to users. CDNs route users to specific PoPs based on a number of factors including distance, PoP availability, and connection speed.


## 4. Why is React known as React?

- React was developed for applications (Facebook) that have constantly changing data.
- Since React is a front-end framework or the “View” in MVC, this means that as the user clicks around and changes the app’s data, the view should “react” or change with those user events.
- React is called "React" because of its core feature, which is its ability to "react" or respond dynamically to changes in data.
- The name "React" also reflects the fact that the library is built around the concept of a unidirectional data flow, where changes in data flow down through the component hierarchy, triggering updates and re-renders as necessary.

## 5. What is crossorigin in script tag ?

- It provides support for CORS(cross-origin resource sharing), defining how the element handles cross-origin requests.
- It is used to handle the CORS request that checks whether it is safe to allow for sharing the resources from other domains.
- Resources may include Audio, Video, Images, Link or external script.
- CORS : It is a mechanism by which one webpage requests to another domain for fetching out the resource like audio, video, script, etc. from the third party server

## 6. What is diference between React and ReactDOM ?

- The react package holds the react source for components, state, props and all the code that is react.
- The react-dom package as the name implies is the glue between React and the DOM. Often, you will only use it for one single thing: mounting your application to the index.html file with ReactDOM.render().
- React DOM is the glue between React and the DOM. When u want to show your react component on DOM u need to use this ReactDOM.render(); from React Dom.
- React is used in web and in mobile. React-Dom is used only in web apps.
- In a nutshell, Whenever we use component, classes, elements, etc. We’re using React and whenever we use methods like render() or findDOMNode() we’re using React-DOM.


## 7. What is difference between react.development.js and react.production.js files via CDN?

- Development build runs the code as a Development environment and it is very slow.
- Production build is for running the code on client browsers with more performance improvements.

- react.development.js: This file is used during development and contains the full, uncompressed version of the React library. It includes additional warnings and error messages that are helpful for debugging and development purposes. It is larger in size compared to the production version.

- react.production.js: This file is optimized for production environments and is used when you are ready to deploy your application. It is a minimized and optimized version of the React library, which means it has been stripped of development-specific features, warnings, and extra code. It is smaller in size compared to the development version, resulting in faster load times for your application.

## 8. What is async and defer?














# -9



