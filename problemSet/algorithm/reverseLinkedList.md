# <a id="reverseLinkedList"></a>反转链表&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.reverseLinkedList] #

## 描述 ##

反转一个单链表。

示例:

输入: 1->2->3->4->5->NULL  
输出: 5->4->3->2->1->NULL

## 解答 ##

迭代法

`88ms` `65.24%`

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {
  let pre = null, next = null;
  if (!head) {
    return null;
  }
  next = head;
  head = head.next;
  next.next = null;
  while (head) {
    pre = head;
    head = head.next;
    pre.next = next;
    next = pre;
  }
  return next;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 反转链表  
  <https://leetcode-cn.com/problems/reverse-linked-list/description/>
* LeetCode problems reverse-linked-list  
  <https://leetcode.com/problems/reverse-linked-list/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.reverseLinkedList]: ../../README.md#problemSet.algorithm.reverseLinkedList "README"
<!-- 链接 结束 -->