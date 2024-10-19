2023-06-01
Tags: #technology #kubernetes 

Uses [[P2P]]

Small number of hosts seeding content to a network of agents running on hosts in the cluster

**Agent**
Deployed on every host
Implements Docker registry interface
Announces available content
Connects to peers to download content

**Origin**
Dedicated seeders
Stores blobs in harbour (in our case)

**Tracker**
Orchestrates all participants in the network
Tracks which peers have what content
Provides list of peers to connect for a blob

**Proxy**
Implements Docker registry interface
Uploads image layers to the origin

**Build-index**
human readable map of tags to blob digest
No consistency
Basically interface to harbour


---
# References
- Uber repo for docs
- https://www.youtube.com/watch?v=waVtYYSXkXU