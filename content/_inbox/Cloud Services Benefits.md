2023-12-17
Tags: #cloud #azure #aws #gcp 

### High Availability
High availability is a benefit of cloud computing services, the provider ensures maximum availability, regardless of disruption or events that may occur, with up-time guarantees depending on your SLA with the provider.

##### Service Level Agreement (SLA)
Formal agreement between service provider and customer [^1], guarantees a stated level of service
Azure SLAs are represented as a percentage of the services availability (up-time)
Also includes downtime and possibly credit if the SLA is not met
Each Azure service has it's own SLA

### Scalability
Scaling is the ability to adjust the resources you use in the cloud to meet current demand. This means that you can dd more resources to better handle increased demand. And importantly if demand drops off you can reduce your resources and thereby reduce your cost. 

There are generally two varieties of scaling
##### Vertical Scaling
Is increasing the resources available to your current services i.e. increasing compute and memory to a VM

##### Horizontal Scaling
Is increasing the services that you have deployed i.e. increasing the number of VMs running

### Reliability
Reliability is the ability of a system to recover from failures and continue to function, it is also one of the pillars of the [[Microsoft Azure Well-Architected Framework]]. The cloud, being a decentralised system by design enables you to have resources deployed across many regions in the world, naturally allowing you to shift if one region experiences a failure or a single instance of a service fails. This reliability is a by product of the horizontal scaling provided by the cloud.

### Predictability

##### Performance
Performance predictability is the ability to predict the right resources needed to deliver a positive experience to your customers. Cloud concepts like [[Autoscaling]], [[load balancing|load balancer]], and high availability help support performance predictability.
##### Cost
Cost performance is the ability to predict the cous of your cloud spend. You can track your resource expenditure in real time and monitor resources to ensure you're using them in the most cost effective manner. You can even use tools like [[Total Cost of Ownership (TCO)]] or [[Pricing Calculator]] to gest estimates of your potential cloud spend.

### Governance in the Cloud
Governance, that is the ability to make sure that all your deployed resources meet corporate standards and government regulatory requirements, is made easy by the cloud. You can use [[ARM templates]] to make sure that your resources meet your standards, and cloud-based auditing helps flag resources out of compliance.  

### Manageability in the Cloud
A major benefit of the cloud is manageability options, there are two types Management *of* the cloud, and Management *in* the cloud. These are terrible names which obscure what they're talking about, the distinction between *of the cloud* and *in the cloud* is actually just *what you manage* and *how you manage*, setting these up as related categories or definitions with a subtle difference is bottom-feeder tier stupid.
##### Management *of* the cloud
Management of the cloud speaks to managing your cloud resources:
- Automatically scale resources based on need
- Deploy resources based on preconfigured templates
- Monitor health of resources and automatically replace failing resources
- Automatic alerts based on configured metrics

##### Management *in* the Cloud
Management *in* the cloud speaks to *how you're able to manage your cloud environment*, using:
- Web Portal
- CLI
- APIs
- PowerShell

---
# References

[^1]: https://learn.microsoft.com/en-gb/training/modules/describe-benefits-use-cloud-services/2-high-availability-scalability-cloud