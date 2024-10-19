2023-06-19
Tags: #programming #software-design 

Principles laid out by [[Robert C. Martin]]


##### S - The Single responsibility Principle

A class should have one and only one reason to change, meaning that a class should have only one job.

##### O - The Open closed Principle

You should be able to extend a classes behaviour, without modifying it.

##### L - The Liskov Substitution Principle

Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program.

##### I - The Interface Segregation Principle

Many client-specific interfaces are better than one general-purpose interface.

##### D - The Dependency Inversion Principle

Depend on abstractions, not on concretions. It states that the high-level module must not depend on the low-level module, but they should depend on abstractions.

It looks like this is just dependency injection with a generic interface, e.g. the adapter or façade pattern. Rather thand my class depending on some low-level utility it depends on an interface, which can be any matching low-level utility



---
# References

- https://www.digitalocean.com/community/conceptual-articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design
- http://butunclebob.com/ArticleS.UncleBob.PrinciplesOfOod
- https://groups.google.com/g/comp.object/c/WICPDcXAMG8?hl=en#adee7e5bd99ab111
- https://medium.com/@peterlee2068/software-design-principles-every-programmer-should-know-c164a83c6f87