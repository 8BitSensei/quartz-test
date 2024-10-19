2023-03-21
#programming #go-lang 

Following the default testing framework[^1]

Designed to be used with the `go test` command, which automates the execution of an function with the signature:

```go
func TestXxx(*testing.T)
```

Where `Xxx` is the function name identifying the test routine.

Within these functions, use the `Error`, `Fail`, or related methods, to signal failure.

To create a new test suite, we must create a new file ending in `_test.go`, this will be excluded from regular package builds, but, it will be identifed and run by the `go test` command.

---
# References

[^1]: https://pkg.go.dev/testing