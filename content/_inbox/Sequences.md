2024-01-12
Tags: #mathematics #CompSci 


##### Arithmetic Sequences
An arithmetic sequence is a sequence of numbers, where the difference between each number is a constant value. For example `n1 - n0` should be equal to `n2 - n1` e.g. `{1, 3, 5}` where the difference is `2` between each number.

We can quickly calculate the sum of an arithmetic sequence with the following equation:
`(first_element + last_element) * number_of_elements /2`
Given the above example we can calculate the sum `(1 + 5) * 3 / 2 = 9`.
##### Geometric Sequences
A geometric sequence is a sequence of numbers, where the *ratio* between them is constant. The ratio can be found by dividing a number by it's predecessor e.g. `n1 / n0`, so given a sequence `{1, 3, 9, 27, 81}` we can see that `3/1 = 3` and that `81/27 = 3`.

We can quickly calculate the sum of a geometric sequence with the following equation:
`first_element * (1 - ratio^number_of_elements) / (1 - ratio)`
Given the above example we can calculate the sum `1 * (1 - 3^5) / (1 - 3) = 1 * -242 / -2 = 1 * 121 = 121 `


---
# References
