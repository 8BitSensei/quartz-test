Tags: #azure #cloud #technology #certifications

Cold start on [practice exam](https://learn.microsoft.com/en-us/credentials/certifications/exams/az-900/practice/assessment?assessment-type=practice&assessmentId=23) is 65%, pass is 80%
Second attempt with no revision is 76%
### Skills Measured

#### Describe cloud concepts (25 - 30%)

##### Cloud Computing
- [[Cloud Computing]]
- The [[Shared responsibility model]]
- [[Cloud models]], including [[Cloud models#public|public]], [[Cloud models#private|private]], and [[Cloud models#hybrid|hybrid]]
- Appropriate use cases for each cloud model
- The [[Cloud models#Consumption-based model|Consumption-based model]]
- [[Cloud pricing models]]
- [[Serverless]]

##### Benefits of using cloud services
- [[Cloud Services Benefits#High availability and scalability|High availability and scalability]] in the cloud
- [[Cloud Services Benefits#Reliability and predictability|Reliability and predictability]] in the cloud
- [[Cloud Services Benefits#Security and governance|Security and governance]] in the cloud
- [[Cloud Services Benefits#Manageability|Manageability]] in the cloud

##### Cloud service types
- [[Infrastructure as a service]] (IaaS)
- [[Platform as a service]] (PaaS)
- [[Software as a service]] (SaaS)
- Appropriate use cases for each cloud service (IaaS, PaaS, and SaaS)

#### Describe Azure architecture and services (35 - 40%)

##### Core Architectural components of Azure
- [[Azure regions]], [[Azure regions#region pairs|region pairs]], and [[Azure regions#sovereign groups|sovereign groups]]
- [[Azure regions#Availability zones|Availability zones]]
- [[Azure datacentres]]
- [[Azure resources and resource groups]]
- [[Azure Subscriptions]]
- [[Azure Management groups]]
- [[Azure, Hierachy of resources|Hierarchy of resources]] groups, subscriptions, and management groups

##### Azure compute and networking services
- [[Azure Compute types|Compute types]], including containers ([[Azure Containers]]), virtual machines, and functions ([[Azure Functions]])
- [[Virtual Machine]] options, including [[Azure Virtual Machines]], [[Azure Virtual Machines#Scale Sets|scale sets]], [[Azure Virtual Machines#Availability Sets|availability sets]], and [[Azure Virtual Desktop]]
- [[Azure Virtual Machines#resources|Resources required]] for Virtual Machines
- Application hosting options, including web apps, containers, and virtual machines
- [[Virtual Networking]], including the purpose of [[Azure virtual Networking]], [[Azure virtual Networking|Azure virtual subnets]], [[Azure virtual Networking|peering]], [[Azure DNS]], [[Azure virtual Networking|Azure VPN Gateway]], and [[Azure virtual Networking|Azure ExpressRoute]]
- public and private endpoints
##### Describe Azure storage services
- [[Azure Storage services]]
- Storage tiers
- Redundancy options
- Storage account options and storage types
- Moving files, including AzCopy, Azure Storage Explorer, and Azure File Sync
- [[Azure Data Migration options]], including Azure Migrate and Azure Data Box

##### Describe Azure identity, access, and security
- [[Azure Authentication methods]] in Azure, including [[Azure Authentication methods|single sign-on (SSO)]], [[Azure Authentication methods|multi-factor authentication (MFA)]], and [[Azure Authentication methods|passwordless]]
- External identities in Azure, including business-to-business (B2B) and business-to-customer (B2C)
- [[Azure Conditional Access]] in Microsoft Entra ID
- [[Azure role-based access control (RBAC)]]
- [[Zero Trust model]]
- The [[Defense-in-depth model]]
- [[Microsoft Defender for Cloud]]

#### Describe Azure management and governance (30 - 35%)

##### Describe cost management in Azure
- [[Factors that can affect costs in Azure]]
- Compare the [[Azure Pricing calculator]] and the [[Azure Total Cost of Ownership (TCO) Calculator]]
- Management capabilities in Azure
- The purpose of [[Azure tags|tags]]

##### Describe features and tools in Azure for governance and compliance
- [[Microsoft Purview]] in Azure
- [[Azure Policy]]
- [[Azure Resource locks]]

##### Describe features and tools for managing and deploying Azure resources
- Azure portal
- Azure Cloud Shell, including Azure Command-Line Interface (CLI) and Azure PowerShell
- [[Azure Arc]]
- Infrastructure as code (IaC)
- Azure Resource Manager (ARM) and [[ARM templates]]

##### Describe monitoring tools in Azure
- [[Azure Advisor]]
- [[Azure Service Health]]
- [[Azure Monitor]], including Log Analytics, Azure Monitor alerts, and Application Insights


---

1) What is Platform as a Service (PaaS)
2) What should you use to estimate  the monthly costs of an Azure solution using PaaS products?
	1) Azure Pricing calculator
3) What are [[Azure Cost Management]] + Billing services?
4) What two features are available by using Azure Cost Management + Billing?
	1) Create and manage Budgets + Generate historical and forecast future usage
5) What can you use to minimize the costs of the virtual machines without reducing the functionality of virtual machines?
	1) Azure Reservations
6) What are Azure Reservations?
7) What can you use to ensure that new and existing Azure resources stay in compliance with corporate standards?
	1) Azure Policy
8) What is an Azure Policy
9) What should you use as part of a deployment solution for Azure virtual machine deployments which enforces company standards on the machines?
	1) Azure Policy
10) What can you use to restrict the deployment of a virtual machine to a specific location?
	1) Azure Policy
11) What can you use to ensure that a development team can only create virtual machines of a certain size?
	1) Azure Policy
12) Which two actions can be performed by using Azure portal?
	1) Create new resources + Create Microsoft Entra user
13) What can you use to define the resources you want to provision in a declarative JSON format?
	1) Azure Resource Manager (ARM) templates
