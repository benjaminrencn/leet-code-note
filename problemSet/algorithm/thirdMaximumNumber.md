# <a id="thirdMaximumNumber"></a>第三大的数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.thirdMaximumNumber] #

## 描述 ##

给定一个非空数组，返回此数组中第三大的数。如果不存在，则返回数组中最大的数。要求算法时间复杂度必须是O(n)。

示例 1:

> 输入: [3, 2, 1]  
> 输出: 1
>
> 解释: 第三大的数是 1.

示例 2:

> 输入: [1, 2]  
> 输出: 2
>
> 解释: 第三大的数不存在, 所以返回最大的数 2 .

示例 3:

> 输入: [2, 2, 3, 1]  
> 输出: 1
>
> 解释: 注意，要求返回第三大的数，是指第三大且唯一出现的数。  
> 存在两个值为2的数，它们都排第二。

## 解答 ##

Object 去重 Array.sort 排序

`135ms` `35.71%`

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var thirdMax = function(nums) {
  var map = {};
  var array = [];
  
  for (let i in nums) {
    map[nums[i]] = true;
  }
  array = Object.keys(map);
  for (let i in array) {
    array[i] = +array[i];
  }
  array.sort(function (a, b) {
    return a > b ? 1 : -1;
  });
  if (array.length >= 3) {
    return array[array.length - 3];
  } else {
    return array[array.length - 1];
  }
};
```

3个最值变量

`72ms` `97.26%`

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var thirdMax = function(nums) {
  let max1, max2, max3;

  for (let i in nums) {
    setMax(nums[i]);
  }

  if (typeof max3 === 'undefined') {
    return max1; 
  } else {
    return max3;
  }

  function setMax(number) {
    if (typeof max1 === 'undefined') {
      max1 = number;
      return;
    }
    if (number > max1) {
      if (typeof max2 === 'undefined') {
        max2 = max1;
        max1 = number;
        return;
      }
      max3 = max2;
      max2 = max1;
      max1 = number;
      return;
    }
    if (number === max1) {
      return;
    }
    if (typeof max2 === 'undefined') {
      max2 = number;
      return;
    }
    if (number > max2) {
      max3 = max2;
      max2 = number;
      return;
    }
    if (number === max2) {
      return;
    }
    if (typeof max3 === 'undefined' || number > max3) {
      max3 = number;
      return;
    }
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 第三大的数  
  <https://leetcode-cn.com/problems/third-maximum-number/description/>
* LeetCode problems third-maximum-number  
  <https://leetcode.com/problems/third-maximum-number/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.thirdMaximumNumber]: ../../README.md#problemSet.algorithm.thirdMaximumNumber "README"
<!-- 链接 结束 -->