# <a id="intersectionOfTwoArrays"></a>两个数组的交集&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.intersectionOfTwoArrays] #

## 描述 ##

给定两个数组，编写一个函数来计算它们的交集。

示例 1:

> 输入: nums1 = [1,2,2,1], nums2 = [2,2]  
> 输出: [2]

示例 2:

> 输入: nums1 = [4,9,5], nums2 = [9,4,9,8,4]  
> 输出: [9,4]

说明:

* 输出结果中的每个元素一定是唯一的。
* 我们可以不考虑输出结果的顺序。

## 解答 ##

一个哈希表

`68ms` `99.55%`

```javascript
/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number[]}
 */
var intersection = function(nums1, nums2) {
  let temp;
  let intersectionObject = {};
  let intersections = [];

  if (nums1.length > nums2.length) {
    temp = nums1;
    nums1 = nums2;
    nums2 = temp;
  }

  for (let i = 0; i < nums1.length; i ++) {
    if (nums2.indexOf(nums1[i]) > -1) {
      intersectionObject[nums1[i]] = true;
    }
  }

  intersectionObject = Object.keys(intersectionObject);
  for (let i in intersectionObject) {
    intersections.push(+intersectionObject[i])
  }

  return intersections;
};
```

两个哈希表

`80ms` `84.68%`

```javascript
/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number[]}
 */
var intersection = function(nums1, nums2) {
  let nums1Obj = {};
  let nums2Obj = {};
  for (let i in nums1) {
    nums1Obj[nums1[i]] = true;
  }
  for (let i in nums2) {
    nums2Obj[nums2[i]] = true;
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
      intersections.push(+i);
    }
  }
  return intersections;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 两个数组的交集  
  <https://leetcode-cn.com/problems/intersection-of-two-arrays/description/>
* LeetCode problems intersection-of-two-arrays  
  <https://leetcode.com/problems/intersection-of-two-arrays/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.intersectionOfTwoArrays]: ../../README.md#problemSet.algorithm.intersectionOfTwoArrays "README"
<!-- 链接 结束 -->