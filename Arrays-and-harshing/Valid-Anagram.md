# [Valid Anagram](https://leetcode.com/problems/valid-anagram)

### Approach - Sort method

Convert the string to char array and sort the char array generated. If they are anagram, the sorted strings will be same.

```java
class Solution {
    public static String sortString(String inputString)
    {
        char temp[] = inputString.toCharArray();
        Arrays.sort(temp);
        return new String(temp); 
    }
    public boolean isAnagram(String s, String t) {
        if(sortString(s).equals(sortString(t)))
            return true;
        return false;
    }
}
```
*Time Complexity - O(n log n)*
