2023-06-21
Tags: #programming #dotNet 

System in the [[Common Language Runtime]] that manages the allocation and release of memory from your application.

Allocates memory every time we create an object (on the managed heap), the GC attempts to collect (remove) objects from memory that are no longer being used by the application to reclaim memory.

##### Memory fundamentals

Each process has its own separate virtual address space
All processes on a single computer share a page file
On 32-bit computers, each process has a 2GB user-mode virtual address space
As a developer, we only work with virtual memory, never physical memory

Virtual memory can be in three states:
- **Free**: The block of memory has no references to it and is available
- **Reserved**: The block is available for use, and can't be used for any other requests, but, you can't store data on the block until it is committed
- **Committed**: The block of memory is assigned to physical storage, and you can commit data to it

Virtual address space can become 'fragmented', meaning that there are free blocks known as holes in the address space

[[Page file (memory)]]

##### GC Generations



---
# References
