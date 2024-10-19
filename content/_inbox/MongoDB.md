2023-08-03
Tags: #database

Created in 2007
Allows frequently accessed data to be stored alongside an application
MongoDB can be self hosted or hosted through Atlas, which has a **free** tier and provides a UI
MongoDB is an open-source, document-based [[NoSQL]] database.
Stores data in a [[JSON]]-like format
Supports high availability, scalability, and security
There is *no concept of [[database schema]]* like [[relational databases]], data is stored as **collections** and **documents**
There are no complex [[joins]] between collections like in relational database tables
Data is stored in the [[BSON]] format (Binary encoding of JSON-like documents)
Provides a default database named test

sharding?
	Sharding is **a method for distributing data across multiple machines**.
	Each shard contains a subset of the shared data, can be deployed as a replica set
	A database architecture that partitions data by key ranges and distributes the data among two or more database instances. Sharding enables horizontal scaling.

Cluser?
	A component of sharding, it has *sharded clusters* consisting of the shard, a `mongos` server, and a config server

mongos?
	Used in sharded clusters, instances route queries and write operations to shards in a shared cluster
	

Config servers?
	Config servers store metadata and configuration settings for the cluster.


##### Collections
Data stored in collections need not have a similar structure
Secondary indexes can be created to make common queries extremely fast ([[Database Index]])
##### Documents
Every document has a unique object id

##### Query API
Has a **query API** for basic read and write actions as well as complex queries and transformations
Supports geospatial queries for documents associated with locations
Aggregation pipelines, group documents together and reduce them to a single result


---
# References

- https://levelup.gitconnected.com/a-beginners-guide-to-mongodb-9a321226544
- https://www.mongodb.com/docs/manual/sharding/#:~:text=Sharding%20is%20a%20method%20for,capacity%20of%20a%20single%20server.