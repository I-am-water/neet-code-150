# [Contains-Duplicate](https://leetcode.com/problems/contains-duplicate)

### Approach 1 - Linear Search
Select a number from the array and search the entire array for that specific number, excluding the position of the selected number. This requires two nested for loops.

```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        for(int i=0;i<nums.length-1;i++)
        {
            for(int j=i+1;j<nums.length;j++)
            {
                if(nums[i]==nums[j])
                    return true;              
            }
            
        }
        return false;
    }
}
```
*Time Complexity - O(n^2)*
This isnt efficient for large arrays (Gives TLE on leetcode)

### Approach 2 - Sort
Sort the array and check if the next adjacent array is the same or not. Check till the last second number.
```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        Arrays.sort(nums);
        for(int i=0;i<nums.length-1;i++)
        {
             if(nums[i]==nums[i+1])
                return true;
        }
        return false;
    }
}
```
*Time Complexity - O(n log n)*

### Approach 3 - Hash Set
A hash set only contains unique elements. To identify and remove duplicates from an array, we can add all the elements from the array to a hash set. After adding all the elements, we can compare the size of the array with the size of the hash set. If the sizes are different, it indicates that there are duplicate elements in the array.
```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        Set<Integer> uniq = new HashSet<Integer>();
        for(int i=0;i<nums.length;i++)
        {
             uniq.add(nums[i]);
        }
        if(nums.length!=uniq.size())
            return true;
        return false;
    }
}
```
*Time Complexity - O(n)*
