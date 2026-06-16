# Selection Sort

It is a simple, comparison-based sorting algorithm.

→ It is named "Selection Sort" because it repeatedly **selects** the smallest (or largest, depending on sorting order) element from the unsorted portion of the array and swaps it into its correct place.

→ The algorithm divides the array into a sorted (left) and unsorted (right) region, linearly scans the unsorted region for the absolute minimum value, and executes exactly one swap per pass to expand the sorted boundary.

→ **Characteristics :** 

1. It is **unstable** (long-distance swaps can easily disrupt the original relative order of duplicate elements), 
2. **in-place** (requires zero extra memory allocations), and 
3. **non-adaptive** (it cannot see if an array is already sorted and always performs the exact same number of comparisons).

Space Complexity: O (1) (Constant Space)

### Time Complexity :

Best Case :   O( n^2 ) 

because the inner loop must always scan the entire remaining unsorted region to guarantee it found the true minimum.

Worst Case : O( n^2 ) 

because the number of comparisons remains completely fixed regardless of the initial arrangement of data.

### Advantages:

Minimal Memory Writes: It performs a maximum of $n - 1$ swaps. This makes it highly efficient for legacy or specialized hardware architectures where writing to memory is significantly slower or more costly than reading from it.
No Extra Storage: Operates completely in-place, meaning its memory footprint does not grow with the size of the dataset.
Predictable Performance: Because it is non-adaptive, its execution behavior and step count are entirely uniform across all data configurations.

### Disadvantages:

Poor Efficiency on Large Data: Sharing an $O(n^2)$ time complexity makes it drastically inefficient for large datasets compared to algorithms like Quick Sort or Merge Sort.
Unstable: Cannot maintain the relative positioning of identical data blocks due to its rigid, long-distance swapping mechanics.
Blind Execution: Lacks any early-exit capabilities, meaning it will spend the exact same amount of time processing a perfectly sorted array as it would a completely reversed one.
Questions :
 not exactly uses selection sort like we learned, but give it a try.
912 — Sort an Array (Medium)
643 — Maximum Average Subarray I (Easy)
744 — Find Smallest Letter Greater Than Target (Easy)
153 — Find Minimum in Rotated Sorted Array (Medium)
215 — Kth Largest Element in an Array (Medium)
973 — K Closest Points to Origin (Medium)
268 — Missing Number (Easy)
765 — Couples Holding Hands (Hard)
1637 — Widest Vertical Area Between Two Points Containing No Points (Easy)
1337 — The K Weakest Rows in a Matrix (Easy)
451 — Sort Characters By Frequency (Medium)
905 — Sort Array By Parity (Easy)
493 — Reverse Pairs (Hard)