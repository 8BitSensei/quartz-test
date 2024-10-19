2023-11-02
Tags: #programming #algorithm 

Given two [[Linked List]]s representing two non-negative integers (each node represents a single digit in the integer), stored in reverse order, add the two numbers together and return it as a linked list. Assuming the two numbers do not contain any leading zero.

e.g. Given the list \[(2)->(4)->(3)] (342) and \[(5)->(6)->(4)] (465) add them together and return the Linked List \[(7)->(0)->(8)] (807)

To do this, we need to add every corresponding digit, so adding 4 + 6, and we need to keep track of any carry , so in the above example we need to carry one and add it to the next addition:

2 + 5 = 7
4 + 6 = 10, so we represent that as 0 carry 1
3 +4 (+ 1) = 8

Returning the result as \[(7)->(0)->(8)]

To solve this problem, we can:

1. Check that the provided nodes are not null and that carry is 0, if so return
2. Add the value of l1, l2, and carry, defaulting to 0 if they are null
3. Calculate the carry by dividing the total by 10 (12/10 = 1), remember this is in reverse order
4. Create a new ListNode with the value of total modulo 10 ( 12%10 = 2), and the next node being a recursive call to this same method 

#### Points to remember
- Recursion is important, when repeating calculations we can call the method from within the method
- Remember that we are working in reverse order, this is easy to lose track of



---
# References
