# <a id="plusOne"></a>加一&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.plusOne] #

## 描述 ##

给定一个非负整数组成的非空数组，在该数的基础上加一，返回一个新的数组。

最高位数字存放在数组的首位， 数组中每个元素只存储一个数字。

你可以假设除了整数 0 之外，这个整数不会以零开头。

示例 1:

> 输入: [1,2,3]  
> 输出: [1,2,4]  
> 解释: 输入数组表示数字 123。

示例 2:

> 输入: [4,3,2,1]  
> 输出: [4,3,2,2]  
> 解释: 输入数组表示数字 4321。

## 解答 ##

从右往左加

`68ms` `97.97%`

```javascript
/**
 * @param {number[]} digits
 * @return {number[]}
 */
var plusOne = function(digits) {
  for (let i = digits.length - 1; i >= 0; i --) {
    if (digits[i] < 9) {
      digits[i] ++;
      return digits;
    } else {
      digits[i] = 0;
    }
  }
  digits.unshift(1);
  return digits;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 加一  
  <https://leetcode-cn.com/problems/plus-one/description/>
* LeetCode problems length-of-last-word  
  <https://leetcode.com/problems/plus-one/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.plusOne]: ../../README.md#problemSet.algorithm.plusOne "README"
<!-- 链接 结束 -->