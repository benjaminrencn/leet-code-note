# <a id="deleteNodeInALinkedList"></a>删除链表中的节点&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.deleteNodeInALinkedList] #

## 描述 ##

请编写一个函数，使其可以删除某个链表中给定的（非末尾）节点，你将只被给定要求被删除的节点。

现有一个链表 -- head = [4,5,1,9]，它可以表示为:

> 4 -> 5 -> 1 -> 9

示例 1:

> 输入: head = [4,5,1,9], node = 5  
> 输出: [4,1,9]  
> 解释: 给定你链表中值为 5 的第二个节点，那么在调用了你的函数之后，该链表应变为 4 -> 1 -> 9.

示例 2:

> 输入: head = [4,5,1,9], node = 1  
> 输出: [4,5,9]  
> 解释: 给定你链表中值为 1 的第三个节点，那么在调用了你的函数之后，该链表应变为 4 -> 5 -> 9.

说明:

* 链表至少包含两个节点。
* 链表中所有节点的值都是唯一的。
* 给定的节点为非末尾节点并且一定是链表中的一个有效节点。
* 不要从你的函数中返回任何结果。

## 解答 ##

1. node 为 null 返回空
2. node 未最后一个节点 删除属性
3. node 非 null 非最后一个节点 val 为 next.val，next 为 next.next

`100ms` `91.67%`

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} node
 * @return {void} Do not return anything, modify node in-place instead.
 */
var deleteNode = function(node) {
  if (!node) {
    return;
  }
  if (!node.next) {
    delete node.val;
    delete node.next;
    return;
  }
  node.val = node.next.val;
  node.next = node.next.next;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 删除链表中的节点  
  <https://leetcode-cn.com/problems/delete-node-in-a-linked-list/description/>
* LeetCode problems delete-node-in-a-linked-list  
  <https://leetcode.com/problems/delete-node-in-a-linked-list/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.deleteNodeInALinkedList]: ../../README.md#problemSet.algorithm.deleteNodeInALinkedList "README"
<!-- 链接 结束 -->