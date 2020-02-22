## [83. 删除排序链表中的重复元素](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-list/)

Remove Duplicates from Sorted List

### 题目描述

给定一个排序链表，删除所有重复的元素，使得每个元素只出现一次。

**示例 1:**

```
输入: 1->1->2
输出: 1->2
```

**示例 2:**

```
输入: 1->1->2->3->3
输出: 1->2->3
```





### 解题



如果不是排序的，去掉重复的：

```java
public ListNode deleteDuplicates(ListNode head) {
    ListNode node = head;
    Set<Integer> set = new HashSet<>();
    set.add(node.val);
    while (node.next != null) {
        if (set.add(node.next.val)) {
            node = node.next;
        } else {
            node.next = node.next.next;
        }
    }

    return head;
}
```

排完序的就简单一点：

```java
    public ListNode deleteDuplicates(ListNode head) {
        if (head == null || head.next == null) return head;
        ListNode node = head;
        while (node.next != null) {
            if (node.next.val != node.val) {
                node = node.next;
            } else {
                node.next = node.next.next;
            }
        }
        return head;
    }
```

