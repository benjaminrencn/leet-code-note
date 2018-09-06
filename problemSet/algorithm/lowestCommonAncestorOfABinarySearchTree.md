# <a id="lowestCommonAncestorOfABinarySearchTree"></a>二叉搜索树的最近公共祖先&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.lowestCommonAncestorOfABinarySearchTree] #

## 描述 ##

给定一个二叉搜索树, 找到该树中两个指定节点的最近公共祖先。

百度百科中最近公共祖先的定义为：“对于有根树 T 的两个结点 p、q，最近公共祖先表示为一个结点 x，满足 x 是 p、q 的祖先且 x 的深度尽可能大（一个节点也可以是它自己的祖先）。”

例如，给定如下二叉搜索树:  root = [6,2,8,0,4,7,9,null,null,3,5]

> ```
>      _______6______
>     /              \
>  ___2__          ___8__
> /      \        /      \
> 0      _4       7       9
>       /  \
>       3   5
> ```

示例 1:

> 输入: root = [6,2,8,0,4,7,9,null,null,3,5], p = 2, q = 8  
> 输出: 6  
> 解释: 节点 2 和节点 8 的最近公共祖先是 6。

示例 2:

> 输入: root = [6,2,8,0,4,7,9,null,null,3,5], p = 2, q = 4  
> 输出: 2  
> 解释: 节点 2 和节点 4 的最近公共祖先是 2, 因为根据定义最近公共祖先节点可以为节点本身。

说明:

所有节点的值都是唯一的。  
p、q 为不同节点且均存在于给定的二叉搜索树中。

## 解答 ##

根据 LCA 的定义和 BST 的特性，当 root 非空时可以区分为三种情况：

1. 两个节点均在 root 的左子树，此时对 root->left 递归求解
2. 两个节点均在 root 的右子树，此时对 root->right 递归求解
3. 两个节点分别位于root的左右子树，此时 LCA 为 root

`100ms` `91.67%`

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
 * @param {TreeNode} p
 * @param {TreeNode} q
 * @return {TreeNode}
 */
var lowestCommonAncestor = function(root, p, q) {
  if (!root) { return root }
  if (p.val > root.val && q.val > root.val) {
    return lowestCommonAncestor(root.right, p, q);
  } else if (p.val < root.val && q.val < root.val) {
    return lowestCommonAncestor(root.left, p, q);
  }
  return root;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 二叉搜索树的最近公共祖先  
  <https://leetcode-cn.com/problems/lowest-common-ancestor-of-a-binary-search-tree/description/>
* LeetCode problems lowest-common-ancestor-of-a-binary-search-tree  
  <https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/description/>
* [LeetCode]235 二叉查找树的最近公共父亲节点 - 失失落沙洲  
  <https://blog.csdn.net/qq_14821023/article/details/50761603>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.lowestCommonAncestorOfABinarySearchTree]: ../../README.md#problemSet.algorithm.lowestCommonAncestorOfABinarySearchTree "README"
<!-- 链接 结束 -->