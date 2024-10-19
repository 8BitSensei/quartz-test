2023-03-20
#programming #go-lang 

A package is the smallest unit of private encapsulation in Go. All identifiers (variables, methods, etc) defined within a package (e.g. `main`) are visible throughout the package, when importing a package you can access only its exported identifiers, an identifier is exported **if it begins with a capital letter**.

This is basically Go's equivalent of public and private. If we want members of a type to only be accessed by members of that type, we would need to place that type and its members in a separate package.

---
# References
