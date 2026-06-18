---
title: "Special Numbers"
description: "Special Numbers and their properties."
pubDate: 2025-06-01
---
## 1. Perfect Number

A perfect number is a positive integer equal to the sum of its proper divisors (divisors excluding the number itself).

- Code
    
    ```java
    public boolean isPerfect(int n){
        int sum = 0;
        for (int i = 1; i < n; i++) {
            sum += (n % i == 0) ? i : 0;
        }
        return sum == n;
    }
    ```
    

## 2. Strong Number

A strong number is a number whose sum of the factorial of its digits equals the number itself.

## 3. Armstrong Number (Narcissistic Number)

A number where the sum of its digits raised to the power of the total number of digits equals the number itself.

- Code
    
    ```java
    import java.util.Scanner;
    
    public class Armstrong{
        public static void main(String[] args){
            Scanner sc = new Scanner(System.in);
            int n = 0;
            while (n != -1) {
                System.out.print("Enter n :");
                n = sc.nextInt();
                if (isArmstrong(n)) {
                    System.out.println("Armstrong");
                } else {
                    System.out.println("Not Armstrong");
                }
            }
        }
    
        public static boolean isArmstrong(int n){
            int temp = n;
            int len = (n + "").length();
            int sum = 0;
            while (temp > 0) {
                sum += power(temp % 10, len);
                temp /= 10;
            }
            return sum == n;
        }
    
        public static int power(int n, int len){
            int power = 1;
            while (len > 0) {
                power *= n;
                len--;
            }
            return power;
        }
    }
    ```
    

## 4. Xylem / Phloem Number

Classification based on comparing the sum of a number's extreme (outermost) digits with its mean (inner) digits.

- **Xylem:**
    
    sum extreme digits = sum of inner digits 
    
- **Phloem:**
    
    sum extreme digits = sum of inner digits 
    

## 5. Happy Number

A number that eventually becomes 1 when replaced repeatedly by the sum of the squares of its digits.

## 6. Neon Number

A number where the sum of the digits of its square is equal to the original number.

## 7. Buzz Number

A number that either ends with 7 or is exactly divisible by 7.

- Code
    
    ```java
    public boolean isBuzz(int n){
        if (n % 10 == 7 || n % 7 == 0) return true;
        return false;
    }
    ```
    

## 8. Twisted Prime Number

A prime number whose digits, when reversed, form another prime number.

## 9. Alternative Prime Numbers

Numbers that appear at every alternate position in a natural chronological prime sequence (skipping one prime every time).

## 10. Sunny Number

A number n is considered a sunny number if adding 1 results in a perfect square.

## 11. Automorphic Number

A number whose mathematical square ends with the exact same digits as the number itself.

- Code
    
    ```java
    int n = 6;
    return n == (n * n) % 10;
    ```
    

## 12. Duck Number

A number that contains at least one zero, but does not start with a leading zero.

## 13. Bouncy Number

A number whose digits are neither strictly increasing nor strictly decreasing.

## 14. Mystery Number

A number that can be expressed as the sum of a positive integer and its reverse.

- Code
    
    ```java
    public class Mystery{
        public static void main(String[] args){
            int n = 121;
            boolean isMystery = false;
    
            for (int i = 1; i <= n / 2; i++) {
                if (i + reverse(i) == n) {
                    System.out.println(n + " is a mystery number: " + i + " + " + reverse(i));
                    isMystery = true;
                    break;
                }
            }
            if (!isMystery) System.out.println("Not a mystery number");
        }
    
        public static int reverse(int n){
            int rev = 0;
            while (n > 0) {
                rev = rev * 10 + n % 10;
                n /= 10;
            }
            return rev;
        }
    }
    ```
    

## 15. Smith Number

A composite number where the sum of its digits equals the sum of the digits of its prime factors.

- Code
    
    ```
    package number_program;
    import java.util.Scanner;
    
    public class NumPro{
        public static void main(String[] args){
            Scanner sc = new Scanner(System.in);
            int n = 0;
            while (n != -1) {
                System.out.print("Enter n : ");
                n = sc.nextInt();
                if (isPrime(n)) {
                    System.out.println("Not a Smith number");
                    System.out.println("============================");
                    continue;
                }
    
                int sumOfDigit = getSumOfDigit(n);
                System.out.println("Sum of Digits : " + sumOfDigit);
    
                int digitSumOfPrime = getDigitSumOfPrimeFactors(n);
                System.out.println("Prime factor sum : " + digitSumOfPrime);
    
                if (sumOfDigit == digitSumOfPrime) {
                    System.out.println("Smith number");
                } else {
                    System.out.println("Not a Smith number");
                }
                System.out.println("============================");
            }
        }
    
        public static boolean isPrime(int n){
            if (n <= 1) return false;
    ```
    

---

---

---

---

---

---

---

---

1. **Automorphic Number**
    
    A number whose square ends with the number itself.
    
    Example:
    
    25² = 625
    
2. **Trimorphic Number**
    
    A number whose cube ends with the number itself.
    
3. **Disarium Number**
    
    A number where the sum of digits powered by their positions equals the number.
    
    Example:
    
    135 → 1¹ + 3² + 5³ = 135
    
4. **Harshad Number (Niven Number)**
    
    A number divisible by the sum of its digits.
    
5. **Kaprekar Number**
    
    A number whose square can be split into two parts that sum to the original number.
    
6. **Spy Number**
    
    A number where sum of digits = product of digits.
    
7. **Neon Number**
    
    Sum of digits of its square equals the number.
    
8. **Duck Number**
    
    Contains zero(s), but not at the beginning.
    
9. **Evil Number**
    
    Has an even number of 1s in binary representation.
    
10. **Odious Number**
    
    Has an odd number of 1s in binary.
    
11. **Magic Number**
    
    Repeated digit sum equals 1.