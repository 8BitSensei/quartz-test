2024-01-11
Tags: #CompSci #mathematics 

To calculate the base 10 value of a number in a given base, we just need to follow the following pattern:

- Working through each digit from the right
	- If the digit is 0 skip
	- Else, take the base to the power of the index (from the right) and multiply it by the digit
- Sum the values

For example, if we take the base 10 number 123, we can do the following maths:
3\*(10^0) + 2\*(10^1) + 1\*(10^2) = 3 + 20 + 100 = 123

This is extra simple in binary, as we don't even have to do multiplication (we would always be multiplying by one anyway).

1110 = 8 + 4 + 2 = 14

---
# References
