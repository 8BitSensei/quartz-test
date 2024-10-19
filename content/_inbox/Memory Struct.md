2023-08-24
Tags: #csharp #dotNet 

Represents a contiguous region of memory, is not a ref struct so can be stored on the managed heap.

Can create a new Memory struct over a specified array: `Memory<T>(T[])`
Creates a new Memory struct over a specified number of elements of an array: `Memory<T>(T[], int32, int32)`

- They allow you to eliminate boxing and unboxing costs associated with generic collections, like List.

---
# References
