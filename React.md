# 1.What is React?
React is a JavaScript library developed by Facebook (now Meta) for building dynamic and interactive user interfaces (UIs) for web and mobile applications.

Why React?

We can use states which means that once we update the state variable, it changes across the page.

We can split our app into multiple components and reuse those components.

React uses a virtual DOM to efficiently update the UI which is better than updating content using DOM Manipulation

Debugging and maintainance is easy

## Key Features of React:
### Component-Based Architecture:
React encourages building your UI by breaking it down into reusable components. Each component manages its own state and logic, which makes the code easier to maintain and scale.

### Declarative Approach:
Instead of manually manipulating the Document Object Model (DOM), React allows you to describe what the UI should look like for any given state. When the state changes, React efficiently updates and renders just the right components.

### Virtual DOM:
React uses a Virtual DOM, which is an in-memory representation of the actual DOM. When changes occur, React first updates the Virtual DOM, compares it with a snapshot of the previous state, and then makes minimal changes to the real DOM. This approach leads to improved performance, especially in complex applications.

### JSX (JavaScript XML):
React often uses JSX, a syntax extension that lets you write HTML-like code within JavaScript. JSX makes the code more readable and easier to write, though it's not strictly required—you can use plain JavaScript if you prefer.

### Ecosystem and Community:
React has a large ecosystem with tools like React Router for handling routing, Redux or Context API for state management, and many third-party libraries that complement its functionality. Its strong community support means there are plenty of resources, tutorials, and extensions available.

# 2. What is Single Page Loading (SPA)?
A Single Page Application (SPA) is a type of web application that dynamically updates a single HTML page as the user interacts with the app, rather than loading entire new pages from the server each time a user navigates

### Dynamic Content Loading:
In an SPA, only the necessary content is updated on the page. Instead of reloading the whole page, the application fetches data from the server in the background (often using AJAX or fetch APIs) and updates the view dynamically. This leads to a smoother, faster user experience.

### Client-Side Routing:
SPAs use client-side routing to manage navigation. When a user clicks a link or performs an action that would normally require a new page, the SPA updates the URL and the view without a full page reload. Modern browser history APIs (like the HTML5 History API) help manage this process.

### Improved Performance and Responsiveness:
Because SPAs only load data as needed and avoid full page reloads, they can offer a more responsive experience similar to that of a desktop application. Once the main page is loaded, interactions tend to be quicker since only small parts of the page are updated.

### Popular Frameworks and Libraries:
Many modern web development frameworks and libraries, such as React, Angular, and Vue.js, are well-suited for building SPAs. They provide tools and abstractions to manage dynamic updates, routing, and state management efficiently.

## Benefits:

Speed: After the initial load, the application feels fast because only parts of the page are updated.

Enhanced User Experience: Smooth transitions and interactions contribute to a more app-like experience.

Reduced Server Load: Since the server often only needs to provide data (usually in JSON format), it can reduce the strain on server resources.
## Considerations:

SEO: SPAs can be less search engine friendly since content is loaded dynamically. However, modern techniques like server-side rendering (SSR) or pre-rendering can mitigate this issue.

Initial Load Time: The initial download might be larger since the entire application framework needs to be loaded upfront.

Browser History and Navigation: Managing state and URL history on the client side requires careful design to ensure a seamless user experience.

# 3.Explain JSX with Examples?
JSX (JavaScript XML) is a syntax extension for JavaScript that looks similar to HTML. It is commonly used with React to describe what the UI should look like. JSX makes it easier to write and understand the structure of React components by allowing you to mix HTML-like code with JavaScript.

## Key Features of JSX
### HTML-Like Syntax in JavaScript:
JSX allows you to write code that looks like HTML directly inside your JavaScript code. This improves readability and helps visualize the component’s structure.

### JavaScript Expressions:
You can embed JavaScript expressions inside JSX by wrapping them in curly braces {}. This enables dynamic content and logic directly within the markup.

### Compilation to JavaScript:
Browsers do not understand JSX natively. Tools like Babel compile JSX into standard JavaScript function calls (e.g., React.createElement), which browsers can execute.

### Component-Based:
JSX is typically used to define components in React, which are reusable, self-contained pieces of the UI.

## JSX Examples
Basic Component Example
Here’s a simple React component written in JSX:

```js
import React from 'react';

function Greeting() {
  const name = "Alice";
  return (
    <div className="greeting">
      <h1>Hello, {name}!</h1>
      <p>Welcome to learning React with JSX.</p>
    </div>
  );
}

export default Greeting;
```
Explanation:

HTML-Like Structure: The return statement contains HTML-like code.

JavaScript Expressions: The variable name is embedded within curly braces ({name}) inside the h1 tag.

className Instead of class: In JSX, you use className because class is a reserved keyword in JavaScript.

Self-Closing Tags
All tags in JSX must be properly closed. For example, an <img> tag in HTML:

```js
<img src="logo.png" alt="Logo">

```
In JSX, it must be self-closed:
```js
<img src="logo.png" alt="Logo" />
```
## Event Handling Example
Handling events in JSX also differs slightly from HTML. In HTML, you might write:
```js
<button onclick="alert('Clicked!')">Click Me</button>
```
In JSX, the event handler is written in camelCase and passed a function:

```js
<button onClick={() => alert('Clicked!')}>Click Me</button>
```
## How JSX Differs from HTML
Embedding JavaScript:

JSX: Allows you to embed JavaScript expressions directly using {}.
```js
<p>The result is: {2 + 2}</p>
```
HTML: Does not allow embedding JavaScript expressions within the markup.
Attribute Naming Conventions:

JSX: Uses camelCase for event handlers and attributes. For example, onClick instead of onclick, and className instead of class.
HTML: Uses lowercase attribute names like onclick and class.
Compilation Step:

JSX: Needs to be transpiled (e.g., using Babel) into plain JavaScript before it can run in a browser.
HTML: Is interpreted directly by the browser without any compilation.
JavaScript Power:

<b>JSX</b>: Is not a templating language; it’s just syntactic sugar for React.createElement. It allows you to use all the power of JavaScript (variables, functions, loops, etc.) within your markup.
HTML: Is static and cannot directly include dynamic logic without additional scripting.

# 4. Explain Props with Example?
In React, props (short for "properties") are a mechanism for passing data from a parent component to a child component. They are read-only and help in creating reusable components by allowing components to be customized with different data. Props enable a unidirectional data flow, meaning that data moves from the parent component down to the child component.

## Key Points About Props
###  Passing Data:
Props allow you to pass any type of data (strings, numbers, objects, arrays, functions, etc.) from one component to another.

###  Read-Only:
Props are immutable within the child component. A child component should not modify its own props; if data needs to be updated, the parent component should handle the change.

###  Reusable Components:
By accepting props, components can be made more generic and reusable, as you can provide different data to the same component to render different outputs.

## Accessing Props:

In functional components, props are passed as a function argument.

In class components, props are accessed using this.props.

## Example Using Functional Components
### Child Component: Greeting

Below is an example of a simple functional component that uses props:

```js
import React from 'react';

function Greeting(props) {
  return (
    <div>
      <h1>Hello, {props.name}!</h1>
      <p>Welcome to our website.</p>
    </div>
  );
}

export default Greeting;
```
Explanation:

The Greeting component receives a props object as an argument.

We access the name prop using props.name and display it within the h1 tag.

### Parent Component: App
Now, let’s see how you might use the Greeting component within a parent component:
```js
import React from 'react';
import Greeting from './Greeting';

function App() {
  return (
    <div>
      <Greeting name="Alice" />
      <Greeting name="Bob" />
      <Greeting name="Charlie" />
    </div>
  );
}

export default App;
```
Explanation:

In the App component, we import the Greeting component.

We then render Greeting multiple times, each time passing a different value for the name prop.

Each instance of the Greeting component receives its own prop, allowing it to render personalized content.

### Example Using Destructuring
You can also use destructuring in the function parameter to access props more directly:
```js
import React from 'react';

function Greeting({ name }) {
  return (
    <div>
      <h1>Hello, {name}!</h1>
      <p>Welcome to our website.</p>
    </div>
  );
}

export default Greeting;
```
Explanation:

Here, we destructure the name property directly from the props object in the function parameter, making the code a bit cleaner.

# 5. Difference between functional and class component?
## 1. Syntax
### Functional Components:
These are JavaScript functions that accept props as an argument and return JSX. They are generally simpler and more concise.
```js
// Functional Component Example
import React from 'react';

function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}

export default Greeting;
```
### Class Components:
These are ES6 classes that extend React.Component and must include a render() method that returns JSX.

```js
// Class Component Example
import React, { Component } from 'react';

class Greeting extends Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}

export default Greeting;
```
## 2. State Management
### Functional Components:
Originally, functional components were “stateless.” However, with the introduction of Hooks (like useState), functional components can now manage state.

```js
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;
```
### Class Components:
State is managed by initializing this.state in the constructor and updating it with this.setState().

```js
import React, { Component } from 'react';

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  increment = () => {
    this.setState((prevState) => ({ count: prevState.count + 1 }));
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}

export default Counter;
```
## 3. Lifecycle Methods
### Functional Components:
With Hooks like useEffect, functional components can mimic lifecycle methods (such as componentDidMount, componentDidUpdate, and componentWillUnmount). This hook runs after the component renders and can be configured to run only when certain values change.

```js
import React, { useEffect } from 'react';

function Greeting({ name }) {
  useEffect(() => {
    // ComponentDidMount & ComponentDidUpdate equivalent
    console.log('Greeting component rendered or updated');
    
    return () => {
      // ComponentWillUnmount equivalent
      console.log('Cleaning up...');
    };
  }, [name]); // Runs whenever 'name' changes

  return <h1>Hello, {name}!</h1>;
}

export default Greeting;
```
### Class Components:
Class components have built-in lifecycle methods like componentDidMount, componentDidUpdate, and componentWillUnmount to handle side effects and cleanups.

```js
import React, { Component } from 'react';

class Greeting extends Component {
  componentDidMount() {
    console.log('Greeting component mounted');
  }

  componentDidUpdate(prevProps) {
    if (prevProps.name !== this.props.name) {
      console.log('Greeting component updated');
    }
  }

  componentWillUnmount() {
    console.log('Greeting component will unmount');
  }

  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}

export default Greeting;
```
## 4. The this Keyword
### Functional Components:
No this keyword is used. Variables and functions are defined directly within the function scope.

### Class Components:
The this keyword is used to access props, state, and other methods. It may require binding methods in the constructor (or using arrow functions) to maintain the proper context.

## 5. Readability and Simplicity
### Functional Components:
Tend to be more straightforward and easier to read, especially for components that primarily render UI. With Hooks, they can now handle complex stateful logic without the verbosity of class components.

### Class Components:
Can become more verbose due to the need for lifecycle methods, constructors, and method binding. However, they provide a clear structure for managing state and side effects in larger applications.

# 6. Difference between stateless and stateful component?
## Stateless Components
### Definition:
Stateless components (often called presentational or functional components) do not manage or hold any internal state. They receive data exclusively through props and render the UI based on that data.

### Characteristics:

Simplicity: They are typically simpler, focusing solely on how things look.

Predictability: Their output is determined entirely by the input props, making them easier to test and debug.

Reusability: Since they have no internal state, they tend to be more reusable across different parts of your application.

No Lifecycle Methods: Before Hooks were introduced, functional components did not have access to lifecycle methods. Now, with Hooks (like useEffect), they can simulate lifecycle behavior if needed.

### Example of a Stateless Functional Component:

```js
import React from 'react';

// A simple component that displays a greeting
const Greeting = ({ name }) => {
  return <h1>Hello, {name}!</h1>;
};

export default Greeting;
```
Explanation:
The Greeting component receives a name prop and uses it to display a personalized message. It doesn’t hold or modify any state internally.

## Stateful Components
### Definition:
Stateful components maintain their own internal state. They are responsible for managing dynamic data that can change over time (like user input, API responses, etc.) and can re-render themselves when that state changes.

### Characteristics:

Data Management: They use state (either through the state object in class components or the useState hook in functional components) to store and update dynamic data.

Complexity: Often contain more logic to handle state updates, side effects, and user interactions.

