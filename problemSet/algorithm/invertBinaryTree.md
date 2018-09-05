# <a id="invertBinaryTree"></a>翻转二叉树&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.invertBinaryTree] #

## 描述 ##

翻转一棵二叉树。

示例：

输入：

> ```
>      4
>    /   \
>   2     7
>  / \   / \
> 1   3 6   9
> ```

输出：

> ```
>      4
>    /   \
>   7     2
>  / \   / \
> 9   6 3   1
> ```

## 解答 ##

递归法

`88ms` `29.79%`

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
 * @return {TreeNode}
 */
var invertTree = function(root) {
  if (!root) { return null; }
  let temp = root.left;

  invertTree(root.left);
  invertTree(root.right);
  root.left = root.right;
  root.right = temp;

  return root;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 翻转二叉树  
  <https://leetcode-cn.com/problems/invert-binary-tree/description/>
* LeetCode problems invert-binary-tree  
  <https://leetcode.com/problems/invert-binary-tree/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.invertBinaryTree]: ../../README.md#problemSet.algorithm.invertBinaryTree "README"
<!-- 链接 结束 -->