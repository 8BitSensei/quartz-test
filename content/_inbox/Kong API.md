2023-03-13
#technology 

For connecting APIs and Microservices. 

Ingress controller used as a middle-man to control DNS traffic and direct it to our micro-services

#### Kong Gateway

Open source gateway

It allows you to exercise granular control over your traffic with Kong’s plugin architecture

#### Kong Server

Built on [[NGINX]], will actually process the API requests and execute configured plugins before proxying the request upstream.

Listens on ports:
- `8000` for proxying HTTP
- `8443` for proxying HTTPS

Also uses the internal ports:
- `8001` for Kong's Admin API
- `8444` for Kong's Admin API over HTTPS

#### Kong Datastore

External datastore to store its configuration details. Kong maintains a cache of this data to avoid database roundtrips when requesting data.


---
# References

https://konghq.com/faqs