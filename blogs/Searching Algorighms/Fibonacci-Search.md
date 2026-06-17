--- 
title: "Fibonacci Search"
description: "Fibonacci Search Algorithm and Implementation"
pubDate: 2026-06-17
---
# Fibonacci Search

advanced comparison-based search algorithm for sorted arrays.

→ It shares a "**divide-and-conquer**" philosophy with Binary Search, but instead of dividing the search space into two equal halves using division (n/2), it uses **Fibonacci numbers** to partition the array into **unequal sections via simple addition and subtraction.**

**Why avoid division?**

Historically, on older or low-level microprocessor architectures, basic mathematical division (/) and multiplication (*) operations took significantly more CPU cycles to compute than simple addition (+) and subtraction (-), maximizing hardware efficiency.

```java
public class FibonacciSearch {

    /**
     * Performs a Fibonacci Search on a sorted array.
     */
    public static int fibonacciSearch(int[] arr, int target) {
        int n = arr.length;
        if (n == 0) return -1;

        // Step 1: Set up the Fibonacci sequence numbers
        int fibM2 = 0; // (m-2)th Fibonacci number
        int fibM1 = 1; // (m-1)th Fibonacci number
        int fibM = fibM2 + fibM1; // mth Fibonacci number

        // Find the smallest Fibonacci number greater than or equal to n
        while (fibM < n) {
            fibM2 = fibM1;
            fibM1 = fibM;
            fibM = fibM2 + fibM1;
        }

        // Marks the eliminated front range of the array
        int offset = -1;

        // Step 2: Traverse the array using Fibonacci cuts
        while (fibM > 1) {
            // Ensure the probe index falls within valid array boundaries
            int i = Math.min(offset + fibM2, n - 1);

            // Target is greater than the value at index i, move window down/right
            if (arr[i] < target) {
                fibM = fibM1;
                fibM1 = fibM2;
                fibM2 = fibM - fibM1;
                offset = i; // Adjust the baseline offset to the current spot
            } 
            // Target is smaller than the value at index i, move window down/left
            else if (arr[i] > target) {
                fibM = fibM2;
                fibM1 = fibM1 - fibM2;
                fibM2 = fibM - fibM1;
            } 
            // Element found
            else {
                return i;
            }
        }

        // Compare the last remaining element against the target
        if (fibM1 == 1 && offset + 1 < n && arr[offset + 1] == target) {
            return offset + 1;
        }

        return -1; // Target not found
    }

    public static void main(String[] args) {
        int[] sortedNumbers = {10, 22, 35, 40, 45, 50, 80, 82, 85, 90, 100};
        int target = 85;

        int result = fibonacciSearch(sortedNumbers, target);
        System.out.println("Element found at index: " + result); // Output: 8
    }
}
```