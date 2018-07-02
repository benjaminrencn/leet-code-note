# <a id="sameTree"></a>相同的树&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.sameTree] #

## 描述 ##

给定两个二叉树，编写一个函数来检验它们是否相同。

如果两个树在结构上相同，并且节点具有相同的值，则认为它们是相同的。

示例 1:

> 输入:
> ```
>    1          1
>   / \        / \
>  2   3      2   3
> [1,2,3],   [1,2,3]
> ```
> 输出: true

示例 2:

> 输入:
> ```
>    1          1
>   /            \
>  2              2
> [1,2],     [1,null,2]
> ```
> 输出: false

示例 3:

> 输入:
> ```
>    1          1
>   / \        / \
>  2   1      1   2
> [1,2,1],   [1,1,2]
> ```
> 输出: false

## 解答 ##

递归法

`68ms` `80.22%`

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} p
 * @param {TreeNode} q
 * @return {boolean}
 */
var isSameTree = function(p, q) {
  if ((p === null && q !== null) || (p !== null && q === null)) {
    return false;
  }
  if (p === null && q === null) {
    return true;
  }
  if (p.val !== q.val) {
    return false;
  }
  if ((p.left === null && q.left !== null) || (p.left !== null && q.left === null) || (p.right === null && q.right !== null) || (p.right !== null && q.right === null)) {
    return false;
  }
  if (!isSameTree(p.left, q.left) || !isSameTree(p.right, q.right)) {
    return false;
  }
  return true;
};
```

递归法

`88ms` `24.18%`

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} p
 * @param {TreeNode} q
 * @return {boolean}
 */
var isSameTree = function(p, q) {
  if (!p && !q){
    return true;
  }
  if ((!p && q) || (!q && p) || (p && q && p.val !== q.val)){
    return false;
  }
  return (isSameTree(p.left, q.left) && isSameTree(p.right, q.right));
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 相同的树  
  <https://leetcode-cn.com/problems/same-tree/description/>
* LeetCode problems same-tree  
  <https://leetcode.com/problems/same-tree/description/>
* LeetCode problems same-tree Discuss Seeking for better solution - Tao2014  
  <https://leetcode.com/problems/same-tree/discuss/32939/Simple-JS-solution>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.sameTree]: ../../README.md#problemSet.algorithm.sameTree "README"
<!-- 链接 结束 -->