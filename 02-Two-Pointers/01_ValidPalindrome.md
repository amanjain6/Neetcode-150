# 125. Valid Palindrome

**Difficulty**: Easy  
🔗 [Leetcode Problem](https://leetcode.com/problems/valid-palindrome/)

---

### Problem Statement  
A phrase is a `palindrome` if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return `true` if it is a palindrome, or `false` otherwise.

---

### Examples

### Examples

**Example 1:**  
**Input:** `s = "A man, a plan, a canal: Panama"`  
**Output:** `true`  
**Explanation:** "amanaplanacanalpanama" is a palindrome.

**Example 2:**  
**Input:** `s = "race a car"`  
**Output:** `false`  
**Explanation:** "raceacar" is not a palindrome.

**Example 3:**  
**Input:** `s = " "`  
**Output:** `true`  
**Explanation:** After removing non-alphanumeric characters, s is an empty string.  
An empty string is considered a valid palindrome.

---

### Constraints
- 1 <= `s.length` <= 2 * 105  
- s consists only of printable ASCII characters.

---

### Solution (Java)
```java
import java.util.HashSet;

class Solution {
    public boolean isPalindrome(String s) {
        int i = 0;
        int j = s.length() - 1;
        while(i<j) {
            while(i<j && !Character.isLetterOrDigit(s.charAt(i))) {
                i++;
            }
            while(i<j && !Character.isLetterOrDigit(s.charAt(j))) {
                j--;
            }
            if(Character.toLowerCase(s.charAt(i)) != Character.toLowerCase(s.charAt(j))) {
                return false;
            }
            i++;
            j--;
        }
        return true;
    }
}
