# <a id="pascalsTriangle"></a>杨辉三角&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.pascalsTriangle] #

## 描述 ##

给定一个非负整数 numRows，生成杨辉三角的前 numRows 行。

在杨辉三角中，每个数是它左上方和右上方的数的和。

示例:

> 输入: 5
> 输出:
> ```
> [
>      [1],
>     [1,1],
>    [1,2,1],
>   [1,3,3,1],
>  [1,4,6,4,1]
> ]
> ```

## 解答 ##

双重循环

`72ms` `63.64%`

```javascript
/**
 * @param {number} numRows
 * @return {number[][]}
 */
var generate = function(numRows) {
  let triangle = [[1], [1, 1]];
  if (numRows <= 2) {
    return triangle.slice(0, numRows);
  }
  for (let i = 2; i < numRows; i ++) {
    for (let j = 0; j <= i; j ++) {
      if (j === 0) {
        triangle.push([1]);
      } else if (j === i) {
        triangle[i].push(1);
      } else {
        triangle[i].push(triangle[i - 1][j - 1] + triangle[i - 1][j]);
      }
    }
  }

  return triangle;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 杨辉三角  
  <https://leetcode-cn.com/problems/pascals-triangle/description/>
* LeetCode problems pascals-triangle  
  <https://leetcode.com/problems/pascals-triangle/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.pascalsTriangle]: ../../README.md#problemSet.algorithm.pascalsTriangle "README"
<!-- 链接 结束 -->