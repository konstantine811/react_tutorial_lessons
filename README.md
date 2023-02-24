# First React App

```html
<script>
  // React app
  const App = () => {
    return React.createElement(
      "div",
      {},
      React.createElement("h1", {}, "Adopt Me!")
    );
  };
  const container = document.getElementById("root");
  const root = ReactDOM.createRoot(container);
  root.render(React.createElement(App));
</script>
```

## This is about the simplest React app you can build.

- The first thing we do is make our own component, App. React is all about
  making components. And then taking those components and making more components
  out of those.
- There are two types of components, function components and class components.
  This is a function component. We'll see class components shortly.
- A function component must return markup (which is what React.createElement
  generates.)
- These component render functions have to be fast. This function is going to be
  called a lot. It's a hot code path.
- Inside of the render function, you cannot modify any sort of state. Put in
  functional terms, this function must be pure. You don't know how or when the
  function will be called so it can't modify any ambient state.
- React.createElement creates one instance of some component. If you pass it a
  string, it will create a DOM tag with that as the string. We used h1 and div,
  those tags are output to the DOM. If we put x-custom-date-picker, it'll output
  that (so web components are possible too.)
- The second empty object (you can put null too) is attributes we're passing to
  the tag or component. Whatever we put in this will be output to the element
  (like id or style.)
- First we're using document.getElementById to grab an existing div out of the
  HTML document. Then we take that element (which we called container) and pass
  that into ReactDOM.createRoot. This is how we signal to React where we want it
  to render our app. Note later we can root.render again to change what the root
  of our React app looks like (I rarely need to do that.)
- Notice we're using React.createElement with App as a parameter to root.render.
  We need an instance of App to render out. App is a class of components and we
  need to render one instance of a class. That's what React.createElement does:
  it makes an instance of a class. An analogy is that App as a class of
  components is like Honda has a line of cars called Civics. It's a whole line
  of cars with various different options and parameters. An instance of a Civic
  would be one individual car. It's a concrete instance of the Civic car line.