14) What is an ARM template
15) What can you use to manage servers across third party cloud platforms and on-premises environments?
	1) Azure Arc
16) What is Azure Arc?
17) What provides recommendations to reduce the cost of Azure resources?
	1) Azure Advisor
18) What is Azure Advisor?
19) Which Azure service evaluates Azure resources and makes recommendations to help improve reliability, security, performance, and cost reduction?
	1) Azure Advisor
20) What tool will notify you when there are new recommendations for reducing Azure costs?
	1) Azure Advisor
21) What should you proactively review and act on to avoid service interruptions, such as service retirements and breaking changes?
	1) Health advisories
22) What service produces health advisories?
23) Which Azure service can generate an alert if virtual machine utilization is over 80% for five minutes?
	1) Azure Monitor
24) What is Azure Monitor?
25) What can you apply to an Azure virtual machine to ensure that users cannot change or delete the resource?
	1) a lock
26) Which feature in the Microsoft Purview governance portal should you use to manage access to data sources and datasets?
	1) Data Policy
27) What are physically separate datacentres within an Azure Region?
	1) Availability zones
28) What are Availability Zones?
29) Which two components are created in an Azure subscription?
	1)  resource groups + resources
30) What is an Azure Storage account named storage001 an example of?
	1) a resource
31) For which resource does Azure generate separate billing reports and invoices by default?
	1) subscriptions
32) Which resource can you use to manage access, policies, and compliance across multiple subscriptions?
	1) management groups
33) What is the deployment and management service for Azure?
	1) Azure Resource Manager (ARM)
34) Name two Azure resources can make use of availability zones?
	1) Azure SQL databases + Virtual Machines
35) Which Azure compute service can you use to deploy and manage a set of identical virtual machines?
	1) Azure Virtual Machine Scale Sets
36) What scenario might a VPN Gateway be used for?
	1) connecting an on-premises datacenter to an Azure virtual network
37) How would you allow resources on two different Azure virtual networks to communicate with each other?
	1) peering
38) What two services can you use to establish network connectivity between an on-premises network and Azure resources?
	1) Azure VPN Gateway + ExpressRoute
39) What is a VPN Gateway
40) What is ExpressRoute
41) What can you use to provide Mac and Android users with access to a Windows environment that will run Windows-based applications?
	1) Azure Virtual Desktop
42) Which storage service should you use to store thousands of files containing text and images?
	1) Azure Blob storage
43) What is Azure Blob storage
44) What is Azure Disk Storage
45) What is Azure Queue Storage
46) What is Azure Table storage
47) What two protocols can be used to access Azure file shares?
	1) Network File System (NFS) + Server Message Block (SMB)
48) What enables a user to sign in one time and use that credential to access multiple resources and applications from different providers?
	1) Single sign-on (SSO)
49) What is single sign-on (SSO)
50) What can you use to allow a user to manage all the resources in a resource group?
	1) Azure role-based access control (RBAC)
51) What Microsoft Entra feature can you use to configure security authentication that requires users to use their mobile phone to sign in?
	1) multi-factor authentication (MFA)
52) Which Microsoft Entra feature can you use to ensure that users can only access Microsoft Office 365 applications from approved client applications?
	1) Conditional Access
53) What can you use to ensure that users authenticate by using multi-factor authentication (MFA) when they attempt to sign in from a specific location?
	1) Conditional Access
54) What two attributes are characteristics of the [[Cloud models#Private cloud|private cloud]] deployment model?
	1) Hardware must be purchased + The company has complete control over physical resources and security.
55) What are two basic services provided by all cloud providers?
	1) compute + storage
56) What are two characteristics of the [[Cloud models#Public cloud|public cloud]] deployment model?
	1) Servers and storage are owned and operated by a third-party cloud service provider + Services are offered over the internet and are available to anyone who wants to purchase them
57) What are two characteristics of a consumption-based model?
	1) no upfront costs + the ability to stop paying for resources that are no longer used
58) What two characteristics are common advantages of cloud computing?
	1) geo-distribution + high availability
59) Which cloud deployment model are you using if you have servers physically located at your organization’s on-site datacenter, and you migrate a few of the servers to the cloud?
	1) [[Cloud models#Hybrid cloud|hybrid cloud]]
60) What is high availability in a public cloud environment dependent on?
	1) the service-level agreement (SLA) that you choose
61) What is a service-level agreement (SLA)
62) What is the term for automatically scaling an application to ensure that the application has the resources needed to meet customer demands
	1) elasticity
63) Which cloud service model provides you with the most control over the hardware that runs applications?
	1) infrastructure as a service (IaaS)
64) In a platform as a service (PaaS) model, what two components are the responsibility of the cloud service provider?
	1) operating system + physical network
65) Which cloud service model is used by Microsoft Office 365?
	1) software as a service (SaaS)
66) Which cloud service model is used by Azure SQL Database?
	1) platform as a service (PaaS)
67) What uses the infrastructure as a service (IaaS) cloud service model?
	1) Azure virtual machines


---
# References

https://learn.microsoft.com/en-us/credentials/certifications/azure-fundamentals/