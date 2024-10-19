2024-01-11
Tags:

##### Set
A set is a collection of *distinct* elements, where the order of the item doesn't matter. The set is the *'parent'* of the permutations and combinations, these may be identical to the set, but are *''drawn from* the set i.e. the set defines all possible elements that could appear in one or the other.

##### Permutation
A permutation is a specific arrangement or ordering of elements of a set, where, the order matters. The order defines the distinctiveness of a specific permutation.

##### Combinations
In a combination, the order *does not matter*. What makes a specific combination distinct, is the elements from the set, not their ordering.

##### Calculating the total Permutations and Combinations
To calculate the number of possible permutations, do the following:

```
n = total elements in the set
r = total elements in a permutation or combination
total permutations = n! / (n - r)!
total combinations = total permutatons / r!
```

If the total elements in the set and the total number in the permutations and combinations are equal, then the total number of permutations will be `n!` and the total number of combinations will be `1`.

The number of possible subsets of a set can be worked out as the number of possible distinct elements to the power of the number of elements in a subset, so:

```
given set {a,b,c}
total possible subsets is 3^3 = 27
or if we limit the subsets to a length of 2, 3^2 = 9
```

---
# References
