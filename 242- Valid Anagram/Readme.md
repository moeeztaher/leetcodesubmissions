# Intuition
Let's start off by defining what is an anagram. An anagram is a word or phrase formed by rearranging the letters of another word or phrase. Now, to solve this problem, we can compare the characters in s and t and check if they contain the same characters with the same frequencies (number of times each letter occurs in the word).

# Approach
1. First, check if s and t are equal in length. If they are not equal, it means they cannot be anagrams, in that case return false.
2. Create an integer array count of size 26 to store the frequencies of each character.
3. Iterate through both s and t simultaneously using a for loop. In each iteration, increment the count of the corresponding character in s and decrement the count of the corresponding character in t. This is done by subtracting the character 'a' from the current character to get the index in the count array.
4. After the iteration, if s and t are anagrams, all counts in the count array should be zero. Iterate through the count array and check if any count is non-zero. If a non-zero count is found, it means the frequencies of characters in s and t are not equal, in that case return false.

# Complexity
- Time complexity:
O(n)

- Space complexity:
O(1)

# Code
```
class Solution {
    public boolean isAnagram(String s, String t) {
        if (s.length() != t.length()) {
            return false;
        }

        int[] count = new int[26];

        for (int i = 0; i < s.length(); i++) {
            count[s.charAt(i) - 'a']++;
            count[t.charAt(i) - 'a']--;
        }

        for (int i = 0; i < 26; i++) {
            if (count[i] != 0) {
                return false;
            }
        }

        return true;
    }
}
```