Lifecycle Methods: Class-based stateful components have access to lifecycle methods (e.g., componentDidMount, componentDidUpdate, componentWillUnmount). Functional components achieve similar behavior using Hooks (like useEffect).

### Example Using a Functional Component with Hooks:
```js
import React, { useState } from 'react';

// A counter component that maintains its own state
function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;
```
### Example Using a Class Component:

```js
import React, { Component } from 'react';

// A counter component that maintains its own state using a class component
class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  increment = () => {
    this.setState(prevState => ({ count: prevState.count + 1 }));
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}

export default Counter;
```
Explanation:
Both versions of the Counter component manage a count state. When the button is clicked, the state updates, triggering a re-render to display the new count.

# 7. What are Controlled and Uncontrolled Components?
## Controlled Components
### Definition:
A controlled component is a component where form data (such as the value of an input field) is handled by React's state. In a controlled component, every change to the input is managed through an event handler (like onChange), and the component's state is considered the "single source of truth" for the input's value.

### Characteristics:

Single Source of Truth: The value of the input element is stored in the state, ensuring that React has full control over the form data.

Real-Time Validation & Formatting: Since the state updates on every change, you can perform validations or transformations immediately.

Predictable Behavior: The UI always reflects the component’s state, making it easier to debug and test.

Slightly More Code: You need to write event handlers and maintain state, which might add some extra boilerplate.

### Example of a Controlled Component:

```js
import React, { useState } from 'react';

function ControlledInput() {
  // State holds the input value
  const [value, setValue] = useState('');

  // Handler to update the state on every keystroke
  const handleChange = (event) => {
    setValue(event.target.value);
  };

  return (
    <div>
      <input
        type="text"
        value={value}         // Value comes from React state
        onChange={handleChange} // Updates state on change
      />
      <p>You typed: {value}</p>
    </div>
  );
}

export default ControlledInput;
```
Explanation:

The input element’s value is tied to the component's state (value).
The handleChange function updates the state whenever the user types.
The component re-renders with the updated state, ensuring that the input value always reflects what’s stored in state.
## Uncontrolled Components
### Definition:
An uncontrolled component is a component where form data is handled by the DOM itself rather than by React. Instead of using state to store the input’s value, you access the current value using a ref. This approach is closer to how traditional HTML form elements work.

### Characteristics:

DOM as the Source of Truth: The form element maintains its own internal state.

Less Code for Simple Use Cases: You don't need to write extra event handlers or maintain state if your form is simple.

Delayed Access to Data: To access the current value, you generally use refs (via React.useRef) at the time of form submission or when needed.

Less React Involvement: Since React isn’t directly controlling the input's value, you lose some benefits like instant validation and synchronization with other parts of your UI.

### Example of an Uncontrolled Component:

```js
import React, { useRef } from 'react';

function UncontrolledInput() {
  // Create a ref to access the input element
  const inputRef = useRef(null);

  const handleSubmit = (event) => {
    event.preventDefault();
    // Access the current value of the input via the ref
    alert(`Submitted value: ${inputRef.current.value}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        defaultValue="Hello"  // Use defaultValue to set the initial value
        ref={inputRef}        // Attach the ref to the input
      />
      <button type="submit">Submit</button>
    </form>
  );
}

export default UncontrolledInput;
```
Explanation:

The input element uses the defaultValue attribute to set its initial value.
A ref (inputRef) is attached to the input element, allowing access to the DOM node.
On form submission, the handleSubmit function retrieves the current value directly from the DOM using the ref.

## Summary of Differences
### Source of Truth:
Controlled: The React state holds the value.\
Uncontrolled: The DOM itself holds the value.
### Data Flow:
Controlled: Data flows from the state to the UI and vice versa through event handlers.\
Uncontrolled: Data is managed by the DOM, and you pull the value when needed using refs.
### Usage Considerations:
Controlled Components are ideal when you need to:

Validate user input in real time.\
Dynamically enable/disable form elements.\
Integrate closely with the component’s logic.

Uncontrolled Components are suitable for:

Simple forms where you don’t need to track every change.\
Scenarios where you want to reduce the amount of code related to state management.

# 8. Difference between Props and State?
## 1. Ownership and Origin
### Props:

Passed Down: Props (short for properties) are passed from a parent component to a child component.

Read-Only: They are immutable within the child component; a component cannot modify its own props.

Communication: Props are used to configure or customize a component and to enable data flow from parent to child.
### State:

Local Data: State is managed within a component and is local to that component.

Mutable: Unlike props, state can be updated by the component itself, typically in response to user interactions or other events.

Dynamic Data: State is used to store data that can change over time and affect how the component renders.
## 2. Purpose and Usage
### Props:

Customization: They allow a parent component to pass data or callback functions to child components to customize behavior or appearance.

Stateless Rendering: Components that only render UI based on props and do not manage their own data are often referred to as "stateless" or "presentational" components.
### State:

Interactivity: State is used to manage dynamic data, such as form inputs, toggled UI elements, or data fetched from an API.

Self-Management: When a component needs to keep track of changes internally, it uses state. This is common in interactive components like counters, forms, or toggles.
## 3. Updating Mechanism
### Props:

Immutable in Child: Since props are passed from a parent, the child component should not modify them. Any change to props must happen in the parent, which then passes new values down.

Re-render Trigger: When the parent component passes new props, the child component re-renders with the updated values.
### State:

Mutable: State is updated using methods like setState in class components or the state updater function from the useState hook in functional components.

Controlled Changes: Changes to state trigger a re-render of the component, allowing the UI to update in response to user actions or other events.
## 4. Code Examples
Example of Using Props

Parent Component:

```js
import React from 'react';
import Greeting from './Greeting';

function App() {
  return (
    <div>
      <Greeting name="Alice" />
      <Greeting name="Bob" />
    </div>
  );
}

export default App;
```
Child Component (Greeting.js):
```js
import React from 'react';

function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

export default Greeting;
```
Explanation:
The App component passes the name prop to the Greeting component, which uses it to display a personalized message. The Greeting component does not manage or change the name value.

Example of Using State
Counter Component (Functional):

```js
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;
```
Explanation:
The Counter component uses state to keep track of the count. Each time the button is clicked, the state updates via setCount, and the component re-renders to display the new count.

## Summary
### Props:

Immutable: Passed from parent to child; the child cannot change them.\
Used for: Configuring and customizing components.\
Data Flow: Unidirectional (parent → child).
### State:

Mutable: Managed within the component; can change over time.\
Used for: Managing dynamic data and interactivity.\
Data Flow: Local to the component; can be lifted up if needed to share across components.

# 9. What is the purpose of the key attribute in React lists?
## Efficient Re-rendering:

Identification: When a list changes (e.g., items are added, removed, or reordered), keys help React quickly identify which elements have changed.
Optimization: By using keys, React can update only the necessary items in the DOM rather than re-rendering the entire list, leading to improved performance.

## Not Accessible as Props:
The key attribute is used internally by React and is not accessible as a prop within the component. It serves as an identifier during rendering only.

## Best Practices:
Ensure keys are unique among siblings and avoid using unstable values like array indexes when possible.

# 10. What are fragments in React?
Fragments are a way to group a list of children elements without adding extra nodes (like additional div elements) to the DOM. 

## Key Points About Fragments
### Avoid Extra Markup:

Traditionally, when returning multiple elements from a component, you had to wrap them in a single parent element (often a div). Fragments let you avoid this extra wrapper.
### Improved DOM Structure:

Using fragments helps keep the DOM clean and reduces the number of unnecessary elements, which can be beneficial for CSS styling and performance.
### Two Syntax Options:

Full Syntax: <React.Fragment></React.Fragment>\
Shorthand Syntax: <>...</>

Note: The shorthand syntax cannot accept keys or attributes. If you need to assign keys (for instance, when mapping over an array of fragments), use the full <React.Fragment> syntax.

# 11. What are hooks in React and Explain the useState and useEffect hooks with examples

Hooks are functions that let you use state and other React features without writing a class. They enable functional components to have their own state and side effects, making it easier to organize and reuse logic across components.

## useState

The useState hook allows you to add state to a functional component.

## useEffect

The useEffect hook is used for handling side effects such as data fetching, subscriptions, and manually updating the DOM. It can replace lifecycle methods like componentDidMount, componentDidUpdate, and componentWillUnmount in class components.

## useContext

The useContext hook lets you consume context without having to wrap your component in a Consumer. It provides an easy way to share values like themes, user data, or settings across your component tree.

### Example:

First, create a context:

```js
import { createContext } from "react";

export const counterContext = createContext(0)
```
Then, use the context in a App.jsx:

```js
import { useState } from 'react'
import reactLogo from './assets/react.svg'
import viteLogo from '/vite.svg'
import './App.css'
import Navbar from './components/Navbar'
import { counterContext } from './context/context'

function App() {
  const [count, setCount] = useState(0)

  return (
    <>
    <counterContext.Provider value={{count, setCount}}>
    <Navbar/>
      <div>
        <a href="https://vitejs.dev" target="_blank">
          <img src={viteLogo} className="logo" alt="Vite logo" />
        </a>
        <a href="https://react.dev" target="_blank">
          <img src={reactLogo} className="logo react" alt="React logo" />
        </a>
      </div>
      <h1>Vite + React</h1>
      <div className="card">
        <button onClick={() => setCount((count) => count + 1)}>
          count is {count}
        </button>
        <p>
          Edit <code>src/App.jsx</code> and save to test HMR
        </p>
      </div>
      <p className="read-the-docs">
        Click on the Vite and React logos to learn more
      </p>
      </counterContext.Provider>
    </>
  )
}

export default App
```
Then we use use in different component as per needed

```js
import React, { useContext } from 'react'
import { counterContext } from '../context/context'


const Component1 = () => {
  const value = useContext(counterContext)
  return (
    <div>
    {value.count}

    <button onClick={()=>value.setCount((count)=>count + 1)}>click me</button>
    </div>
  )
}

export default Component1
```
## useRef

The useRef hook allows you to persist mutable values between renders without causing re-renders when updated. It’s also used to access DOM elements directly.

When you change the ref.current property, React does not re-render your component. so if we use a ref value in return() the value will not get updated, better to use useState if we want our value to change. React is not aware of when you change it because a ref is a plain JavaScript object.

Do not write or read ref.current during rendering, except for initialization. This makes your component’s behavior unpredictable.
## example 1
```js
import React, { useRef } from 'react';

function FocusInput() {
  // Create a ref to store the input element
  const inputRef = useRef(null);

  const focusInput = () => {
    // Directly access the DOM element to focus it
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} type="text" placeholder="Click the button to focus me" />
      <button onClick={focusInput}>Focus Input</button>
    </div>
  );
}

export default FocusInput;
```

## example 2
```js
import { useState, useEffect, useRef } from 'react'
import reactLogo from './assets/react.svg'
import viteLogo from '/vite.svg'
import './App.css'

function App() {
  const [count, setCount] = useState(0)
  const a = useRef(0)

  useEffect(() => {
    a.current = a.current + 1
    console.log(`rerendering and the value of a is ${a.current}..`) 
  });
  

  return (
    <>
      <div>
        <a href="https://vitejs.dev" target="_blank">
          <img src={viteLogo} className="logo" alt="Vite logo" />
        </a>
        <a href="https://react.dev" target="_blank">
          <img src={reactLogo} className="logo react" alt="React logo" />
        </a>
      </div>
      <h1>Vite + React</h1>
      <div className="card">
        <button onClick={() => setCount((count) => count + 1)}>
          count is {count}
        </button>
        <p>
          Edit <code>src/App.jsx</code> and save to test HMR
        </p>
      </div>
      <p className="read-the-docs">
        Click on the Vite and React logos to learn more
      </p>
    </>
  )
}

export default App
```
## useMemo

useMemo is used to memoize expensive computations so that they are only recomputed when one of the dependencies changes. This can improve performance by avoiding unnecessary recalculations.

```js
import React, { useState, useMemo } from 'react';

function ExpensiveCalculationComponent({ num }) {
  // Simulate an expensive calculation
  const computeFactorial = (n) => {
    console.log('Calculating factorial...');
    return n <= 0 ? 1 : n * computeFactorial(n - 1);
  };

  // Memoize the result to avoid recalculating on every render
  const factorial = useMemo(() => computeFactorial(num), [num]);

  return <div>Factorial of {num} is {factorial}</div>;
}

