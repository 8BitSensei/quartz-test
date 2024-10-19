2023-12-18
Tags: #azure #cloud #networking 

Virtual Networks and Virtual Subnets enable resources (VMs, web apps, databases etc) to communicate with each other, with users over the internet, and with on-premise client machines.

Virtual Networks provide the following network capabilities:
- Isolation and segmentation
- Internet communication
- Communication between resources
- Communicate with on-prem resources
- Route network traffic
- Filter network traffic
- Connect virtual networks

Virtual Networks support both public and private endpoints to enable communication between external or internal resources with other internal resources.

#### Isolation and Segmentation
Virtual Networks allow you to define a private IP address using public or private IP address ranges which only exist in your virtual network and isn't internet routable. You can then divide this range into different subnets and use in-built name resolution to reach them.

#### Internet Communication
You can use a Public IP to enable incoming connections via the internet or by putting the resource behind a load balancer.

#### Communication between Azure resources
You can use Virtual Networks or Service endpoints to connect between different Azure resources.

#### Communicate with on-premise resources
Virtual networks allow you to connect your on-premise resources with each other and within Azure. There are three mechanisms to doing this:
- **Point-to-site virtual private network connections**: Connect from a computer outside your organisation back into your corporate network by initiating an encrypted VPN connection to the Azure Virtual Network.
- **Site-to-site virtual private network**: Connects your on-premise VPN to the Azure VPN gateway effectively making Azure resources appear as belonging to your network.
- **Azure ExpressRoute**: provides a dedicated private connection to Azure that doesn't travel over the internet. 

#### Route network traffic
Azure routes traffic between subnets on any virtual network and the internet, you can control routing and override behaviour as follows:
- **Route tables**: allow you to define rules about how traffic should be directed
- **Vorder Gateway Protocol (BGP)**: works with VPN Gateways, Route Server, and ExpressRoute to propagate on-premise BGP routes to Azure virtual networks

#### Filter network traffic
Virtual networks allow you to filter traffic between subnets with:
- **Network security groups**: Azure resources that can contain inbound and outbound security rules.
- **Network virtual appliances**: VMs that can carry out a particular network function such as running a firewall or or performing WAN optimisations

#### Virtual Network peering
Virtual Networks can be linked using peering, allowing those networks to directly communicate with each other over the private Microsoft backbone network, never entering the public internet. User-defined routes (UDR) control the routing between subnets within a virtual network or between virtual networks.


## Azure VPN Gateway
Azure VPN Gateway is a Gateway which is deployed in a dedicated subnet on a Virtual Network, only one can exist per Virtual Network. They enable connectivity in the following scenarios:
- site-to-site connection, e.g. on-premise datacentre to virtual network
- point-to-point connection, e.g. individual device to virtual network
- network-to-network connection, e.g. virtual network to another virtual network

All data transfer is encrypted inside a private tunnel as it crosses the internet, how they determine what traffic is encrypted is determined by the type of VPN you use, either policy based or route based, though regardless of the type, all authentication employs a pre-shared key.

**Policy based** VPN gateways specify statically the IP address of packets that should be encrypted.
**Route based** gateways have multiple IPSec tunnels and IP routing decides what tunnel a packet will be sent down.

Ways to maximise the resiliency of your VPN gateway

#### Active/standby
Deploy an Active Gateway but have a hidden Gateway in standby if the active one becomes unavailable. 

#### Active/active
You have two instances, both active and available with separate tunnels and use which ever one is available at the time.

#### ExpressRoute failover
Secure failover path for ExpressRoute connections, you can provision a VPN Gateway that uses the internet as an alternate method of connectivity if the ExpressRoute fails.

#### Zone-redundant gateways
Deploy VPN Gateways in different zones in a single geography , protecting you from zone-level failures.


---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-azure-compute-networking-services/8-virtual-network