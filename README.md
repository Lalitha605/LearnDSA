# LearnDSA
# | 2025-07-17 | Two Sum | Easy | Used HashMap, clear logic |
# Did one program Two sum problem 
# This is my first program in it, not just submitted the logic not checked the complexity
# Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        for(int i=0;i<nums.Length;i++){
            for(int j=i+1;j<nums.Length;j++){
                if(nums[i]+nums[j]==target){
                    return new int[] {i,j};
                }
            }
        }
        return new int[] {};
    }
}
# Using hash map of dictionary
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        Dictionary<int, int> map = new Dictionary<int, int>();
        for(int i=0;i<nums.Length;i++){
            int complement = target-nums[i];
            if(map.ContainsKey(complement)){
                return new int[] {map[complement],i};
            }
            map[nums[i]]=i;        
        }
        return new int[] {};
    }
}
