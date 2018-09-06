# <a id="palindromeLinkedList"></a>回文链表&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.palindromeLinkedList] #

## 描述 ##

请判断一个链表是否为回文链表。

示例 1:

> 输入: 1->2  
> 输出: false

示例 2:

> 输入: 1->2->2->1  
> 输出: true

进阶：

你能否用 O(n) 时间复杂度和 O(1) 空间复杂度解决此题？

## 解答 ##

数组

`88ms` `77.31%`

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
 * @return {boolean}
 */
var isPalindrome = function(head) {
  let list = [];
  while (head) {
    list.push(head.val);
    head = head.next;
  }
  for (let i = 0; i < list.length / 2; i ++) {
    if (list[i] !== list[list.length - 1 - i]) { return false; }
  }
  return true;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 回文链表  
  <https://leetcode-cn.com/problems/palindrome-linked-list/description/>
* LeetCode problems palindrome-linked-list  
  <https://leetcode.com/problems/palindrome-linked-list/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.palindromeLinkedList]: ../../README.md#problemSet.algorithm.palindromeLinkedList "README"
<!-- 链接 结束 -->