# Runtime analysis

## Introduction

So far, our analysis has been based on *empirical data*, which is sensitive to
- platform
- concurrent tasks
- implementation details

Messy, and doesn't help to find big-picture trends.

Ideally, we would describe the runtime behavior in a rigorous, mathematical way. Reframing the problem:

Given an algorithm that takes *input size* **n**, find a function *T(n)* such that the algorithm takes *T(n)* time.

Runtime is determined by the *number and cost of primitive operations* carried out while executing the algorithm.

## Performing runtime analysis

One approach is as follows: a **cost** is assigned to each line in the algorithm, and then the amount of times each line is evaluated is tracked. *T(n)* then returns an expression in the same units as the costs.

However, these costs are platform-dependent and make the final expression too complicated, so 

- Simplification 1: costs are dropped, and only the amount of times each line is executed matters.

Now, depending on the input, the number of times each line is executed may depend. Here the analysis can split into *average-case* and *worst-case* scenario: we will consider the latter unless otherwise noted. Then the count will be made based on the worst-case input.

## Big-O notation: our desired formalism

- Simplification 2: in the resulting expression for *T(n)*, only the leading term with dropped constants will be considered, and the **big-O** notation is used instead, which represents the bounding behavior, or **asymptotic behavior**, of *T(n)*.

Now, there are multiple bounding functions for a certain function *f*, so it will usually be implied that the used big-O notation is asymptotically tight. This refers to another formalism, big-theta, but we'll avoid that here.

Examples:
- Computing discriminant: O(1)
- Binary search: O(log n)
- Linear search: O(n)
- Heap sort: O(n log n)
- Insertion sort: O(n<sup>2</sup>)
- Matrix multiplication: O(n<sup>3</sup>)
- Brute-forcing an n-bit password: O(2<sup>n</sup>)
- Traveling salesman problem: O(n!)