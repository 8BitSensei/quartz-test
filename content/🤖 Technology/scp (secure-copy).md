---
date: 2023-03-15
draft: false
tags:
  - technology
  - command-line-utility
---
Command-line utility for securely copying files and directories between two locations in an encrypted manner.

This can be used to retrieve a file from EC2 servers with the following command:

`scp -i "[private key location]" ubuntu@[public address]:[file or directory to copy] [local location to copy to]`

Useful for downloading stuff from EC2 instances

---
# References
