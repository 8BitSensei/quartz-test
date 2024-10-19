2023-12-18
Tags: #cloud #azure 

As it's core physical infrastructure Azure has datacentres like any traditional large corporate datacentre. They're facilities with resources arranged racks, dedicated power, cooling, and networking infrastructure. These datacentres around the world are not accessible to customers, datacentres are grouped by regions or availability zones that are designed to help you achieve resiliency and reliability.

**A region is** a geographical area on the planet that contains at least one or multiple datacentres that are geographically near each other and networked together with a low-latency network. Not all services are available in all regions, certain VM sizes or storage types are also not available in certain regions.
### Availability zones
Zones are physically separate datacentres within an Azure region.  Each zone is made up of one or more datacentres equipped with independent power, cooling, and high-speed networking between them. Zones are set-up as isolation boundaries, if one goes down the others continue working. Co-locating compute, storage, networking, and data resources in a single zone and replicating to other zones helps build high-availability into an application. 

Azure services fall into one of three categories regarding their relationship to zones:
- Zonal services, services which are pinned to a specific service e.g. VM, managed disks, IP addresses
- Zone-redundant services, services which automatically replicate across zones e.g. zone-redundant storage, SQL Database
- Non-regional services, services which are available across all geographies

![[Pasted image 20231218124215.png]]

### region pairs
Most Azure Regions are paired with another region at least 300 miles away e.g. West US & East US, SE Asia & East Asia. Data and services are replicated between regions so that if one fails for some reason, (almost) everything can fail over to the back-up region. 

### sovereign groups
Azure has sovereign regions which are isolated from the wider infrastructure for legal purposes e.g. US Government regions which are operated by screened US personnel.

---
# References
