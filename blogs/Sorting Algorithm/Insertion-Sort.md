--- 
title: "Insertion Sort"
description: "Insertion Sort algorithm overview"
pubDate: 2026-06-17
---
# Insertion Sort

It is a simple, comparison-based sorting algorithm.

→ It is named "Insertion Sort" because it works the way you might sort a hand of playing cards: you take one unsorted card at a time and **insert** it into its correct, sorted position relative to the cards you are already holding.

→ The algorithm virtually splits the array into a sorted and an unsorted part. Values from the unsorted part are picked and placed at the correct position in the sorted part by shifting all larger elements to the right.

→ It is **stable** and **in-place.**

→ Space Complexity: O(1) (Constant Space)

## Time Complexity :

Best Case :   O( n ) 

 when the array is already sorted (the inner loop never executes a shift).

Worst Case : O( n^2 ) 

when the array is sorted in reverse order.

## Advantages:

1. Simplicity: Extremely easy to understand and implement with very low overhead.
2. Online/Adaptive: It can sort a list as it receives it (real-time data streaming) and is highly efficient for datasets that are already substantially or partially sorted.
3. Better than Bubble/Selection: In practice, it generally outperforms Bubble Sort and Selection Sort on small datasets because it avoids unnecessary swaps and has fewer comparisons in the average case.

## Disadvantages:

1. Poor Efficiency on Large Data: Like all O(n^2) algorithms, it scales terribly and is highly inefficient for large datasets compared to Merge Sort or Quick Sort.
2. Heavy Shifting: In the worst-case scenario, it requires a massive amount of array-shifting operations to make room for inserted elements.

## Questions :

not exactly uses insertion sort like we learned, but give it a try.

- 912 — Sort an Array (Medium)
- 147 — Insertion Sort List (Medium) *— A direct implementation challenge using a linked list.*
- 148 — Sort List (Medium)
- 75 — Sort Colors (Medium)
- 21 — Merge Two Sorted Lists (Easy) *— Shares the core mechanic of inserting elements into a sorted structure.*
- 283 — Move Zeroes (Easy)
- 1089 — Duplicate Zeros (Easy)
- 1200 — Minimum Absolute Difference (Easy)
- 977 — Squares of a Sorted Array (Easy)
- 169 — Majority Element (Easy)
- 315 — Count of Smaller Numbers After Self (Hard)
- 493 — Reverse Pairs (Hard)