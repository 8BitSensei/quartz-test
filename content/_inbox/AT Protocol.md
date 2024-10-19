2023-09-26
Tags: #networking #protocol 

#### Identity
Users identified by [[Domain Names]]
These domain names map to [[cryptographic URL]]s

#### Data repositories
Data is exchanged in [[signed data repositories]]
Collections of records which include posts, comments, likes, follows, media, blobs, etc

#### Federation
AT Protocol syncs the repositories in a federated networking model.
provides a convenient to use and reliably available network.
Repository data is synced between servers over standard web tech HTTP and WebSockets.

Three core services in our network are **[[Personal Data Servers (PDS)]]**, **[[Big Graph Services (BGS)]]**, and **[[App Views]]**.

Low-level primitives that can get stacked together differently are the **repositories**, **lexicons**, and **DIDs**.

#### Interoperation
A global schemas network called [[Lexicon]] is used to unify the names and behaviours of the calls across the servers.

Servers implement "lexicons" to support feature sets, including the core [[ATP Lexicon]] for syncing user repositories and the [[Bsky Lexicon]] to provide basic social behaviours.

AT protocol does not exchange documents like the web, it exchanges schematic and semantic information, this is to enable software from different organisations to understand each others' data. Gives freedom to produce user interfaces independently of the servers removes the need to exchange rendering code while browsing content.

#### Achieving Scale
PDSs host *your* data, distribute it, manage *your* identity, and orchestrate requests to other services to give you *your* views. 

BGSs handle all of your events like retrieving large-scale metrics (likes, reposts, followers), content discovery, and user search.

#### Algorithmic choice
users are free to select their aggregators.
Feeds, App views, and search indicies can be provided by independent third parties, requests are routed by the PDS based on user configuration.

#### Account Portability
A PDS may fail at any time, users can migrate  their account to a new PDS without the servers involvement.

User data is stored in [[signed data repositories]] and verified by [[DID]]s
The repos are like Git repos but for database records, and DIDs are registries of user certificates, similar to the TLS certificate system. Similar to TLS in some ways. Expected to be secure, reliable and independent of PDSs.

Each DID document publishes two public keys, a *signing key* and a *recovery key*. 
The signing key is entrusted to the PDS so that it can manage the users data, the recovery key is saved by the user, this makes it possible for the user to update their account to a new PDS without the original host's help.

#### Speech and Reach
Two layers, the permisive speech layer, and the reach layer which is post-indexing and aggregation, which is controlled by the user.


![[Pasted image 20230926153058.png]]

---
# References
