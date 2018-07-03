# <a id="mergeSortedArray"></a>合并两个有序数组&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.mergeSortedArray] #

## 描述 ##

给定两个有序整数数组 nums1 和 nums2，将 nums2 合并到 nums1 中，使得 num1 成为一个有序数组。

说明:

* 初始化 nums1 和 nums2 的元素数量分别为 m 和 n。
* 你可以假设 nums1 有足够的空间（空间大小大于或等于 m + n）来保存 nums2 中的元素。

示例:

> 输入:  
> nums1 = [1,2,3,0,0,0], m = 3  
> nums2 = [2,5,6], n = 3
>
> 输出: [1,2,2,3,5,6]

## 解答 ##

从右到左

`68ms` `97.00%`

```javascript
/**
 * @param {number[]} nums1
 * @param {number} m
 * @param {number[]} nums2
 * @param {number} n
 * @return {void} Do not return anything, modify nums1 in-place instead.
 */
var merge = function(nums1, m, nums2, n) {
  while (n > 0) {
    nums1[m + n - 1] = (m === 0 || nums2[n - 1] > nums1[m - 1]) ? nums2[-- n] : nums1[-- m];
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 合并两个有序数组  
  <https://leetcode-cn.com/problems/merge-sorted-array/description/>
* LeetCode problems merge-sorted-array  
  <https://leetcode.com/problems/merge-sorted-array/description/>
* LeetCode problems merge-sorted-array Discuss 1 Line Solution - fabrizio3  
  <https://leetcode.com/problems/merge-sorted-array/discuss/29505/1-Line-Solution>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.mergeSortedArray]: ../../README.md#problemSet.algorithm.mergeSortedArray "README"
<!-- 链接 结束 -->