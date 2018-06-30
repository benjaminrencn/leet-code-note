# <a id="palindromeNumber"></a>回文数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.palindromeNumber] #

## 描述 ##

判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。

示例 1:

> 输入: 121  
> 输出: true

示例 2:

> 输入: -121  
> 输出: false  
> 解释: 从左向右读, 为 -121 。 从右向左读, 为 121- 。因此它不是一个回文数。

示例 3:

> 输入: 10  
> 输出: false  
> 解释: 从右向左读, 为 01 。因此它不是一个回文数。

进阶:

你能不将整数转为字符串来解决这个问题吗？

## 解答 ##

字符反转

`392ms` `60.96%`

```javascript
/**
 * @param {number} x
 * @return {boolean}
 */
var isPalindrome = function(x) {
  x = x + '';
  return x === x.split('').reverse().join('');
};
```

反转一半数字

`384ms` `68.46%`

```javascript
/**
 * @param {number} x
 * @return {boolean}
 */
var isPalindrome = function(x) {
  if (x < 0 || (x % 10 === 0 && x !== 0)) {
    return false;
  }
  var reverse = 0;
  var remainder;
  while (x > reverse) {
    reverse = reverse * 10 + x % 10;
    x = Math.trunc(x / 10);
  }
  return x === reverse || x === Math.trunc(reverse / 10);
};
```

头尾比较

`336ms` `93.43%`

```javascript
/**
 * @param {number} x
 * @return {boolean}
 */
var isPalindrome = function(x) {
  x = x.toString();
  for (var i = 0; i < x.length / 2; i ++) {
    if (x[i] !== x[x.length - 1 - i]) {
      return false;
    }
  }
  return true;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 回文数  
  <https://leetcode-cn.com/problems/palindrome-number/description/>
* LeetCode problems palindrome-number  
  <https://leetcode.com/problems/palindrome-number/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.palindromeNumber]: ../../README.md#problemSet.algorithm.palindromeNumber "README"
<!-- 链接 结束 -->