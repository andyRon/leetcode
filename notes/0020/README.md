## [20. 有效的括号](https://leetcode-cn.com/problems/valid-parentheses/)

### 题目描述

给定一个只包括 `'('`，`')'`，`'{'`，`'}'`，`'['`，`']'` 的字符串，判断字符串是否有效。

有效字符串需满足：

1. 左括号必须用相同类型的右括号闭合。
2. 左括号必须以正确的顺序闭合。

注意空字符串可被认为是有效字符串。

**示例 1:**

```
输入: "()"
输出: true
```

**示例 2:**

```
输入: "()[]{}"
输出: true
```

**示例 3:**

```
输入: "(]"
输出: false
```

**示例 4:**

```
输入: "([)]"
输出: false
```

**示例 5:**

```
输入: "{[]}"
输出: true
```

### 思路

使用栈，具体：

1. 遍历字符串；

2. 如果是左半括号(`{` `(` `[`)，把其压进栈中；

3. 如果是右半括号，

   a：此时栈为空直接返回false

   b：栈顶是与之对应的左半括号，弹出栈顶

   c：栈顶不是与之对应的左半括号，返回false





```java
class Solution {
    public boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();
        for(int i = 0; i < s.length(); i++) {
            if (s.charAt(i) == '(' || s.charAt(i) == '{' || s.charAt(i) == '[') {
                stack.push(s.charAt(i));
            } else {
                if (stack.size() == 0) return false;

                char top = stack.peek();
                stack.pop();

                char match;
                if (s.charAt(i) == ')') {
                    match = '(';
                } else if (s.charAt(i) == ']') {
                    match = '[';
                } else {
                    match = '{';
                }

                if (top != match) return false;
            }
        }
        if( stack.size() != 0 ) return false;

        return true;
    }
}
```