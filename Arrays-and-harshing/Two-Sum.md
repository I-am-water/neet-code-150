# [Two Sum](https://leetcode.com/problems/two-sum)

### Approach 1 - Linear Search

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for(int i=0;i<nums.length-1;i++)
        {
            for(int j=i+1;j<nums.length;j++)
            {
                if((nums[i]+nums[j])==target)
                    return new int[] {i,j};
            }
        }
        return new int[] {};
    }
}
```
*Time Complexity - O(n^2)*

### Approach 2 - Hash Map

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> findSum = new HashMap<Integer,Integer>();
        for(int i=0;i<nums.length;i++)
            findSum.put(nums[i],i);
        int diff = 0;
        for(int i=0;i<nums.length;i++)
        {
            diff = target - nums[i];
            if(findSum.containsKey(diff)&&findSum.get(diff)!=i)
                return new int[] {i,findSum.get(diff)};
        }
        return new int[] {};
    }
}
```
*Time Complexity - O(n)*
