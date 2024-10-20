---
date: 2023-03-20
draft: false
tags:
  - programming
  - go-lang
---
#### Basic valid declarations

Initialises to default value (`0`)
```go
var age int
```

Initialises `int` `age` at value `29`
```go
var age int = 29
```


Go will infer the type as int
```go
var age = 29
```

Multiple variables with different values can be declared in one line
```go
var width, height int = 100, 50
```

Go will still infer the type in this instance, this is also allows us to use different types
```go
var name, height = "Charlie", 50
```

These can also be declared in a block, I don't see much use for this
```go
var (
	name = "Charlie"
	age = 27
	height int
)
```


#### Short hand declaration

Go also provides a short hand declaration using the `:=` operator which allows us to drop the `var` keyword.

```go
count := 10
```

The trade off is that *we have to* declare a value, otherwise this produced an *undefined* error. Unlike, above where we can declare `var age int` which will initialise to 0, Go must know the type to be able to initialise a default value.

Like before, multi-variable declarations work, and Go can infer multiple types. If one of the values is left out this will result in an error, as it does not know what type the variable is to initialise a default value
```go
name, age := "Charlie", 27
```

Short hand declaration can only be used when at least one of the left hand variables is new, otherwise it results in an error. To assign new values to a variable, you must use the `=` operator
```go
a, b := 10, 20 //Valid
b, c := 30, 40 //Valid
b, c := 50 60 //Error!
```


#### Strongly typed variables

Because Go is a [[strongly typed]] language, variables declared as belonging to one type cannot be assigned a value of another type. 
```go
age := 29
age = 33 //Valid
age = "Twenty Nine" //Error!
```


#### [[Pointer|Pointers]]

Variables are just the names given to a memory location where the actual data is stored. A pointer is a special kind of variable that is not only used to store the memory addresses of other variables, but also points to where the memory is located and provides a way to find out the value stored at the memory location.

We declare these pointer in Go using the *dereferencing operator* `*`, which is prefixed to the type of the variable, so we can declare a new pointer like so:
```go
var s *string
```

But, this needs to be initialised with the memory address of another variable, to get the memory address of a variable we use the `&` operator on it:
```go
var x int = 100
var p *int

p = &x

// x = 100
// &x = 0x414020
// p = 0x414020 
```

Memory addresses in Go are represented as hexadecimal values and the default value of a pointer is always *nil*

We can also use type inference with pointers
```go
var x = 100
var p = &x

// x = 100
// &x = 0x414020
// p = 0x414020 
```

Short hand syntax also works
```go
x := 100
p := &x

// x = 100
// &x = 0x414020
// p = 0x414020 
```

We can also **dereference** the pointer, that is, we can retrieve the value which is stored in the memory location by re-using the dereference operator `*` on the pointer
```go
x := 100
p := &x
*p

// x = 100
// &x = 0x414020
// p = 0x414020
// *p = 100
```

We can use this to modify the value held in memory from the pointer
```go
x := 100
p := &x
*p = 200

// x = 200
// &x = 0x414020
// p = 0x414020
// *p = 200
```

Assigning the value stored in memory to a new variable will copy the value to a new memory location
```go
x := 100
p := &x
y := *p

// x = 100
// &x = 0x414020
// p = 0x414020
// *p = 100
// y = 100
// &y = 0x515028
```

---
# References

https://golangbot.com/variables/

https://www.geeksforgeeks.org/pointers-in-golang/