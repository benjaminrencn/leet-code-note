# <a id="pathSum"></a>路径总和&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.pathSum] #

## 描述 ##

给定一个二叉树和一个目标和，判断该树中是否存在根节点到叶子节点的路径，这条路径上所有节点值相加等于目标和。

说明: 叶子节点是指没有子节点的节点。

示例:
给定如下二叉树，以及目标和 `sum = 22`，

```
       5
      / \
     4   8
    /   / \
  11  13   4
 /  \       \
7    2       1
```

返回 `true`, 因为存在目标和为 22 的根节点到叶子节点的路径 `5->4->11->2`。

## 解答 ##

`88ms` `85.37%`

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
 * @param {number} sum
 * @return {boolean}
 */
var hasPathSum = function(root, sum) {
  if (!root) {
    return false;
  }
  if (root.val === sum && !root.left && !root.right) {
    return true;
  }
  return hasPathSum(root.left, sum - root.val) || hasPathSum(root.right, sum - root.val);
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 路径总和  
  <https://leetcode-cn.com/problems/path-sum/description/>
* LeetCode problems path-sum  
  <https://leetcode.com/problems/path-sum/description/>
* LeetCode problems path-sum Discuss 3 lines of  c++ solution - pankit  
  <https://leetcode.com/problems/path-sum/discuss/36367/3-lines-of-c++-solution>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.pathSum]: ../../README.md#problemSet.algorithm.pathSum "README"
<!-- 链接 结束 -->