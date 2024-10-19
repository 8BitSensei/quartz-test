2024-01-07
Tags: #dotNet #programming 

Filters run in the filter pipeline (*action invocation pipeline*), the filter pipeline runs after .net selects the action to execute (which itself happens after the middleware pipeline).

#### Filter types
- Authorisation Filters
	- Runs first and determines whether the user is authorised for the request, short-circuits if not
- Resource Filters
	- Runs two methods `onResourceExecuting()` which runs before everything else, and `OnResourceExecuted()`, which runs after everything else
- Action Filters
	- Runs immediately before and after an action  method is called, can change arguments and results, not supported in Razor Pages 
- Endpoint Filters
	- Seems to be the same as an Action filter, except it can be invoked on both actions and endpoints
- Exception Filters
	- Applies global policies to unhanded exceptions that occur before the response body has been written to
- Result Filters
	- Runs before execution of action results, and only when action method was successful

Razor has it's own *Razor Page filters*

Filters can be added at three scopes:
1. As an attribute on a controller
2. As an attribute on a controller action
3. Globally for all controllers through the builder




---
# References
