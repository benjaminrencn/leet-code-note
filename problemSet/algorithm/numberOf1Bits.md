# <a id="numberOf1Bits"></a>位1的个数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.numberOf1Bits] #

## 描述 ##

编写一个函数，输入是一个无符号整数，返回其二进制表达式中数字位数为 ‘1’ 的个数（也被称为汉明重量）。

示例 :

> 输入: 11  
> 输出: 3  
> 解释: 整数 11 的二进制表示为 00000000000000000000000000001011

示例 2:

> 输入: 128  
> 输出: 1  
> 解释: 整数 128 的二进制表示为 00000000000000000000000010000000

## 解答 ##

toString

`88ms` `81.50%`

```javascript
/**
 * @param {number} n - a positive integer
 * @return {number}
 */
var hammingWeight = function(n) {
  let bits = n.toString(2);
  let count = 0;
  for (let i in bits) {
    if (+bits[i]) {
      count ++;
    }
  }
  return count;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 位1的个数  
  <https://leetcode-cn.com/problems/number-of-1-bits/description/>
* LeetCode problems number-of-1-bits  
  <https://leetcode.com/problems/number-of-1-bits/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.numberOf1Bits]: ../../README.md#problemSet.algorithm.numberOf1Bits "README"
<!-- 链接 结束 -->