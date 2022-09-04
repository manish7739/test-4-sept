##  (1) What are components in React?
- It is a reusable class/function which contains the JSX.
- Inside components we put all the various components that we will be using.
- A component can return the JSX.
- One file can have multiple classes/function, therefore it can have multiple      components.
- The Component name should follow PascalCasing. Otherwise it will not work.
- It can be wrapped using ().


## (2) What are props in React?
- Props are arguments passed into React components.
- This is short for properties.
- Props are passed to components via HTML attributes.
- Props means sending of data from 1 component to another.
- In the child component. For functional component, we can get the prop directly as the function's parameter.
- The Props only flows from parent to Child Component.
- The prop data can be anything, primitive data type, non primitive data type, even functional references.


## (3) How to Use CSS in React. Explain all methods by using a small code snippet.

  # Inline Styling:
- We can directly style an element using inline style attributes. Make sure the value of style is a JavaScript object:

Example

 function style(){
    return(
        <div> 
         <h3 style={{ color: "Yellow" }}>This is a heading</h3>
        </div>
    );
 }

 # Using JavaScript object:

 
 function style(){
    headingStyles = 
    {
    color: "blue",
    fontSize: "48px"
    }
    return(
        <div> 
         <h3 style={this.headingStyles}>This is a heading</h3>
        </div>
    );
 }

## CSS Stylesheet:
import './RandomComponent.css';

function Style() {
 
   return (
     <div>
       <h3 className="heading">This is a heading</h3>
     </div>
   );
 
}

## CSS Modules:

 - Create a file with module.css
.paragraph{
 color:"red";
 border:1px solid black;
}

- We can import this file inside the component and use 
import styles from  './styles.module.css';

function Style() {
 
   return (
     <div>
       <h3 className="heading">This is a heading</h3>
       <p className={styles.paragraph} >This is a paragraph</p>
     </div>
   );
 
}


## (4) What's the Use of the useMemo() Hook? Explain by giving an example.
    
- This will be used for recomputing the memoized value when there is a change in one of the dependencies.


import React, { useState} from "react";

function Hooks() {
  const [msg, setMsg] = useState("hello");
  const reverseMsg = useMemo(() => {
    return msg.split("").reverse().join("");
  },[msg]);

  return (
    <div>
      <h1>{msg}</h1>
      <h1>{reverseMsg}</h1>
      <h1>{reverseMsg}</h1>
      <button onClick={() => setMsg("Hello")}>Change Msg</button>
    </div>
  );
}

export default Hooks;