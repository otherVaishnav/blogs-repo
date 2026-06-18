--- 
title: "Jump Search (or Block Search)"
description: "Jump Search Algorithm and Implementation"
pubDate: 2026-06-17
---
# Jump Search (or Block Search)

→ for searching sorted arrays. 

→ It sits right between Linear Search and Binary Search in terms of performance and strategy.

→ Instead of checking elements one-by-one or splitting the array down the middle, it checks fewer elements by skipping ahead by fixed steps (or blocks).

**3. How It Works (Step-by-Step)**
→ Search for target value 26 in an array of 16 elements ( n=16, so our jump size m = sqrt{16} = 4 ).
  [ 0, 1, 4, 9, 11, 15, 22, 26, 31, 35, 40, 45, 52, 57, 60, 66 ] 
• **Jump 1 (Index 0):** Value is 0. 0 < 26 , keep jumping.
• **Jump 2 (Index 4):** Value is 11.  11 < 26, keep jumping.
• **Jump 3 (Index 8):** Value is 31. Stop! 31 > 26 . We overshot.
• **Define Boundaries:** The target must be somewhere between our last known position (Index 4) and our current position (Index 8).
• **Linear Crawl:** Walk forward linearly starting from Index 4:
    ◦ Index 5: 15 ( ≠ 26 )
    ◦ Index 6: 22 ( ≠ 26 )
    ◦ Index 7: 26 ( found **!** Return index 7 )

- Code
    
    ```java
    public class JumpSearch {
        public static int jumpSearch(int[] arr, int target) {
            int n = arr.length;
            if (n == 0) return -1;
    
            // Calculate optimal block size
            int step = (int) Math.floor(Math.sqrt(n));
            int prev = 0;
    
            // Phase 1: Jump through blocks
            // Loop runs while the end of the current block is still smaller than the target
            while (arr[Math.min(step, n) - 1] < target) {
                prev = step;
                step += (int) Math.floor(Math.sqrt(n));
                
                // If we've jumped completely out of the array boundaries
                if (prev >= n) {
                    return -1;
                }
            }
    
            // Phase 2: Linear Search within the identified block
            while (arr[prev] < target) {
                prev++;
    
                // If we hit the next block boundary or run out of the array entirely
                if (prev == Math.min(step, n)) {
                    return -1;
                }
            }
    
            // Phase 3: Confirm if the element matches
            if (arr[prev] == target) {
                return prev;
            }
    
            return -1; // Target not found
        }
    
        public static void main(String[] args) {
            int[] sortedNumbers = {0, 1, 4, 9, 11, 15, 22, 26, 31, 35, 40, 45, 52, 57, 60, 66};
            int target = 26;
    
            int result = jumpSearch(sortedNumbers, target);
            System.out.println("Element found at index: " + result); // Output: 7
        }
    }
    ```