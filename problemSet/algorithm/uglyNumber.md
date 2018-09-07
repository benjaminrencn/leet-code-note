# <a id="uglyNumber"></a>丑数&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.uglyNumber] #

## 描述 ##

编写一个程序判断给定的数是否为丑数。

丑数就是只包含质因数 2, 3, 5 的正整数。

示例 1:

> 输入: 6  
> 输出: true  
> 解释: 6 = 2 × 3

示例 2:

> 输入: 8  
> 输出: true  
> 解释: 8 = 2 × 2 × 2

示例 3:

> 输入: 14  
> 输出: false  
> 解释: 14 不是丑数，因为它包含了另外一个质因数 7。

说明：

1 是丑数。

输入不会超过 32 位有符号整数的范围: [−231,  231 − 1]。

## 解答 ##

迭代法

`104ms` `67.12%`

```javascript
/**
 * @param {number} num
 * @return {boolean}
 */
var isUgly = function(num) {
  let uglyFactors = [2, 3, 5];
  let uglyFlag = false;

  if (!num) { return false; }
  while (num !== 1) {
    uglyFlag = false;
    for (let i in uglyFactors) {
      if (!(num % uglyFactors[i])) {
        num /= uglyFactors[i];
        uglyFlag = true;
        break;
      }
    }
    if (!uglyFlag) { return false; }
  }

  return true;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 丑数  
  <https://leetcode-cn.com/problems/ugly-number/description/>
* LeetCode problems ugly-number  
  <https://leetcode.com/problems/ugly-number/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.uglyNumber]: ../../README.md#problemSet.algorithm.uglyNumber "README"
<!-- 链接 结束 -->