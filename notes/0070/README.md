## [70. 爬楼梯](https://leetcode-cn.com/problems/climbing-stairs/)

Climbing Stairs

### 题目描述

假设你正在爬楼梯。需要 *n* 阶你才能到达楼顶。

每次你可以爬 1 或 2 个台阶。你有多少种不同的方法可以爬到楼顶呢？

**注意：**给定 *n* 是一个正整数。

**示例 1：**

```
输入： 2
输出： 2
解释： 有两种方法可以爬到楼顶。
1.  1 阶 + 1 阶
2.  2 阶
```

**示例 2：**

```
输入： 3
输出： 3
解释： 有三种方法可以爬到楼顶。
1.  1 阶 + 1 阶 + 1 阶
2.  1 阶 + 2 阶
3.  2 阶 + 1 阶
```



### 解题



```java
public int climbStairs(int n) {
  int a = 1, b = 1;
  while (--n > 0) {
    b += a;
    a = b - a;
  }
  return b;
}
```



```java
    public int climbStairs(int n) {
        int[] dp = new int[n + 1];
        dp[0] = 1;
        dp[1] = 1;
        for (int i = 2; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }

        return dp[n];
    }
```







在45个台阶时已经达到int极限了

### 参考

[https://github.com/awangdev/LintCode/blob/master/Java/Climbing%20Stairs.java](https://github.com/awangdev/LintCode/blob/master/Java/Climbing Stairs.java)

