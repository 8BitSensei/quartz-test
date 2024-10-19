2023-10-27
Tags: #programming #protocol 

Protocol which allows a client to communicate with a server application on a different machine as if it were a local object. Based around the idea of defining a service, specifying the methods that can be called remotely with their parameters and return types.

By default, gRPC uses [[Protocol Buffers]], Google's open source mechanism for serialising structured data.

Overall, provides a quick and efficient way for clients and services to communicate with each other, the fact that server commands are treated as if they were a local object makes development easier, and allows different microservices to use different languages and environments where necessary.

Built on top of low-level HTTP2, so unavailable through browsers.

Language neutral.

---
# References

https://grpc.io/docs/what-is-grpc/introduction/