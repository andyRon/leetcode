## [67. 二进制求和](https://leetcode-cn.com/problems/add-binary/)

Add Binary

### 题目描述



给定两个二进制字符串，返回他们的和（用二进制表示）。

输入为**非空**字符串且只包含数字 `1` 和 `0`。

**示例 1:**

```
输入: a = "11", b = "1"
输出: "100"
```

**示例 2:**

```
输入: a = "1010", b = "1011"
输出: "10101"
```



### 解题

```java
class Solution {
    public String addBinary(String a, String b) {
        if (a.length() > b.length())
            return calculate(a, b);
        else
            return calculate(b, a);

    }

    private String calculate(String ls, String ss) {
        int l = ls.length();
        int s = ss.length();
        int d = l - s;
        int carry = 0;
        StringBuilder sb = new StringBuilder();
        for (int i = l - 1; i >= 0; i--) {
            int first = Integer.parseInt(String.valueOf(ls.charAt(i)));
            int second = i - d >= 0 ? Integer.parseInt(String.valueOf(ss.charAt(i - d))) : 0;
            int sum = first + second + carry;
            carry = sum / 2;
            sb.append(sum % 2);
        }
        if (carry != 0) sb.append(carry);
        return sb.reverse().toString();
    }
}
```

