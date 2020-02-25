## [107. 二叉树的层次遍历 II](https://leetcode-cn.com/problems/binary-tree-level-order-traversal-ii/)

 Binary Tree Level Order Traversal II

### 题目描述

给定一个二叉树，返回其节点值自底向上的层次遍历。 （即按从叶子节点所在层到根节点所在的层，逐层从左向右遍历）

例如：
给定二叉树 `[3,9,20,null,null,15,7]`,

```
    3
   / \
  9  20
    /  \
   15   7
```

返回其自底向上的层次遍历为：

```
[
  [15,7],
  [9,20],
  [3]
]
```



### 解题??

```java
public List<List<Integer>> levelOrderBottom(TreeNode root) {
  if (root == null) return Collections.emptyList();
  List<List<Integer>> list = new LinkedList<>();
  LinkedList<TreeNode> q = new LinkedList<>();
  q.add(root);
  while (!q.isEmpty()) {
    int size = q.size();
    List<Integer> sub = new LinkedList<>();
    for (int i = 0; i < size; ++i) {
      TreeNode node = q.remove();
      sub.add(node.val);
      if (node.left != null) q.add(node.left);
      if (node.right != null) q.add(node.right);
    }
    list.add(0, sub);
  }
  return list;
}
```







### 参考

https://github.com/Blankj/awesome-java-leetcode/blob/master/note/107/README.md

