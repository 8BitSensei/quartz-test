2023-12-18
Tags: #cloud #azure

Form of [[Serverless]] computing.

Azure's event-driven serverless compute option. Similar to [[AWS Lambda]].

Allows us to run code based on an event (REST, timer, or message) which wakes the function with a request, functions are commonly used to build out REST API architecture. 

Functions only run your code when recieveing a valid event, meaning that when your code isn't being used you aren't being charged for it. Functions are also automatically scaled based on demand. They can also be stateless or stateful by passing a context to the next run.

Serverless functions are very popular at the moment because they are easy to develop, easy to manage, automatically scale, and you only pay when it's being used.


---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-azure-compute-networking-services/6-functions