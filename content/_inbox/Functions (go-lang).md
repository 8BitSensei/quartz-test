2023-03-20
#programming #go-lang 


#### Signature

```go
func (input) output type
```


output parameters in `(...)` must be named
```go
func (input) (named output)
```

Multiple variables as input or output
```go
func (a, int, b string) (x int, y string)
```

When two or more function parameters share a type, you can omit the type from all but the last
```go
func (a, b int) int
```


---
# References

https://go101.org/article/function.html

https://go.dev/tour/basics/5