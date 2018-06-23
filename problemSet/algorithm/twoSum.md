# <a id="twoSum"></a>1\. 两数之和&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.twoSum] #

## 描述 ##

给定一个整数数组和一个目标值，找出数组中和为目标值的两个数。

你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。

示例:

> 给定 nums = [2, 7, 11, 15], target = 9
>
> 因为 nums[0] + nums[1] = 2 + 7 = 9
> 所以返回 [0, 1]

## 解答 ##

暴力法

114ms

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
  for (var i = 0; i < nums.length - 1; i ++) {
    for (var j = i + 1; j < nums.length; j ++) {
      if (target === nums[i] + nums[j]) {
        return [i, j];
      }
    }
  }

  throw new Error('No two sum solution');
};
```

两遍哈希表

88ms

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
  var object = {};
  for (key in nums) {
    if (object[nums[key]]) {
      object[nums[key]].push(+key);
    } else {
      object[nums[key]] = [+key];
    }
  }
  var difference;
  var keys;
  for (var i = 0; i < nums.length; i ++) {
    difference = target - nums[i];
    keys = object[difference];
    if (difference !== nums[i] && keys) {
      return [i, keys[0]];
    }
    if (difference === nums[i] && keys.length > 1) {
      return [i, keys[1]];
    }
  }

  throw new Error('No two sum solution');
};
```

一遍哈希表

80ms

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
  var object = {};
  var difference;
  var keys;
  for (key in nums) {
    if (object[nums[key]]) {
      object[nums[key]].push(+key);
    } else {
      object[nums[key]] = [+key];
    }

    difference = target - nums[key];
    keys = object[difference];
    if (nums[key] !== difference && keys || nums[key] === difference && keys.length > 1) {
      return [+key, keys[0]];
    }
  }

  throw new Error('No two sum solution');
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 两数之和  
  <https://leetcode-cn.com/problems/two-sum/description/>
* LeetCode problems two-sum  
  <https://leetcode.com/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.twoSum]: ../../README.md#problemSet.algorithm.twoSum "README"
<!-- 链接 结束 -->