function App() {
  const [number, setNumber] = useState(5);
  return (
    <div>
      <input
        type="number"
        value={number}
        onChange={e => setNumber(Number(e.target.value))}
      />
      <ExpensiveCalculationComponent num={number} />
    </div>
  );
}

export default App;
```
## useCallback

useCallback caches a function between re-renders until its dependencies change.

## App.jsx
```js
import { useState, useCallback } from 'react'
import reactLogo from './assets/react.svg'
import viteLogo from '/vite.svg'
import './App.css'
import Navbar from './components/Navbar'

function App() {
  const [count, setCount] = useState(0)
  const [count2, setCount2] = useState(0)
  const [adjective, setAdjective] = useState("good")

  // const getAdjective = () => {
  //   return "another" + count
  // }

  const getAdjective = useCallback(() => {
    return "another" + count
  },[count] )



  return (
    <>
      <Navbar adjective={"good"} getAdjective={getAdjective} />
      <div>
        <a href="https://vitejs.dev" target="_blank">
          <img src={viteLogo} className="logo" alt="Vite logo" />
        </a>
        <a href="https://react.dev" target="_blank">
          <img src={reactLogo} className="logo react" alt="React logo" />
        </a>
      </div>
      <h1>Vite + React</h1>
      <div className="card">
        <button onClick={() => setCount((count) => count + 1)}>
          count is {count}
        </button>
        <p>
          Edit <code>src/App.jsx</code> and save to test HMR
        </p>
      </div>
      <p className="read-the-docs">
        Click on the Vite and React logos to learn more
      </p>
    </>
  )
}

export default App
```

## component.jsx

```js
import React from 'react'
import { memo } from 'react'

const Navbar = ({adjective, getAdjective}) => {
    console.log("Navbar is rendered")
  return (
    <div>
      I am a {adjective} Navbar
      <button onClick={()=>{getAdjective()}}>{getAdjective()}</button>
    </div>
  )
}

export default memo(Navbar)
```
# 12. What is props drilling in React?
Props drilling refers to the process of passing data from a parent component to deeply nested child components through intermediary components that do not necessarily need that data for their own logic or rendering.

To alleviate the issues caused by props drilling, React offers some solutions:

## Context API:
Allows you to create a global context that can be accessed by any component without passing props explicitly at every level.

## State Management Libraries:
Tools like Redux, MobX, or Recoil can help manage state across your application without needing to drill props through many levels.

# 13. Reconciliation in React?

Reconciliation is the process by which React updates the DOM to reflect changes in the component's state or props. Rather than re-rendering the entire DOM, React uses an efficient algorithm to determine the minimum number of changes required to update the UI. 

Reconciliation is also done using react fibre and react portal

## 1. The Virtual DOM
### Virtual Representation:
React maintains a lightweight copy of the actual DOM called the Virtual DOM. When a component’s state or props change, React creates a new Virtual DOM tree representing the UI in its new state.

### Comparison:
React compares this new Virtual DOM with the previous Virtual DOM to detect what has changed. This process is known as diffing.

## 2. The Diffing Algorithm
### Efficiency Through Heuristics:
The diffing algorithm uses heuristics to quickly identify changes. Instead of comparing every element in the entire tree, it makes assumptions such as:

### Element Type Matching:
If two elements of the same type have different properties, React updates the element rather than replacing it entirely.

### Keyed Elements:
When rendering lists, unique keys help React identify which items have changed, been added, or removed. This allows for precise updates rather than re-rendering entire lists.

### Minimal Updates:
The algorithm computes the minimal set of changes (additions, deletions, and modifications) needed to update the actual DOM, thereby improving performance.

## 3. Updating the Real DOM
### Batching Updates:
After identifying changes, React applies updates in batches rather than one at a time, reducing the number of reflows and repaints in the browser.

### Selective Rendering:
Only the parts of the DOM that have actually changed are updated, ensuring that the application remains fast and responsive.


## 4. Benefits of Reconciliation
### Performance Optimization:
By minimizing direct DOM manipulations, reconciliation makes the UI updates faster and more efficient.

### Better User Experience:
Faster UI updates result in a smoother, more responsive application.

### Maintainable Code:
Developers can write components declaratively without worrying about manually managing the DOM, as React takes care of efficient updates under the hood.

# 14. What are High Order Components (HOC)?
An HOC is a function that takes a component as an argument and returns a new component with enhanced functionality

It allows you to inject common functionality into multiple components without repeating code.

HOCs are ideal for sharing common concerns (e.g., logging, authentication, data fetching, error handling) across different components.

HOCs do not modify or mutate the original component; instead, they create a new component that wraps the original one.

# 15. How does React Router handle navigation in a single-page app?
React Router is a popular library that enables client-side routing in a single-page application (SPA). Instead of relying on traditional server-side routing where the browser fetches a new page from the server for each navigation, React Router allows you to update the UI and URL dynamically without a full page refresh. Here’s how it works:

## How React Router Handles Navigation
### Client-Side Routing:
In a SPA, the entire application is loaded once, and navigation is handled on the client side. React Router listens for changes to the URL (using the HTML5 History API) and determines which components should be rendered based on the current route.

useParams to access URL parameters

eg.
```js
import {useParams} from "react-router-dom'

const params = useParams()
<div> I am {params.userName}</div>
```
use NavLink to apply className of specific type
```js
eg. <NavLink classname = {(e)=>return {e.isActive:"background-color?red":""}} to="/hpme"></Navlink>
```
### Router Components:

#### BrowserRouter/HashRouter:
These are the top-level components that wrap your application.

BrowserRouter uses the HTML5 History API (pushState, replaceState) for clean URLs.

HashRouter uses the URL hash (#) to manage routing, which can be useful in environments where you cannot configure the server.
### Routes and Route:
You define a set of Route components within a Routes container (or Switch in older versions) to map specific URL paths to components.
### Intercepting Navigation Events:
When a user clicks on a link created with React Router’s Link component, the router prevents the browser’s default behavior of reloading the page. Instead, it:

Updates the URL in the address bar.\
Looks up the new URL in its routing configuration.\
Renders the corresponding component for that route.

### Dynamic Routing:
React Router supports dynamic segments and nested routes, allowing you to build complex routing structures. For example, you can pass parameters in the URL (like /user/:id) and extract them in your components.

### Programmatic Navigation:
Using hooks like useNavigate (in React Router v6) or higher-order components like withRouter (in earlier versions), you can navigate programmatically within your components—triggering route changes in response to events or logic.

# 16.Explain React strict mode.
React Strict Mode is a development tool introduced in React 16.3 that helps identify potential issues in your application by enabling additional checks and warnings.

Strict Mode warns you about deprecated lifecycle methods (e.g., componentWillMount, componentWillReceiveProps, componentWillUpdate) and practices that may lead to bugs in future React releases.

 In development mode, React Strict Mode intentionally double-invokes certain lifecycle methods and functions (such as constructor, render, and effects) to help you catch side effects that might not be safe to run multiple times.

# 17. React-Redux
React-Redux is a popular state management library that helps manage the application state in React applications. React-Redux connects the Redux store to React components, enabling seamless communication between the two.

## It is based on three fundamental principles:

Single Source of Truth: The entire application state is stored in a single JavaScript object called the store.

State is Read-Only: The only way to change the state is by dispatching an action that describes the change.

Changes are Made with Pure Functions: Changes to the state are made using reducers, which are pure functions that take the previous state and an action, and return the new state.

## Create a Redux Store
Create a file named src/app/store.js. Import the configureStore API from Redux Toolkit. We'll start by creating an empty Redux store, and exporting it:

```js
app/store.js

import { configureStore } from '@reduxjs/toolkit'

export const store = configureStore({
  reducer: {},
})
```
This creates a Redux store, and also automatically configure the Redux DevTools extension so that you can inspect the store while developing.

## Provide the Redux Store to React
Once the store is created, we can make it available to our React components by putting a React-Redux `<Provider>` around our application in src/index.js. Import the Redux store we just created, put a `<Provider>` around your `<App>`, and pass the store as a prop:

```js
index.js
import React from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App'
import { store } from './app/store'
import { Provider } from 'react-redux'

const container = document.getElementById('root')

if (container) {
  const root = createRoot(container)

  root.render(
    <Provider store={store}>
      <App />
    </Provider>,
  )
} else {
  throw new Error(
    "Root element with ID 'root' was not found in the document. Ensure there is a corresponding HTML element with the ID 'root' in your HTML file.",
  )
}
```

## Create a Redux State Slice
Add a new file named src/features/counter/counterSlice.js. In that file, import the createSlice API from Redux Toolkit.

Creating a slice requires a string name to identify the slice, an initial state value, and one or more reducer functions to define how the state can be updated. Once a slice is created, we can export the generated Redux action creators and the reducer function for the whole slice.

Redux requires that we write all state updates immutably, by making copies of data and updating the copies. However, Redux Toolkit's createSlice and createReducer APIs use Immer inside to allow us to write "mutating" update logic that becomes correct immutable updates.

```js
features/counter/counterSlice.js
import { createSlice } from '@reduxjs/toolkit'

const initialState = {
  value: 0,
}

export const counterSlice = createSlice({
  name: 'counter',
  initialState,
  reducers: {
    increment: (state) => {
      // Redux Toolkit allows us to write "mutating" logic in reducers. It
      // doesn't actually mutate the state because it uses the Immer library,
      // which detects changes to a "draft state" and produces a brand new
      // immutable state based off those changes
      state.value += 1
    },
    decrement: (state) => {
      state.value -= 1
    },
    incrementByAmount: (state, action) => {
      state.value += action.payload
    },
  },
})

// Action creators are generated for each case reducer function
export const { increment, decrement, incrementByAmount } = counterSlice.actions

export default counterSlice.reducer
```
## Add Slice Reducers to the Store
Next, we need to import the reducer function from the counter slice and add it to our store. By defining a field inside the reducer parameter, we tell the store to use this slice reducer function to handle all updates to that state.

```js
app/store.js
import { configureStore } from '@reduxjs/toolkit'
import counterReducer from '../features/counter/counterSlice'

export const store = configureStore({
  reducer: {
    counter: counterReducer,
  },
})
```
## Use Redux State and Actions in React Components
Now we can use the React-Redux hooks to let React components interact with the Redux store. We can read data from the store with useSelector, and dispatch actions using useDispatch. Create a src/features/counter/Counter.js file with a `<Counter>` component inside, then import that component into App.js and render it inside of `<App>`.

```js
features/counter/Counter.js
import React from 'react'
import { useSelector, useDispatch } from 'react-redux'
import { decrement, increment } from './counterSlice'

export function Counter() {
  const count = useSelector((state) => state.counter.value)
  const dispatch = useDispatch()

  return (
    <div>
      <div>
        <button
          aria-label="Increment value"
          onClick={() => dispatch(increment())}
        >
          Increment
        </button>
        <span>{count}</span>
        <button
          aria-label="Decrement value"
          onClick={() => dispatch(decrement())}
        >
          Decrement
        </button>
      </div>
    </div>
  )
}
```
Now, any time you click the "Increment" and "Decrement" buttons:

The corresponding Redux action will be dispatched to the store

The counter slice reducer will see the actions and update its state

The `<Counter>` component will see the new state value from the store and re-render itself with the new data

# 18. Zustand vs React-Redux

Zustand is one of many state management libraries for React.

## First create a store
Your store is a hook! You can put anything in it: primitives, objects, functions. The set function merges state.
```js
import { create } from 'zustand'

const useStore = create((set) => ({
  bears: 0,
  increasePopulation: () => set((state) => ({ bears: state.bears + 1 })),
  removeAllBears: () => set({ bears: 0 }),
  updateBears: (newBears) => set({ bears: newBears }),
}))
```
## Then bind your components, and that's it!
You can use the hook anywhere, without the need of providers. Select your state and the consuming component will re-render when that state changes.
```js
function BearCounter() {
  const bears = useStore((state) => state.bears)
  return <h1>{bears} bears around here...</h1>
}

