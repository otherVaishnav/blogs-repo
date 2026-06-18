---
title: "Number Programming Questions"
description: "Number Programming Questions and Solutions"
pubDate: 2026-06-17
---

1. Write a program to find maximum between two numbers
    
    ```java
    public static int maxOfTwo(int a,int b){
    		return a > b ? a : b;
    }
    ```
    
2. Write a program to check whether a number is divisible by 5 and 11 or not
    
    ```java
    public boolean isDivisible(int x){
    		return ( x%5==0 && x%11==0 );
    }
    ```
    
3. Write a program to check whether a year is leap year or not
    
    ```java
    public boolean isLeap(int year){
    		if(year%4==0 && year%100 != 0){
    				return true;
    		}
    		if(year%100 == 0 && year%400==0){
    				return true;
    		}
    		return false;
    }				
    ```
    
4. Write a program to input any alphabet and check whether it is vowel or consonant. 
    
    ```java
    public boolean isVowel(char ch){
    		if( ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u' || 
    				ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U' ){
    				return true;
    		}
    		return false;
    }
    ```
    
5. Write a program to check whether a character is uppercase or lowercase alphabet.
    
    ```java
    // ASCII 
    public void isUpper(char ch){
    		return ch >= 'A' && ch <= 'Z';
    }
    ```
    
6. Write a program to count the total number of notes in given amount. 
    
    ```java
    
    ```
    
7. Write a program to find all roots of a quadratic equation. 
    
    ```java
    // roots of quatratic equation. 
    ```
    
8. Write a program to input marks of five subjects Physics, Chemistry, Biology, Mathematics and Computer. Calculate percentage and grade according to
following:
    
    • Percentage >= 90% : Grade A
    • Percentage >= 80% : Grade B
    • Percentage >= 70% : Grade C
    • Percentage >= 60% : Grade D
    • Percentage >= 40% : Grade E
    • Percentage < 40% : Grade F
    
9. Write a program to input basic salary of an employee and calculate its Gross salary according to following :
• Basic Salary <= 10000 : HRA = 20%, DA = 80%
• Basic Salary <= 20000 : HRA = 25%, DA = 90%
• Basic Salary > 20000 : HRA = 30%, DA = 95%
The current year and the year in which the employee joined the organization are
entered through the keyboard. If the number of years for which the employee has
served the organization is greater than 3 then a bonus of Rs. 2500/- is given to
the employee. If the years of service are not greater than 3, then the program "
10. Write a program that prints numbers between a starting number and an ending number, inclusive. The starting and ending numbers should be entered by the user.
11. Write a program to find the sum of all even numbers up to a given integer 'num' and number starting from zero. Make use of a do-while loop.
12. Write Java Program to print n natural numbers.
13. Write Java Program to print sum of n natural numbers.
14. Write Java Program to print product of n natural numbers.
15. Write Java Program to print product of even numbers from given range.
    
    ```java
    // product of even numbers till n. 
    package number_program;
    public class EvenRange {
    	public static void getEvenNumbers(int s,int f) {
    		do {
    			if(s%2==0) {
    				System.out.println(s);
    			}
    			s++;
    		}while(s<=f);
    	}
    	
    	public static void main(String[] args) {
    		getEvenNumbers(8,3);
    	}
    }
    ```
    
16. Write Java Program to check the prime number or not.
    
    ```java
    public boolean isPrime(int n){
    		if(n<2) return false;
    		for(int i = 2;i*i <= n ;i++){
    				if(n%i==0) return false;
    		}
    		return true;
    }
    ```
    
17. Write Java Program to print factorial of a numbers.
    
    ```java
    // 4. factors of a given program 
    // how can we do this, reduce the number of iterations. !! 
    // values are duplicates, need to remove them. 
    public class Factors {
    	public static void getFactors(int n) {
    		for(int i = 1;i<=n;i++){
    			if(n%i==0) {
    				System.out.println("i :" + i);
    			}
    		}
    	}
    	public static void main(String[] args) {
    		getFactors(90);
    	}
    }
    ```
    
