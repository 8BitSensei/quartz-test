2023-07-19
Tags: #networking #technology 


##### Types of Network

[[LAN]] (Local Area Network) connects computers across a single location
[[WAN]] (Wide Area Network) connects computers across different locations
[[VPN (Virtual Private Network)]] a secure, encrypted channel which connects two endpoints

##### Network Infrastructure

**Nodes** are physical devices within networks which can can create, receive, or send data (e.g. computers, printers, switched)
**Routers*** link different networks together, forwarding data packets on to the correct network, using IPs to determine the location
**Switches** forward data packets to network devices within the same network, they use MAC to determine the destination

##### Network Topology

**[[Bus (topology)]]** each device is connected to a single cable, strength of the signal weakens over distance so nearness between nodes is required
[[Ring (topology)]] each device is connected to two neighbours, creating a ring
[[Mesh (topology)]] each device connects to all other devices, robust but requires a lot of overhead
[[Star (topology)]] each device connects to a centralised switch which can be linked together, commonly used as it is robust and scalable.

##### Other Tools

**[[Data packets]]** or **Datagrams**, are packets of data sent between devices consisting of raw data and a header, the header includes addresses of the sender and recipient.
[[Ports]] are logical channels which allow data to be routed to a specific application or service within a host. They are identified by a unique number, and a combination of IP and Port specifies a particular service on a particular host.
[[MAC (Media Access Control)]] addresses are unique identifiers assigned to every device during manufacturing


##### Communication Protocols

[[TCP (Transmission Control Protocol)]] chunks data into packets which can sent across an IP-based network
[[IP (Internet Protocol)]] is responsible for assigning sender and destination addresses to to the header of a data packet
[[UDP (User Datagram Protocol)]] is used for establishing low-latency and loss-toleration in communications between applications
[[HTTP (Hypertext Transfer Protocol)]] uses TCP/IP to deliver webpage content from a server browser
[[FTP (File Transfer Protocol)]] is used to deliver files between computers on a network

##### Security Protocols

[[SSL (Secure Socket Layer)]] creates an encrypted connection between a computer and the server on the internet
[[TLS (Transfer Layer Security)]] is the more robust successor to SSL
[[HTTPS (Hypertext Transfer Protocol Secure)]] modifies HTTP to use TSL and encrypt the connection between the web browser and a server
[[SSH (Secure Shell)]] provides an encrypted connection between computer and a server

##### The Internet Protocol Suite

Otherwise knows as TCP/IP, this is a framework for organising the set of communication protocols used in the internet and similar networks according to function criteria. It has 4 layers with corresponding protocols:

| Layer             | Protocols          |
| ----------------- | ------------------ |
| Application Layer | HTTP, TLS, DNS     |
| Transport Layer   | TCP, UDP           |
| Network Layer     | IP (v4, v6)        |
| Link Layer        | Ethernet, Wireless |

The **Application Layer** defines how network devices create and share data with other applications
The **Transport Layer** performs host-to-host communication
The **Network Layer** is responsible for exchanging datagrams across networks
The **Link Layer** contains the networking methods which hosts use to communicate, it is the physical mechanism for sending digital data


---
# References

- https://medium.com/@softwaresisterz/networking-101-the-basics-of-computer-networks-and-the-internet-8cf82011c656
- https://www.ibm.com/topics/networking