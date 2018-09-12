# <a id="powerOfThree"></a>3的幂&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.powerOfThree] #

## 描述 ##

给定一个整数，写一个函数来判断它是否是 3 的幂次方。

示例 1:

> 输入: 27  
> 输出: true

示例 2:

> 输入: 0  
> 输出: false

示例 3:

> 输入: 9  
> 输出: true

示例 4:

> 输入: 45  
> 输出: false

进阶：

你能不使用循环或者递归来完成本题吗？

## 解答 ##

迭代法

`352ms` `98.55%`

```javascript
/**
 * @param {number} n
 * @return {boolean}
 */
var isPowerOfThree = function(n) {
  if (n === 0) { return false; }
  if (n === 1) { return true; }
  do {
    if (n % 3 !== 0) { return false; }
    n /= 3;
  } while (n !== 1);
  return true;
};
```

最大3的幂求余

`516ms` `35.51%`

```javascript
/**
 * @param {number} n
 * @return {boolean}
 */
var isPowerOfThree = function(n) {
  if (n <= 0) { return false; }
  if (n === 1) { return true; }
  if (typeof Number.MAX_THREE_POWER === 'undefined') { getMaxPower(); }
  return Number.MAX_THREE_POWER % n === 0;

  function getMaxPower() {
    let n = 1;
    while (n < (Math.pow(2, 32) - 1)) {
      n *= 3;
    }
    Number.MAX_THREE_POWER =  n / 3;
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 3的幂  
  <https://leetcode-cn.com/problems/power-of-three/description/>
* LeetCode problems power-of-three  
  <https://leetcode.com/problems/power-of-three/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.powerOfThree]: ../../README.md#problemSet.algorithm.powerOfThree "README"
<!-- 链接 结束 -->