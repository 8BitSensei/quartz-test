2023-02-15
#technology #security 

The [[Transport Layer Security]] protocol uses SSL certificates to encrypt and authenticate data streams for HTTPS.
SSL works on top of HTTP to create HTTPS.
SSL Certificates are TLS certificates.
When a web browser initiates a secure connection over HTTPS, the SSL cert is sent to the browser, the browser checks the information in the cert and authenticates it against *its own root certificate store*. 
All major browsers maintain their own web browser root certificate stores. This is where they post the root certificates of CAs the publishers have decided their browsers will trust.


---
# References
