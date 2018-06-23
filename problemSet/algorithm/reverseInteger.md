# <a id="reverseInteger"></a>7. 反转整数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.reverseInteger] #

## 描述 ##

给定一个 32 位有符号整数，将整数中的数字进行反转。

示例 1:

> 输入: 123  
> 输出: 321

示例 2:

> 输入: -123  
> 输出: -321

示例 3:

> 输入: 120  
> 输出: 21

注意:

假设我们的环境只能存储 32 位有符号整数，其数值范围是 [−231,  231 − 1]。根据这个假设，如果反转后的整数溢出，则返回 0。

## 解答 ##

字符反转

100ms

```javascript
/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(x) {
  var minusFlag = x < 0;
  var number = +String(Math.abs(x)).split('').reverse().join('');
  number = minusFlag ? -number : number;
  if (number < -Math.pow(2, 31) || number > Math.pow(2, 31) - 1) {
    return 0;
  }
  return number;
};
```

数字反转

100ms

```javascript
/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(x) {
  var reverse = 0;
  var remainder;
  while (x !== 0) {
    remainder = x % 10;
    x = Math.trunc(x / 10);
    reverse = reverse * 10 + remainder;
    if (reverse < Math.pow(-2, 31) || reverse > Math.pow(2, 31) - 1) {
      return 0;
    }
  }
  return reverse;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 两数之和  
  <https://leetcode-cn.com/problems/reverse-integer/description/>
* LeetCode problems two-sum  
  <https://leetcode.com/problems/reverse-integer/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.reverseInteger]: ../../README.md#problemSet.algorithm.reverseInteger "README"
<!-- 链接 结束 -->