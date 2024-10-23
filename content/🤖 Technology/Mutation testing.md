---
date: 2024-10-21
tags:
  - go-lang
  - programming
  - testing
---
Interesting talk on Mutation testing in Go at [October's London Gophers meet up](https://www.meetup.com/londongophers/events/303133589/?eventOrigin=group_past_events). The talk was Who Tests The Tests?* by Daniela Petruzalek, I wasn't aware of this kind of testing before, so I'm happy to have learnt about it.  

The idea is, instead of aiming for an arbitrary test coverage metric (which leads to ignoring code quality), you aim to 'kill' as many mutations of your tests as possible. Basically, a '*mutant*' is a variant of your test where you have made some small mutation, such as reversing boolean operators , changing operators, inverting boolean expressions, deleting statements etc. This causes the behaviour of your code to fundamentally change, the example used in the talk was changing the following:

```go
// Original
func divide(dividend, divisor int) (int, error) {
	if divisor == 0 {
		return 0, ErrDivideByZero
	}

	return dividend / divisor
}

//Mutation
func divide(dividend, divisor int) (int, error) {
	if divisor == 0 {
		return 0, ErrDivideByZero
	}

	return dividend * divisor
}
```

A poor test, but one which achieves code coverage, could potentially miss this change e.g. if you are only testing for that divide by zero error.

What is proposed as a PoC, is that we create tooling to walk the AST of our code and make these mutations, then see if our tests still pass, if they do that's a red flag. Some tooling already exists actually, there is a Go Gremlins project to do this, but seems to have been abandoned now.

![image](https://github.com/danicat/gophercon2024/raw/main/gopher_vs_mutant.jpeg)

References
---
- https://github.com/go-gremlins/gremlins?tab=readme-ov-file
- https://github.com/danicat/gophercon2024?tab=readme-ov-file
