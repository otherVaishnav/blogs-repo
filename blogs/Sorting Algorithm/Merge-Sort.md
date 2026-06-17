# Merge Sort

→ It is an efficient, comparison-based sorting algorithm.

→ It is named "Merge Sort" because its entire strategy revolves around the fundamental operation of **merging** two already-sorted subarrays into a single, fully sorted array.

→ The algorithm uses a **Divide and Conquer** strategy: it recursively splits the array in half until individual elements are reached, and then blends them back together in sorted order.

- Code
    
    ```java
    class MergeSort{
        static public void divide(int[] nums, int start, int end){
            // System.out.println("inside divide");
            if(start<end){
                // this is going to get to the left most node and then back-track from there. 
                // Only divide and merge if there are at least 2 elements
                int mid = start + (end-start)/2;
                divide(nums, start, mid);  
                divide(nums, mid+1, end);
                // one the left and right part are broken down to one, your start merging them. 
                merge(nums,start,mid,end);
            }
        }
        static public void merge(int[] nums,int start, int mid, int end){
            // there are 2 arrays 
            // first : from start to mid 
            // second : from mid + 1 to end. 
            // let's merge them 
            // helper is an extra array that we are taking
            int[] helper = new int[end-start+1];
            int i = start; // for first array 
            int j = mid+1; // for second array 
            int k = 0;
            // copy sorted elements into helper 
            while(i <= mid && j <= end){
                // check and swap 
                if(nums[i] > nums[j]){   
                    // j is small 
                    helper[k++] = nums[j++];
                }else{
                    // tim-sort 
                    helper[k++] = nums[i++];
                }
            }
            while(i<=mid){
                helper[k++] = nums[i++];
            }
            while(j<=end){
                helper[k++] = nums[j++];
            }
            // copy the sorted back to og array from helper. 
            k = 0; // helper is a different array, only it's length is same, to travel helper we need to start at 0.
            for(int l=start;l<=end;l++){
                nums[l] = helper[k++];
            }
            return;
        }
        public static void main(String[] args) {
            int[] nums = {3,50,1,8,10,32,2,61};
            mergeSort(nums);
            System.out.print("[");
            for(int i =0;i<nums.length;i++){
                System.out.print(nums[i] + ",");
            }
            System.out.println("]");
        }
        static public void mergeSort(int[] nums){
            System.out.println("inside mergeSort");
            divide(nums, 0, nums.length-1);
            return;
        }
    }
    ```
    
- Code *
    
    ```java
    class MergeSort {
        public static void mergeSort(int[] nums, int start, int end) {
            if (start >= end) return; // Base Case: 1 or 0 elements
            int mid = start + (end - start) / 2;
            
            mergeSort(nums, start, mid);    // Sort Left Half
            mergeSort(nums, mid + 1, end);  // Sort Right Half
            
            merge(nums, start, mid, end);   // Combine them
        }
    
        private static void merge(int[] nums, int start, int mid, int end) {
            int[] temp = new int[end - start + 1];
            int i = start;   // Pointer for left half
            int j = mid + 1; // Pointer for right half
            int k = 0;       // Pointer for temp array
    
            // Compare elements from both halves
            while (i <= mid && j <= end) {
                if (nums[i] <= nums[j]) { // '<=' ensures stability
                    temp[k++] = nums[i++];
                } else {
                    temp[k++] = nums[j++];
                }
            }
    
            // Copy any leftover elements from the left half
            while (i <= mid) {
                temp[k++] = nums[i++];
            }
    
            // Copy any leftover elements from the right half
            while (j <= end) {
                temp[k++] = nums[j++];
            }
    
            // Copy back to the original array
            for (int p = 0; p < temp.length; p++) {
                nums[start + p] = temp[p];
            }
        }
    }
    ```
    

→ **Characteristics:** 

1. It is **stable** (preserves the original order of duplicate elements), 
2. **out-of-place** (requires extra memory to hold the split arrays during merging), 
3. and **non-adaptive** (takes the same amount of time regardless of how sorted the initial input is).

→ Space Complexity: O(n) due to the temporary arrays needed during the merging phase.

## Time Complexity :

Best Case :   O( n log n ) 

because the array is always split in half and merged, regardless of its initial order.

Worst Case : O( n log n ) 

even in the absolute worst-case scenario, making it highly reliable.

## Advantages:

1. Highly Predictable: Guarantees an O(n log n) performance even on completely randomized or reverse-sorted data.
2. Excellent for Large Datasets: Scales beautifully and handles massive amounts of data much better than O(n^2) algorithms.
3. Perfect for Linked Lists: It can sort linked lists in O(1) auxiliary space, making it the preferred sorting method for sequential data structures.

## Disadvantages:

1. High Memory Overhead: Requires O(n) additional memory space, making it less ideal for memory-constrained environments or embedded systems.
2. Slower on Small Datasets: For very small arrays, the recursive overhead and extra allocations make it slower in practice than simpler algorithms like Insertion Sort.

## Questions :

not exactly uses merge sort like we learned, but give it a try.

- 912 — Sort an Array (Medium)
- 148 — Sort List (Medium) *— The textbook application of Merge Sort on a Linked List.*
- 21 — Merge Two Sorted Lists (Easy) *— Focuses entirely on the "Merge" step of the algorithm.*
- 23 — Merge k Sorted Lists (Hard)
- 88 — Merge Sorted Array (Easy)
- 315 — Count of Smaller Numbers After Self (Hard) *— Solved by counting inversions during the merge step.*
- 493 — Reverse Pairs (Hard)
- 2426 — Number of Pairs Satisfying Inequality (Hard)
- 56 — Merge Intervals (Medium)
- 147 — Insertion Sort List (Medium)