2023-12-27
Tags: #react #programming 

Props in React stands for Properties, used to pass data from one component to another and mostly from parent component to child component. Props is a '*data carrier*' or a means to transport data.

Example usage
```js
// User component, component should start with an uppercase
const User = (props) => {
  return (
    <div>
      <h1>
        {props.firstName}
        {props.lastName}
      </h1>
      <small>{props.country}</small>
    </div>
  )
}
// calling or instantiating a component, this component has three properties and we call them props:firstName, lastName, country
<User firstName = 'Asabeneh', lastName='Yetayeh' country = 'Finland' />
```

We can see that *props*, is just a dynamic object, and we are able to set the properties in the HTML element.

---
# References
