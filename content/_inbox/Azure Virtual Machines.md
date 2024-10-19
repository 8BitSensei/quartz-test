2023-12-18
Tags: #cloud #azure 

Azure VMs provide Infrastructure as a Service in the form of a virtualised server and can be used in many ways. VMs are an ideal choice when you need:
- Control over the OS
- Ability to run custom software
- Custom hosting configurations

#### Scale Sets
Allows you to centrally create and manage a group of identical, load-balanced VMs. 
Scale sets allow you to centrally manage, configure, and update a large number of VMs in minutes. The number of VM instances can automatically increase or decrease in response to demand, or you can set it to scale based on a defined schedule.

#### Availability Sets
A tool for organising your VMs in such a way that ensures staggered updates and varies power and network connectivity to prevent you from losing all your VMs in a single fault.
- **Update domains**: a group of VMs that can be updated all together, your VMs will be split into multiple update domains so that updates are staggered.
- **Fault domain**: a group of VMs that share a common power source and network switch, by default your VMs will be split across three fault domains so that  a single power or network failure won't take down all your VMs

#### VM Resources
- Size (number of cores, amount of RAM)
- Storage disks (HDDs, SSDs)
- Networking (virtual network, public IP address, port configuration)


---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-azure-compute-networking-services/2-virtual-machines