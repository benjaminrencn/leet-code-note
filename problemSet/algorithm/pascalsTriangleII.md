# <a id="pascalsTriangleII"></a>杨辉三角 II&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.pascalsTriangleII] #

## 描述 ##

给定一个非负索引 k，其中 k ≤ 33，返回杨辉三角的第 k 行。

在杨辉三角中，每个数是它左上方和右上方的数的和。

示例:

> 输入: 3  
> 输出: [1,3,3,1]

进阶：

你可以优化你的算法到 O(k) 空间复杂度吗？

## 解答 ##

`72ms` `80.77%`

```javascript
/**
 * @param {number} rowIndex
 * @return {number[]}
 */
var getRow = function(rowIndex) {
  let row = [1];
  
  for (let i = 0; i < rowIndex + 1; i ++) {
    for (let j = i; j >= 1; j --) {
      row[j] = (row[j] || 0) + row[j - 1];
    }
  }

  return row;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 杨辉三角 II  
  <https://leetcode-cn.com/problems/pascals-triangle-ii/description/>
* LeetCode problems pascals-triangle-ii  
  <https://leetcode.com/problems/pascals-triangle-ii/description/>
* LeetCode problems pascals-triangle-ii Discuss Here is my brief O(k) solution - LongsPeak  
  <https://leetcode.com/problems/pascals-triangle-ii/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.pascalsTriangleII]: ../../README.md#problemSet.algorithm.pascalsTriangleII "README"
<!-- 链接 结束 -->