# <a id="rangeSumQuery-Immutable"></a>区域和检索 - 数组不可变&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.rangeSumQuery-Immutable] #

## 描述 ##

给定一个整数数组  nums，求出数组从索引 i 到 j  (i ≤ j) 范围内元素的总和，包含 i,  j 两点。

示例：

给定 nums = [-2, 0, 3, -5, 2, -1]，求和函数为 sumRange()

sumRange(0, 2) -> 1
sumRange(2, 5) -> -1
sumRange(0, 5) -> -3
说明:

你可以假设数组不可变。
会多次调用 sumRange 方法。

## 解答 ##

存储0 - i子序列和

`88ms` `76.92%`

```javascript
/**
 * @param {number[]} nums
 */
var NumArray = function(nums) {
  this.array = nums;
  this.sums = {};

  for (let i in this.array) {
    if (i === '0') {
      this.sums[0] = this.array[0];
    } else {
      this.sums[i] = this.sums[i - 1] + this.array[i];
    }
  }
};

/**
 * @param {number} i 
 * @param {number} j
 * @return {number}
 */
NumArray.prototype.sumRange = function(i, j) {
  if (i === 0) {
    return this.sums[j];
  } else {
    return this.sums[j] - this.sums[i - 1];
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 区域和检索 - 数组不可变  
  <https://leetcode-cn.com/problems/range-sum-query-immutable/description/>
* LeetCode problems range-sum-query-immutable  
  <https://leetcode.com/problems/range-sum-query-immutable/description/>
* LeetCode（303）Range Sum Query - Immutable - 逆風的薔薇
  <https://blog.csdn.net/fly_yr/article/details/50173755>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.rangeSumQuery-Immutable]: ../../README.md#problemSet.algorithm.rangeSumQuery-Immutable "README"
<!-- 链接 结束 -->