18. Number of odd factors of n. 
    
    ```java
    // number of odd factors 
    package number_program;
    public class OddFactors {
    	public static void getOddFactors(int n) {
    		int i = 1,c=0;
    		do {
    			if(n%i==0) {
    				System.out.println(i);
    				c++;
    			}
    			i+=2;
    		}while(i<=n);
    		System.out.println("Count of odd factors : " + c );
    	}
    	public static void main(String[] args) {
    		getOddFactors(40);
    	}
    }
    ```
    
19. Write Java Program to print n Fibonacci numbers.
    
    ```java
    public static int[] Fibonacci(int n){
    		n == 1 ? 
    				return int[] {0} : 
    				(n==2 ? 
    						return int[]{0,1} : )
    		int[] arr = new int[n];
    		
    ```
    
20. Write Java Program to print sum of all digits.
21. Write Java Program to print perfect number or not.
    
    ```java
    // addition of factors = number 
    public boolean isPrefect(int n){
    		int sum = 0;
    		for(int i = 1;i<n;i++){
    				sum += (n%i == 0) ? i : 0;
    		}
    		return sum == n;
    }
    // ---------------------------------
    public boolean isPrefect(int n){
    		int sum = 1;
    		for(int i = 2;i*i <= n;i++){
    				if(n%i == 0){
    						sum += i;
    						if(i != n/i ) sum += n/i;
    				}
    		}
    		return n > 1 && sum == n;
    }
    ```
    
22. Kaprekar number. 
    
    ```java
    /*
    A Kaprekar number is a number whose square when divided into two parts the sum 
    of those parts is equal to the original number and none of the parts has value 0. 
    Now given a number, your task is to check if it is Kaprekar number or not.
    Example 1:
    Input:
    	N=45
    Output:
    	1
    Explanation:
    45*45=2025. Now, 20+25=45.
    Thus, 45 is a kaprekar number.
    */
    // User function Template for Java
    
    class Solution {
        public boolean isKaprekar(int N) {
            // take the square 
            // break it in two half 
            // sum of this halfs should be = num 
            int square = N*N;
            int len = (square+"").length();
            int c = len%2==0 ? len/2 : len/2+1;
            int secondHalf = 0;
            int x = 1;
            while(c>0){
                secondHalf += (square%10)*x;
                x = x*10;
                c--;
                square/=10;
            }
            int sumOfHalfs = square + secondHalf;
            return sumOfHalfs == N;
        }
    }
    ```
    
23. Write Java Program to check given number strong number.
    
    ```java
    // A number equal to the sum of the factorial of its digits.
    public boolean isStrong(int n) {
    		int temp = n;
    		int sum = 0;
    		while(n>0) {
    			int digit = n%10;
    			int fact = 1;
    			
    			while(digit>1) {
    				fact *= digit--;
    			}
    //			for(int i = 1;i<=digit;i++) {
    //				fact+=i;
    //			}
    			sum+= fact;
    			n/=10;
    		}
    		System.out.println("Num : " + temp);
    		System.out.println("Sum : " + sum);
    		System.out.println("Not strong !!");
    		return sum==temp;
    	}
    ```
    
24. Write Java Program to check given number is Armstrong number. ( **Narcissistic Number )**
    
    ```java
    // A number equal to the sum of its digits each raised to the power of 
    // the number of digits.
    
    ```
    
25. Write Java Program to reverse given number.
    
    ```java
    public int getReverse(int n){
    		int rev = 0;
    		while(n>0){
    				rev = rev*10 + n%10;
    				n/=10;
    		}
    		return rev;
    }
    ```
    
26. Write Java Program to check given number is palindrome or not.
    
    ```java
    public boolean isPalindrome(int n){
    		return n == getReverse(n);
    }
    ```
    
