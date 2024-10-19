2023-12-27
Tags: #react #programming 

Small reusable piece of code which is responsible for one part of the application UI. 
React application is an aggregation ore re-usable components.

There two types of component, a **functional component** which uses functions, and a **class-based component** which uses a class.

Other terms have been used in older versions of React:
- Functional Component / Presentational Component / Stateless Component / Dumb Component
- Class Component / Container Component/ Statefull Component / Smart Component

Component name must start with an uppercase, and if the name is two words, it should be CamelCase - a camel with two humps.

A React component is just any function or class that returns a JSX element.

##### Functional Component

```js
const jsx = <tag> Content </tag>
const ComponentName = () => {
  return jsx
}
```

When we need to render a component, instead of calling them in `{...}` curly braces, we call it in `<... />` chevrons

```js
// Footer Component
const Footer = () => (
  <footer>
    <div className='footer-wrapper'>
      <p>Copyright 2020</p>
    </div>
  </footer>
)

// The App, or the parent or the container component
const App = () => (
  <div className='app'>
    <Footer />
  </div>
)

const rootElement = document.getElementById('root')
// we render the App component using the ReactDOM package
ReactDOM.render(<App />, rootElement)
```

#### Class component

#### Controlled & Uncontrolled
Controlled components update their state based on form events from a form that they also control.  For example, a component that renders a form, which `onChange` calls a method in that component to update the state, this state affects the form. This is a tightly coupled, *controlled* component

An uncontrolled component is one where the associated form uses the `ref` element to store the input values in the [[DOM]], and the component gets their value from the `ref` through the [[DOM]]. The DOM is acting as an intermediary, and it controls the data, the component *does not control it*.
#### Component Lifecycle
In the component life cycle there are three stages, **Mounting**, **Updating**, and **Unmounting**. 
##### Mounting
When a component is rendered, or put into the [[DOM]], it is called mounting. A component (that is a class extending `React.Component`), has four inherited methods which run in the following order:
1. `constructor()`
2. `static getDerivedStateFromProps()` - Where the state is set from initial props
3. `render()` - Returns JSX elements, only required method
4. `componentDidMount()` -  Initialization that requires DOM nodes should go here. If you need to load data from a remote endpoint, this is a good place to instantiate the network request
##### Updating
An update sequence is triggered when the state or props of a component changes and it is re-rendered, the following methods will be called in the following order:
1. `static getDerivedStateFromProps()`  - Where the state is set from initial props
2. `shouldComponentUpdate()` - Returns true by default, if this returns false the component will not be re-rendered, for optimisation reasons
3. `render()`
4. `getSnapshotBeforeUpdate()` - Called before the rendered JSX is committed to the DOM,  It enables your component to capture some information from the DOM (e.g. scroll position) before it is potentially changed. Return value is passes to `componentDidUpdate()`
5. `componentDidUpdate()` - This is also a good place to do network requests as long as you compare the current props to previous props (e.g. a network request may not be necessary if the props have not changed).
##### Unmounting
The component is removed from the DOM, the only method called is `componentWillUnmount()`, you can perform any necessary cleanup in this method, such as invalidating timers, canceling network requests.

---

#### Higher Order Component
In JS, a higher order function is a function that takes another function as a parameter or returns another function. Similarly, a higher order component takes a component and can return another component

# References

https://github.com/Asabeneh/30-Days-Of-React/blob/master/04_Day_Components/04_components.md