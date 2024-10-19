2024-01-16
Tags: #algorithm #CompSci 

```
- Given a sorted array of increasing integers and a target
- Select the middle point of the array
- If the value in the middle is the target, return
- Else if the value in the middle is greater than your target throw away it and everything to the right
- Else if the value in the middle is lesser than your target throw away it and everything to the left
- Find the new middle point and repeat
```

Basic features:
- Takes an ordered array
- Has two 'arms', the left arm and the right arm, which shrink with the search radius
- A feasibility function, that allows us to decide whether the given index is a valid target or not (this is the binary choice of binary search)
- Logic which allows us to deduce whether we should restrict our search to the left or right of the given index (this depends on how the array is sorted)

There are two key scenarios in which binary search is deployed

#### Vanilla Binary Search
In the vanilla binary search, we are looking for a single target with a simple feasibility function. For example, we would use this if I want to find a unique name in an alphabetised array `{'Alex', 'Billy', 'Charlie', ...}`. We would simply check the mid point, if it is not our target decide whether it is to the right or the left of our target e.g. given the target `Billy` and a mid point of `Charlie`, we know that our target must be to the left, so reduce the search radius to `0 - (mid point - 1)`, and start again. If our target is to the left, invert that (`mid point + 1`) and repeat.

#### Boundary Binary Search
A boundary binary search is a bit more interesting, and can be applied to a wide range of problems. In this case, we are looking for the boundary in an array, for example, given the array `{0, 0, 0, 1, 1}`, we want to find the first instance of `1`, that is the boundary point. To do this we adjust how we manipulate our search radius, if we find a `1` at our mid point, we know that that *could be the boundary*, but we're not certain, so we record it as a *possible answer* and throw it and everything to the right away. If we find a `0` at our mid point, throw it away and everything to the left, eventually we will find the furthest right `1`.
#### Implicitly Sorted arrays
Not every problem you encounter will be as explicit as 'find the target', or find the first `1`. In fact, most problems will represent some kind of implicit sorting, that is where they are not obviously sorted, but we can deduce a pattern that allows us to apply binary sort.

Take two examples:
`{5, 6, 10, 1, 2, 4}` at first glance, this array isn't sorted, it's a mess! But, we can see there is a boundary, where the increasing-order drops and then starts again, which means we could apply boundary binary search if we wanted to find the smallest, or the largest integer. We could use a feasibility function such that `f(x) => arr[x] <= arr[arr.Count - 1]` giving us the following binary boundary `{F, F, F, T, T, T}`.

`{0, 1, 2, 3, 2, 1, 0}` in this case, we we can see that there is an order where the integers climb to `3` before falling, we can use a feasibility function that looks to see if we are descending yet e.g. `f(x) => arr[x] > arr[x + 1]` giving us the following binary boundary `{F, F, F, T, T, T, T}`.

The key thing to look out for when accessing a problem, is once the data supplied is laid out, can you come up with a feasibility function, which allows us to find a boundary, and is that boundary what we are looking for?

---
# References
