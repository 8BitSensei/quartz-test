---
date: 2023-02-15
draft: false
tags:
  - technology
  - security
---
A trusted entity that *issues [[SSL certificates]]*. 
These certificates are cryptographically link an entity with a *public key*. 
Also encrypts communications over the internet and maintains integrity of documents signed with it.
The certificate contains information about the entity it has been issued to.
The certificate it also includes the name of the issuing CA and its digital signature.
The signature proves the issuing CA and that it has not been modified.

An entity can request a digital certificate from a CA. First, it generates a key pair consisting of:
- **Private Key** which is always kept a secret
- **Public Key** which is mentioned (?) in the digital certificate the CA issues -- the applicant also generates a certificate signing request (**CSR**), an encoded text file that specifies the information that will be included in the certificate

The applicant sends the CSR to the CA which verifies the information and applicants identity (how?), then generates a digital certificate, signs it with its private key, and sends the cert to the authority.

![[cert authority.jpg]]

---
# References
