---
date: 2023-03-20
draft: false
tags:
  - programming
  - go-lang
---
`defer` is a keyword in Go that tells the compiler to *defer* the execution of a command, that is, the compiler won't run that command until the rest of the current function has finished executing
```go
package main

impirt "fmt"

func main() {
	defer fmt.Println("World")
	fmt.Println("Hello")
}

/*
Output:  

Hello
World
*/
```

If we use `defer` multiple times in the same function, they execute in reverse order, that is *first-one-in-last-one-out*
```go
package main

impirt "fmt"

func main() {
	defer fmt.Println("One")
	defer fmt.Println("Two")
	defer fmt.Println("Three")
	fmt.Println("Hello")
}

/*
Output:

Hello
Three
Two
One
*/
```

---
# References

https://www.educative.io/answers/what-is-the-defer-keyword-in-golang