# Binary Search

→ only works on sorted data. 

Binary search maintains three pointer indices to track the current search window:
low :  The start index of the current search space.
high : The end index of the current search space.
mid : The middle index of the current search space. 

calculated as : 

```java
     			      ( end - start ) 
mid = start +  -----------------
										  2 
```

### Time complexity :

**Best-Case Complexity: O(1)**

→ Target is directly at the first midpoint check.

**Worst-Case & Average Complexity: O( log (N) )**

→ The search window shrinks exponentially by dividing by 2 each iteration.

### Steps :

1. Divide the search space into two halves by **finding the middle index "mid"**.
2. Compare the middle of the search space with the **key**.
3. If the **key** is found at middle, the process is terminated.
4. If the **key** is not found at middle, choose which half will be used as the next search space.
    
    → If the **key** is smaller than the middle, then the **left** side is used for next search. 
    
    → If the **key** is larger than the middle, then the **right** side is used for next search.
    
5. This process is continued until the **key** is found or the total search space is exhausted.

### **How to Implement Binary Search?**

It can be implemented in the following two ways

1. Iterative Binary Search Algorithm
2. Recursive Binary Search Algorithm

- Code
    
    ```java
    // iterative approach ( better , no stack overhead ).
    public int binarySearch(int[] nums, int target){
    		int left = 0;
    		int right = nums.length - 1;
    		while(left <= right){
    				int mid = left + ( right - left ) / 2;
    				if(target == nums[mid]){
    						return mid;
    				}else if(target > nums[mid]){
    						// target is on right side. 
    						// move the left to mid
    						left = mid + 1;
    				}else{
    						// else it must be on the left side
    						right = mid - 1;
    				}
    		}
    		
    		return -1;
    }
    
    //-----------------------------------------------------
    // recursive approach 
    public int binarySearch(int[] nums, int target){ 
    		return recursiveBinary(nums, target, 0 , nums.length - 1);
    }
    
    public int recursiveBinary(int[] nums, int target, int left , int right){
    		if(left  > right) return -1;
    		int mid = left + ( right - left ) / 2;
    		if(target == nums[mid]){
    				return mid;
    		}else if ( target > nums[mid]){
    				return recursiveBinary( nums, target, mid + 1 , right);
    		}else{
    				return recursiveBinary( nums, target, left, mid - 1);
    		}
    }
    
    ```
    

### Questions

1. [**704. Binary Search](https://leetcode.com/problems/binary-search/) (Easy)**
2. [**35. Search Insert Position**](https://leetcode.com/problems/search-insert-position/) (Easy) 
3. [**278. First Bad Version](https://leetcode.com/problems/first-bad-version/) (Easy)**

---

1. [**34. Find First and Last Position of Element in Sorted Array](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/)  (Medium)**
2. **** [33. Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/) ( Medium )**
3. ** [153. Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/) (Medium)
4. [744. Find Smallest Letter Greater Than Target](https://leetcode.com/problems/find-smallest-letter-greater-than-target/) (Easy)
5. [**74. Search a 2D Matrix**](https://leetcode.com/problems/search-a-2d-matrix/) (Medium) 

---

1. [**69. Sqrt(x)**](https://leetcode.com/problems/sqrtx/) (Easy)
2. [852. Peak Index in a Mountain Array](https://leetcode.com/problems/peak-index-in-a-mountain-array/) (Medium)
3. [162. Find Peak Element](https://leetcode.com/problems/find-peak-element/) (Medium)
4. [**875. Koko Eating Bananas**](https://leetcode.com/problems/koko-eating-bananas/) (Medium)
5. [367. Valid Perfect Square](https://leetcode.com/problems/valid-perfect-square/) (Easy)
6. [1011. Capacity To Ship Packages Within D Days](https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/) (Medium)
7. [410. Split Array Largest Sum](https://leetcode.com/problems/split-array-largest-sum/) (Hard)