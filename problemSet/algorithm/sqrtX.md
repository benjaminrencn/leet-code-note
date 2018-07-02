# <a id="sqrtX"></a>二进制求和&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.sqrtX] #

## 描述 ##

实现 `int sqrt(int x)` 函数。

计算并返回 x 的平方根，其中 x 是非负整数。

由于返回类型是整数，结果只保留整数的部分，小数部分将被舍去。

示例 1:

> 输入: 4  
> 输出: 2

示例 2:

> 输入: 8  
> 输出: 2  
> 说明: 8 的平方根是 2.82842...,  
> 由于返回类型是整数，小数部分将被舍去。

## 解答 ##

穷举法

`132ms` `27.12%%`

```javascript
/**
 * @param {number} x
 * @return {number}
 */
var mySqrt = function(x) {
  let i;
  for (i = 0; i * i <= x; i ++) {}

  return i - 1;
};
```

二分法

`144ms` `16.38%`

```javascript
/**
 * @param {number} x
 * @return {number}
 */
var mySqrt = function(x) {
  if (x < 0) {
    return -1;
  }
  if (x === 0) {
    return 0;
  }
  if (x === 1) {
    return 1;
  }

  let left = 0, right = x, middle;
  while (true) {
    middle = Math.floor((left + right) / 2);
    if (middle * middle > x) {
      right = middle - 1;
    } else if (middle * middle < x) {
      if ((middle + 1) * (middle + 1) > x) {
        return middle;
      }
      left = middle + 1;
    } else {
      return middle;
    }
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 二进制求和  
  <https://leetcode-cn.com/problems/sqrtx/description/>
* LeetCode problems sqrtx  
  <https://leetcode.com/problems/sqrtx/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.sqrtX]: ../../README.md#problemSet.algorithm.sqrtX "README"
<!-- 链接 结束 -->