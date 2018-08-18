# <a id="reverseBits"></a>颠倒二进制位&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.reverseBits] #

## 描述 ##

颠倒给定的 32 位无符号整数的二进制位。

示例:

> 输入: 43261596  
> 输出: 964176192  
> 解释: 43261596 的二进制表示形式为 00000010100101000001111010011100 ，  
> 返回 964176192，其二进制表示形式为 00111001011110000010100101000000 。

进阶:  
如果多次调用这个函数，你将如何优化你的算法？

## 解答 ##

parseInt  toString reverse

`96ms` `86.11%`

```javascript
/**
 * @param {number} n - a positive integer
 * @return {number} - a positive integer
 */
var reverseBits = function(n) {
  return parseInt(('00000000000000000000000000000000'.slice(((n).toString(2).length - 32) || 32) + n.toString(2)).split('').reverse().join(''), 2);
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 颠倒二进制位  
  <https://leetcode-cn.com/problems/reverse-bits/description/>
* LeetCode problems reverse-bits  
  <https://leetcode.com/problems/reverse-bits/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.reverseBits]: ../../README.md#problemSet.algorithm.reverseBits "README"
<!-- 链接 结束 -->