# <a id="moveZeroes"></a>移动零&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.moveZeroes] #

## 描述 ##

给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。

示例:

> 输入: [0,1,0,3,12]  
> 输出: [1,3,12,0,0]

说明:

1. 必须在原数组上操作，不能拷贝额外的数组。
2. 尽量减少操作次数

## 解答 ##

暴力法

`108ms` `31.19%`

```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var moveZeroes = function(nums) {
  let i = 0, j = 0, temp = 0;
  for (i = 0; i < nums.length; i ++) {
    if (!nums[i]) { continue; }
    for (j = i; j > 0 && !nums[j - 1]; j --) {
      temp = nums[j - 1];
      nums[j - 1] = nums[j];
      nums[j] = temp;
    }
  }
};
```

双指针法

`108ms` `31.19%`

```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var moveZeroes = function(nums) {
  let i = 0, j = 0;
  for (i = 0; i < nums.length; i ++) {
    if (nums[i] !== 0) {
      nums[j ++] = nums[i];
    }
  }
  while (j < nums.length) {
    nums[j ++] = 0;
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 移动零  
  <https://leetcode-cn.com/problems/move-zeroes/description/>
* LeetCode problems move-zeroes  
  <https://leetcode.com/problems/move-zeroes/description/>
* LeetCode problems move-zeroes Discuss Java solution two pointers - AnShafs
  <https://leetcode.com/problems/move-zeroes/discuss/167932/Java-solution-two-pointers>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.moveZeroes]: ../../README.md#problemSet.algorithm.moveZeroes "README"
<!-- 链接 结束 -->