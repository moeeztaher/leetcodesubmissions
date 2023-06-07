# Intuition
The idea is to reverse the digits of the given integer. We can achieve this by continuously extracting the last digit of the number using the modulo operator and building the reversed number by multiplying it by 10 and adding the extracted digit.

# Approach
1. Firstly, initialize a variable reversed to store the reversed number.
2. Iterate until the input number x is equal to 0
3. Extract the last digit of x by x % 10.
4. Reduce the value of x by dividing it by 10 (x /= 10).
5. Update reversed by multiplying it by 10 and adding the extracted digit (reversed = reversed * 10 + digit).
6. After the loop, check if the reversed number exceeds the range of a 32-bit signed integer (Integer.MAX_VALUE or Integer.MIN_VALUE). If it does, return 0, else, cast reversed to an int and return it as the result.

# Complexity
- Time complexity:
O(log10(x))

- Space complexity:
O(1)

# Code
```
class Solution {
    public int reverse(int x) {
        long reversed = 0;

        while (x != 0) {
            int digit = x % 10;
            x /= 10;
            reversed = reversed * 10 + digit;
        }

        if (reversed > Integer.MAX_VALUE || reversed < Integer.MIN_VALUE) {
            return 0;
        }

        return (int) reversed;
    }
}

```
