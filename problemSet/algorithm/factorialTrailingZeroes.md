# <a id="factorialTrailingZeroes"></a>阶乘后的零&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.factorialTrailingZeroes] #

## 描述 ##

给定一个整数 n，返回 n! 结果尾数中零的数量。

示例 1:

> 输入: 3  
> 输出: 0  
> 解释: 3! = 6, 尾数中没有零。

示例 2:

> 输入: 5  
> 输出: 1  
> 解释: 5! = 120, 尾数中有 1 个零.

说明: 你算法的时间复杂度应为 O(log n) 。

## 解答 ##

除以5递归

`800ms` `16.67%`

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var trailingZeroes = function(n) {
  return n === 0 ? 0 : Math.floor(n / 5) + trailingZeroes(Math.floor(n / 5));
};
```

除以5循环

`72ms` `96.30%`

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var trailingZeroes = function(n) {
  let count = 0;
  do {
    n = Math.floor(n / 5);
    count += n;
  } while (n);
  return count;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 阶乘后的零  
  <https://leetcode-cn.com/problems/factorial-trailing-zeroes/description/>
* LeetCode problems factorial-trailing-zeroes  
  <https://leetcode.com/problems/factorial-trailing-zeroes/description/>
* LeetCode problems factorial-trailing-zeroes Discuss My one-line solutions in 3 languages - xcv58  
  <https://leetcode.com/problems/factorial-trailing-zeroes/discuss/52371/My-one-line-solutions-in-3-languages>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.factorialTrailingZeroes]: ../../README.md#problemSet.algorithm.factorialTrailingZeroes "README"
<!-- 链接 结束 -->