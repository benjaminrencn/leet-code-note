# <a id="climbingStairs"></a>爬楼梯&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.climbingStairs] #

## 描述 ##

假设你正在爬楼梯。需要 n 步你才能到达楼顶。

每次你可以爬 1 或 2 个台阶。你有多少种不同的方法可以爬到楼顶呢？

注意：给定 n 是一个正整数。

示例 1：

> 输入： 2
> 输出： 2
> 解释： 有两种方法可以爬到楼顶。
> 1. 1 步 + 1 步
> 1. 2 步

示例 2：

> 输入： 3
> 输出： 3
> 解释： 有三种方法可以爬到楼顶。
> 1. 1 步 + 1 步 + 1 步
> 1. 1 步 + 2 步
> 1. 2 步 + 1 步

## 解答 ##

斐波那契数列

`76ms` `37.96%`

```javascript
/**
 * @param {number} n
 * @return {number}
 */
var climbStairs = function(n) {
  let steps = [1, 2];
  for (let i = 2; i < n; i ++) {
    steps[i] = steps[i - 1] + steps[i - 2];
  }
  return steps[n - 1];
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 爬楼梯  
  <https://leetcode-cn.com/problems/climbing-stairs/description/>
* LeetCode problems climbing-stairs  
  <https://leetcode.com/problems/climbing-stairs/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.climbingStairs]: ../../README.md#problemSet.algorithm.climbingStairs "README"
<!-- 链接 结束 -->