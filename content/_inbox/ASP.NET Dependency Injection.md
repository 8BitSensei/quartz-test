2024-01-07
Tags: #dotNet #programming 

DI in ASP.NET is achieved with a built in solution, you can add dependencies to your project through the `IServiceCollection` class on your `builder`, this provides multiple methods for adding a dependency with a specific lifecycle e.g. scoped

This works in pretty much the same way as regular [[Dependency  Injection (.NET)]], except that you will be using a different type of builder (check this, I'm not sure)

---
# References

https://learn.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-8.0