---
date: 2023-02-15
draft: false
tags:
  - technology
  - security
---
A root certificate is a certificate issued by a **trusted** [[Cert Authority]], a cert isn't considered valid until signed by a trusted CA. SSL is based on a "chain of trust", when a device validates a certificate, it compares the cert issuer with the lost of trusted CAs, if a match isn't found, the client checks the certificate of the CA was issued by a trusted CA, and so on. The certificate at the top of this chain is considered the root certificate.

![[Pasted image 20230215200055.jpg]]

---
# References
