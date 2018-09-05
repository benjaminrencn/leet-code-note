# <a id="powerOfTwo"></a>2的幂&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.powerOfTwo] #

## 描述 ##

给定一个整数，编写一个函数来判断它是否是 2 的幂次方。

示例 1:

> 输入: 1  
> 输出: true  
> 解释: 2<sup>0</sup> = 1

示例 2:

> 输入: 16  
> 输出: true  
> 解释: 2<sup>4</sup> = 16

示例 3:

> 输入: 218  
> 输出: false

## 解答 ##

暴力法

`100ms` `85.07%`

```javascript
/**
 * @param {number} n
 * @return {boolean}
 */
var isPowerOfTwo = function(n) {
  if (n === 0) { return false; }
  while (n !== 1) {
    if (n % 2) { return false }
    n /= 2;
  };
  return true;
};
```

位运算法

`84ms` `98.51%`

```javascript
/**
 * @param {number} n
 * @return {boolean}
 */
var isPowerOfTwo = function(n) {
  return n > 0 && (n & (n - 1)) == 0;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 2的幂  
  <https://leetcode-cn.com/problems/power-of-two/description/>
* LeetCode problems power-of-two  
  <https://leetcode.com/problems/power-of-two/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.powerOfTwo]: ../../README.md#problemSet.algorithm.powerOfTwo "README"
<!-- 链接 结束 -->