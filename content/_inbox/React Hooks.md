2023-12-29
Tags: #react #programming 

Hooks are a way of managing states in Functional Components in a similar way to Class Components.  Hooks are basically JS Functions, but they come with two extra rules:
- Only call Hooks **at the top level**. Don’t call Hooks inside loops, conditions, or nested functions.
- Only call Hooks **from React function components**. Don’t call Hooks from regular JavaScript functions.
#### State Hook
You can use `useState()` to create a new state object, with an initial value. This will return a reference variable and a set method (here we are using the destructuring syntax to retrieve them):
```js
function ExampleWithManyStates() {
  // Declare multiple state variables!
  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState('banana');
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
  // ...
}
```

Hooks allow us to 'hook' into state data from Functional components, they *can't be used in a class*. 

#### Effect Hook
The Effect Hook allows you to use the `useEffect()` method, which serves the same purpose as `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` in React classes, in that you can access and manage data *after* the component is rendered.
```js
// Similar to componentDidMount and componentDidUpdate:
useEffect(() => {    
	// Update the document title using the browser API
	document.title = `You clicked ${count} times`;
});
```

---
# References
https://legacy.reactjs.org/docs/hooks-overview.html#:~:text=Hooks%20are%20functions%20that%20let,if%20you'd%20like.)