# <a id="excelSheetColumnNumber"></a>Excel表列序号&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.excelSheetColumnNumber] #

## 描述 ##

给定一个Excel表格中的列名称，返回其相应的列序号。

例如，

> A -> 1  
> B -> 2  
> C -> 3  
> ...  
> Z -> 26  
> AA -> 27  
> AB -> 28  
> ...

示例 1:

> 输入: "A"  
> 输出: 1

示例 2:

> 输入: "AB"  
> 输出: 28

示例 3:

> 输入: "ZY"  
> 输出: 701

## 解答 ##

逐为次方相加

`84ms` `94.34%`

```javascript
/**
 * @param {string} s
 * @return {number}
 */
var titleToNumber = function(s) {
  let number = 0;
  let length = s.length;
  const A = 'A'.charCodeAt();
  for (let i = 0; i < length; i ++) {
    number += (s[i].charCodeAt() - A + 1) * Math.pow(26, length - i - 1);
  }
  return number;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 Excel表列序号  
  <https://leetcode-cn.com/problems/excel-sheet-column-number/description/>
* LeetCode problems excel-sheet-column-number  
  <https://leetcode.com/problems/excel-sheet-column-number/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.excelSheetColumnNumber]: ../../README.md#problemSet.algorithm.excelSheetColumnNumber "README"
<!-- 链接 结束 -->