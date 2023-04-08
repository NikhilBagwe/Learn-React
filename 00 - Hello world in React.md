## Intro :

- Here I have used React without actually installing it.
- This is the CORE way of creating a React element.
- Since it is just a library, we have simply added the CDN links and now we use React in our project.
- No complex things such as JSX, Props, etc. are used, just simple HTML and JS.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Home</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width" />
  </head>

  <body>
    <div class="header">Header</div>
    <div id="root"></div>
    <div class="footer">Footer</div>
  

    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

    <script>
      // creating a React element
      const heading = React.createElement('h1', {
        id: 'title'
      }, 'Namaste React')
      console.log(heading)

      // Telling React that this is my root element inside which i want to run react code
      const root = ReactDOM.createRoot(document.getElementById('root'))
      
      root.render(heading)
    </script>
  </body>
</html>


```

- We can have rest of our HTML code inside body tag with root element. Still react will work fine since it's just a library. Whatever React code will be rendered only in that root element, rest code will be unaffected.

```html
<body>
    <div class="header">Header</div>
    <div id="root"></div>
    <div class="footer">Footer</div>
</body>
```

- We can also have multiple root elements in React but generally we use only one.
- NOTE: Even if we hardcode some elements inside root, on rendering React will override everything and will only display the elements which we passed inside render()

## Understaning React.createElement() :

- React Element is a plain JS object.
- In createElement(), we pass 3 parameters in it.
- Type of HTML element we want.
- Attributes/props of that element
- Text or element to be rendered.

## Rendering a Nested React element :

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Home</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width" />
  </head>

  <body>
    <div id="root"></div>

    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

    <script>
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
    </script>
  </body>
</html>

```

### FACT : React team wanted to write all their HTML, CSS inside JS. So they came up with this idea.







