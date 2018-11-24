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


## React.js how to convert Date into human-readable format

Date works in a strange way.
A command like,

``` Date() ```

renders a long string like "Wed Nov 21 2018 16:16:59 GMT.... "

How to save the date:
``` date = newDate().getTime() ```
This will render a long number like "1542846323960" which is actually the number of milliseconds between midnight of January 1, 1970 and the moment the line was executed just now. 

This is fine if you are just rendering it on a page. But if you are saving the state in local storage, then repopulating the page and need the date at that time, you will find an error because while React can load date, loading it back from local storage will be an issue.

Here is a concise way to render the time from the command:
```
import React from 'react';

class CurrentDate extends React.Component {
    constructor() {
        super();

        let date = new Date().getTime();
        let hours = date.getHours();
        let minutes = date.getMinutes();
        let seconds = date.getSeconds();
        let displayTime = hours + ":" + minutes + ":" + seconds; //making it in the format of HH:MM:SS
        return displayTime;

        this.state = {date: date};  //saving the state
    }

    render() {
        return (
            <div className='date'>
                {this.state.date}
            </div>
        );
    }
}


```



## How to make a small JavaScript project with HTML and CSS

Most web pages do not have a comfortable environment with HTML, CSS, and JavaScript in 3 convenient panes to write your code in. In fact, most of the time when you inspect any internet page, it is a single HTML page with scripts inside of it containing JavaScript.

So how do you make a webpage using a tool like CodePen and then turn it into a real web page?

Here is how:
Say you are using CodePen to develop your code...

Your HTML looks like this:
```
<html>
  <head>
      <meta charset="utf-8">
      <title>SimpleWebPage</title>
      <script src="https://unpkg.com/react@16/umd/react.development.js"></script>
      <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
      <script src="https://unpkg.com/babel-standalone@6.26.0/babel.js"></script>
  </head>
  <body>    
      <div id="root">ROOT</div>        
      <script type="text/babel">               
      </script>
  </body>
</html>
```
And your CSS looks like this:

```
body {
  background-color: lightgrey;
}
```

and your 3rd pane with JavaScript looks like this:
```
class HelloReact extends React.Component {
  constructor(props) {
    super(props); 
  }
  render() {
    return (
      <h1>Hello React!</h1>
    );
  }
}

ReactDOM.render( 
  <HelloReact/>, 
  document.getElementById('root')); 
```

Here is how to combine them all into one single working project:
1) On your computer, create a file structure like so:
    <folder>
     |
     +--<CSS folder>
     |
     +-- index.html

1) Copy and paste your HTML code into the newly created index.html file. Save. 
2) Go into your HTML file. Locate the top of the scripts in the head tags. Add your CSS file like this:
``` <link rel="stylesheet" href="css/styles.css"> ```
This means you will be saving your CSS file in the CSS folder you just created.
3) Open a new pair of script tags in the body of the HTML and paste your entire JavaScript inside. Save.
3) Go into the CSS folder and create a file called styles.css.
4) Paste the CSS code inside the styles.css file. Save.
6) Now right-click on your index.html file and say open with browser.
You should see your project live in the browser!

While this may seem simple, it can be confusing to those just beginning to design web applications.
