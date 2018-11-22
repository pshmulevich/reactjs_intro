# reactjs_intro
## Introduction to React.js
React.js is a Javascript library for building user interfaces.
But why __"React"__? This JavaScript library allows users to reuse code in components that change frequently. React also doesn't rerender everything when only one component changes.

What does this mean?
It means you don't want to rebuild your entire car when pressing the gas pedal, you just change the state of the speed you are going at.

Virtual DOM allows ReactJS to know exactly what to re-render because it can detect what has changed. This is because it is reactionary in nature (hence the name, React.js).

__What are the basics?__


The basic structure of any React.js class is as follows:

* Javascript library links (if any, some required)
* Root element
* Top-level React Class which has the render() method embedded
* ReactDOM.render method invokes react.render which binds class and root element together.

React components also have state. That means a change in one of these components triggers a change of state.
Changing the state causes React to call the render() method, updating the content.
State changes can be triggered by mouse clicks, typing, or other events. 

For now, here is a basic component in React.js with a familiar example:

[Here is a live example](https://codepen.io/pshmulevich/pen/RqQYzB?editors=1011)

```
class HelloReact extends React.Component {
  render() { //<--- the render method must be in the top level class in React.
    return (
      <h1>Hello React!</h1>
    );
  }
}

ReactDOM.render( 
  <HelloReact/>, 
  document.getElementById('root')); 
```

More resources: 
[Here is a good cheat sheet for React to use](https://devhints.io/react) 
