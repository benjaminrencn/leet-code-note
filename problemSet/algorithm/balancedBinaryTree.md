# <a id="balancedBinaryTree"></a>平衡二叉树&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.balancedBinaryTree] #

## 描述 ##

给定一个二叉树，判断它是否是高度平衡的二叉树。

本题中，一棵高度平衡二叉树定义为：

> 一个二叉树每个节点 的左右两个子树的高度差的绝对值不超过1。

示例 1:

给定二叉树 `[3,9,20,null,null,15,7]`

```
    3
   / \
  9  20
    /  \
   15   7
```

返回 `true` 。

示例 2:

给定二叉树 `[1,2,2,3,3,null,null,4,4]`

```
      1
     / \
    2   2
   / \
  3   3
 / \
4   4
```

返回 `false` 。

## 解答 ##

递归法 I

`140ms` `2.86%`

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
 * @return {boolean}
 */
var isBalanced = function(root) {
  if (!root) {
    return true;
  }

  let left = getDepth(root.left);
  let right = getDepth(root.right);

  return Math.abs(left - right) <= 1 && isBalanced(root.left) && isBalanced(root.right);

  function getDepth(node) {
    if (!node) {
      return 0;
    }

    return Math.max(getDepth(node.left), getDepth(node.right)) + 1;
  }
};
```

递归法 II

`116ms` `5.71%`

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
 * @return {boolean}
 */
var isBalanced = function(root) {
  return getDepth(root) !== -1;
  
  function getDepth(node) {
    if (!node) {
      return 0;
    }

    const left = getDepth(node.left);
    const right = getDepth(node.right);
    if (left === -1 || right === -1 || Math.abs(left - right) > 1) {
      return -1;
    } else {
      return 1 + Math.max(left, right);
    }
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 平衡二叉树  
  <https://leetcode-cn.com/problems/balanced-binary-tree/>
* LeetCode problems balanced-binary-tree  
  <https://leetcode.com/problems/balanced-binary-tree/description/>
* LeetCode problems balanced-binary-tree Discuss The bottom up O(N) solution would be better - benlong  
  <https://leetcode.com/problems/balanced-binary-tree/discuss/35691/The-bottom-up-O(N)-solution-would-be-better>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.balancedBinaryTree]: ../../README.md#problemSet.algorithm.balancedBinaryTree "README"
<!-- 链接 结束 -->