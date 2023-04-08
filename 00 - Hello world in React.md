## Intro :

- Here I have used React without actually installing it.
- Since it is just a library, we have simply added the CDN links and now we use React in our project.
- No complex things such as JSX, Props, etc. are used, just simple HTML and JS.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Home</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width" />
    <link rel="stylesheet" href="styles.css" />
    <script type="module" src="script.js"></script>
  </head>
  
  <body>
    <div id="root"></div>
  </body>

  <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
  <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

  <script>
    // creating a React element
  	const heading = React.createElement('h1', {}, 'Namaste React')

    // Telling React that this is my root element inside which i want to run react code
    const root = ReactDOM.createRoot(document.getElementById('root'))
    
    root.render(heading)
  </script>
</html>

```
