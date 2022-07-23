## [1844. Replace All Digits with Characters](https://leetcode.com/problems/replace-all-digits-with-characters/)

## Description
You are given a  **0-indexed**  string  `s`  that has lowercase English letters in its  **even**  indices and digits in its  **odd**  indices.

There is a function  `shift(c, x)`, where  `c`  is a character and  `x`  is a digit, that returns the  `xth`  character after  `c`.

-   For example,  `shift('a', 5) = 'f'`  and  `shift('x', 0) = 'x'`.

For every  **odd** index  `i`, you want to replace the digit  `s[i]`  with  `shift(s[i-1], s[i])`.

Return  `s` _after replacing all digits. It is  **guaranteed**  that_ `shift(s[i-1], s[i])` _will never exceed_ `'z'`.

**Example 1:**

**Input:** s = "a1c1e1"
**Output:** "abcdef"
**Explanation:** The digits are replaced as follows:
- s[1] -> shift('a',1) = 'b'
- s[3] -> shift('c',1) = 'd'
- s[5] -> shift('e',1) = 'f'

**Example 2:**

**Input:** s = "a1b2c3d4e"
**Output:** "abbdcfdhe"
**Explanation:** The digits are replaced as follows:
- s[1] -> shift('a',1) = 'b'
- s[3] -> shift('b',2) = 'd'
- s[5] -> shift('c',3) = 'f'
- s[7] -> shift('d',4) = 'h'

**Constraints:**

-   `1 <= s.length <= 100`
-   `s`  consists only of lowercase English letters and digits.
-   `shift(s[i-1], s[i]) <= 'z'`  for all  **odd**  indices  `i`.

## Solution

<!-- tabs:start -->

### **Python3**

```python
class Solution:
    def replaceDigits(self, s: str) -> str:
        ans=""

        for i in range (len(s)):           
            if s[i] >='a' and s[i] <='z':
                ans+=s[i]
            else : 
                a = chr(ord(s[i-1]) + int(s[i])) 
                ans+=a
        return (ans)
# ord() for getting the ascii value of given character and chr() for converting ascii value to its respective character
```
