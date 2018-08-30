# <a id="containsDuplicateII"></a>存在重复元素 II&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.containsDuplicate] #

## 描述 ##

给定一个整数数组和一个整数 k，判断数组中是否存在两个不同的索引 i 和 j，使得 nums [i] = nums [j]，并且 i 和 j 的差的绝对值最大为 k。

示例 1:

> 输入: nums = [1,2,3,1], k = 3  
> 输出: true

示例 2:

> 输入: nums = [1,0,1,1], k = 1  
> 输出: true

示例 3:

> 输入: nums = [1,2,3,1,2,3], k = 2  
> 输出: false

## 解答 ##

哈希法

`104ms` `70.87%`

```javascript
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {boolean}
 */
var containsNearbyDuplicate = function(nums, k) {
  let numMap = {};
  for (let i = 0; i < nums.length; i ++) {
    if (typeof numMap[nums[i]] !== 'undefined') {
      if (i - numMap[nums[i]] <= k) {
        return true;
      }
    }
    numMap[nums[i]] = i;
  }
  return false;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 存在重复元素 II  
  <https://leetcode-cn.com/problems/contains-duplicate-ii/description/>
* LeetCode problems contains-duplicate-ii  
  <https://leetcode.com/problems/contains-duplicate-ii/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.containsDuplicateII]: ../../README.md#problemSet.algorithm.containsDuplicateII "README"
<!-- 链接 结束 -->