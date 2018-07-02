# <a id="maximumDepthOfBinaryTree"></a>二叉树的最大深度&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.maximumDepthOfBinaryTree] #

## 描述 ##

给定一个二叉树，找出其最大深度。

二叉树的深度为根节点到最远叶子节点的最长路径上的节点数。

说明: 叶子节点是指没有子节点的节点。

示例：
给定二叉树 [3,9,20,null,null,15,7]，

```
    3
   / \
  9  20
    /  \
   15   7
```

返回它的最大深度 3 。

## 解答 ##

递归法

`96ms` `41.58%`

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
 * @return {number}
 */
var maxDepth = function(root) {
  if (root === null) {
    return 0;
  }
  return 1 + Math.max(maxDepth(root.left), maxDepth(root.right));
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 二叉树的最大深度  
  <https://leetcode-cn.com/problems/maximum-depth-of-binary-tree/description/>
* LeetCode problems maximum-depth-of-binary-tree  
  <https://leetcode.com/problems/maximum-depth-of-binary-tree/description/>
* LeetCode problems maximum-depth-of-binary-tree Discuss Simple solution using Java - ray050899
  <https://leetcode.com/problems/maximum-depth-of-binary-tree/discuss/34216/Simple-solution-using-Java>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.maximumDepthOfBinaryTree]: ../../README.md#problemSet.algorithm.maximumDepthOfBinaryTree "README"
<!-- 链接 结束 -->