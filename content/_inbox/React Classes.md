2023-12-28
Tags: #react #programming 

Class objects can inherit with the ` extend ...` syntax
Classes have constructors with the `constructor(props){}` or `constructor(){}` syntax
Constructors can call the parent constructor with `super()` or `super(props)`
You can access props data with `this.props.`

We set a persistent state on classes with the `state` object:
```js
state = {
    count: 0,
  }
```
This can be read in the class with `this.state.count` and set with `this.setState({count: this.state.count + 1})`

---
# References

https://github.com/Asabeneh/30-Days-Of-React/blob/master/08_Day_States/08_states.md