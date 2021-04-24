 # What is useRef ?
 useRef hook is part of the React Hooks API. It is a function which takes a maximum of one argument and returns an Object . The returned object has a property called current whose value is the argument passed to useRef . If you invoke it without an argument, the returned object's current property is set to undefined <br><br>
 # Why we use useRef in react?
 The useRef Hook allows us to create mutable variables in functional components. It's useful for accessing DOM nodes/React elements, and to store mutable variables without triggering a re-render.<br><br>
 The useRef Hook is a function that returns a mutable ref object whose .current property is initialized with the passed argument (initialValue). The returned object will persist for the full lifetime of the component.<br><br>
: **Syntax**
 ```
 const refContainer = useRef(initialValue);
 ```
 ## There are two main uses of useRef that are explained in the following sections: Accessing the DOM nodes or React elements and keeping a mutable variable.<br><br>
 ##Accessing the DOM nodes or React elements
 **If you’ve worked with React for a while, you might be used to using refs for this purpose. Below there’s an example of the use of refs in class components:**
 ```
 import React, { Component, createRef } from "react";

class CustomTextInput extends Component {
  textInput = createRef();

  focusTextInput = () => this.textInput.current.focus();

  render() {
    return (
      <>
        <input type="text" ref={this.textInput} />
        <button onClick={this.focusTextInput}>Focus the text input</button>
      </>
    );
  }
}
```
**And its equivalent using a functional component:**
```
import React, { useRef } from "react";

const CustomTextInput = () => {
  const textInput = useRef();

  focusTextInput = () => textInput.current.focus();

  return (
    <>
      <input type="text" ref={textInput} />
      <button onClick={focusTextInput}>Focus the text input</button>
    </>
  );
}
```
### Notice that with a functional component we are using useRef instead of createRef. If you create a ref using createRef in a functional component, React will create a new instance of the ref on every re-render instead of keeping it between renders.

# Keeping a mutable variable
Both in class components and functional components using Hooks, we have two ways of keeping data between re-renders:<br><br>
**In class components**
1. In the component state: Every time the state changes, the component will be re-rendered.
2. In an instance variable: The variable will persist for the full lifetime of the component. Changes in an instance variable won’t generate a re-render.
**In functional components**
The equivalent ways in functional components using Hooks:
In a state variable: useState or useReducer. Updates in state variables will cause a re-render of the component.
In a ref: Equivalent to instance variables in class components. Mutating the .current property won’t cause a re-render.
Below is an example of keeping a mutable variable in a ref. The component <Timer> initializes a setInterval on every re-render and needs to implement a callback to stop its interval imperatively:<br>
```
import React, { useRef, useEffect } from "react";

const Timer = () => {
  const intervalRef = useRef();

  useEffect(() => {
    const id = setInterval(() => {
      console.log("A second has passed");
    }, 1000);
    
    // We need the interval id to be accessible from the whole component.
    // If we stored the id in a state variable, the component would be re-rendered
    // after the state update so a new interval will be created (this effect is triggered
    // after every re-render) leading us to the infinite loop hell.
    intervalRef.current = id;
    
    return () => clearInterval(intervalRef.current);
  });

  const handleCancel = () => clearInterval(intervalRef.current);
  
  return (
    <>
      //...
    </>
  );
}
```


