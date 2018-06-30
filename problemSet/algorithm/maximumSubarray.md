# <a id="maximumSubarray"></a>最大子序和&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.maximumSubarray] #

## 描述 ##

给定一个整数数组 nums ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。

示例:

> 输入: [-2,1,-3,4,-1,2,1,-5,4],  
> 输出: 6  
> 解释: 连续子数组 [4,-1,2,1] 的和最大，为 6。

进阶:

如果你已经实现复杂度为 O(n) 的解法，尝试使用更为精妙的分治法求解。

## 解答 ##

Kadane 算法

`84ms` `79.83%`

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function(nums) {
  let currentSum = nums[0];
  let totalSum = nums[0];

  for (let i = 1; i < nums.length; i ++) {
    currentSum = Math.max(nums[i], currentSum + nums[i]);
    totalSum = Math.max(totalSum, currentSum);
  }

  return totalSum;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 最大子序和  
  <https://leetcode-cn.com/problems/maximum-subarray/description/>
* LeetCode problems maximum-subarray  
  <https://leetcode.com/problems/maximum-subarray/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.maximumSubarray]: ../../README.md#problemSet.algorithm.maximumSubarray "README"
<!-- 链接 结束 -->