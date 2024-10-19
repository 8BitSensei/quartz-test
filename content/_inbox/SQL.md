2023-12-07
Tags: #database #sql


#### RDBMS (Relational Database Management System)
An RDBMS is in fact a type of DBMS, it's unique quality being that it has relational data. But, to begin with a plain DBMS has four important qualities:
- **Data Definition** - define the data being tracked
- **Data Manipulation** - add, update, or remove data
- **Data Retrieval** - extract and report on the data in the db
- **Administration** - defining users on the system, security, monitoring, system administration

**DDL** - Data Definition Language (e.g. CREATE TABLE), used to define our tables which enforces rules on our data.

**DML** - Data Manipulation Language e.g. INSERT, UPDAT, DELETE; rules for our manipulation is enforced by the DDL

SQL is not a DDL, but it contains DDL commands, as well as DML (Data Manipulation Language) commands

##### ACID - Atomicity, Consistency, Isolation, and Durability

**Atomicity** - Entire transaction must finish, or revert the database to an old state

**Consistency** - Data integrity constraints must be followed, helps ensure the data is in a correct state

**Isolation** - Concurrent execution safe eg. operations on the same data must happen episodically, this is controlled by the RDBMS through concurrency control, there are multiple types of concurrency control such as optimistic vs pessimistic

**Durability** - Committed transactions must be written to non-volatile memory
#### History

Dr Codd first paper about Relational Data models

Early form SQL known as SEQUEL (Structured English Query Language) starts appearing in the early 70s, became SQL due to trademark issues

Company called Relational Software started working on a SQL based RDBMS for the US government, later they would change their name to Oracle

1979 they release their first commercially available RDBMS

In 1986 DARPA starts working on the POSTGRES project which would give us the PostgresSQL database

In 1987 Microsoft released their first SQL server

In 1995 a Swedish company released MySQL for internal use

In 2010 Oracle buys the then current owner of MySQL

In 2012 one of the creators of MySQL created a fork called MariaDB out of concern for the future of MySQL

ANSI (American National Standards Institute) has published a series of standards for the SQL language

All major RDBMS' support ANSI standards to varying degrees

Key points:
- SQL and the idea of RDBMS are closely connected, emerging around the same time, before any commercial RDBMS became widely available
- Each RDBMS has it's own version of SQL and tries to keep to a shared standard defined by ANSI, but their can still be quirks and small differences
	- Important to ask what kind of RDBMS they are using as that affects the SQL we should know



---
# References
