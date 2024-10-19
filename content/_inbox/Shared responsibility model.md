2023-12-12
Tags: #cloud #azure #aws #gcp


The Shared responsibility model defines the responsibilities shared between the consumer and the cloud provider. In a traditional datacenter model, the consumer is also the owner, and thus responsible for all infrastructure, including: the physical space, security, maintaining servers.

In the cloud, the consumer has less responsibilities, and the provider becomes responsible for physical security, power, cooling, and network responsibility at a minimum. The consumer on the other hand is always responsible for the data and information stored in the cloud, as well as access security.

The share of responsibilities can change however, based on the context. For example, if you deployed an SQL database to the cloud, the provider would be responsible for maintaining the actual database, but the consumer is responsible for the ingested data. However, if you deployed an SWL database into a VM, you'd be responsible for the whole database including patches and updates, as well as int data ingested.

The shared responsibility model is heavily tied to the cloud service type used by the consumer, such as [[Infrastructure as a service]] (IaaS), [[Platform as a service]] (PaaS), or [[Software as a service]] (SaaS), with responsibility leaning towards provider or the consumer based on the service.


![[shared-responsibility-b3829bfe.svg]]

You’ll always be responsible for:
- The information and data stored in the cloud
- Devices that are allowed to connect to your cloud (cell phones, computers, and so on)
- The accounts and identities of the people, services, and devices within your organization

The cloud provider is always responsible for:
- The physical datacenter
- The physical network
- The physical hosts

Your service model will determine responsibility for things like:
- Operating systems
- Network controls
- Applications
- Identity and infrastructure

---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-cloud-compute/4-describe-shared-responsibility-model