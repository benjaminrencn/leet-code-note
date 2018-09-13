# <a id="intersectionOfTwoArraysII"></a>两个数组的交集 II&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.intersectionOfTwoArraysII] #

## 描述 ##

给定两个数组，编写一个函数来计算它们的交集。

示例 1:

> 输入: nums1 = [1,2,2,1], nums2 = [2,2]  
> 输出: [2,2]

示例 2:

> 输入: nums1 = [4,9,5], nums2 = [9,4,9,8,4]  
> 输出: [4,9]

说明：

* 输出结果中每个元素出现的次数，应与元素在两个数组中出现的次数一致。
* 我们可以不考虑输出结果的顺序。

进阶:

* 如果给定的数组已经排好序呢？你将如何优化你的算法？
* 如果 nums1 的大小比 nums2 小很多，哪种方法更优？
* 如果 nums2 的元素存储在磁盘上，磁盘内存是有限的，并且你不能一次加载所有的元素到内存中，你该怎么办？

## 解答 ##

两个哈希表

`80ms` `79.65%`

```javascript
/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number[]}
 */
var intersect = function(nums1, nums2) {
  let nums1Obj = {};
  let nums2Obj = {};
  for (let i in nums1) {
    nums1Obj[nums1[i]] = nums1Obj[nums1[i]] ? nums1Obj[nums1[i]] + 1 : 1;
  }
  for (let i in nums2) {
    nums2Obj[nums2[i]] = nums2Obj[nums2[i]] ? nums2Obj[nums2[i]] + 1 : 1;
  }

  let temp = {};
  let intersections = [];
  if (Object.keys(nums1Obj).length > Object.keys(nums2Obj).length) {
    temp = nums1Obj;
    nums1Obj = nums2Obj;
    nums2Obj = temp;
  }
  for (let i in nums1Obj) {
    if (nums2Obj[i]) {
      for (let j = 0; j < nums1Obj[i] && j < nums2Obj[i]; j++) {
        intersections.push(+i);
      }
    }
  }
  return intersections;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 两个数组的交集 II  
  <https://leetcode-cn.com/problems/intersection-of-two-arrays-ii/description/>
* LeetCode problems intersection-of-two-arrays-ii  
  <https://leetcode.com/problems/intersection-of-two-arrays-ii/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.intersectionOfTwoArraysII]: ../../README.md#problemSet.algorithm.intersectionOfTwoArraysII "README"
<!-- 链接 结束 -->