function Controls() {
  const increasePopulation = useStore((state) => state.increasePopulation)
  return <button onClick={increasePopulation}>one up</button>
}
```


Conceptually, Zustand and Redux are quite similar, both are based on an immutable state model. However, Redux requires your app to be wrapped in context providers; Zustand does not.

Redux has a more complex setup and concepts, requiring actions, reducers, and a store. Zustand is simpler, using hooks and a direct state update mechanism. 

Redux is designed for large, scalable applications, offering features and tools for managing complex state. Zustand is more suitable for smaller to medium-sized projects. 

Zustand offers better performance for components that re-render less frequently, as it only re-renders components that use the specific piece of state that has changed. Redux can sometimes lead to more re-renders when connecting components to the store. 

# 19. React Hook Form
In ReactJS, creating a form can be a nightmare as it involves handling inputs and validating inputs. React-hook-form is a ReactJS library that simplifies the process of creating forms.

The library provides all the features that a modern form needs.

React Hook Form is a popular third-party library that simplifies form management in React functional components using hooks. It provides a comprehensive set of functionalities to handle various aspects of form handling like state management, field handling, form submission, etc.
## Steps to use React Hook Form
### Step 1. 
 Install the react-hook-form library
```js
npm install react-hook-form
```
### Step 2: 
Import useForm hook from react-hook-form. It will return your register, handlesubmit, and errors methods

<b>Register</b>: This is used to handle input fields. We can access the input field later using the name given to it. 

```js
<input {...register("firstname")} />
```
 <b>handlesubmit</b>: Is used to handle the form submission. It takes a custom method ( eg: onSubmit ). It will automatically collect field values.

```js
 const onSubmit = data =>  console.log(data);

<form onSubmit={handleSubmit(onSubmit)}>
     // input field 1
     // input field 2
     <input type="submit" />
</form>

```
<b>Errors</b>:  We use this to handle errors. if we leave "firstname" field empty it will set errors.first name =  true

```js
<input {...register("firstname", { required: true })} />
{errors.firstname && <span>This field is required</span>}


```
## Final Code
```js
import { useState } from 'react' 
import './App.css'
import { useForm } from "react-hook-form"
 
 

function App() { 
  const {
    register,
    handleSubmit,
    setError,    
    formState: { errors, isSubmitting },
  } = useForm();

  const delay = (d)=>{
    return new Promise((resolve, reject)=>{
      setTimeout(() => {
        resolve()
      }, d * 1000);
    })
  }

  const onSubmit = async (data) => {
    // await delay(2) // simulating network delay
    let r = await fetch("http://localhost:3000/", {method: "POST",  headers: {
      "Content-Type": "application/json", 
    }, body: JSON.stringify(data)})
    let res = await r.text()
    console.log(data, res)
    // if(data.username !== "shubham"){
    //   setError("myform", {message: "Your form is not in good order because credentials are invalid"})
    // }
    // if(data.username === "rohan"){
    //   setError("blocked", {message: "Sorry this user is blocked"})
    // }
  }

  return (
    <> 
    {isSubmitting && <div>Loading...</div>}
       <div className="container">
        <form action="" onSubmit={handleSubmit(onSubmit)}>
          <input placeholder='username' {...register("username", { required: {value: true, message: "This field is required"}, minLength: {value: 3, message: "Min length is 3"}, maxLength: {value: 8, message: "Max length is 8"} })} type="text"   />
          {errors.username && <div className='red'>{errors.username.message}</div>}
          <br />
          <input placeholder='password'  {...register("password", {minLength: {value: 7, message: "Min length of password is 7"},})} type="password"/>
          {errors.password && <div className='red'>{errors.password.message}</div>}
          <br />
          <input disabled={isSubmitting} type="submit" value="Submit" />
          {errors.myform && <div className='red'>{errors.myform.message}</div>}
          {errors.blocked && <div className='red'>{errors.blocked.message}</div>}
        </form>
       </div>
    </>
  )
}

export default App
```

## Storing values in localStorage: 
As we are building a login form, we need to verify log-in credentials so we store the form data in local storage.
```js
const onSubmit = (data) => {
    localStorage.setItem(data.email, JSON.stringify({ 
        name: data.name, password: data.password 
    }));
    console.log(JSON.parse(localStorage.getItem(data.email)));
  };
  ```
localStorage provides setItem methods to store whatever we want in the form of key-value pairs of string. And getItem to fetch the stored data back with the help of a key. We use JSON.stringify() converts our object data into a string ( setItem only takes values in the string ) and JSON.parse() parses the string data into an object.

# 20. How do you improve performance of React Js Applications?
## 1. Use React’s Production Build
Always deploy the production version of your app:

```js
npm run build
```
It minifies and optimizes your code.

Removes development warnings and extra checks.

## 2. Avoid Unnecessary Re-renders
Prevent components from re-rendering when not needed.

Use React.memo() for functional components.

Use PureComponent for class components.

Use shouldComponentUpdate() to control re-renders manually.

## 3. Use useCallback and useMemo Hooks
These hooks cache functions and values, preventing unnecessary recalculations.

```js
const memoizedValue = useMemo(() => expensiveCalculation(data), [data]);
const memoizedCallback = useCallback(() => handleClick(id), [id]);
```
## 4. Code Splitting (Lazy Loading)
Load components only when needed using React.lazy() and Suspense.

```js
const LazyComponent = React.lazy(() => import('./MyComponent'));

<Suspense fallback={<div>Loading...</div>}>
  <LazyComponent />
</Suspense>
```
This reduces the initial bundle size.

## 5. Keep Component State Local Where Necessary
Avoid lifting state too high unnecessarily — keep state close to where it's used to reduce renders in parent components.

## 6. Virtualize Long Lists
For large lists or tables, use virtualization libraries like:

react-window

react-virtualized

These render only visible items on screen, saving DOM processing.

## 7. Clean and Optimize State Management
Avoid excessive use of global state.

Use context only when needed (it causes re-renders).

Use libraries like Zustand, Jotai, or Redux Toolkit efficiently.

## 8. Minimize API Calls and Debounce Input
Cache API responses.

Use debounce or throttle on user input (like search fields) to reduce processing and requests.

## 9. Use Keys in Lists
Always use unique and stable keys in list-rendered components to help React track changes efficiently.

```js
{items.map(item => <div key={item.id}>{item.name}</div>)}
```
## 10. Optimize Images and Assets
Use modern formats like WebP.

Compress images.

Lazy load images using libraries like react-lazyload.

## 11. Analyze Performance
Use React DevTools and Chrome DevTools:

Identify components that re-render often.

Use the Profiler tab to measure performance.

# 21. How do you test React JS components ? 

Types of Testing in React
## 1. Unit Testing
Tests individual components or functions in isolation.

## 2. Integration Testing
Tests how components work together.

## 3. End-to-End (E2E) Testing
Tests the entire app flow as a user would, in a real browser.

## Common Tools for Testing React
Tool |	Purpose
------|--------
Jest	| Test runner and assertion library (built-in with CRA)
React Testing Library (RTL)	| Tests component behavior via the DOM (preferred for React)
Enzyme	| Older library for testing component internals (less common now)
Cypress / Playwright	| For end-to-end browser testing

## How to Unit Test a React Component (With RTL + Jest)
## 1. Install Dependencies
If not already installed (Create React App includes these):

```js
npm install --save-dev @testing-library/react @testing-library/jest-dom jest
```
## 2. Example Component (Greeting.js)
```js
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}
export default Greeting;
```
## 3. Example Test File (Greeting.test.js)
```js
import { render, screen } from '@testing-library/react';
import Greeting from './Greeting';

test('renders greeting message', () => {
  render(<Greeting name="John" />);
  const greetingElement = screen.getByText(/Hello, John!/i);
  expect(greetingElement).toBeInTheDocument();
});
```
 This test checks that the text Hello, John! appears on the screen.

## Other Useful RTL Methods
Method |	Description
-------|--------------
render()	| Renders the component for testing
screen.getByText()	| Finds element by its text content
fireEvent.click()	| Simulates user clicks
userEvent.type()	| Simulates typing input
expect().toBeInTheDocument()	| Checks if element exists in the DOM

 ## Example with Button Click
```js
function Counter() {
  const [count, setCount] = React.useState(0);
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```
Test:
```js
import { render, screen, fireEvent } from '@testing-library/react';
import Counter from './Counter';

test('increments counter on button click', () => {
  render(<Counter />);
  const button = screen.getByText('Increment');
  fireEvent.click(button);
  expect(screen.getByText(/Count: 1/i)).toBeInTheDocument();
});
```
## End-to-End Testing with Cypress (Optional)
Install Cypress:

```js
npm install cypress --save-dev
npx cypress open
```
Example test:

```js
describe('Home Page', () => {
  it('loads successfully', () => {
    cy.visit('http://localhost:3000');
    cy.contains('Hello');
  });
});
```

# 22. How does React JS Handle different types of errors?

## 1. Error Boundaries (for UI rendering errors)
React provides Error Boundaries — special class components that catch JavaScript errors in child components during:

Rendering

Lifecycle methods

Constructors

## Key Concepts:
Prevents the entire app from crashing due to one component.

Can display fallback UI (like an error message).

Only works for render-time errors, not async logic or event handlers.

 Example:
```js
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {
    return { hasError: true }; // update state to show fallback UI
  }

  componentDidCatch(error, info) {
    console.error("Error caught in boundary:", error);
  }

  render() {
    if (this.state.hasError) {
      return <h2>Something went wrong.</h2>;
    }
    return this.props.children;
  }
}

// Usage:
<ErrorBoundary>
  <MyComponent />
</ErrorBoundary>
```
## 2. Try-Catch (for event handlers and async functions)
React doesn’t catch errors in event handlers or async logic, so you must use standard JavaScript error handling.

 Example:
```js
function handleClick() {
  try {
    // custom logic
    throw new Error("Clicked!");
  } catch (err) {
    console.error("Caught error:", err);
  }
}

<button onClick={handleClick}>Click me</button>
```
## For async/await:
```js
async function fetchData() {
  try {
    const res = await fetch('/api/data');
    const data = await res.json();
  } catch (err) {
    console.error("Async error:", err);
  }
}
```
## 3. componentDidCatch() Lifecycle Method (Class Components)
Used in Error Boundaries to log or send errors to monitoring services (like Sentry or LogRocket).

```js
componentDidCatch(error, info) {
  logErrorToService(error, info);
}
```
## 4. Tools and Libraries for Error Tracking
Sentry, LogRocket, and Bugsnag: Capture, log, and report errors with stack traces and user session info.

React DevTools: Helps identify where the error is occurring in the component tree.


# 23. What are life cycle methods?

In React, lifecycle methods are special methods in class components that allow you to run code at specific points during a component's life — from creation to destruction.

They are only available in class components. In functional components, their behavior is mimicked using Hooks (like useEffect).

## Phases of React Component Lifecycle
React component lifecycle has three main phases:

Mounting – Component is created and added to the DOM.

Updating – Component is re-rendered due to changes in props or state.

Unmounting – Component is removed from the DOM.

## 1. Mounting Phase Methods
## constructor(props)
Called before the component is mounted.

Used to initialize state and bind methods.

```js
constructor(props) {
  super(props);
  this.state = { count: 0 };
}
```
## static getDerivedStateFromProps(props, state)
Called before rendering.

Rarely used; syncs state with props (without side effects).

```js
static getDerivedStateFromProps(props, state) {
  if (props.reset) {
    return { count: 0 };
  }
  return null;
}
```
## render()
Required method.

Returns the JSX UI.

```js
render() {
  return <h1>Count: {this.state.count}</h1>;
}
```
## componentDidMount()
Called once after the component is mounted.

Ideal for fetching data, setting up subscriptions, timers, etc.

```js
componentDidMount() {
  console.log("Component mounted!");
  fetchData();
}
```
## 2. Updating Phase Methods
## shouldComponentUpdate(nextProps, nextState)
Controls whether the component should re-render.

Return false to skip rendering.

```js
shouldComponentUpdate(nextProps, nextState) {
  return nextState.count !== this.state.count;
}
```
## getSnapshotBeforeUpdate(prevProps, prevState)
Called right before the DOM is updated.

Used to capture things like scroll position.

```js
getSnapshotBeforeUpdate(prevProps, prevState) {
  return window.scrollY;
}
```
## componentDidUpdate(prevProps, prevState, snapshot)
Called after the component updates.

Great for working with DOM updates or additional API calls.

```js
componentDidUpdate(prevProps, prevState, snapshot) {
  console.log('Updated from', prevState.count, 'to', this.state.count);
}
```
## 3. Unmounting Phase Method
## componentWillUnmount()
Called just before the component is removed.

Ideal for cleanup: clearing timers, removing listeners, aborting fetches.

```js
componentWillUnmount() {
  clearInterval(this.timer);
}
```
 Full Example

```js
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
    console.log('Constructor');
  }

  componentDidMount() {
    console.log('Mounted');
  }

  shouldComponentUpdate(nextProps, nextState) {
    console.log('Should Update');
    return true;
  }

  componentDidUpdate() {
    console.log('Updated');
  }

  componentWillUnmount() {
    console.log('Will Unmount');
  }

  render() {
    return (
      <div>
        <h2>Count: {this.state.count}</h2>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Increment
        </button>
      </div>
    );
  }
}
```
# 24. what is "Lifting State up" and why it is important ?

Lifting state up is a concept in React where you move the state to the closest common ancestor of two or more components that need to share or coordinate data.

Instead of maintaining separate states in child components, you "lift" the state to a parent component, and then pass data and state-changing functions (setState) to children via props.

## Why is Lifting State Up Important?
✅ Data Synchronization: Keeps multiple components in sync by managing shared state in one place.

✅ Single Source of Truth: Prevents inconsistencies by avoiding duplicate states in different components.

✅ Improved Reusability: Child components stay stateless and reusable.

✅ Easier Debugging: All state logic is centralized, making it easier to manage.

## Real-World Example: Shared Input and Display
Let’s say you have two child components:

One accepts user input (InputBox)

Another displays that input (DisplayBox)

❌ Without Lifting State (Not Synced)
Each has its own state — they won’t sync with each other.

✅ With Lifting State
```js
function ParentComponent() {
  const [text, setText] = React.useState('');

  return (
    <div>
      <InputBox text={text} setText={setText} />
      <DisplayBox text={text} />
    </div>
  );
}

