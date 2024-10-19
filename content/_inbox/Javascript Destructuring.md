2023-12-28
Tags: #programming #javascript 

Syntax in JS that allows us to unpack values from arrays or objects (basically the same thing in JS) into distinct variables. 

For example in Arrays:
```javascript
let introduction = ["Hello", "I" , "am", "Sarah"];
let [greeting, pronoun] = introduction;

console.log(greeting);//"Hello"
console.log(pronoun);//"I"
```

Or in an object:
```javascript
let person = {name: "Sarah", country: "Nigeria", job: "Developer"};

let {name, country, job} = person;

console.log(name);//"Sarah"
console.log(country);//"Nigeria"
console.log(job);//Developer"
```

---
# References
