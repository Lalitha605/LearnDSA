# 📘 LearnDSA

---

### Day 1 – 2025-07-17  
**Problem:** Two Sum  
**Level:** Easy  
**Status:** Solved using brute force and optimized dictionary approach  

### Problem Statement  
Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to `target`.  
You may assume exactly one solution exists, and you may not use the same element twice.

### Brute Force Approach – O(n²)

```csharp
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        for(int i = 0; i < nums.Length; i++) {
            for(int j = i + 1; j < nums.Length; j++) {
                if(nums[i] + nums[j] == target) {
                    return new int[] { i, j };
                }
            }
        }
        return new int[] {};
    }
}

###  Optimized Approach – Using Dictionary (Hash Map) – O(n)
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        Dictionary<int, int> map = new Dictionary<int, int>();
        for(int i = 0; i < nums.Length; i++) {
            int complement = target - nums[i];
            if(map.ContainsKey(complement)) {
                return new int[] { map[complement], i };
            }
            map[nums[i]] = i;
        }
        return new int[] {};
    }
}


| 2025-07-18 | Valid Anagram | Easy | Used HashMap & sorted strings approach | 65 mins |

| 2025-07-20 | Contains Duplicate | Easy | Used Dictionary and HashSet to track seen nums | 30 mins |



