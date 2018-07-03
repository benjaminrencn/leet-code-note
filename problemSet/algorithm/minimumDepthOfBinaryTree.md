# <a id="minimumDepthOfBinaryTree"></a>二叉树的最小深度&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.minimumDepthOfBinaryTree] #

## 描述 ##

给定一个二叉树，找出其最小深度。

最小深度是从根节点到最近叶子节点的最短路径上的节点数量。

说明: 叶子节点是指没有子节点的节点。

示例:

给定二叉树 [3,9,20,null,null,15,7],

```
    3
   / \
  9  20
    /  \
   15   7
```

返回它的最小深度  2.

## 解答 ##

递归法

`88ms` `80.49%`

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
var minDepth = function(root) {
  if (root === null) {
    return 0;
  }

  let left = minDepth(root.left);
  let right = minDepth(root.right);

  return left === 0 || right === 0 ? left + right + 1 : Math.min(left, right) + 1;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 二叉树的最小深度  
  <https://leetcode-cn.com/problems/minimum-depth-of-binary-tree/description/>
* LeetCode problems minimum-depth-of-binary-tree  
  <https://leetcode.com/problems/minimum-depth-of-binary-tree/description/>
* LeetCode problems minimum-depth-of-binary-tree Discuss My 4 Line java solution - caiqi8877  
  <https://leetcode.com/problems/minimum-depth-of-binary-tree/discuss/36045/My-4-Line-java-solution>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.minimumDepthOfBinaryTree]: ../../README.md#problemSet.algorithm.minimumDepthOfBinaryTree "README"
<!-- 链接 结束 -->