## [35. 搜索插入位置](https://leetcode-cn.com/problems/search-insert-position/)

search insert position

### 题目描述

给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组中，返回它将会被按顺序插入的位置。

你可以假设数组中无重复元素。

**示例 1:**
```
输入: [1,3,5,6], 5
输出: 2
```
**示例 2:**
```
输入: [1,3,5,6], 2
输出: 1
```
**示例 3:**
```
输入: [1,3,5,6], 7
输出: 4
```
**示例 4:**
```
输入: [1,3,5,6], 0
输出: 0
```


### 解答



```java
class Solution {
    public int searchInsert(int[] nums, int target) {
        int site = 0;
        int l = nums.length;
        if (l == 0) site = 0;
        if (l == 1) site = nums[0] >= target ? 0 : 1;
        if (nums[l - 1] < target) site = l;
        for (int n = 0; n < l; n++) {
            if (nums[n] >= target) {
                site = n;
                break;    // 如果没有break，将会怎么样？
            }
        }
        return site;
    }
}
```

