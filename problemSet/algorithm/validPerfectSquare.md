# <a id="validPerfectSquare"></a>有效的完全平方数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.validPerfectSquare] #

## 描述 ##

给定一个正整数 num，编写一个函数，如果 num 是一个完全平方数，则返回 True，否则返回 False。

说明：不要使用任何内置的库函数，如  sqrt。

示例 1：

> 输入：16  
> 输出：True

示例 2：

> 输入：14  
> 输出：False

## 解答 ##

暴力法

`72ms` `83.21%`

```javascript
/**
 * @param {number} num
 * @return {boolean}
 */
var isPerfectSquare = function(num) {
  for (let i = 1; Math.pow(i, 2) < Math.pow(2, 31) && Math.pow(i, 2) <= num; i ++) {
    if (Math.pow(i, 2) === num) {
      return true;
    }
  }
  return false;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 有效的完全平方数  
  <https://leetcode-cn.com/problems/valid-perfect-square/description/>
* LeetCode problems valid-perfect-square  
  <https://leetcode.com/problems/valid-perfect-square/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.validPerfectSquare]: ../../README.md#problemSet.algorithm.validPerfectSquare "README"
<!-- 链接 结束 -->