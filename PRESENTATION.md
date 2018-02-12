![alt text](react-icon.jpg "React")

# React.js

#### Roksolana Fedkovych

---

# What is React.js?
---

# Why was React developed?

-- --

### Why was React developed?

* Complexity of Facebook's UI architecture
* Complexity of two-way data binding
* Bad UX from using "cascading updates" of DOM tree
* A lot of data on a page changing over time

---


# Sites Using React

-- --

![alt](https://i0.wp.com/onhax.me/wp-content/uploads/2016/09/wk.1.png?resize=300%2C300&ssl=1)
![alt](http://blog.postofficeshop.co.uk/wp-content/uploads/2014/04/new-ebay-logo.jpg)
![alt](https://n6-img-fp.akamaized.net/free-vector/instagram-icon_1057-2227.jpg?size=338&ext=jpg)
![alt](https://is2-ssl.mzstatic.com/image/thumb/Purple118/v4/3a/e0/0b/3ae00b50-9e6f-295c-1456-77c8a17f59b4/AppIcon-1x_U007emarketing-0-0-GLES2_U002c0-512MB-sRGB-0-0-0-85-220-0-0-0-6.png/246x0w.jpg)
![alt](https://assets.ifttt.com/images/channels/1352860597/icons/on_color_large.png)
![alt](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT8JqBq4Suu09IC10UdUEG73T1-0xk7nkfYdMPl9FREe-OhtKa6)
![alt](https://cfl.dropboxstatic.com/static/images/logo_catalog/glyph_m1@2x-vflA6lTFZ.png)
![alt](https://images-na.ssl-images-amazon.com/images/G/01/imdb/images/logos/imdb_fb_logo-1730868325._CB514892123_.png)

https://github.com/facebook/react/wiki/Sites-Using-React

---

# Configuration

-- --

## Own configuration

* `package.json` - dependencies
* `webpack.config.js` - config for transpiling js and jsx


![alt](https://www.bram.us/wordpress/wp-content/uploads/2016/04/es6-webpack-react-babel.png)

-- --

## Create React App
* `$ create-react-app my-app`

* `$ cd my-app`

* `$ npm start`

---

# Virtual DOM

-- --

## Virtual DOM

A virtual DOM object has the same properties as a real DOM object, but it lacks the real thing's power to directly change what's on the screen.

Manipulating the DOM is slow. Manipulating the virtual DOM is much faster, because nothing gets drawn onscreen. Think of manipulating the virtual DOM as editing a blueprint, as opposed to moving rooms in an actual house.

-- --

## Projecting Data

![alt](v-dom1.jpg)

-- --

## Projecting Data

![alt](v-dom2.jpg)

---

# What is JSX

-- --

## What is JSX

JSX is an XML/HTML-like syntax used by React that extends ECMAScript so that XML/HTML-like text can co-exist with JavaScript/React code. The syntax is intended to be used by preprocessors (i.e., transpilers like Babel) to transform HTML-like text found in JavaScript files into standard JavaScript objects that a JavaScript engine will parse

-- --

## Syntax

```jsx
const element = <img className="userAvatar" src={this.props.user.avatarUrl}></img>;
```

```jsx
const element = <img src={this.getImageScr()} />;
```

-- --
![alt](http://blog.tamizhvendan.in/images/react-hello-world/babel-loader.png)
-- --

## JSX/JavaScript code

```jsx
const nav = (
  <ul id="nav">
    <li><a href="#" className="home">Home</a></li>
    <li><a href="#" className="about">About</a></li>
    <li><a href="#" className="contact_us">Contact Us</a></li>
  </ul>
);

```
-- --

## Babel will transform it into

```jsx
let nav = React.createElement(
  "ul",
  { id: "nav" },
  React.createElement("li", null,
    React.createElement(
       "a", { href: "#" },
       "Home"
    )
  ),
  React.createElement("li", null,
    React.createElement(
       "a", { href: "#" },
       "About"
    )
  ),
  React.createElement("li", null,
    React.createElement(
       "a", { href: "#" },
       "Contact Us"
    )
   )
);
```

---

# Component

-- --

## Component

Components are self-contained reusable building blocks of web application.
React components are basically just idempotent functions (same input produces same output).

They describe your UI at any point in time, just like a server-rendered app.

-- -- 

### Functional component

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

-- --

### Class component

```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}

```

-- --

### Rendering a component

```jsx
const element = <Welcome name="Yoda" />;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

-- --

### Composing Components

```jsx
function App() {
  return (
    <div>
      <Welcome name="Vader" />
      <Welcome name="Luke" />
      <Welcome name="Leia" />
    </div>
  );
}

ReactDOM.render(
  <App />,
  document.getElementById('root')
);
```

---

# Props & State

---

# Props

-- --

## Props are Read-Only

```jsx
function Avatar(props) {
  return (
    <img className="avatar"
      src={this.props.src}
      alt={this.props.alt}
    />
  );
}

...

function Comment(props) {
  return (
    <div className="comment">
      <div className="user-info">
        <Avatar 
          src={this.props.author.image.src}
          alt={this.props.author.fullName}
        />
      </div>
  ....


```

---

# State

-- --

## State

```jsx
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }

  tick() {
    this.setState({
      date: new Date()
    });
  }

  render() {
    return (...);
  }
}

```

---

# Lifecycle

-- --

## Mounting

* `constructor()`
* `componentWillMount()`
* `render()`
* `componentDidMount()`

-- --

## Updating

* `componentWillReceiveProps(nextProps)`
* `shouldComponentUpdate(nextProps, nextState)`
* `componentWillUpdate(nextProps, nextState)`
* `render()`
* `componentDidUpdate(prevProps, prevState)`

-- --

## Unmounting

* `componentWillUnmount()`

-- --

## `render()`

* React elements 
* String and numbers
* Portals
* null
* Booleans.

-- --
## [Understanding the React Component Lifecycle](http://busypeoples.github.io/post/react-component-lifecycle/)

---


# Thinking in React

-- --

### Start With A Mock

![alt](https://reactjs.org/static/thinking-in-react-mock-1071fbcc9eed01fddc115b41e193ec11-4dd91.png)

```javascript
// JSON API returns:
[
  {category: "Sporting Goods", price: "$49.99", stocked: true, name: "Football"},
  {category: "Sporting Goods", price: "$9.99", stocked: true, name: "Baseball"},
  {category: "Sporting Goods", price: "$29.99", stocked: false, name: "Basketball"},
  {category: "Electronics", price: "$99.99", stocked: true, name: "iPod Touch"},
  {category: "Electronics", price: "$399.99", stocked: false, name: "iPhone 5"},
  {category: "Electronics", price: "$199.99", stocked: true, name: "Nexus 7"}
];
```

-- --

### Step 1: Break The UI Into A Component Hierarchy

![alt](https://reactjs.org/static/thinking-in-react-components-eb8bda25806a89ebdc838813bdfa3601-82965.png)

```
* FilterableProductTable
  * SearchBar

  * ProductTable
    * ProductCategoryRow
    * ProductRow
```

-- --

### Step 2: Build A Static Version in React

-- --

### Step 3: Identify The Minimal (but complete) Representation Of UI State

-- --

### Step 4: Identify Where Your State Should Live

-- --

### Step 5: Add Inverse Data Flow

-- --

### And That’s It


---

# [*Calculator*](https://ahfarmer.github.io/calculator/)

-- --

+ components
  + App.js
  + Display.js
  + ButtonPanel.js
  + Button.js

-- --

### App.js

```jsx
import React from 'react';
import Display from './Display';
import ButtonPanel from './ButtonPanel';
import calculate from '../logic/calculate';

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      total: null,
      next: null,
      operation: null,
    };
  }

  handleClick = (buttonName) => {
    this.setState(calculate(this.state, buttonName));
  }

  // ...
```

-- --

### App.js

```jsx
  // ...

  render() {
    return (
      <div className="component-app">
        <Display
          value={this.state.next || this.state.total || '0'}
        />
        <ButtonPanel
          clickHandler={this.handleClick}
        />
      </div>
    );
  }
}
export default App;
```

-- --

### ButtonPanel.js

```jsx
class ButtonPanel extends React.Component {
  handleClick = (buttonName) => {
    this.props.clickHandler(buttonName);
  }

  render() {
    return (
      <div className="component-button-panel">
        <div>
          <Button name="AC" clickHandler={this.handleClick} />
          <Button name="+/-" clickHandler={this.handleClick} />
          <Button name="%" clickHandler={this.handleClick} />
          <Button name="÷" clickHandler={this.handleClick} orange />
        </div>
        <div>
          <Button name="7" clickHandler={this.handleClick} />
          <Button name="8" clickHandler={this.handleClick} />
          <Button name="9" clickHandler={this.handleClick} />
          <Button name="x" clickHandler={this.handleClick} orange />
        </div>
        // ...
      </div>
    );
  }
}
export default ButtonPanel;
```

-- --

### Button.js

```jsx
import React from 'react';

class Button extends React.Component {
  handleClick = () => {
    this.props.clickHandler(this.props.name);
  }

  render() {
    const className = [
      "component-button",
      this.props.orange ? "orange" : "",
      this.props.wide ? "wide" : "",
    ];

    return (
      <div className={className.join(" ").trim()}>
        <button onClick={this.handleClick}>
          {this.props.name}
        </button>
      </div>
    );
  }
}
export default Button;
```

-- --

### Display.js

```jsx
import React from 'react';

class Display extends React.Component {
  render() {
    return (
      <div className="component-display">
        <div>
          {this.props.value}
        </div>
      </div>
    );
  }
}
export default Display;
```

---

# Server-Side React Rendering

---

# Thanks!
