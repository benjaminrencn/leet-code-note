# <a id="excelSheetColumnTitle"></a>Excel表列名称&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.excelSheetColumnTitle] #

## 描述 ##

给定一个正整数，返回它在 Excel 表中相对应的列名称。

例如，

> 1 -> A  
> 2 -> B  
> 3 -> C  
> ...  
> 26 -> Z  
> 27 -> AA  
> 28 -> AB  
> ...

示例 1:

> 输入: 1  
> 输出: "A"

示例 2:

> 输入: 28  
> 输出: "AB"

示例 3:

> 输入: 701  
> 输出: "ZY"

## 解答 ##

递归余数

`68ms` `71.15%`

```javascript
/**
 * @param {number} n
 * @return {string}
 */
var convertToTitle = function(n) {
  let letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('');
  return n === 0 ? '' : convertToTitle(Math.floor(--n / 26)) + letters[n % 26];
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 Excel表列名称  
  <https://leetcode-cn.com/problems/excel-sheet-column-title/description/>
* LeetCode problems excel-sheet-column-title  
  <https://leetcode.com/problems/excel-sheet-column-title/description/>
* LeetCode problems excel-sheet-column-title Discuss My 1 lines code in Java, C++, and Python - xcv58  
  <https://leetcode.com/problems/excel-sheet-column-title/discuss/51398/My-1-lines-code-in-Java-C++-and-Python>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.excelSheetColumnTitle]: ../../README.md#problemSet.algorithm.excelSheetColumnTitle "README"
<!-- 链接 结束 -->