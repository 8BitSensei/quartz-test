2023-12-27
Tags: #programming #react 

NodeJS is an asynchronous event-driven JavaScript runtime environment that allows JavaScript to run on a server. 

Created in 2009.

Free from locks so no dead-locking to worry about, performs almost no I/O so the process never blocks except when I/O is performed using synchronous methods.

Is cross-platform

For executing JS code outside of a browser

built on Chrome’s V8 JavaScript engine

> It is often **Mistaken that Node is Multi-Threaded**. It is based on **Single Threaded Event Loop** Architecture. This **Event Loop is Single Threaded**. All the Requests are received on this Event Thread. Every Requests consists of Asynchronous and Synchronous Execution. The Main Thread is responsible to Execute Only the Synchronous Part of the Request. As soon as Asynchronous I/O Operation is encountered, the Main Thread allocates a Background thread to process the I/O Operation.

---
# References
https://github.com/Asabeneh/30-Days-Of-React/blob/master/03_Day_Setting_Up/03_setting_up.md#node
https://nodejs.org/en/about
https://www.turing.com/kb/understanding-the-nodejs-architecture
https://medium.com/technofunnel/node-js-single-threaded-event-based-architecture-9f73daee37a1