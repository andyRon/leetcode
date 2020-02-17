## [58. 最后一个单词的长度](https://leetcode-cn.com/problems/length-of-last-word/)

Length of Last Word

### 题目描述

给定一个仅包含大小写字母和空格 ' ' 的字符串 s，返回其最后一个单词的长度。

如果字符串从左向右滚动显示，那么最后一个单词就是最后出现的单词。

如果不存在最后一个单词，请返回 0 。

说明：一个单词是指仅由字母组成、不包含任何空格的 最大子字符串。

**示例:**

```
输入: "Hello World"
输出: 5
```



### 解题



```java
class Solution {
    public int lengthOfLastWord(String s) {
        String[] strs = s.split(" ");
        if (strs.length > 0) {
            return strs[strs.length - 1].length();
        }
        return 0;

    }
}
```

另外思路：

```java
class Solution {
    public int lengthOfLastWord(String s) {
        int p = s.length() - 1;
        while (p >= 0 && s.charAt(p) == ' ') p--;
        int end = p;
        while (p >= 0 && s.charAt(p) != ' ') p--;
        return end - p;
    }
}
```

