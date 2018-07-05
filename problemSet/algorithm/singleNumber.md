# <a id="singleNumber"></a>只出现一次的数字&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.singleNumber] #

## 描述 ##

给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。

说明：

你的算法应该具有线性时间复杂度。 你可以不使用额外空间来实现吗？

示例 1:

> 输入: [2,2,1]  
> 输出: 1

示例 2:

> 输入: [4,1,2,1,2]  
> 输出: 4

## 解答 ##

indexOf

`460ms` `16.51%`

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var singleNumber = function(nums) {
  let i = 0, index;
  while (i < nums.length) {
    index = nums.indexOf(nums[i], i + 1);
    if (index === -1 || i === nums.length - 1) {
      return nums[i];
    } else {
      nums[i] = nums[index] = NaN;
      while (isNaN(nums[++ i])) {}
    }
  }
};
```

异或

`108ms` `50.12%`

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var singleNumber = function(nums) {
  let result = 0;
  for (let i = 0; i < nums.length; i ++) {
    result ^= nums[i];
  }
  return result;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 只出现一次的数字  
  <https://leetcode-cn.com/problems/single-number/description/>
* LeetCode problems single-number  
  <https://leetcode.com/problems/single-number/description/>
* LeetCode problems single-number Discuss My O(n) solution using XOR - Ivantsang  
  <https://leetcode.com/problems/single-number/discuss/42997/My-O(n)-solution-using-XOR>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.singleNumber]: ../../README.md#problemSet.algorithm.singleNumber "README"
<!-- 链接 结束 -->