# <a id="intersectionOfTwoLinkedLists"></a>相交链表&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.intersectionOfTwoLinkedLists] #

## 描述 ##

编写一个程序，找到两个单链表相交的起始节点。

注意：

* 如果两个链表没有交点，返回 null.
* 在返回结果后，两个链表仍须保持原有的结构。
* 可假定整个链表结构中没有循环。
* 程序尽量满足 O(n) 时间复杂度，且仅用 O(1) 内存。

## 解答 ##

哈希法

`128ms` `48.39%`

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} headA
 * @param {ListNode} headB
 * @return {ListNode}
 */
var getIntersectionNode = function(headA, headB) {
  if (!headA || !headB) { return null; }
  let aVals = {};
  while (headA) {
    aVals[headA.val] = true;
    headA = headA.next;
  }
  while (headB) {
    if (aVals[headB.val]) {
      return headB;
    }
    headB = headB.next;
  }
  return null;
};
```

两次遍历

`124ms` `61.29%`

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} headA
 * @param {ListNode} headB
 * @return {ListNode}
 */
var getIntersectionNode = function(headA, headB) {
  if (!headA || !headB) { return null; }
  if (headA.val === headB.val) { return headA; }

  while (headA) {
    headA.visited = true;
    headA = headA.next;
  }
  while (headB) {
    if (headB.visited) { return headB; }
    headB = headB.next;
  }
  return null;
};
```

一次循环

`168ms` `11.29%`

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} headA
 * @param {ListNode} headB
 * @return {ListNode}
 */
var getIntersectionNode = function(headA, headB) {
  if (!headA || !headB) { return null; }
  if (headA.val === headB.val) { return headA; }

  while (headA || headB) {
    if (headA) {
      if (headA.visited) { return headA; }
      headA.visited = true;
      headA = headA.next;
    }
    if (headB) {
      if (headB.visited) { return headB; }
      headB.visited = true;
      headB = headB.next;
    }
  }
  return null
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 相交链表  
  <https://leetcode-cn.com/problems/min-stack/description/>
* LeetCode problems intersection-of-two-linked-lists  
  <https://leetcode.com/problems/intersection-of-two-linked-lists/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.intersectionOfTwoLinkedLists]: ../../README.md#problemSet.algorithm.intersectionOfTwoLinkedLists "README"
<!-- 链接 结束 -->