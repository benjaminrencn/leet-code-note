# <a id="missingNumber"></a>缺失数字&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.missingNumber] #

## 描述 ##

给定一个包含 0, 1, 2, ..., n 中 n 个数的序列，找出 0 .. n 中没有出现在序列中的那个数。

示例 1:

> 输入: [3,0,1]  
> 输出: 2

示例 2:

> 输入: [9,6,4,2,3,5,7,0,1]  
> 输出: 8

说明:

你的算法应具有线性时间复杂度。你能否仅使用额外常数空间来实现?

## 解答 ##

排序 遍历

`152ms` `39.41%`

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var missingNumber = function(nums) {
  nums.sort(function (a, b) {
    return a > b ? 1 : -1;
  }) ;
  for (let i = 0; i < nums.length; i ++) {
    if (nums[i] !== i) {
      return i;
    }
  }
  return nums.length;
};
```

长度总数减数组和

`80ms` `87.68%`

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var missingNumber = function(nums) {
  var sum = 0;
  for (let i in nums) {
    sum += nums[i]
  }
  return ((nums.length * (nums.length + 1)) / 2) - sum;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 缺失数字  
  <https://leetcode-cn.com/problems/missing-number/description/>
* LeetCode problems missing-number  
  <https://leetcode.com/problems/missing-number/description/>
* LeetCode problems missing-number 范例
  <https://leetcode-cn.com/submissions/detail/6689530/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.missingNumber]: ../../README.md#problemSet.algorithm.missingNumber "README"
<!-- 链接 结束 -->