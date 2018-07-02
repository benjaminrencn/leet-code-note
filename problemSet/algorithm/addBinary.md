# <a id="addBinary"></a>二进制求和&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.addBinary] #

## 描述 ##

给定两个二进制字符串，返回他们的和（用二进制表示）。

输入为非空字符串且只包含数字 1 和 0。

示例 1:

> 输入: a = "11", b = "1"  
> 输出: "100"

示例 2:

> 输入: a = "1010", b = "1011"  
> 输出: "10101"

## 解答 ##

从右往左

`92ms` `69.89%`

```javascript
/**
 * @param {string} a
 * @param {string} b
 * @return {string}
 */
var addBinary = function(a, b) {
  var sum = '';
  var temp = 0;
  for (let i = a.length - 1, j = b.length - 1; i >= 0 || j >= 0 || temp === 1; i --, j--) {
    temp += (+a[i] || 0) + (+b[j] || 0);
    sum = temp % 2 + sum;
    temp = Math.floor(temp / 2);
  }
  return sum;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 二进制求和  
  <https://leetcode-cn.com/problems/add-binary/description/>
* LeetCode problems add-binary  
  <https://leetcode.com/problems/add-binary/discuss/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.addBinary]: ../../README.md#problemSet.algorithm.addBinary "README"
<!-- 链接 结束 -->