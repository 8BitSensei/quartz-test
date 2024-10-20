---
date: 2023-02-21
draft: false
tags:
  - technology
  - automation
---
Packer is an open source tool for generating identical machine images from single source configuration. Packer can create multiple machine image formats for multiple platforms, AMIs, VMXs, OVF etc. [^1]

Begins with a *packerfile* which codifies all the inputs for a machine image, for example source code, configuration management, or security controls. The *packerfile* takes these and specifies how to use them to create the desired machine image. The *packerfile* is fed into the Packer service, which is able to take and execute the definitions within it to create multiple machine images for different platforms, e.g. AMI. VMWare image, Docker Container. [^2]

After images are created, the metadata of our images can be published to a cloud hosted Packer registry. Our machine images are recorded as artifacts with versions, and for each version there may be multiple instances of our artifact for different platforms. This Packer registry can be queried via the API to retrieve the desired version of an artifact for a platform, this is useful to passing to downstream systems, such as Terraform. [^2]



---
# References

[^1]: https://developer.hashicorp.com/packer/docs/intro
[^2]: https://www.youtube.com/watch?v=r0I4TTO957w