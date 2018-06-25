# <a id="mergeTwoSortedLists"></a>合并两个有序链表&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.mergeTwoSortedLists] #

## 描述 ##

将两个有序链表合并为一个新的有序链表并返回。新链表是通过拼接给定的两个链表的所有节点组成的。

示例：

> 输入：1->2->4, 1->3->4  
> 输出：1->1->2->3->4->4

## 解答 ##

递归

96ms

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var mergeTwoLists = function(l1, l2) {
  if (!l1 || !l2) {
    return l1 || l2;
  }
  if (l1.val < l2.val)  {
    l1.next = mergeTwoLists(l1.next, l2);
    return l1;
  } else {
    l2.next = mergeTwoLists(l1, l2.next);
    return l2;
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 合并两个有序链表  
  <https://leetcode-cn.com/problems/merge-two-sorted-lists/description/>
* LeetCode problems merge-two-sorted-lists  
  <https://leetcode.com/problems/merge-two-sorted-lists/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.mergeTwoSortedLists]: ../../README.md#problemSet.algorithm.mergeTwoSortedLists "README"
<!-- 链接 结束 -->