function InputBox({ text, setText }) {
  return (
    <input
      value={text}
      onChange={(e) => setText(e.target.value)}
    />
  );
}

function DisplayBox({ text }) {
  return <h2>You typed: {text}</h2>;
}
```
 Here, both child components share the same state from the parent, so they're always in sync.
# 25. Difference between React built-in state management and Redux?
## React Built-in State Management

React provides local state management using the useState and useReducer hooks (in functional components) or this.state (in class components).

## Key Features:
Component-level state: Each component manages its own state.

Simple and great for small to medium apps.

State is lifted up to a parent if shared between components.

## Pros:
Easy to learn and use.

No extra setup or library needed.

Encourages simple, modular components.

## Cons:
Becomes hard to manage when many components need to share state.

Prop-drilling: You have to pass data through multiple levels of components.

No built-in tools for time-travel debugging or state history.

## Redux (External State Management Library)

Redux is a centralized state management library for JavaScript apps. It stores your entire app’s state in a single object (called the store) and updates it using actions and reducers.

## Key Features:
Global state: Any component can access or update state via the store.

Uses a strict unidirectional data flow (predictable state changes).

Middleware support for async actions (e.g., Redux Thunk or Saga).

## Pros:
Great for large and complex applications.

Avoids prop-drilling.

Excellent developer tools (Redux DevTools).

Makes debugging easier (with time-travel & action history).

## Cons:
More setup and boilerplate code.

Requires understanding of concepts like actions, reducers, and middleware.

Overkill for small apps.

# Redux thunk and Redux Saga ?
Both Redux Thunk and Redux Saga are middleware libraries used to handle asynchronous operations (like API calls) in a Redux-based application. However, they differ in how they work and how much control they give you over async logic.

## What is Middleware in Redux?
Middleware in Redux is a way to intercept actions before they reach the reducer — useful for logging, crash reporting, or handling async logic.

## Redux Thunk

Redux Thunk is a function-based middleware that allows you to write action creators that return a function instead of an action object.

## Key Features:
Simple and beginner-friendly.

The returned function receives dispatch and getState as arguments.

Great for straightforward async logic (like fetching data from an API).

 Example:
```js
// Action Creator using Thunk
export const fetchUsers = () => {
  return async (dispatch) => {
    dispatch({ type: "FETCH_USERS_REQUEST" });
    try {
      const response = await fetch("/api/users");
      const data = await response.json();
      dispatch({ type: "FETCH_USERS_SUCCESS", payload: data });
    } catch (error) {
      dispatch({ type: "FETCH_USERS_FAILURE", error });
    }
  };
};
```
## Redux Saga

Redux Saga is a middleware library that uses generator functions to handle complex asynchronous flows in a more structured and powerful way.

## Key Features:
Uses ES6 function* generators to handle async actions.

Better for complex workflows (chaining, cancellation, retries).

Easier to test compared to Thunk.

 Example:
```js
// Saga
import { call, put, takeEvery } from 'redux-saga/effects';

function* fetchUsersSaga() {
  try {
    const response = yield call(fetch, "/api/users");
    const data = yield response.json();
    yield put({ type: "FETCH_USERS_SUCCESS", payload: data });
  } catch (error) {
    yield put({ type: "FETCH_USERS_FAILURE", error });
  }
}

export function* rootSaga() {
  yield takeEvery("FETCH_USERS_REQUEST", fetchUsersSaga);
}
```

## When to Use What?
### Use Redux Thunk if:

Your async logic is simple (e.g., fetch API).

You want minimal setup and boilerplate.

You're new to Redux or working on a small app.

### Use Redux Saga if:

You need advanced control (e.g., debounce, cancel, retry, chain).

You're working on a large, complex application.

You want more testable and maintainable async logic.


# 26. Concept of "Reactive updates" in React and how it is different from traditional "data binding" ?

## What is Reactive Update in React?
In React, reactive updates mean the UI automatically re-renders when the state or props change. Instead of manually updating the DOM, you update the state, and React takes care of the rest.

 Example:
```js
const [count, setCount] = useState(0);

return (
  <div>
    <p>Count: {count}</p>
    <button onClick={() => setCount(count + 1)}>Increment</button>
  </div>
);
```
When setCount is called, the component re-renders with the new value.

You don't touch the DOM directly — React reactively updates the DOM based on state. Uses Virtual DOM

## What is Traditional Data Binding?
In traditional frameworks like Angular (especially AngularJS), data binding involves synchronizing data between the model and the view.

## Types:
One-way binding: Data flows from model → view.

Two-way binding: Data flows in both directions (model ↔ view).

 Example (Angular-like syntax):
```js
<input [(ngModel)]="username" />
<p>Hello, {{ username }}</p>
```
Changing the input updates username, and vice versa.

Behind the scenes, the framework uses watchers or digest cycles to keep everything in sync.
# 28. Difference between React, Angular, Vue ?
React, Angular, and Vue are three of the most popular technologies used for building modern web applications.

## React
developed by Meta (formerly Facebook), is a library focused on building user interfaces with a component-based architecture. It uses JSX, a syntax extension that combines JavaScript and HTML, and relies on one-way data binding. React is highly flexible, with a vast ecosystem, but many core functionalities like routing and state management require external libraries. This makes it ideal for developers who want full control and prefer assembling tools as needed.React Uses Virtual DOM.

## Angular
on the other hand, is a full-fledged framework maintained by Google. It comes with everything built-in, including routing, state management, form validation, and dependency injection. Angular uses TypeScript by default, which adds strong typing and better tooling for large-scale applications. It supports two-way data binding and uses a real DOM with a change detection mechanism. However, Angular has a steeper learning curve due to its complexity and structure, making it better suited for enterprise-level or large-scale projects where consistency and scalability are important.

## Vue
created by Evan You (a former Google engineer), is a progressive framework that strikes a balance between the two. It’s easy to learn, especially for beginners, and supports both one-way and two-way data binding. Vue’s syntax is clean and familiar, especially to those with experience in HTML and JavaScript. It offers optional tools like Vue Router and Vuex for advanced features but doesn’t enforce their use, allowing for gradual adoption. Vue is especially popular for lightweight to medium-scale applications and is favored by developers who want a fast, approachable solution without the complexity of Angular. Vue uses Virtual DOM.

In terms of performance, all three perform well for most common use cases, but Angular tends to have a larger initial bundle size. Choosing the best one depends on your specific needs: React is best for flexibility and large community support, Angular is ideal for complex enterprise applications, and Vue is great for ease of use and quick project startup. If you’re new to frontend frameworks, Vue is often the easiest to learn, while React is the most in-demand in the job market. Angular is powerful but more suitable when working in structured, large-team environments.

# 29.One-Way Data Binding and Two-Way Binding ?

## One-Way Data Binding
In one-way binding, the data flows in one direction — from the component (model) to the view (UI).

If the component’s state changes, the UI updates automatically.

But if the user changes something in the UI (like typing in an input), it doesn't directly change the model unless you write code to handle it (e.g., using onChange events in React).

### Example (React):
```js
<input value={name} onChange={(e) => setName(e.target.value)} />
```
Here, name is the model. When the value changes in the input field, you manually update the state using setName.

 Advantage: Easier to debug and more predictable.

 Used in: React, default in Vue.

## Two-Way Data Binding
In two-way binding, the data flows both ways — from the model to the view, and from the view back to the model automatically.

If you update the model, the view updates.

If the user updates the view (e.g., types in a field), the model updates instantly without needing extra event handling.

### Example (Angular or Vue):
```js
<!-- Angular -->
<input [(ngModel)]="name" />

<!-- Vue -->
<input v-model="name" />
```
Here, name stays in sync between the UI and the component automatically.

 Advantage: Less boilerplate code, easier to sync UI and data.

 Used in: Angular, Vue (via v-model).

 # 30. What is Node module in React?

 In the context of React, a Node module refers to any reusable package or dependency installed via Node.js's package manager, npm (Node Package Manager), that lives inside the node_modules directory of your project.

## What Is a Node Module?

A package of JavaScript (or TypeScript) code.

Installed via npm or yarn.

Stored in the node_modules/ folder.

Used to add functionality to your project — such as routing, state management, UI components, etc.

## How Node Modules Work in React
React is built using Node.js and npm, so when you start a React project (e.g., with create-react-app), it creates a node_modules directory and installs core dependencies like:

react – the core React library

react-dom – for rendering components to the DOM

Any other packages like axios, react-router-dom, redux, etc.

These are all Node modules.

You import and use them in your code like this:

```js
import React from 'react'; // from node_modules/react
import axios from 'axios'; // from node_modules/axios
```
## What Is Inside node_modules/?
All the npm packages you've installed

Their own dependencies (sometimes nested)

Sometimes thousands of files (which is normal)

### You should never edit files in node_modules directly. It's a managed folder.

 ## Should You Push node_modules to Git?
No. It is automatically excluded by .gitignore in most setups because:

It’s huge.

You can recreate it anytime using package.json by running npm install.

# 31. What is Pure Component in React ?

In React, a Pure Component is a special type of component that helps optimize performance by preventing unnecessary re-renders.

## What Is a Pure Component?
A Pure Component is like a regular React component but with one key difference:

It automatically implements a shallow comparison of props and state in its shouldComponentUpdate method.

## This means:

If the props or state haven't changed, the component will not re-render.

It's a simple way to boost performance in components that receive the same props often.


## In Class Components:
Use React.PureComponent instead of React.Component.

```js
import React from 'react';

class MyComponent extends React.PureComponent {
  render() {
    console.log('Rendered');
    return <div>{this.props.name}</div>;
  }
}
```
Here, if props.name doesn’t change, React won’t re-render the component.

## In Functional Components:
Use React.memo() to make it a "pure" function.

```js
import React from 'react';

