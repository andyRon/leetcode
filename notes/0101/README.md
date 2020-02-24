## [101. 对称二叉树](https://leetcode-cn.com/problems/symmetric-tree/)

Symmetric tree

### 题目描述

给定一个二叉树，检查它是否是镜像对称的。

例如，二叉树 `[1,2,2,3,4,4,3]` 是对称的。

```
    1
   / \
  2   2
 / \ / \
3  4 4  3
```

但是下面这个 `[1,2,2,null,3,null,3]` 则不是镜像对称的:

```
    1
   / \
  2   2
   \   \
   3    3
```

**说明:**

如果你可以运用递归和迭代两种方法解决这个问题，会很加分。

### 解题

```java
    public boolean isSymmetric(TreeNode root) {
        if (root == null) return true;
        return assist(root.left, root.right);
    }

    private boolean assist(TreeNode left, TreeNode right) {
        if (left == null || right == null) return left == right;
        if (left.val != right.val) return false;
        return assist(left.left, right.right) && assist(left.right, right.left);
    }
```

