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


**State** is a simple JavaScript object used by React to represent information about the current situation in a component. The heart of every React component is its "state".
The state of a component is an object containing some information that may change during the life of the component.
State can only be used natively in class components. In functional components, you must use the `useState` hook to enable stateful functions.
> State is used to manage data and props are used to transfer data.

> State can be changed using the setState() method, while properties can be passed from a parent component to a child component only in a unidirectional flow.


## Lifecyrcle
Each React component consists of three lifecycle stages. 
### Mounting 
Is the moment when a component is first created. 

* `constructor()`
* `getDerivedStateFromProps()`
* `render()`
* `componentDidMount()`

```
import React from 'react';

class App extends React.Component {
	constructor(props) {
		super(props)
		console.log("Inside the constructor")
	}

	componentDidMount = () => {
		console.log("Inside component did mount")
	}

	render() {
		console.log("Inside render method")
		return (
			<div>
				The component is rendered
			</div>
		);
	}
}

export default App;
```


### Update 
Is the rendering of a component when its state or properties (props) change. 

* `getDerivedStateFromProps()`
* `shouldComponentUpdate()`
* `render()`
* `getSnapshotBeforeUpdate`
* `componentDidMount()`

```
import React from 'react';

class App extends React.Component {
	state = { counter: "0" };

	incrementCounter = () => this.setState({ counter: parseInt(this.state.counter) + 1 });

	shouldComponentUpdate() {
		console.log("Inside shouldComponentUpdate")
		return true;
	}

	getSnapshotBeforeUpdate(prevProps, prevState) {
		console.log("Inside shouldComponentUpdate ");
		console.log("Prev counter is " + prevState.counter);
		console.log("New counter is " + this.state.counter);
		return prevState;
	}

	componentDidUpdate() {
		console.log("Inside component did mount")
	}

	render() {
		console.log("Inside render")
		return (
			<div>
				<button onClick={this.incrementCounter}>Click Me</button>
				{this.state.counter}
			</div>
		);
	}
}

export default App;
```


### Unmounting 
Is the removal of a component from the Document Object Model (DOM).
* `componentWillUnmount()`

```
import React from 'react';

class AppInner extends React.Component {
	componentWillUnmount() {
		console.log("This component will unmount")
	}
	render() {
		return <div>inner component</div>
	}
}

class App extends React.Component {
	state = { innerComponent: <AppInner /> }
	componentDidMount() {
		setTimeout(() => {
			this.setState({innerComponent:<div>unmounted</div>})
		}, 5000)
	}

	render() {
		console.log("Inside render")
		return (
			<div>
				{this.state.innerComponent}
			</div>
		);
	}
}

export default App;
```



## Pass data to a child through props

```
class App extends React.Component {
	state = { childColor: "green", name: "John" }
	changeColor = () => {
		const newColor = document.getElementById("colorbox").value;
		this.setState({childColor: newColor})
	}

	changeName = () => {
		const newName = document.getElementById("namebox").value;
		this.setState({ childColor: newName})
	}

	render() {
		console.log("Inside render")
		return (
			<div>
				Color <input type="Text" onChange=(this.changeColor) id="colorbox"/>
				<br />
				Name <input type="Text" onChange=(this.changeColor) id="namebox"/>
				<AppInner color=(this.state.childColor) name=(this.state.name)/>
			</div>
		);
	}
}

class AppInner extends React.Component {
	constructor(props) {
		super(props)
	}
	render() {
		const txtStyle = { color: this.props.color }
		return <span style={txtStyle}>{this.props.name}</span>
	}
}
```

## Initialization
Component is constructed with props and default state.


## Methods
1. The `constructor()` method creates an object. This can call a super constructor with the props object if any specific properties are set.
1. The `getDerivedStateFromProps()` method is used only when the state depends on changes in the props.
1. The `render()` method is required in a React component. This method causes the component to appear. It must return a DOM element and can only return a single root element, which may or may not contain many nested child elements.
1. The `componentDidMount()` method is called immediately after the component is mounted or inserted into the DOM tree.
1. The `getDerivedStateFromProps()` method is used only when the state depends on changes in the props.
1. The `shouldComponentUpdate()` method returns true by default.
1. The `getSnapshotBeforeUpdate()` method is called just before the changes are rendered. It helps you track changes. Any value returned by this lifecycle will be passed as a parameter to the `componentDidUpdate()` method, and `componentDidUpdate()` will be called immediately after the update.
1. When a component is unmounted or removed from the DOM tree, the `componentWillUnmount()` method is called.