const MyComponent = React.memo(({ name }) => {
  console.log('Rendered');
  return <div>{name}</div>;
});
```
## Shallow Comparison
PureComponent only checks top-level values. It does not deeply compare objects or arrays.

```js
{ name: 'John' } === { name: 'John' } // false, because they are different objects
```
So, be cautious when passing objects or arrays. Mutating them instead of replacing them may cause re-renders.

## When to Use PureComponent?
### Use it when:

You want to avoid unnecessary re-renders.

Your component renders the same output for the same props.

Your props/state are primitives or shallowly compared objects.

### Avoid it if:

You rely on deep objects/arrays that change internally.

You already use state management that prevents redundant renders.

# 32. what is the default localhost server port in react, how can we change it ?

In a React app created using Create React App (CRA), the default localhost port is:

### Default Port: 3000
So when you run:

```js
npm start
```
The app typically runs at:

```js
http://localhost:3000
```
## How to Change the Port in React
There are a few simple ways to change the port:

## 1. Using Environment Variable (Recommended)
You can set a custom port by defining the PORT variable.

On Linux/macOS (bash, zsh):
```js
PORT=4000 npm start
```
On Windows (CMD):
```js
set PORT=4000 && npm start
```
On Windows (PowerShell):
```js
$env:PORT=4000; npm start
```
## 2. Using .env File
You can create a file called .env in your project's root directory and add:

```js
PORT=4000
```
Then restart the dev server with npm start.

 This is the most convenient method for persistent port configuration.

## Note
Make sure the port you choose is not already in use by another app.

If the port is in use, CRA will ask if you want to use another available port, like 3001, 3002, etc.

# 33. What is super , constructor , render function in React ?
In React (especially class components), super, constructor, and render() are core parts of the component lifecycle and structure. Here's a clear explanation of each:

## constructor()
The constructor is a special method in JavaScript classes that runs when the component is created. In React, it's typically used to:

Initialize state

Bind event handler methods

Example:
```js
class MyComponent extends React.Component {
  constructor(props) {
    super(props); // calls the parent class constructor
    this.state = {
      count: 0
    };
  }
}
```
 ## When to use: 
 Only when you need to initialize state or bind methods. Otherwise, it's optional.

## super(props)
The super() function is used to call the constructor of the parent class (React.Component). This is required when using constructor() in a subclass.

If you're using constructor, you must call super(props) before using this.

It gives your component access to this.props.

Why props?
```js
super(props)
```
This ensures this.props is correctly set in your constructor.

## render()
The render() method is required in every React class component. It returns the JSX (i.e., the UI) that should be displayed on the screen.

React calls render() whenever the component’s state or props change.

Example:
```js
render() {
  return (
    <div>
      <h1>Hello, {this.props.name}</h1>
    </div>
  );
}
```
 render() must return a single element (usually a `<div>` or `<Fragment>` wrapping everything).

 Full Example:
```js
import React from 'react';

class MyComponent extends React.Component {
  constructor(props) {
    super(props); // Call the parent constructor
    this.state = { count: 0 };
  }

  render() {
    return (
      <div>
        <h1>Hello, {this.props.name}</h1>
        <p>Count: {this.state.count}</p>
      </div>
    );
  }
}
```

why choose react app if we can use javascript
why vite
react element
react component
why react component return one element
how to return without using fragment or any html element
diff between map and for each
context api vs redux

# 34. How can you optimize re-render in React?/ How do you prevent un-necessary renrenders and state dependencies?

## Why Does React Re-render?

### React re-renders a component when:

Its state changes (useState, useReducer)

Its props change

Its parent re-renders (which can trigger child renders)

Its context value changes

Re-renders themselves are not bad — they’re how React updates the UI —
but unnecessary re-renders can waste CPU and make the app feel slow 

## A. Use React.memo() — Prevent Child Component Re-renders

### When to use:
If a child component re-renders even though props didn’t change.

Example:
```js
const Child = React.memo(function Child({ value }) {
  console.log("Child rendered");
  return <div>{value}</div>;
});

function Parent() {
  const [count, setCount] = React.useState(0);
  return (
    <>
      <button onClick={() => setCount(c => c + 1)}>Increment</button>
      <Child value="static prop" />
    </>
  );
}
```

 Child will not re-render when count changes
(because its prop didn’t change).

## B. Use useCallback() — Memoize Event Handlers

If you pass a new function reference to a child on every render, React thinks props changed → triggers re-render.

Example:
```js
function Parent() {
  const [count, setCount] = useState(0);

  // ❌ Without useCallback: new function on every render
  const handleClick = () => setCount(c => c + 1);

  // ✅ With useCallback: function reference stays the same
  const memoizedClick = useCallback(() => setCount(c => c + 1), []);

  return <Child onClick={memoizedClick} />;
}
```

 Prevents unnecessary re-renders of memoized children.

## C. Use useMemo() — Memoize Expensive Calculations or Derived Data


To avoid recalculating expensive values (e.g., sorting, filtering) on every render.

Example:
```js
const filteredList = useMemo(() => {
  return items.filter(item => item.active);
}, [items]);
```

 Recomputes only when items change.

## D. Avoid Unnecessary State Changes

Common mistake:
Updating state with the same value.
```js
setCount(prev => prev); // ❌ still triggers re-render
```

 Only call state setters when the new value is different.

You can check before updating:
```js
if (newValue !== oldValue) setValue(newValue);
```
## E. Keep State Local (Minimize “upward state lifting”)

If you put all state in a top-level component, every child may re-render when it changes.

 Instead, keep state as close as possible to where it’s needed.

Example:
```js
// ❌ Lifting too high
function App() {
  const [input, setInput] = useState("");
  return <Form input={input} setInput={setInput} />;
}

// ✅ Better — move inside Form
function Form() {
  const [input, setInput] = useState("");
  ...
}
```
## F. Split Large Components

Break down big components into smaller ones so React only re-renders the affected parts.

// Instead of one big render with multiple sections,

// split each section into a memoized component.

## G. Avoid Re-Creating Objects/Arrays Inline

Each re-render creates new references → causes child re-renders.
```js
// ❌ New array each render
<Child items={[1, 2, 3]} />

// ✅ Memoize it
const items = useMemo(() => [1, 2, 3], []);
<Child items={items} />
```
## H. Use useRef() for Mutable Values That Don’t Affect UI

If you store data that doesn’t need to trigger a re-render → use useRef instead of useState.
```js
const renderCount = useRef(0); // ✅ won't cause re-render
renderCount.current++;
```
## I. Optimize Context Usage

React Context can cause re-renders of all consumers when the value changes.

✅ Solution:

Split contexts by concern (don’t put all global state in one provider)

Use memoized context values:
```js
<MyContext.Provider value={useMemo(() => ({ theme, toggleTheme }), [theme])}>

```
Or use libraries like Zustand, Jotai, or Recoil to avoid over-rendering.

## J. Use Performance Tools

React provides:

React DevTools Profiler → shows which components re-render and why.

why-did-you-render (third-party lib) → logs unnecessary re-renders in the console.
```js
npm install @welldone-software/why-did-you-render

import React from "react";
if (process.env.NODE_ENV === "development") {
  const whyDidYouRender = require("@welldone-software/why-did-you-render");
  whyDidYouRender(React);
}
```

## 3️⃣ Understanding Dependency Arrays (Common Mistakes)
Over-dependence causes re-renders:
```js
useEffect(() => {
  console.log("Runs every render");
}, [object]); // object reference changes every render
```
## Memoize dependencies:
```js
const memoizedObj = useMemo(() => ({ key: value }), [value]);
useEffect(() => {
  console.log("Runs only when value changes");
}, [memoizedObj]);
```
# 35. difference between useCallback() and useMemo() ?
| Hook                        | Purpose                                | Returns                                                   |
| --------------------------- | -------------------------------------- | --------------------------------------------------------- |
| **`useCallback(fn, deps)`** | Memoizes a **function**                | The **same function instance** until dependencies change  |
| **`useMemo(fn, deps)`**     | Memoizes a **computed value (result)** | The **result of a computation** until dependencies change |

## 1. useCallback()


useCallback returns a memoized version of a function, which only changes if one of its dependencies changes.

### Use Case:

When you pass a callback to a child component (especially one wrapped with React.memo()), and you don’t want that function to be recreated on every render.

### Example:
```js
import React, { useState, useCallback } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  // ✅ The same increment function instance is reused
  const increment = useCallback(() => {
    setCount(prev => prev + 1);
  }, []); // no deps => never changes

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>+</button>
    </div>
  );
}
```

Without useCallback, the increment function would be recreated on every render → causing unnecessary re-renders if passed as a prop to a memoized child.

## 2. useMemo()


useMemo returns a memoized value that is recomputed only when its dependencies change.

### Use Case:

When a computation is expensive (e.g., filtering, sorting, or large calculations) and you don’t want it to re-run every render.

### Example:
```js
import React, { useState, useMemo } from 'react';

function FilteredList({ items }) {
  const [query, setQuery] = useState('');

  // ✅ Expensive filtering runs only when items or query change
  const filtered = useMemo(() => {
    console.log('Filtering...');
    return items.filter(item => item.toLowerCase().includes(query.toLowerCase()));
  }, [items, query]);

  return (
    <div>
      <input value={query} onChange={e => setQuery(e.target.value)} />
      <ul>{filtered.map((i, index) => <li key={index}>{i}</li>)}</ul>
    </div>
  );
}
```

| Feature         | `useCallback()`                              | `useMemo()`                               |
| --------------- | -------------------------------------------- | ----------------------------------------- |
| Returns         | Memoized **function**                        | Memoized **value**                        |
| Used for        | Prevent re-creating functions                | Prevent re-running expensive computations |
| Common use case | Passing stable functions to child components | Caching results of expensive calculations |
| Syntax          | `useCallback(fn, deps)`                      | `useMemo(fn, deps)`                       |


Without useMemo, the filter operation would re-run on every render, even if query and items didn’t change.
# 36. What are Rect Fibre and Concurrent Rendering ? How do they improve UI responsiveness?

What Is React Fiber?

React Fiber is the new reconciliation engine introduced in React 16 (rewritten from scratch) to make React faster, smoother, and interruptible.

Before Fiber, React used a synchronous rendering model — once it started rendering a component tree, it could not stop until it finished.
That caused UI freezes, especially for complex updates.

## With Fiber

React rendering is now:

Incremental → broken into small units of work

Interruptible → can pause, resume, or abort rendering

Prioritized → some updates (like typing) are more important than others (like off-screen animations)

## Think of React Fiber as:

A “request scheduler” for React rendering work.

## Why “Fiber”?

React internally represents each component as a Fiber node, a data structure (an object) that holds:

Component type

Props & state

Return / child / sibling pointers (like a linked list tree)

Effect information (what needs to change in the DOM)

Each fiber is one unit of work React can process, pause, or resume.

## The Problem Fiber Solves
### Before (Legacy Reconciliation):

React walked the component tree recursively, synchronously.

Once started, React blocked the main thread until it was done.

So long renders made the app feel frozen — no typing, scrolling, or animations.

### After (Fiber Reconciliation):

React breaks the rendering into small chunks of work.

Between each chunk, React can check if there’s something more urgent (like user input).

If yes, it pauses rendering and handles the urgent task first.

 This leads directly to Concurrent Rendering.

## What Is Concurrent Rendering?


Concurrent Rendering is React’s ability to work on multiple UI updates simultaneously and pause or resume them as needed — without blocking the browser.

### Core Idea:

React rendering is no longer blocking or synchronous.
It’s cooperative — React works with the browser’s event loop.

### Example Analogy:

Imagine React as a chef in a kitchen:

🥗 Old React (Stack Reconciler): makes one full dish at a time — no matter how long it takes.

🍱 React Fiber (Concurrent): prepares multiple dishes in small steps, switching to the most urgent order when needed (like a new customer request).

## How Concurrent Rendering Improves UI Responsiveness
### A. User Interaction Feels Instant

React can pause background rendering (like loading new data)
to immediately respond to typing, clicking, or scrolling.

Example:
```js
import { startTransition } from "react";

