2023-06-01
#programming #dotNet #csharp 


### Don't sync over async

All callers of async methods should be async. If not, there is no point in calling asynchronous methods in the first place, apparently, this can be worse than being entirely synchronous. Make everything async all the way up the call stack.

### Avoid async void

Because async void methods can't be tracked, there exceptions can't be handled and may crash the application, `Task` returning methods allow us to handle exceptions as the `TaskScheduler.UnobservedTaskException`.

### Prefer `Task.FromResult` over `Task.Run` for trivial computations

`Task.Run` will schedule a work item in the thread pool, this is unnecessary for pre-computed or trivial calculations. Using `Task.FromResult` will simply wrap the data in a Task, without wasting a thread pool. Or, better yet, use `ValueTask<T>` which does not schedule a thread pool, and does not allocate a `Task` object on the heap.

### Avoid using `Task.Run` for long living work

Long running work, that is a thread that will be running for the the lifetime of the application doing background work. `Task.Run` will queue an item to the thread pool, with the assumption it will finish and free up the thread soon. It is better practice to manually create a new thread for this type of work, leaving the thread pool open for other tasks.




---
# References

https://github.com/davidfowl/AspNetCoreDiagnosticScenarios/blob/master/AsyncGuidance.md