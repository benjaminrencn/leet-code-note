# <a id="sumOfTwoIntegers"></a>两整数之和&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.sumOfTwoIntegers] #

## 描述 ##

不使用运算符 + 和 - ​​​​​​​，计算两整数 ​​​​​​​a 、b ​​​​​​​之和。

示例 1:

> 输入: a = 1, b = 2  
> 输出: 3

示例 2:

> 输入: a = -2, b = 3  
> 输出: 1

## 解答 ##

^ 异或 不进位 & 与 << 左移 进位

`64ms` `94.07%`

```javascript
/**
 * @param {number} a
 * @param {number} b
 * @return {number}
 */
var getSum = function(a, b) {
  let carry;

  if (a === 0) { return b; }
  while (b !== 0) {
    carry = a & b;
    a = a ^ b;
    b = carry << 1;
  }

  return a;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 两整数之和  
  <https://leetcode-cn.com/problems/sum-of-two-integers/description/>
* LeetCode problems sum-of-two-integers  
  <https://leetcode.com/problems/sum-of-two-integers/description/>
* LeetCode problems sum-of-two-integers Discuss Java simple easy understand solution with explanation - zhaolz  
  <https://leetcode.com/problems/sum-of-two-integers/discuss/84290/Java-simple-easy-understand-solution-with-explanation>


<!-- 链接 开始 -->
[readme.problemSet.algorithm.sumOfTwoIntegers]: ../../README.md#problemSet.algorithm.sumOfTwoIntegers "README"
<!-- 链接 结束 -->