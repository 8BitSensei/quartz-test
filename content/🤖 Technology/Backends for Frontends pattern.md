---
date: 2023-06-23
draft: false
tags:
---
Using different backend services for specific frontend applications or interfaces. This is useful if you want to avoid customising a single backend for multiple interfaces. 

You may have developed a backend in parallel with a frontend desktop application, but say we now want to develop a mobile application. The mobile frontend has very different needs to the desktop application and the backend may not be well suited to those needs. The two frontends may have completely different teams and both request changes to the backend service, at this point the backend becomes a development bottleneck.

#### Solution
Crate one backend per user interface. Fine-tune behaviour for each backend to best match the needs of the frontend environment without worrying about affecting other frontend services.

---
# References
