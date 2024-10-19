2023-09-14
Tags: #dotNet #programming #compiler 

> there are throughput benefits to going through tier 0, in that there are things the JIT can learn about a method from tier 0 which can then improve its tier 1 compilation. And the list of things the JIT can learn gets a whole lot bigger with dynamic PGO. [^1]

> The typical flow is you build your application with some additional instrumentation, you then run your application on key scenarios, you gather up the results of that instrumentation, and then you rebuild your application, feeding that instrumentation data into the optimizer

> The typical flow is you build your application with some additional instrumentation, you then run your application on key scenarios, you gather up the results of that instrumentation, and then you rebuild your application, feeding that instrumentation data into the optimizer, allowing it to use the knowledge about how the code executed to impact how it’s optimized. This approach is often referred to as “static PGO.” “Dynamic PGO” is similar, except there’s no effort required around how the application is built, scenarios it’s run on, or any of that. With tiering, the JIT is already generating a tier 0 version of the code and then a tier 1 version of the code… why not sprinkle some instrumentation into the tier 0 code as well?

---
# References
 - First seen in https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-8/#tiering-and-dynamic-pgo