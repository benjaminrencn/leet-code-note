# <a id="binaryTreePaths"></a>二叉树的所有路径&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.binaryTreePaths] #

## 描述 ##

给定一个二叉树，返回所有从根节点到叶子节点的路径。

说明: 叶子节点是指没有子节点的节点。

示例:

> 输入:
> ```
>    1
>  /   \
> 2     3
>  \
>   5
> ```
> 输出: ["1->2->5", "1->3"]
>
> 解释: 所有根节点到叶子节点的路径为: 1->2->5, 1->3

## 解答 ##

递归法

`76ms` `86.21%`

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
 * @return {string[]}
 */
var binaryTreePaths = function(root) {
  let paths = [];
  
  getPath(root);

  return paths;

  function getPath(node, path) {
    if (!node) {
      return;
    } else if (node.left || node.right) {
      path = path ? path + '->' + node.val : String(node.val);
      getPath(node.left, path);
      getPath(node.right, path);
    } else if (!node.left && !node.right) {
      path = path ? path + '->' + node.val : String(node.val);
      paths.push(path);
    } else {
      return;
    }
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 二叉树的所有路径  
  <https://leetcode-cn.com/problems/binary-tree-paths/description/>
* LeetCode problems binary-tree-paths  
  <https://leetcode.com/problems/binary-tree-paths/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.binaryTreePaths]: ../../README.md#problemSet.algorithm.binaryTreePaths "README"
<!-- 链接 结束 -->