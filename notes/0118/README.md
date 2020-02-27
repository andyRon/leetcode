## [118. 杨辉三角](https://leetcode-cn.com/problems/pascals-triangle/)

Pascal's Triangle 

### 题目描述

给定一个非负整数 *numRows，*生成杨辉三角的前 *numRows* 行。

![img](https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif)

在杨辉三角中，每个数是它左上方和右上方的数的和。

**示例:**

```
输入: 5
输出:
[
     [1],
    [1,1],
   [1,2,1],
  [1,3,3,1],
 [1,4,6,4,1]
]
```

### 解题

```java
    public List<List<Integer>> generate(int numRows) {
        if (numRows <= 0) return Collections.emptyList();
        List<List<Integer>> listList = new ArrayList<>();
        for (int i = 0; i < numRows; ++i) {
            List<Integer> list = new ArrayList<>();
            for (int j = 0; j <= i; ++j) {
                if (j == 0 || i == j) {
                    list.add(1);
                } else  {
                    List<Integer> upList = listList.get(i - 1);
                    list.add(upList.get(j - 1) + upList.get(j));
                }
            }
            listList.add(list);
        }
        return listList;
    }
```

