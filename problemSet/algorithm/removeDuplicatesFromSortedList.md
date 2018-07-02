# <a id="removeDuplicatesFromSortedList"></a>爬楼梯&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.removeDuplicatesFromSortedList] #

## 描述 ##

给定一个排序链表，删除所有重复的元素，使得每个元素只出现一次。

示例 1:

> 输入: 1->1->2  
> 输出: 1->2

示例 2:

> 输入: 1->1->2->3->3  
> 输出: 1->2->3

## 解答 ##

2 个 node 遍历法

`100ms` `57.97%`

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
var deleteDuplicates = function(head) {
  if (!head || !head.next) {
    return head;
  }

  let start = head;
  let end = head.next;

  while (end) {
    if (start.val !== end.val) {
      start.next = end;
      start = end;
    } else if (!end.next) {
      start.next = null;
    }
    end = end.next;
  }
  
  return head;
};
```

1 个 node 遍历

`104ms` `40.58%`

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
var deleteDuplicates = function(head) {
  let node = head;

  while (node && node.next) {
    if (node.val === node.next.val) {
      node.next = node.next.next;
    } else {
      node = node.next;
    }
  }
  
  return head;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 删除排序链表中的重复元素  
  <https://leetcode-cn.com/problems/remove-duplicates-from-sorted-list/description/>
* LeetCode problems remove-duplicates-from-sorted-list  
  <https://leetcode.com/problems/remove-duplicates-from-sorted-list/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.removeDuplicatesFromSortedList]: ../../README.md#problemSet.algorithm.removeDuplicatesFromSortedList "README"
<!-- 链接 结束 -->