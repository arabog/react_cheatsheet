# The React Cheatsheet for 2022
## Table of Contents
React Elements  
React Element Attributes  
React Element Styles  
React Fragments  
React Components  
React Props  
React Children Props  
React Conditionals  
React Lists  
React Context  
React Hooks  
React useState Hook  
React useEffect Hook  
React useRef Hook  
React useContext Hook  
React useCallback Hook  
React useMemo Hook  

## React Elements
React elements are written just like regular HTML elements. You can write any valid HTML element in React.  

```
<h1>My Header</h1>
<p>My paragraph>
<button>My button</button>
```
We write React elements using a feature called JSX. However, because JSX is really just JavaScript functions (and not HTML), the syntax is a bit different. Unlike HTML, single-tag elements (like the img element), must be self-closing. They must end in a forward slash `/`:  

```
<img src="my-image.png" />
<br />
<hr />
```

## React Element Attributes
Additionally, JSX requires a different syntax for its attributes. Since JSX is really JavaScript and JavaScript uses a camelcase naming convention (that is, “camelCase”), attributes are written differently than HTML. The most common example is the class attribute, which we write as className.
```
<div className="container"></div>
```
## React Element Styles
To apply inline styles, instead of using double quotes (“”), we use two sets of curly braces. Inline styles are not written as plain strings, but as properties on objects:
```
<h1 style={{ fontSize: 24, margin: '0 auto', textAlign: 'center' }}>My header</h1>
```

## React Fragments
React also gives us an element called a fragment. React requires that all returned elements be returned within a single “parent” component.  

For example, we can’t return two sibling elements, like an h1 and a paragraph from a component:
```
// this syntax is invalid
function MyComponent() {
  return (
    <h1>My header</h1>
    </p>My paragraph</p>
  );
} 
```

If we don’t want to wrap our elements in a container element like a div, we can use a fragment:
```
// valid syntax
function MyComponent() {
  return (
    <>
      <h1>My header</h1>
      </p>My paragraph</p>
    </>
  );
} 
```
We can write fragments in a regular or shorthand syntax: `<React.Fragment></React.Fragment> or <></>`.

## React Components
We can organized groups of elements into React components. A basic function component is written similarly to a regular JavaScript function with a couple of differences.  
Component names must start with a capital letter (that is, MyComponent, instead of myComponent)  
Components, unlike JavaScript functions, must return JSX.  
Here is the basic syntax of a React function component:
```
function App() {
  return (
     <div>Hello world!</div>
  );
} 
```

## React Props
React components can accept data passed to them called props. Props are passed from the parent component to a child component. Here we are passing a prop name from App to the User component.  
```
function App() {
  return <User name="John Doe" />
}

function User(props) {
  return <h1>Hello, {props.name}</h1>; // Hello, John Doe!
}
```
Props is an **object**, so we can select the `name` prop within User to get its value.  

To embed any dynamic value (that is, a variable or expression) within JSX, you must wrap it in `curly braces, {}`.  

Since we are only using the name property on the props object, we can make our code simpler with object destructuring:
```
function App() {
  return <User name="John Doe" />
}

function User({ name }) {
  return <h1>Hello, {name}!</h1>; // Hello, John Doe!
}
```
**Any JavaScript value can be passed as a prop, including other elements and components.**

## React Children Props
