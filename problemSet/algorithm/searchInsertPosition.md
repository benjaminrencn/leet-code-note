# <a id="searchInsertPosition"></a>搜索插入位置&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.searchInsertPosition] #

## 描述 ##

给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组中，返回它将会被按顺序插入的位置。

你可以假设数组中无重复元素。

示例 1:

> 输入: [1,3,5,6], 5
> 输出: 2

示例 2:

> 输入: [1,3,5,6], 2
> 输出: 1

示例 3:

> 输入: [1,3,5,6], 7
> 输出: 4

示例 4:

> 输入: [1,3,5,6], 0
> 输出: 0

## 解答 ##

indexOf 加遍历插入

72ms

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var searchInsert = function(nums, target) {
  let i = nums.indexOf(target);
  if (i !== -1) {
    return i;
  }
  for (let j = 0; j < nums.length; j ++) {
    if (target < nums[j]) {
      nums.splice(j, 0, target);
      return j;
    }
  }
  nums.splice(nums.length, 0, target);
  return nums.length - 1;
};
```

indexOf 加遍历

76ms

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var searchInsert = function(nums, target) {
  let i = nums.indexOf(target);
  if (i !== -1) {
    return i;
  }
  for (let j in nums) {
    if (target < nums[j]) {
      return +j;
    }
  }
  return nums.length;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 搜索插入位置  
  <https://leetcode-cn.com/problems/search-insert-position/description/>
* LeetCode problems search-insert-position  
  <https://leetcode.com/problems/search-insert-position/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.searchInsertPosition]: ../../README.md#problemSet.algorithm.searchInsertPosition "README"
<!-- 链接 结束 -->