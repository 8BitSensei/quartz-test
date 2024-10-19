2023-06-13
Tags: #csharp #programming 

Occasionally we need to treat a value type, which would usually be managed on the stack, as a reference type and manage it on the heap. For example, an int on an ArrayList must be treated by the ArrayList as an object, to do this the int is '*boxed*' inside an object, allowing us to treat it as a reference type.


---
# References

https://www.youtube.com/watch?v=2ng3d1yB0ck&ab_channel=RyanMcBeth

https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/types#8313-boxing-and-unboxing