function SearchApp() {
  const [query, setQuery] = useState("");
  const [results, setResults] = useState([]);

  function handleChange(e) {
    const value = e.target.value;
    setQuery(value);

    // ✅ Mark data loading as low-priority work
    startTransition(() => {
      const filtered = heavySearchFunction(value);
      setResults(filtered);
    });
  }

  return (
    <>
      <input value={query} onChange={handleChange} />
      <ResultsList results={results} />
    </>
  );
}
```

 Here:

Typing (setQuery) = high priority (UI update)

Filtering (startTransition) = low priority (can be paused/interrupted)

→ Result: typing remains smooth, even if filtering is expensive.

## B. Rendering Doesn’t Block Animation or Input

Fiber + concurrent rendering let React yield to the browser so:

Scroll stays smooth

Input doesn’t lag

Animations remain 60fps

## C. Prioritized Updates

React gives different priorities to work:

User input (highest)

Animation

Network updates (medium)

Background data re-render (lowest)

This prevents slow components from freezing the whole app.

## D. Suspense + Concurrent Rendering = Magic

Concurrent React pairs beautifully with Suspense:

React can “pause” rendering until async data (e.g., API) is ready.

Meanwhile, it can show a fallback UI.

When data arrives, React resumes rendering seamlessly.

Example:
```js
<Suspense fallback={<Spinner />}>
  <UserProfile />
</Suspense>
```
## E. Fiber + Concurrent Rendering Workflow

Render Phase (can be paused, resumed, aborted)

React creates a new fiber tree.

Calculates which DOM changes are needed.

Commit Phase (always synchronous)

React applies those changes to the DOM.

React Fiber makes the render phase interruptible, but commit phase stays atomic (DOM updates remain consistent).
# 37. Explain Custom hooks - when would you create one ?
A custom hook is simply a JavaScript function whose name starts with "use" and that uses one or more React hooks (useState, useEffect, useCallback, etc.) inside it.

Custom hooks let you extract and reuse stateful logic across multiple components.

You create a custom hook when you find yourself repeating the same logic (especially involving state, side effects, or event handling) in multiple components.

Instead of duplicating code, you move that logic into a reusable hook.

They are not components — they don’t return JSX, only data or functions.

When Should You Create a Custom Hook?

## Create one when:

You repeat the same hook logic (like fetching, form handling, event listeners, timers, etc.)

You want to abstract away complex logic from a component to make it more readable.

You want to share logic between components but not UI (unlike components that share JSX).

You want to encapsulate side effects or data fetching patterns.

## Common Real-World Examples

| Hook Name                            | Purpose                                        |
| ------------------------------------ | ---------------------------------------------- |
| `useFetch(url)`                      | Handle API fetching, loading, and error states |
| `useLocalStorage(key, initialValue)` | Sync state with `localStorage`                 |
| `useDebounce(value, delay)`          | Return a debounced version of a value          |
| `useToggle(initialValue)`            | Handle boolean toggling logic                  |
| `usePrevious(value)`                 | Store previous value for comparison            |
| `useOnlineStatus()`                  | Track whether the user is online/offline       |


## 1. Creating the Custom Hook
```js
// useFetch.js
import { useState, useEffect } from "react";

function useFetch(url) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    if (!url) return;

    const controller = new AbortController(); // helps cancel fetch when component unmounts
    const signal = controller.signal;

    async function fetchData() {
      try {
        setLoading(true);
        setError(null);

        const response = await fetch(url, { signal });
        if (!response.ok) throw new Error(`Error ${response.status}`);

        const result = await response.json();
        setData(result);
      } catch (err) {
        if (err.name !== "AbortError") {
          setError(err.message);
        }
      } finally {
        setLoading(false);
      }
    }

    fetchData();

    return () => controller.abort(); // cleanup on unmount
  }, [url]);

  return { data, loading, error };
}

export default useFetch;
```

## 2. Using It in a Component

```js
// App.jsx
import React from "react";
import useFetch from "./useFetch";

