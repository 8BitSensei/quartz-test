---
date: 2023-11-02
draft: false
tags:
  - programming
  - algorithm
---
The Two Sum problem, is a problem where in we are given an array of integers, and a target integer. We must find what two integers in the array will add up to the target integer (if at all).

The naïve approach to solving this problem is to:
1. Loop through the given array of integers
	1. For each integer calculate it's compliment (target - current integer)
	2. Given the compliment, loop through the array again
		1. For each integer, if it matches the compliment return the index of the first and second loop
		2. Else continue
	3. If the compliment is found loop again
2. If no two numbers that achieve the target are found, return null

This is a fairly slow and clumsy approach. 

In most languages, a [[Hash Table]] data structure provides near constant time lookup speed, this means we can search it for a compliment much more quickly than looping through the array again, at the cost of added memory. In C#, the Dictionary class is a Hash Table we can easily use.

Do the following:
1. Create an empty Dictionary class  
2. Loop through the given array of integers
	1. Calculate the complement (target - current integer)
	2. Search the Dictionary for the complement
	3. If not found
		1. Add the current integer to the Dictionary
	4. Else return the index of the outer loop and the index of the complement in the dictionary
3. Return null if no pair found

The worse case for this algorithm is if the two matching numbers that add up to our target are at opposite ends of the array, as we will have to loop over the entire array before we find it.

##### Important points

- Hash tables are quick for retrieval if you know what you are looking for
- Loop as little as possible

---
# References

https://leetcode.com/problems/two-sum/editorial/