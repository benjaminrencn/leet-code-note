# <a id="majorityElement"></a>求众数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.majorityElement] #

## 描述 ##

给定一个大小为 n 的数组，找到其中的众数。众数是指在数组中出现次数大于 ⌊ n/2 ⌋ 的元素。

你可以假设数组是非空的，并且给定的数组总是存在众数。

示例 1:

> 输入: [3,2,3]  
> 输出: 3

示例 2:

> 输入: [2,2,1,1,1,2,2]  
> 输出: 2

## 解答 ##

哈希法

`84ms` `86.29%`

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var majorityElement = function(nums) {
  let length = nums.length;
  let numCounts = {};
  for (let i = 0; i < length; i ++) {
    numCounts[nums[i]] = numCounts[nums[i]] ? ++numCounts[nums[i]] : 1;
    if (numCounts[nums[i]] >= length / 2) {
      return nums[i];
    }
  }
  return;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 求众数  
  <https://leetcode-cn.com/problems/majority-element/description/>
* LeetCode problems majority-element  
  <https://leetcode.com/problems/majority-element/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.majorityElement]: ../../README.md#problemSet.algorithm.majorityElement "README"
<!-- 链接 结束 -->