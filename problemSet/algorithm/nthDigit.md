# <a id="nthDigit"></a>第N个数字&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.nthDigit] #

## 描述 ##

在无限的整数序列 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, ...中找到第 n 个数字。

注意:

n 是正数且在32为整形范围内 ( n < 231)。

示例 1:

> 输入:  
> 3
>
> 输出:  
> 3

示例 2:

> 输入:  
> 11
>
> 输出:  
> 0

说明:

第11个数字在序列 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, ... 里是0，它是10的一部分。

## 解答 ##

迭代法

`76ms` `44.44%`

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var findNthDigit = function(n) {
  let i = 1, base = 9 * Math.pow(10, i - 1) * i, digit = 0;

  while (n > base) {
    n -= base;
    i ++;
    base = 9 * Math.pow(10, i - 1) * i;
  }
  digit = Math.pow(10, i - 1) + Math.floor((n - 1) / i);
  return +String(digit)[(n - 1) % i];
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 第N个数字  
  <https://leetcode-cn.com/problems/nth-digit/description/>
* LeetCode problems nth-digit  
  <https://leetcode.com/problems/nth-digit/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.nthDigit]: ../../README.md#problemSet.algorithm.nthDigit "README"
<!-- 链接 结束 -->