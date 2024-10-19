2023-05-15
#programming #csharp

#### Startup
A program may be compiled either as a [[Class Library|class library (C Sharp)]] or as an [[application|application (C Sharp)]], the mechanism for determining which mode of compilation is implementation-specific (up to VS I guess).

A program compiled as an application has to contain at least one method that qualifies as an entry point, an entry point must satisfy the following requirements:
- Named `Main`
- Shall be marked `Static`
- Not be generic
- Declared in a non-generic type
	- If the type declaring the method is nested, none of its enclosing types may be generic
- May have an `async` modifier provided it has a return type of `Task` or `Task<int>`
- The return type shall be `void`, `int`, `Task`, or `Task<int>`
- Shall not be a partial method without an implementation
- The formal parameter list shall be empty, or have a single value of type `string[]`

Multiple methods may qualify as an entry point, in which case an external mechanism is used to specify the method which is actual entry point for the application.

Qualifying methods with a return type of `int` or `void` overrule qualifying methods with a return type of `Task` or `Task<int>`.

Compiling an application without a valid entry point is a compile-time error.

A program compiled as a class library may contain methods that would qualify as entry points, but the resulting library has no entry points.

Unlike the regular rules of accessibility, the [[execution environment]] can access the application's entry point regardless of its declared accessibility and it's enclosing type. (why doe it need to be static then?)

When the entry point has a type of `Task` or `Task<int>` the compiler creates a synchronous entry-point method that calls the corresponding Main method, the created method has parameters and return types based on the `Main` method. On execution, the created method calls the `Main` with `GetAwaiter().GetResult()` and propagates any results or errors.

**effective entrypoint**: is defined as the entry point within the program or the synthesised method used when the entrypoint is async

When an application is run, a new **application domain** is created. This enables application isolation by acting as a container for the application state, so several different instantons of an application may co-exist on the same machine. Types in an application domain are distinct from types in another domain, and instances of objects are not directly shared between domains.

Other than at start up, the entry point method behaves like any other method, it may be invoked at any other point in the application lifecycle and will not receive special handling.

#### Termination


---
# References

https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/basic-concepts#72-application-termination