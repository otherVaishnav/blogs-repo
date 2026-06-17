--- 
title: "Strings Questions"
description: "String practice questions and LeetCode problems."
pubDate: 2026-06-17
---
# Strings

1. Write a Java Program to convert a given string into lowercase.
2. Write a Java Program to convert a given string into uppercase.
3. Write a Java Program to count the number of vowels, consonants, numbers, and special characters.
4. Write a Java Program to count the number of spaces in a given string.
5. Write a Java Program to convert even index characters to uppercase and odd index characters to lowercase.
6. Write a Java Program to remove spaces from a string.
7. Write a Java Program to remove the first and last character from a string.
8. Write a Java Program to remove vowels from a given string.
9. Write a Java Program to remove starting and ending spaces from a given string.
10. Write a Java Program to convert each letter of every word in uppercase.
11. Write a Java Program to reverse a string.
12. Write a Java Program to check if a string is palindrome.
13. Write a Java Program to count the number of words present in a given sentence.
14. Write a Java Program to remove a specific character from a string (remove all occurrences).
15. Write a Java Program to remove the first occurrence of a specified character from a string.
16. Write a Java Program to replace a given character with another specified character.
17. Write a Java Program to add a specified character at the given index.
18. Write a Java Program to reverse each word in a given string.
19. Write a Java Program to check if two strings are equal using different ways in Java.
20. Write a Java Program to remove duplicate characters from a given string.
21. Write a Java Program to print duplicate words in a given string.
22. Write a Java Program to check if two strings are anagrams.
23. Write a Java Program to check if a string is a pangram.
24. Write a Java Program to remove odd index characters from a string.
25. Write a Java Program to remove a substring from a string.
a. Example: Input: hello, toRemove: he → Output: llo
26. Write a Java Program to remove a substring from a string (variant 2).
a. Example: Input: hello, toRemove: eh → Output: llo
27. Write a Java Program to print the longest and smallest word in a given string (sentence) based on length.
28. Substring Search
29. Longest Palindromic Substring

---

---

### LeetCode :

