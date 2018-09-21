# <a id="sumOfLeftLeaves"></a>左叶子之和&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.sumOfLeftLeaves] #

## 描述 ##

计算给定二叉树的所有左叶子之和。

示例：
> ```
>   3
>  / \
> 9  20
>   /  \
>  15   7
> ```

在这个二叉树中，有两个左叶子，分别是 9 和 15，所以返回 24

## 解答 ##

递归法

`80ms` `63.33%`

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
var sumOfLeftLeaves = function(root) {
  let sum = 0;
  leftLeave(root);
  return sum;

  function leftLeave(node) {
    if (!node || !node.left && !node.right) {
      return;
    }
    if (node.left && !node.left.left && !node.left.right) {
      console.log(node.left.val);
      sum += node.left.val;
    }
    if (node.left) {
      leftLeave(node.left);
    }
    if (node.right) {
      leftLeave(node.right);
    }
    return;
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 左叶子之和  
  <https://leetcode-cn.com/problems/sum-of-left-leaves/description/>
* LeetCode problems sum-of-left-leaves  
  <https://leetcode.com/problems/sum-of-left-leaves/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.sumOfLeftLeaves]: ../../README.md#problemSet.algorithm.sumOfLeftLeaves "README"
<!-- 链接 结束 -->