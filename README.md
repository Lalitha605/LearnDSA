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

| 2025-07-20 | Intersection of Two Arrays | Easy | Used nested loops and HashSet to track unique nums | 30 mins |

| 2025-07-21 | Top K Frequent Elements | Medium | Used dictionary and sorted and return K elements | 60 mins |

public class Solution {
    public string FrequencySort(string s) {
        Dictionary<char, int> charFreq  = new Dictionary<char, int>();
        char[] chars = s.ToCharArray();
        // Count frequency
        foreach(char c in chars){
            if(charFreq.ContainsKey(c)){
                charFreq[c]++;
            }
            else{
                charFreq[c]=1;
            }
        }
        // Create buckets: index = frequency, value = list of characters
        List<char>[] buckets = new List<char>[s.Length+1]; 
        foreach(var pair in charFreq){
            int f=pair.Value;
            if(buckets[f]==null){
                buckets[f] = new List<char>();
            }
            buckets[f].Add(pair.Key);
        }
        StringBuilder result = new StringBuilder();
        // Build the result from buckets
        for(int i=buckets.Length-1;i>0;i--){
            if(buckets[i]!=null){
                foreach(char c in buckets[i]){
                    result.Append(new string(c,i)); // repeat char i times
                }
            }
        }
         return result.ToString();
    }
}
| 2025-07-22 | Sort Characters By Frequency | Medium | Used dictionary with sorting and bucket sort of chars frequescy | 75 mins |

| 2025-07-23 | Product of Array Except Self | Medium | Used nested loops | 75 mins |

| 2025-07-24 | Set Matrix Zeroes | Medium | Explored brute force with extra space, improved marking with boolean arrays, and optimized in-place solution using first row and column as markers | 90 mins |