1. [Reverse String (344)](https://leetcode.com/problems/reverse-string/)
2. [Reverse Words in a String III (557)](https://leetcode.com/problems/reverse-words-in-a-string-iii/)
3. [Valid Palindrome (125)](https://leetcode.com/problems/valid-palindrome/)
4. [Length of Last Word (58)](https://leetcode.com/problems/length-of-last-word/)
5. [Valid Anagram (242)](https://leetcode.com/problems/valid-anagram/) → frequency array | hashmap
- 6. [Longest Common Prefix (14)](https://leetcode.com/problems/longest-common-prefix/) → assume first is the answer
    
    ```java
    class Solution {
        public String longestCommonPrefix(String[] strs) {
            String longestPrefix = strs[0];
            for(int i =0;i<longestPrefix.length();i++){
                // flower 
                for(int j = 1;j<strs.length;j++){
                    // flow  
                    if( i >= strs[j].length() || longestPrefix.charAt(i) != strs[j].charAt(i) ){
                        return longestPrefix.substring(0,i);
                    }
    
                }
            }
            return longestPrefix;
        }
    }
    ```
    
- 7. [Repeated Substring Pattern (459)](https://leetcode.com/problems/repeated-substring-pattern/) → concatination, double trick
    
    ```java
    class Solution {
        public boolean repeatedSubstringPattern(String s) {
            // Concatenation trick 
            /* 
                let's say s is made up of string p. 
                then s atleast havs 2p's 
                
                note : s.contains(2p) - > true 
                
                if, you double s -> it had 4p's 
                now if you remove the first and last character 
                it still have 2p's ( which is the original s)
                (2p's).contains(2p's) -> true 
                (2p's).contains(s) -> true 
                (4p's).contains(s) -> true
                (double s).contains(s) -> true 
            */
            // double the string 
            String doubleS = s + s;
            // remove first and last character 
            String removedString = doubleS.substring(1,doubleS.length()-1);
            return removedString.contains(s);
            /*
              other options : 
                - Longest Proper Prefix
                - Divisor‑based Brute Force
            */
        }
    }
    ```
    
- 8. [First Unique Character in a String (389)](https://leetcode.com/problems/first-unique-character-in-a-string/)  → freqArray / hashmap
    
    ```java
    class Solution {
        public int firstUniqChar(String s) {
            // or a HashMap for generic inputs 
            int[] freqArray = new int[26];
            for(char c : s.toCharArray()){
                freqArray[c-'a']++;
            }
            for(int i = 0;i<s.length();i++){
                if(freqArray[s.charAt(i) - 'a'] == 1){
                    return i;
                }
            }
            return -1;
            /*
                Other : 
                    1. Store first index ( in array )
                    2. LinkedHash map ( 2 flags, index for unique and -1 for duplicates)
                    3. Queue with lazy deletion
    
            */
        }
    }
    ```
    
- 9. [Ransom Note (383)](https://leetcode.com/problems/ransom-note/)
    
    ```java
    class Solution {
        public boolean canConstruct(String ransomNote, String magazine) {
            // get the freq of ransom notes 
            // remove the freq of magzine from freq of ransom Note.
            // after that ransom note must be empty.
            
            
            /*
            HashMap<Character,Integer> map = new HashMap<>();
            for(char c: ransomNote.toCharArray()){
                map.put(c,map.getOrDefault(c,0)+1);
            }
            for(char c: magazine.toCharArray()){
                if(map.containsKey(c)){
                    map.put(c,map.get(c)-1);
                    if(map.get(c)==0){
                        map.remove(c);
                    }
                }        
            }
            return map.isEmpty();
            */
            int[] freqArray = new int[26];
            for(char c: ransomNote.toCharArray()){
                freqArray[c-'a']++;
            }
            for(char c:magazine.toCharArray()){
                freqArray[c-'a']--;
            }
            for(int i = 0;i<26;i++){
                if(freqArray[i]>0) return false;
            }
            return true;
        }
    }
    ```
    
- 10. [Group Anagrams (49)](https://leetcode.com/problems/group-anagrams/)
    
    ```java
    class Solution {
        public List<List<String>> groupAnagrams(String[] strs) {
            if(strs.length == 0 ) return new ArrayList();
            HashMap<String, ArrayList<String>> result = new HashMap<>();
            for(String s : strs){
                char[] s1 = s.toCharArray();
                Arrays.sort(s1);
                String sortedS = new String(s1);
                result.putIfAbsent(sortedS,new ArrayList());
                result.get(sortedS).add(s);
            }
            return new ArrayList<>(result.values());
        }
    }
    ```
    
- 11. [Find All Anagrams in a String (438)](https://leetcode.com/problems/find-all-anagrams-in-a-string/)
    
    ```java
    import java.util.ArrayList;
    import java.util.Arrays;
    import java.util.List;
    
    class Solution {
        public List<Integer> findAnagrams(String s, String p) {
            List<Integer> res = new ArrayList<>();
            if (s == null || p == null || s.length() < p.length()) {
                return res;
            }
    
            int[] freqArray = new int[26];
            int[] winArray = new int[26];
    
            // Fill the target frequency array
            for (int i = 0; i < p.length(); i++) {
                freqArray[p.charAt(i) - 'a']++;
            }
    
            int k = p.length();
            
            // Right pointer moves across the string 's'
            for (int right = 0; right < s.length(); right++) {
                // Add the current character to the window
                winArray[s.charAt(right) - 'a']++;
    
                // Once the window exceeds size k, remove the leftmost character
                if (right >= k) {
                    int left = right - k;
                    winArray[s.charAt(left) - 'a']--;
                }
    
                // If the window size is exactly k, check for an anagram match
                if (right >= k - 1) {
                    if (Arrays.equals(freqArray, winArray)) {
                        res.add(right - k + 1); // The start index of the window
                    }
                }
            }
    
            return res;
        }
    }
    ```
    
- 12. [Longest Substring Without Repeating Characters (3)](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
    
    ```java
    class Solution {
        public int lengthOfLongestSubstring(String s) {
            
            // create a hashmap which stores the element as key ind index as value
            // keep adding until you get duplicate
            // keep the maxLength updated
            // if duplicate is found, 
            // we skip all elements until the index of that old value and continue the process
            HashMap<Character,Integer> map = new HashMap<>();
            int left = 0;
            int maxLength = 0;
            for(int right = 0; right < s.length();right++){
                char c = s.charAt(right);
                if(map.containsKey(c) && map.get(c) >= left){
                    left = map.get(c) + 1;
                }
                map.put(c,right);
                maxLength = Math.max(maxLength, ( right - left + 1));
            }
            return maxLength;
        }
    }
    
    ```
    
- 13. [Permutation in String (567)](https://leetcode.com/problems/permutation-in-string/) - sliding window + prefix
    
    ```java
    class Solution {
        public boolean checkInclusion(String s1, String s2) {
            int[] freqArray = new int[128];
            int k = s1.length();
            for(int i = 0;i<k;i++){
                freqArray[s1.charAt(i)]++;
            }
    
            int[] winFreq = new int[128];
            int start = 0;
            for(int i = 0;i<s2.length();i++){
                winFreq[s2.charAt(i)]++;
                if(i - start + 1 > k){ // current windoq length is more 
                    winFreq[s2.charAt(start)]--; // remove the starting point
                    start++;
    
                }
                if(Arrays.equals(freqArray,winFreq)){
                    return true;
                }
            }
            return false;
        }
    }
    ```
    
- 14. [String Compression (443)](https://leetcode.com/problems/string-compression/) - sliding window + Freq
    
    ```java
    class Solution {
        public int compress(char[] chars) {
            if(chars.length < 2) return chars.length;
            // to make the required string. 
            StringBuilder s = new StringBuilder();
            int left = 0; // window start 
            int freq = 0; // freq of current character. 
            for(int right = 0;right<chars.length;right++){
                // same chars, keep increasing the freq
                if(chars[left]==chars[right]){
                    freq++;
                }else{
                    // if the continuity breks, append the previous char and it's freq
                    s.append(chars[left]);
                    if(freq != 1){
                        s.append(freq);
                        freq = 1;
                    }
                    // move the left ahead.
                    left = right;
                }
            }
            // handle the last char freq. 
            if(left<=chars.length-1){
                s.append(chars[left]);
                if(freq>1) s.append(freq);
            }
            // we got the string, modify the OG array.
            System.out.println(s);
            for(int i = 0;i<s.length();i++){
                chars[i] = s.charAt(i);
            }
            return s.length();
        }
    }
    ```
    

---

---

- 15. [Longest Palindromic Substring (5)](https://leetcode.com/problems/longest-palindromic-substring/)
    
    ```java
    // brute force 
    class Solution {
        public String longestPalindrome(String s) {
            // check if left to right is a palindrome 
            // if yes, return 
            // if no move the left pointer 
            if(s.length()<1) return s;
            String longestString = s.charAt(0) + "";
            for(int i = 0 ;i<s.length();i++){
                for(int j=i;j<s.length();j++){
                    String winString = s.substring(i,j+1);
                    if(isPalindrome(winString)){
                        if(winString.length() > longestString.length()){
                            longestString = winString;
                        }
                    }
                }
            }
            return longestString;
        }
        static public boolean isPalindrome(String s){
            int left = 0;
            int right = s.length()-1;
            while (left <= right) {
                if(s.charAt(left) != s.charAt(right)) return false;
                left++;
                right--;
            }   
            return true;
        }
    }
    ```
    
- 16. [Minimum Window Substring (76)](https://leetcode.com/problems/minimum-window-substring/)
    
    ```java
    class Solution {
        public String minWindow(String s, String t) {
            // sliding window and a frequency array 
            int[] targetChars = new int[128];
            for(char c: t.toCharArray()){
                targetChars[c]++;
            }
    
            // to keep track of the lowest length window
            // we could have taken a string, but then there is no suitable initial value.
            int minLen = Integer.MAX_VALUE; 
            // best starting point, it will help while returning the best substring. 
            int bestStart  = 0;
            // left pointer of the window, start of current window
            int currentStart = 0;
            // freq counter
            int requiredMatches = t.length();
    
            for(int right = 0;right<s.length();right++){
                char currentChar = s.charAt(right);
                // check if the current character is among target 
                if(targetChars[currentChar] > 0){
                    requiredMatches--;
                }
                // decrease the freq of current character 
                // if the char is unwanted, it becomes -ve.
                targetChars[currentChar]--; 
    
                // if you got all the required characters. 
                // while ? there could be useless elements at left pointer.
                while(requiredMatches==0){
                    // get the best length
                    if(minLen > right-currentStart+1){
                        minLen = right - currentStart + 1;
                        bestStart = currentStart;
                    }
                    // check if you can shrink from start pointer or not.
                    // get the start char of the window 
                    char leftChar = s.charAt(currentStart);
                    // remove it 
                    targetChars[leftChar]++;
    
                    if(targetChars[leftChar]>0){ 
                        // it means had +ve freq originally 
                        // i.e it is part of target string. 
                        // -> current window is invalid, need to store it and break
                        requiredMatches++;
                    }
                    // we can move the start, as both valid and invalid cases are handled above 
                    currentStart++;
                }
            }
            return minLen == Integer.MAX_VALUE ? "" : s.substring(bestStart,bestStart+minLen);
        }
    }
    ```