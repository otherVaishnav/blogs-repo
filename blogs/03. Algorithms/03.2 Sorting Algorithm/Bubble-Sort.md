--- 
title: "Bubble Sort"
description: "Bubble Sort algorithm overview and implementation"
pubDate: 2026-06-17
---
# Bubble Sort

→ comparison-based sorting algorithm. 

→ . It is named "Bubble Sort" because with each complete pass through the list, the largest unsorted element "bubbles up" to its correct position at the end of the list, much like bubbles rising to the surface of water.

→ You repeatedly step through the list, compare adjacent elements, and swap them if they are in the wrong order. This process is repeated until the entire list is sorted.

**→ it is stable and in-place.** 

→ Space Complexity: O(1) (Constant Space)

### Time Complexity :

Best Case :   O( n^2 ) or   O ( n ) in case of early exit.

Worst Case : O( n^2 ) 

**Advantages:**

1. **Simplicity:** Extremely easy to understand, implement, and debug.

2. **No Extra Memory:** Ideal for memory-constrained systems since its space complexity is O(1).

3. **Detects Sorted Arrays:** It can gracefully exit early on an already-sorted array, making it highly efficient for checking if a list is sorted.

**Disadvantages:**

1. **Poor Efficiency:** An O(n^2) time complexity makes it drastically inefficient for large datasets compared to algorithms like Quick Sort, Merge Sort, or Heap Sort (O(n log n)).

2. **Excessive Writing:** It performs significantly more swap operations (write operations) than alternative basic algorithms like **Selection Sort**.
****

## Questions :

#### ** not exactly uses bubble sort like we learned, but give it a try.

1. 912 — Sort an Array (Medium)
2. 75 — Sort Colors (Medium)
3. 179 — Largest Number (Medium)
4. 2164 — Sort Even and Odd Indices Independently (Easy)

---

1. 1464 — Maximum Product of Two Elements in an Array (Easy)
2. 283 — Move Zeroes (Easy)
3. 905 — Sort Array By Parity (Easy)
4. 665 — Non-decreasing Array (Medium)
5. 1534 — Count Good Triplets (Easy)
6. 1869 — Longer Contiguous Segments of Ones than Zeroes (Easy)

---

1. 2426 — Number of Pairs Satisfying Inequality (Hard) 
2. 315 — Count of Smaller Numbers After Self (Hard)