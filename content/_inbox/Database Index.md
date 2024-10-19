2023-08-03
Tags: #database 

An index is a data structure used in databases that provides faster access to data.

An index usually consists of two elements, a search key, and the data pointer.

The key stores the value you want to search for and the pointer points to the block where the data resides.

Indexes allow us to split our data into blocks based on the key property e.g. entries where id < 40, so that the database knows what block the data we want will be in

---
# References

https://www.mongodb.com/basics/database-index#:~:text=Each%20collection%20in%20MongoDB%20automatically,index%20will%20come%20in%20handy.