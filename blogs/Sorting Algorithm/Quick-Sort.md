# Quick Sort

→ It is a highly efficient, comparison-based sorting algorithm.

→ It is named "Quick Sort" because, in practice, it is typically faster than other O(n log n) algorithms (like Merge Sort) due to its tight, cache-friendly inner loops.

→ The algorithm uses a **Divide and Conquer** strategy: it picks an element as a **pivot** and partitions the array around it, moving all smaller elements to its left and all larger elements to its right, then recursively sorts the sub-arrays.

- Code
    
    ```java
    class QuickSort{
        static public void quickSort(int[] nums,int start,int end){
            if(end-start < 1) return;
            // select a pivot 
            int pivot = nums[start + (end-start)/2];
            // place all small elements on left and bigger on right 
            int left = start;
            int right = end;
            while (left <= right) {
                // left need to search for element greater than or equal to pivot.
                while(nums[left] < pivot) left++;
                while(nums[right] > pivot) right--;
                // swap
                if(left<=right){
                    int t = nums[left];
                    nums[left] = nums[right];
                    nums[right] = t;
                    left++;
                    right--;
                }
            }
            // do it recursively 
            // left unsorted part
            // right unsorted part
            System.out.print("start : " + start);
            System.out.print(" left : " + left);
            System.out.print(" Right : " + right);
            System.out.print(" end : " + end + "\n");
            printArray(nums);
            System.err.println("\n---------------");
            quickSort(nums,start,right);
            quickSort(nums,left, end);
            return;
        }
        public static void main(String[] args) {
            int[] nums = {3,50,1,10,10,-32,2,61,0,-10,-1};
            quickSort(nums,0,nums.length-1);
            printArray(nums);
        }
        static void printArray(int[] nums){
            System.out.print(" [");
            for(int i =0;i<nums.length;i++){
                System.out.print(nums[i] + ",");
            }
            System.out.println("]");
        }
    }
    ```
    
- Code*
    
    ```java
    static public void quickSort(int[] nums, int start, int end) {
        if (start >= end) return; // Base Case
        int pivot = nums[start + (end - start) / 2];
        int left = start, right = end;
        while (left <= right) {
            while (nums[left] < pivot) left++;   // Find element >= pivot
            while (nums[right] > pivot) right--; // Find element <= pivot
            
            if (left <= right) {
                int t = nums[left];
                nums[left] = nums[right];
                nums[right] = t;
                left++;
                right--;
            }
        }
        
        quickSort(nums, start, right); // Recurse Left Half
        quickSort(nums, left, end);    // Recurse Right Half
    }
    ```
    

→ **Characteristics:** 

1. It is **unstable** (swaps can disrupt the original relative order of duplicate elements), 
2. **in-place** (operates directly within the original array), 
3. and **highly adaptive** to pivot selection strategies.

→ Space Complexity: O(log n) on average due to the recursive call stack.

## Time Complexity :

Best Case :   O( n log n ) 

occurs when the pivot consistently splits the array into two roughly equal halves.

Worst Case : O( n^2 ) 

occurs when the pivot consistently picks the smallest or largest element (e.g., sorting an already sorted array using the first element as the pivot).

## Advantages:

1. Cache Friendly: It exhibits excellent locality of reference, making it blazing fast on modern computer architectures.
2. No Extra Storage: Unlike Merge Sort, it operates in-place and does not require $O(n)$ auxiliary arrays.
3. Highly Customizable: Performance can be easily optimized against worst-case scenarios using randomized pivot selection (Randomized Quick Sort).

## Disadvantages:

1. Unstable: Cannot guarantee that identical elements will maintain their original relative positioning.
2. Worst-Case Vulnerability: A poor choice of pivot on structured data can degrade its performance to a sluggish O(n^2).
3. Recursive Overhead: Highly dependent on stack memory; a deep recursive tree on bad inputs risks causing a stack overflow.

## Questions :

not exactly uses quick sort like we learned, but give it a try.

- 912 — Sort an Array (Medium)
- 75 — Sort Colors (Medium) *— Uses the Dutch National Flag algorithm, which is a 3-way Quick Sort partition.*
- 215 — Kth Largest Element in an Array (Medium) *— Uses QuickSelect, an optimization derived directly from Quick Sort.*
- 973 — K Closest Points to Origin (Medium)
- 169 — Majority Element (Easy)
- 506 — Relative Ranks (Easy)
- 283 — Move Zeroes (Easy)
- 905 — Sort Array By Parity (Easy)
- 148 — Sort List (Medium)
- 179 — Largest Number (Medium)