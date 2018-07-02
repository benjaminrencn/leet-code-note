# <a id="symmetricTree"></a>对称二叉树&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.symmetricTree] #

## 描述 ##

给定一个二叉树，检查它是否是镜像对称的。

例如，二叉树 [1,2,2,3,4,4,3] 是对称的。
```
    1
   / \
  2   2
 / \ / \
3  4 4  3
```

但是下面这个 [1,2,2,null,3,null,3] 则不是镜像对称的:
```
    1
   / \
  2   2
   \   \
   3    3
```

说明:

如果你可以运用递归和迭代两种方法解决这个问题，会很加分。

## 解答 ##

递归法

`84ms` `72.00%`

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
var isSymmetric = function(root) {
  if (!root || !root.left && !root.right) {
    return true;
  }
  if ((root.left && !root.right) || (!root.left && root.right) || (root.left && root.right && root.left.val !== root.right.val)) {
    return false;
  }
  return isSymmetric2(root.left, root.right);

  function isSymmetric2(left, right) {
    if (!left && !right || (left && right && left.val === right.val && isSymmetric2(left.left, right.right) && isSymmetric2(left.right, right.left))) {
      return true;
    } else {
      return false;
    }
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 对称二叉树  
  <https://leetcode-cn.com/problems/symmetric-tree/description/>
* LeetCode problems same-tree  
  <https://leetcode.com/problems/symmetric-tree/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.symmetricTree]: ../../README.md#problemSet.algorithm.symmetricTree "README"
<!-- 链接 结束 -->