27. Write Java Program to check given number is Xylem/Phloem.
    
    ```java
    public boolean isXylem(int n){
    		while(n!= -1) {
    			System.out.print("Enter n :");
    			n = sc.nextInt();
    			// sum of extreme == sum of mid 
    			int temp = n/10;  
    			int sumOfMid = 0;
    			while(temp>=10) {
    				sumOfMid += temp%10;
    				temp/=10;
    			}
    		}
    		int sumOfExtreme = n%10 + temp;
    		return sumOfMid==sumOfExtreme;
    }
    ```
    
28. Write Java Program to check given number is Happy number.
    
    ```java
    
    ```
    
29. Write Java Program to check given number is prime number.
30. Write Java Program to check given number is Neon number.
31. Write Java Program to swap two numbers without 3rd variable.
32. Write Java Program to check given number is Buzz number.
33. Write Java Program to do sum of all numbers until you get single digit.
34. Write Java Program to check given year is leap year or not.
35. Write Java Program to find alternative prime numbers.
36. Write Java Program to find twisted prime number.
    
    ```java
    public boolean isTwistedPrime(int n){
    			return isPrime(n) == isPrime(getReverse(n));
    }
    ```
    
37. Write Java Program to check given number is sunny number or not.
38. Write Java Program to check given number is Automorphic number or not.
39. Write Java Program to check given number is Duck number or not.
40. Write Java Program to check given number is Bouncy number or not.
41. Write Java Program to check given number is Mistry number or not.
42. Write Java Program to check given number is Smith number or not.
43. Write Java Program to convert decimal to Binary. 
44. Write Java Program to convert decimal to octal.
45. Write Java Program to convert decimal to Hexadecimal.
46. Write Java Program to convert Binary to octal.
47. Write Java Program to convert Binary to decimal.
48. Write Java Program to convert Octal to Decimal.
49. Write Java Program to convert Octal to Binary.
50. Write Java Program to convert Binary to Hexadecimal.
51. Write Java Program to convert Hexadecimal to Binary.
52. Keith number : 
    
    ```java
    /*
    A x digit number n is called Keith number if it appears in a special sequence 
    (defined below) generated using its digits. The special sequence has first x 
    terms as digits of n and other terms are recursively evaluated as sum of 
    previous x terms.The task is to find if a given number is Keith Number or not.
    
    Example 1:
    
    Input: n = 197
    Output: 1 
    Explanation: 197 has 3 digits, so n = 3 
    The number is Keith because it appears 
    in the special sequence that has first
    three terms as 1, 9, 7 and remaining
    terms evaluated using sum of previous 3
    terms. 1, 9, 7, 17, 33, 57, 107, 197, ..... 
    
    */
    // User function Template for Java
    class Solution {
        static int isKeith(int n) {
            // find the length 
            // declare array of that length 
            // store every digit at index. 
            // get array sum, keep a pointer to reset at 3 , use it to replace
            // sum with digit and 
            // keep finding sum until sum is < num. 
            int len = (n+"").length();
            int[] arr = new int[len];
            int num = n;
            for(int i = len-1;i>=0;i--){
                arr[i] = num%10;
                num/=10;
            }
            // displayArr(arr);
            int replacePointer = 0;
            int arrSum = getArraySum(arr);
            while(arrSum<n){
                // displayArr(arr);
                arr[replacePointer] = arrSum;
                replacePointer = ++replacePointer > len - 1 ? 0 : replacePointer; 
                arrSum = getArraySum(arr);
            }
            
            return arrSum == n ? 1 : 0;
        }
        
        static void displayArr(int[] arr){
            for(int i=0;i<arr.length;i++){
                System.out.print(arr[i]+" ");
            }
            System.out.println("\n-----");
        }
        
        static int getArraySum(int[] arr){
            int sum = 0;
            for(int i=0;i<arr.length;i++){
                // System.out.println(arr[i]);
                sum += arr[i];
            }
            // System.out.println();
            return sum;
        }
    }
    ```
    

---
