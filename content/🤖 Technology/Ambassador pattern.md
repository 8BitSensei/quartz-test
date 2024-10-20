---
date: 2023-06-23
draft: false
tags:
  - DesignPattern
---
Create helper services that send network requests on behalf of a consumer service or application.

#### Problem
Useful for offloading common client connectivity task such as monitoring, logging, routing, and security in a language agnostic way. Often used with legacy applications that are difficult to modify in order to extend their networking capabilities.

Cloud applications that are resilient often need features like circuit breaking, routing, metering and monitoring, as well as substantial configuration, authentication, and authentication. This may be difficult or impossible to implement in a legacy service.

#### Solution
Put client frameworks and libraries into an external process that acts as a proxy between your application and external services. Deploy the proxy on the same host environment as your application to allow control over routing, security, and to avoid access restrictions.

![[Pasted image 20230623135520.png]]


#### Fantasy
An old king rules a kingdom that has grown to the size of an empire, it encompasses many lands, many cultures, and many languages, they have had to develop a system of signals and postal ponies to communicate across his kingdom. In the pas the king would be able to communicate directly with his lords, he should simply ride to their keeps or order them to visit him, they understood how to act around each other and knew each others language. Now, the king has had to employ a young squire as his ambassador, he passes the kings messages on, writes letters in every language and organises the postal system, reading the kings messages to him and responding for him.

---
# References

https://learn.microsoft.com/en-us/azure/architecture/patterns/ambassador