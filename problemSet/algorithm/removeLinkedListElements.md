# <a id="removeLinkedListElements"></a>删除链表中的节点&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.removeLinkedListElements] #

## 描述 ##

删除链表中等于给定值 val 的所有节点。

示例:

> 输入: 1->2->6->3->4->5->6, val = 6  
> 输出: 1->2->3->4->5

## 解答 ##

递归法

`128ms` `16.85%`

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
 * @param {number} val
 * @return {ListNode}
 */
var removeElements = function(head, val) {
  if (!head) { return head; }
  head.next = removeElements(head.next, val);
  return head.val === val ? head.next : head;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 删除链表中的节点  
  <https://leetcode-cn.com/problems/remove-linked-list-elements/description/>
* LeetCode problems remove-linked-list-elements  
  <https://leetcode.com/problems/remove-linked-list-elements/description/>
* LeetCode problems remove-linked-list-elements Discuss 3 line recursive solution - renzid  
  <https://leetcode.com/problems/remove-linked-list-elements/discuss/57306/3-line-recursive-solution>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.removeLinkedListElements]: ../../README.md#problemSet.algorithm.removeLinkedListElements "README"
<!-- 链接 结束 -->