# <a id="convertSortedArrayToBinarySearchTree"></a>将有序数组转换为二叉搜索树&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.convertSortedArrayToBinarySearchTree] #

## 描述 ##

将一个按照升序排列的有序数组，转换为一棵高度平衡二叉搜索树。

本题中，一个高度平衡二叉树是指一个二叉树每个节点 的左右两个子树的高度差的绝对值不超过 1。

示例:

给定有序数组: [-10,-3,0,5,9],

一个可能的答案是：[0,-3,9,-10,null,5]，它可以表示下面这个高度平衡二叉搜索树：

```
      0
     / \
   -3   9
   /   /
 -10  5
```

## 解答 ##

递归法

`128ms` `14.06%`

```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {number[]} nums
 * @return {TreeNode}
 */
var sortedArrayToBST = function(nums) {
  if (nums.length === 0) {
    return null
  }
  
  const middle = Math.floor(nums.length / 2);
  const root = new TreeNode(nums[middle]);
  root.left = sortedArrayToBST(nums.slice(0, middle));
  root.right = sortedArrayToBST(nums.slice(middle + 1, nums.length));

  return root;
};
```

二分法

## 参考 ##

* LeetCode (中国) 题库 算法 将有序数组转换为二叉搜索树  
  <https://leetcode-cn.com/problems/convert-sorted-array-to-binary-search-tree/description/>
* LeetCode problems convert-sorted-array-to-binary-search-tree  
  <https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/description/>
* LeetCode problems convert-sorted-array-to-binary-search-tree Discuss 84ms js version - technicalcute
  <https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/discuss/117440/84ms-js-version>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.convertSortedArrayToBinarySearchTree]: ../../README.md#problemSet.algorithm.convertSortedArrayToBinarySearchTree "README"
<!-- 链接 结束 -->