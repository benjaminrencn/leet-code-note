# <a id="binaryTreeLevelOrderTraversalII"></a>二叉树的层次遍历 II&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.binaryTreeLevelOrderTraversalII] #

## 描述 ##

给定一个二叉树，返回其节点值自底向上的层次遍历。 （即按从叶子节点所在层到根节点所在的层，逐层从左向右遍历）

例如：
给定二叉树 [3,9,20,null,null,15,7],

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

## 解答 ##

递归法

`84ms` `41.03%`

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[][]}
 */
var levelOrderBottom = function(root) {
  let levels = [], length, level = 1;
  getNodes(root, 1);
  return levels;

  function getNodes(node, level) {
    if (!node) {
      return;
    }
    while (levels.length < level) {
      levels.unshift([]);
    }
    length = levels.length;
    levels[length - level].push(node.val);
    getNodes(node.left, level + 1);
    getNodes(node.right, level + 1);
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 二叉树的层次遍历 II  
  <https://leetcode-cn.com/problems/binary-tree-level-order-traversal-ii/description/>
* LeetCode problems binary-tree-level-order-traversal-ii  
  <https://leetcode.com/problems/binary-tree-level-order-traversal-ii/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.binaryTreeLevelOrderTraversalII]: ../../README.md#problemSet.algorithm.binaryTreeLevelOrderTraversalII "README"
<!-- 链接 结束 -->