# React
React is a JavaScript user interface (UI) library created and maintained by Facebook and the developer community as open source.


## JSX
JSX is a syntactic extension to regular JavaScript and is used to create React elements. These elements are then rendered in the React Document Object Model, or DOM. JSX is a declarative language that combines JavaScript with HTML. JSX  particularly popular in React applications, optimizes code performance by compiling source code into JavaScript that runs faster than its equivalent code written directly in JavaScript.

I have mastered:
-	Create a simple React page
-	Create, run and render a React application
-	Set properties for a react component
> Functional components are most useful when the component has properties (props), but there is no need to manage the component's lifecycle. Properties can be constrained by the user and passed to the function as parameters.

> Class components are preferred over functional components because of their versatility. They inherit from React.Component and must override the render method. Class components can have states and properties. These components have a life cycle that can be managed and maintained. This way you can create a class component instead of an application with functional components.


## Components
Components make the task of creating a user interface easier. The user interface can be broken down into several separate parts called components and combine them into a parent component that forms the final user interface. They can be reused and processed independently.
The main function of a React component is to render the user interface and update it whenever its internal state changes.
Components in a React application can be styled by using the className attribute and applying any Cascading Style Sheets (CSS) styles to it.
- In addition to rendering the UI, it manages UI-related events, such as a button component that has a click event.
- A state is an object that describes the behavior and display of a component at a given moment.
- A React component can be stateful or stateless.
- Stateful components are a class type, while stateless components are a function type.

Lifecycle methods are built-in React methods that work with
components throughout their entire stay in the DOM.
Higher Order Component (HOC) is an advanced React technique for reusing component logic.
This component is not a React component available in the API. This is a pattern that emerged as a result of the compositional nature of React. Essentially, HOC are functions that return components that are used to share logic with other components.

### React components - Components are reusable segments of code that come under the class and functional component types.
```
import React from 'react';
import {Text} from 'react-native’;
const Helloworld= ()=>
{
    return
    (Hello, World!);
}
export default Helloworld;
```

### React class Component - React class component contains- Props: set from outside the class State: internal to the class
```
import React from "react";
class App extends React.Component {
constructor(props) {
super(props);
this.state={change: true };
}
render() {
return(
<button Click={()=>{this.setState({change: !this.state.change});}}>Click Here!</button>
{this.state.change?(Hello!!):(Welcome to the React Course)});}}
export default App;
```

### onClick - When an event fires, event handlers decide what should happen next. This could involve pressing a button or altering a text entry.
```
function changeColor() {
const shoot = () => {
    alert("Color Changed!");
}
return (
<button onClick={change}>Change the Color! </button>
);
}
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<changeColor />);
```
