# [Group-Anagram](https://leetcode.com/problems/group-anagrams/)

Appraoch -

We create a unordered hashmap with key as the string for the sorted word and value as a string list to store the anagrams. We loop through the string given to us and sort out the word. The sorted word is later checked for if already present if not we add an key and empty value. In the end we check for the sorted word in the map if present we add the word else the loop continues.

```java
class Solution {
  public static String sortedString(String str) {
        char arr[] = str.toCharArray();
        Arrays.sort(arr);
        return new String(arr);
    }
  public List<List<String>> groupAnagrams(String[] strs) {
        HashMap<String, List<String>> grouping = new HashMap<String, List<String>>();
        for(String unsortedWord: strs) {
        String sortedWord = sortedString(unsortedWord);
        if(!grouping.containsKey(sortedWord))
            grouping.put(sortedWord, new ArrayList<>());
        grouping.get(sortedWord).add(unsortedWord);
        }
        return new ArrayList<>(grouping.values());
    }
}
```
*Time Complexity - O(n \* k \* log(k)) where k is the length of the longest string*
