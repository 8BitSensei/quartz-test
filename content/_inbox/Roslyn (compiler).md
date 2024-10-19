2023-02-24
#programming 

Roslyn is actually a platform *which contains* compilers and tools for parsing and analysing code written in C# and Visual Basic.

We can use tools provided by roslyn to do complete code parsing and analysis. The Visual Studio environment allows us to create tools embedded in the IDE itself which use roslyn tools to analyse the code we write.

---

Traditional compiler pipeline:

parser ->
Symbols & Metadata ->
Binder ->
IL Emitter

In Roslyn, every phase exists, but it is treated as a separate component with an API, and the parsing phase is represented by a syntax tree.

Syntax Tree API ->
Symbol API ->
Binding & Flow Analysis API ->
Emit API

These phases are collectively referred to as the Compiler APIs, it is this architectural change that forces us to think of Roslyn as a compiler platform, rather than a single traditional compiler.

![[Pasted image 20230621104120.jpg]]




---
# References

https://sergvasiliev.medium.com/introduction-to-roslyn-and-its-use-in-program-development-bce2043fc45d

https://www.syncfusion.com/succinctly-free-ebooks/roslyn/walking-through-roslyn-architecture-apis-syntax - good one