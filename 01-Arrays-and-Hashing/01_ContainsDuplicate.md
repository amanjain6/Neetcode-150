# 217. Contains Duplicate

**Difficulty**: Easy  
**Leetcode Link**: [https://leetcode.com/problems/contains-duplicate/](https://leetcode.com/problems/contains-duplicate/)

---

### Problem Statement  
Given an integer array `nums`, return `true` if any value appears at least twice in the array, and return `false` if every element is distinct.

---

### Examples

**Example 1:**
Input: nums = [1,2,3,1]
Output: true

**Example 2:**
Input: nums = [1,2,3,4]
Output: false

**Example 3:**
Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true

---

### Constraints
- 1 <= `nums.length` <= 10⁵  
- -10⁹ <= `nums[i]` <= 10⁹

---

### Solution (Java)
```java
import java.util.HashSet;

class Solution {
    public boolean containsDuplicate(int[] nums) {
        HashSet<Integer> set = new HashSet<Integer>();
        for(int i : nums){
            if(set.contains(i)){
                return true;
            } else{
                set.add(i);
            }
        }
        return false;
    }
}