function App() {
  const { data, loading, error } = useFetch("https://jsonplaceholder.typicode.com/posts");

  if (loading) return <h3>Loading...</h3>;
  if (error) return <h3>Error: {error}</h3>;

  return (
    <div>
      <h2>Posts:</h2>
      <ul>
        {data.slice(0, 5).map(post => (
          <li key={post.id}>{post.title}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;

```
# 38. How does React.memo differ from useMemo() ?
| Concept          | **`React.memo`**                                       | **`useMemo`**                                |
| ---------------- | ------------------------------------------------------ | -------------------------------------------- |
| **Type**         | Higher-order **component wrapper**                     | React **hook**                               |
| **Purpose**      | Prevents **unnecessary re-renders** of a **component** | Memoizes a **computed value (result)**       |
| **Used on**      | A **whole component**                                  | A **value or expression** inside a component |
| **Returns**      | A **memoized component**                               | A **memoized value**                         |
| **When it runs** | When the parent re-renders                             | During rendering (based on dependencies)     |

## React.memo — Component-Level Memoization

React.memo is a higher-order component (HOC) that prevents a component from re-rendering if its props have not changed.

## Example
```js
import React from "react";

const Child = React.memo(function Child({ name }) {
  console.log("Child rendered");
  return <h3>Hello, {name}!</h3>;
});

function Parent() {
  const [count, setCount] = React.useState(0);

  return (
    <>
      <button onClick={() => setCount(c => c + 1)}>Count: {count}</button>
      <Child name="Rajat" />
    </>
  );
}

```
## What happens:

Parent re-renders each time you click.

Child does not re-render because its prop (name) hasn’t changed.

Without React.memo, the Child component would re-render unnecessarily.

 So: React.memo → Optimizes component re-rendering.

## useMemo — Value-Level Memoization


useMemo is a hook that memoizes a value (or result of a computation) between renders.

## Example

```js
import React, { useMemo, useState } from "react";

function ExpensiveComponent({ num }) {
  const [count, setCount] = useState(0);

  const computedValue = useMemo(() => {
    console.log("Computing...");
    return num * 1000;
  }, [num]);

  return (
    <div>
      <h3>Computed: {computedValue}</h3>
      <button onClick={() => setCount(c => c + 1)}>Clicked {count}</button>
    </div>
  );
}
```

## What happens:

The “Computing...” log runs only when num changes.

Re-renders caused by count do not recompute the expensive value.

 So: useMemo → Optimizes calculations inside a component.

 ## Key Difference in Purpose

 | Feature         | `React.memo`                                | `useMemo`                                     |
| --------------- | ------------------------------------------- | --------------------------------------------- |
| **Level**       | Component level                             | Inside component                              |
| **Used for**    | Preventing unnecessary re-render of a child | Preventing expensive recalculation of a value |
| **Depends on**  | Prop equality                               | Dependency array                              |
| **Return type** | A memoized component                        | A memoized value                              |

# 39. How can you optimize performance in React Applications ?
# 40. What are some common optimization techniques ?

## 1) How can you optimize performance in React applications?

measure first, then optimize the real bottlenecks. Use the React Profiler and browser tools to find hot spots, then apply targeted techniques (memoization, code-splitting, virtualization, cheaper renders, offloading work). Below is a practical, prioritized approach and concrete examples.

## A — Performance workflow (best practice)

Measure with React DevTools Profiler and Chrome DevTools (Performance + Memory).

Identify frequent/expensive renders, long tasks, large memory growth.

Fix the root (not micro-optimizing prematurely).

Verify improvements with the profiler.

Repeat as app evolves.

## B — Concrete optimization techniques (with examples)
## 1. Avoid unnecessary re-renders

Use React.memo for pure/dumb components.

Memoize callbacks with useCallback.

Memoize computed values with useMemo.
```js
// Child.jsx
const Child = React.memo(({ onClick, items }) => {
  console.log('Child render');
  return <button onClick={onClick}>{items.length}</button>;
});

// Parent.jsx
function Parent({ items }) {
  const [count, setCount] = useState(0);

  // Stable callback prevents Child re-render when 'count' changes
  const handle = useCallback(() => console.log('clicked'), []);
  const stableItems = useMemo(() => items, [items]); // if items are recreated upstream

  return <>
    <button onClick={() => setCount(c => c+1)}>Inc {count}</button>
    <Child onClick={handle} items={stableItems} />
  </>;
}

```
Caveat: Only memoize when there’s an actual performance problem — unnecessary memoization can add overhead.

## 2. Code-splitting and lazy-loading

Load code only when needed: React.lazy() and dynamic import().
```js
const Heavy = React.lazy(() => import('./HeavyComponent'));

function App() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <Heavy />
    </Suspense>
  );
}
```
## 3. Virtualize long lists

Render only visible rows using react-window or react-virtualized.
```js
import { FixedSizeList as List } from 'react-window';

function Row({ index, style, data }) {
  return <div style={style}>{data[index].title}</div>;
}

<List height={500} itemCount={items.length} itemSize={35} width={'100%'} itemData={items}>
  {Row}
</List>
```
## 4. Debounce/throttle expensive updates

For search input or scroll handlers, debounce before triggering expensive work.
```js
const debouncedSearch = useMemo(() => debounce(fn, 300), [fn]);
```

## 5. Use startTransition (Concurrent features) for low-priority UI updates

Mark expensive updates as non-urgent so urgent interactions stay snappy:
```js
import { startTransition } from 'react';

function onChange(e) {
  setQuery(e.target.value); // immediate feedback
  startTransition(() => {
    setResults(expensiveFilter(e.target.value)); // low priority
  });
}
```
## 6. Use Web Workers for heavy CPU tasks

Offload expensive calculations to a worker to avoid blocking the main thread.

## 7. Optimize rendering of large images / media

Use responsive srcset, modern formats (WebP/AVIF), lazy-loading, CDN.

Use placeholders / blur-up for UX.

## 8. Keep state local and minimize context updates

Lift state only when necessary.

Avoid passing large objects through props repeatedly.

For global state, consider libraries that avoid re-rendering unrelated consumers (Zustand, Jotai).

## 9. Minimize object/array recreation

Pass stable references to children:
```js
// BAD: new array on each render -> child prop changes
<Child items={[1,2,3]} />

// BETTER:
const items = useMemo(() => [1,2,3], []);
<Child items={items} />
```
## 10. Use keys correctly and avoid index keys for dynamic lists

Bad keys -> full re-renders / reordering cost. Use stable unique ids.

## 2) Common optimization techniques (summary list)

Profiling first (React DevTools Profiler)

React.memo, useCallback, useMemo

Code-splitting (React.lazy, dynamic imports)

Virtualization for lists (react-window)

Debounce / throttle input or scroll handlers

StartTransition and Suspense for smoothing async work

Web Workers for CPU-heavy tasks

Image optimization (lazy, srcset, modern formats)

Avoid recreating props (objects/arrays/functions)

Efficient context usage or adopt alternative state libs

Batching updates (React already batches setState in event handlers; use functional updates if relying on previous state)

Memoize expensive render logic or break components into smaller pieces
# 41. How do you identify and fix Memory Leak in React Application ?

## A — What is a memory leak in UI apps?

A memory leak occurs when memory that is no longer needed is not released (references remain). In React apps leaks commonly happen when:

Timers or intervals are not cleared.

Event listeners are not removed.

Subscriptions (WebSocket, RxJS) aren't unsubscribed.

Fetches / async tasks call setState after a component unmounts, retaining closures.

Large caches or DOM nodes remain referenced.

## B — How to identify memory leaks
### Tools / techniques

Chrome DevTools — Memory Tab

Take Heap Snapshots before and after actions to see retained objects.

Use Allocation instrumention / timeline to see allocations over time.

Chrome DevTools — Performance

Look for long frames or increasing memory usage during scenario.

React DevTools Profiler

See repeated renders and component mounting/unmounting oddities.

Why-did-you-render (dev tool)

Helps find unnecessary renders which can cause retention.

Manual inspection

Search for setInterval, addEventListener, subscribe, fetch usage without proper cleanup.

## C — Common leak patterns and fixes (with examples)
## 1. setInterval / setTimeout without cleanup

Leaky:
```js
useEffect(() => {
  const id = setInterval(() => {
    setTick(t => t + 1);
  }, 1000);
}, []); // no return cleanup -> leak after unmount

```
Fixed:
```js
useEffect(() => {
  const id = setInterval(() => {
    setTick(t => t + 1);
  }, 1000);
  return () => clearInterval(id);
}, []);
```
## 2. Event listeners not removed
Leaky:
```js

useEffect(() => {
  window.addEventListener('resize', onResize);
  // no cleanup -> event handler keeps references
}, []);
```

Fixed:
```js
useEffect(() => {
  window.addEventListener('resize', onResize);
  return () => window.removeEventListener('resize', onResize);
}, []);
```
## 3. Fetch / async work continuing after unmount (calling setState on unmounted component)

Leaky pattern (causes setState after unmount):
```js
useEffect(() => {
  fetch(url).then(res => res.json()).then(data => setData(data));
}, [url]);
```

Fix A — AbortController (recommended):
```js
useEffect(() => {
  const controller = new AbortController();
  fetch(url, { signal: controller.signal })
    .then(res => res.json())
    .then(data => setData(data))
    .catch(err => {
      if (err.name === 'AbortError') return;
      setError(err);
    });
  return () => controller.abort(); // cancels fetch on unmount
}, [url]);
```

Fix B — ignore flag (less ideal than abort):
```js
useEffect(() => {
  let mounted = true;
  fetch(url).then(r => r.json()).then(data => {
    if (mounted) setData(data);
  });
  return () => { mounted = false; };
}, [url]);
```
## 4. Subscriptions (WebSocket, RxJS) not unsubscribed

Leaky:
```js
useEffect(() => {
  const sub = myObservable.subscribe(...);
}, []);
```

Fixed:
```js
useEffect(() => {
  const sub = myObservable.subscribe(...);
  return () => sub.unsubscribe();
}, []);
```

For WebSocket:
```js
useEffect(() => {
  const ws = new WebSocket('wss://...');
  ws.onmessage = handle;
  return () => {
    ws.close();
  };
}, []);
```
## 5. Large caches or retained DOM nodes

Make sure caches clear or are bounded (LRU), and avoid holding DOM nodes in state.

## D — Step-by-step process to find & fix a leak

Reproduce the scenario that causes memory growth (navigate, open modal, repeat action).

Record heap snapshots:

Take snapshot at start,

Perform action ~N times,

Take snapshot after,

Compare to find retained objects and allocation stack.

Use allocation profiler to find allocation timestamps and responsible code.

Inspect closures / listeners in snapshot (look for functions referencing big objects).

Locate missing cleanup in useEffects or listeners.

Patch: add cleanup (return () => ...) or abort controllers, unsubscribe, clear timers, bound caches.

Re-test with snapshots to confirm memory is freed.

## E — Example: Detect and fix a leak in a component that fetches on mount
```js
BrokenComponent (leaky if unmounted during fetch):

function BrokenComponent({ url }) {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch(url)
      .then(res => res.json())
      .then(json => setData(json))
      .catch(console.error);
  }, [url]);

  return <div>{data ? 'Loaded' : 'Loading...'}</div>;
}

```
Fix using AbortController:
```js
function FixedComponent({ url }) {
  const [data, setData] = useState(null);
  useEffect(() => {
    const controller = new AbortController();
    let mounted = true;

    async function load() {
      try {
        const res = await fetch(url, { signal: controller.signal });
        const json = await res.json();
        // If fetch aborted, we won't reach here
        if (mounted) setData(json);
      } catch (err) {
        if (err.name !== 'AbortError') console.error(err);
      }
    }
    load();
    return () => {
      mounted = false;         // defensive
      controller.abort();      // cancel network
    };
  }, [url]);

  return <div>{data ? 'Loaded' : 'Loading...'}</div>;
}

```
AbortController prevents the network promise from resolving after unmount; mounted ensures setState never runs on unmounted component (defensive).

## F — Additional practical tips

Avoid isMounted except as defensive pattern; prefer abort/cancel when possible.

Avoid storing DOM nodes in component state. Use ref if needed.

Make caches bounded (max size) or weakly referenced if possible.

Use production builds (they can behave differently than dev blobgy memory).

Run automated checks and memory snapshots in CI for long-running apps where memory matters (e.g., dashboards).
# 42. How do you optimize image rendering in React ?

## 1️⃣ Use Correct Image Sizes (Responsive Images)

### Problem:
If you serve a large 3000px-wide image to a 300px container — it wastes bandwidth and slows down page load.

### Solution:
Use responsive images with srcSet and sizes, or let the browser pick the right one.
```js
<img
  src="small.jpg"
  srcSet="small.jpg 480w, medium.jpg 1024w, large.jpg 1600w"
  sizes="(max-width: 600px) 480px, (max-width: 1200px) 1024px, 1600px"
  alt="Example"
/>

```
 The browser automatically downloads the image size that best fits the device.

## 2️⃣ Lazy Loading (Load Images Only When Visible)

### Problem:
Loading all images upfront increases initial load time.

### Solution:
Use lazy loading to load images only when they appear in the viewport.

 Modern browsers:
```js
<img src="image.jpg" loading="lazy" alt="Lazy image" />
```

## Or using React libraries:

react-lazyload

react-intersection-observer

### Example using IntersectionObserver:
```js
import { useEffect, useRef, useState } from "react";

function LazyImage({ src, alt }) {
  const [visible, setVisible] = useState(false);
  const imgRef = useRef();

  useEffect(() => {
    const observer = new IntersectionObserver(([entry]) => {
      if (entry.isIntersecting) {
        setVisible(true);
        observer.disconnect();
      }
    });
    observer.observe(imgRef.current);
  }, []);

  return (
    <img
      ref={imgRef}
      src={visible ? src : ""}
      alt={alt}
      loading="lazy"
      style={{ minHeight: 200, background: "#eee" }}
    />
  );
}
```

## 3️⃣ Optimize Image Formats

### Problem:
Old formats (JPEG/PNG) are heavier than modern ones.

### Solution:
Use next-gen formats like:

WebP → smaller size, good quality

AVIF → even smaller, high compression

Example:
```js
<picture>
  <source srcSet="image.avif" type="image/avif" />
  <source srcSet="image.webp" type="image/webp" />
  <img src="image.jpg" alt="Fallback" />
</picture>
```

 Browser automatically picks the best supported format.

## 4️⃣ Use a CDN or Image Optimization Service

Use services like:

Cloudinary

Imgix

ImageKit

Vercel Image Optimization (Next.js)

## These handle:

Dynamic resizing

Compression

WebP/AVIF conversion

Caching

## Example (Cloudinary):
```js
<img
  src="https://res.cloudinary.com/demo/image/upload/w_400,h_300,c_fill/sample.jpg"
  alt="Optimized"
/>
```
## 5️⃣ Memoize Heavy Image Components

If you render a list of many images, wrap image components with React.memo()
→ prevents unnecessary re-renders when props don’t change.
```js
const OptimizedImage = React.memo(({ src, alt }) => (
  <img src={src} alt={alt} loading="lazy" />
));
```
## 6️⃣ Use Skeletons or Blurred Placeholders (Progressive Loading)

### Problem:
Images load slowly on slow networks → white flicker before appearing.

### Solution:
Show a low-quality placeholder or skeleton first.
```js
function ProgressiveImage({ lowSrc, highSrc, alt }) {
  const [src, setSrc] = useState(lowSrc);

  useEffect(() => {
    const img = new Image();
    img.src = highSrc;
    img.onload = () => setSrc(highSrc);
  }, [highSrc]);

  return (
    <img
      src={src}
      alt={alt}
      style={{
        filter: src === lowSrc ? "blur(10px)" : "none",
        transition: "filter 0.3s ease",
      }}
    />
  );
}
```

Result: fast, smooth image loading experience.

## 7️⃣ Use next/image in Next.js (if applicable)

If you’re using Next.js, just use the built-in `<Image />` component — it does everything above automatically.
```js
import Image from "next/image";

<Image
  src="/profile.jpg"
  alt="User"
  width={400}
  height={300}
  placeholder="blur"
  priority
/>
```

Features:
✅ Lazy loading
✅ Responsive sizing
✅ WebP optimization
✅ CDN caching

## 8️⃣ Cache Images in Browser or Service Worker

You can use:

Browser caching via HTTP headers

service workers (in PWAs) for offline support

### Example (in your server headers):
```js
Cache-Control: public, max-age=31536000, immutable
```
# 43. How do micro-frontend work?
Micro-Frontends extend the microservices idea to the frontend.
Instead of one big monolithic UI, you break it into smaller, independently built and deployed pieces, each owned by a team.

Each micro-frontend is a self-contained application — it can be built with React, Angular, Vue, or plain JS — and all are stitched together at runtime to form one cohesive user experience.

## The Motivation

Traditional frontends (a single SPA or monolithic bundle) become hard to manage when:

The app grows huge (slow build times, hard deployments)

Many teams contribute (merge conflicts, coupled code)

You want independent deployments per feature or business area

## Micro-frontends solve this by:

Decoupling codebases

Allowing independent development, deployment, and scaling

Enabling technology diversity (React + Angular coexisting)

Reducing deployment risk (small parts deploy separately)

## Key Concepts
### Shell (Container)

The main app that loads and coordinates multiple micro-frontends.
Handles shared routing, layout, authentication, and communication between apps.

### Remote Apps

Each feature/vertical (like Dashboard, Profile, Analytics) runs as its own standalone micro-frontend.

### Integration Strategies

There are a few ways to integrate them:

| Strategy                                     | Description                                       | Pros                   | Cons                         |
| -------------------------------------------- | ------------------------------------------------- | ---------------------- | ---------------------------- |
| **Build-time integration**                   | Combine apps at build                             | Simple                 | Tight coupling               |
| **Run-time integration (Module Federation)** | Load micro-frontends dynamically from remote URLs | Independent deployment | Slightly complex setup       |
| **iFrames**                                  | Each micro-frontend in an iFrame                  | Isolation              | Poor UX & communication      |
| **Web Components**                           | Wrap each MF as a custom element                  | Framework-agnostic     | Limited inter-app state mgmt |

## How Module Federation (Webpack 5) Makes It Work

Module Federation is the most popular modern approach.

It allows one app (the “host”) to dynamically import code from another (“remote”) at runtime.

## Basic Idea

Each micro-frontend exposes its components using Webpack’s exposes.

The container app consumes them using Webpack’s remotes.

## Example (React + Webpack 5)
➤ In webpack.config.js of MicroApp (remote)
```js
new ModuleFederationPlugin({
  name: 'MicroApp',
  filename: 'remoteEntry.js',
  exposes: {
    './Widget': './src/Widget.jsx',
  },
  shared: { react: { singleton: true }, 'react-dom': { singleton: true } },
});
```

➤ In webpack.config.js of Container (host)
```js
new ModuleFederationPlugin({
  remotes: {
    MicroApp: 'MicroApp@http://localhost:3001/remoteEntry.js',
  },
  shared: { react: { singleton: true }, 'react-dom': { singleton: true } },
});
```
➤ In the Container’s code:
```js
import React, { Suspense } from 'react';
const RemoteWidget = React.lazy(() => import('MicroApp/Widget'));

export default function App() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <RemoteWidget />
    </Suspense>
  );
}

```
 Result:

The host app loads the remote bundle at runtime.

Micro-frontend can be deployed separately to its own URL.

## Communication Between Micro-Frontends

Because each app is isolated, they need controlled communication.

Common patterns:

Global Event Bus
Use a shared event emitter for cross-app messaging.

Shared Context/Store
Expose a global store (e.g., Redux or Zustand) and share via Module Federation.

Custom APIs / Props
Pass props down from the host shell.

URL / Router Sync
Use the browser’s URL as a shared source of truth for navigation.

## Deployment Independence

Each micro-frontend:

Has its own CI/CD pipeline

Builds to its own remoteEntry.js

Can be updated or rolled back without redeploying the entire app

Example folder structure:
```js
/shell
  /src
  /webpack.config.js
/dashboard
  /src
  /webpack.config.js
/profile
  /src
  /webpack.config.js
```

Each can be deployed to different servers or CDN paths.

## Real-World Example

Imagine an e-commerce platform:

Feature	Micro-Frontend	Tech
Product Listing	products-app	React
Cart & Checkout	checkout-app	React
Reviews	reviews-app	Vue
Admin Dashboard	admin-app	Angular

Each team owns its feature and deploys updates independently.
The shell app composes them at runtime for the end user.

## Benefits

✅ Independent deployments (faster release cycles)
✅ Smaller codebases (easy maintenance)
✅ Scalability (teams work in parallel)
✅ Tech diversity (React + Vue + Angular coexist)
✅ Incremental upgrades (migrate one app at a time)

## Challenges

❌ Complex routing and shared state management
❌ Larger initial setup (Webpack config, communication)
❌ Version mismatches between shared libs
❌ Increased runtime complexity (loading failures, dependency duplication)





