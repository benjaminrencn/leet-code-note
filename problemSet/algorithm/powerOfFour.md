# <a id="powerOfFour"></a>4的幂&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.powerOfFour] #

## 描述 ##

给定一个整数 (32 位有符号整数)，请编写一个函数来判断它是否是 4 的幂次方。

示例 1:

> 输入: 16  
> 输出: true

示例 2:

> 输入: 5  
> 输出: false

进阶：

你能不使用循环或者递归来完成本题吗？

## 解答 ##

迭代法

`152ms` `10.00%`

```javascript
/**
 * @param {number} num
 * @return {boolean}
 */
var isPowerOfFour = function(num) {
  if (num === 1) { return true; }
  if (num <= 3) { return false; }
  do {
    if (num % 4 !== 0) { return false; }
    num /= 4;
  } while (num !== 1);
  return true;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 4的幂  
  <https://leetcode-cn.com/problems/power-of-three/description/>
* LeetCode problems power-of-three  
  <https://leetcode.com/problems/power-of-three/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.powerOfFour]: ../../README.md#problemSet.algorithm.powerOfFour "README"
<!-- 链接 结束 -->