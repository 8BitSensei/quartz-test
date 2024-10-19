2023-09-15
Tags: #dotnet #programming #compiler 

Introduced in .NET 7 to handle a floor in the [[JIT Tiering]] method

> the code generated for loops also included a counting mechanism, and after a loop iterated to a certain threshold, the JIT would compile a new optimized version of the method and jump from the minimally-optimized code to continue execution in the optimized variant [^1]



---
# References
1. First seen in https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-8/#tiering-and-dynamic-pgo
