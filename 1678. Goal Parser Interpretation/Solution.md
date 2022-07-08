## [1678. Goal Parser Interpretation](https://leetcode.com/problems/goal-parser-interpretation/)

## Description

You own a  **Goal Parser**  that can interpret a string  `command`. The  `command`  consists of an alphabet of  `"G"`,  `"()"`  and/or  `"(al)"`  in some order. The Goal Parser will interpret  `"G"`  as the string  `"G"`,  `"()"`  as the string  `"o"`, and  `"(al)"`  as the string  `"al"`. The interpreted strings are then concatenated in the original order.

Given the string  `command`, return  _the  **Goal Parser**'s interpretation of_ `command`.

**Example 1:**

**Input:** command = "G()(al)"

**Output:** "Goal"

**Explanation:** The Goal Parser interprets the command as follows:

G -> G

() -> o

(al) -> al

The final concatenated result is "Goal".

**Example 2:**

**Input:** command = "G()()()()(al)"

**Output:** "Gooooal"

**Example 3:**

**Input:** command = "(al)G(al)()()G"

**Output:** "alGalooG"

**Constraints:**

-   `1 <= command.length <= 100`
-   `command`  consists of  `"G"`,  `"()"`, and/or  `"(al)"`  in some order.

## Solutions

<!-- tabs:start -->

### **Python3**

#### **Method 1**
```python
class Solution:
    def interpret(self, command: str) -> str:
        return command.replace("()","o").replace('(al)','al')
```
#### **Method 2**
```python
class Solution:
    def interpret(self, command: str) -> str:
        d = {"(al)":"al", "()":"o","G":"G"}
        tmp= ""
        res=""
        for i in range(len(command)):
            print(command[i])
            tmp+=command[i]
            if(tmp in d):
                res+=d[tmp]
                tmp=""
        return res
```
