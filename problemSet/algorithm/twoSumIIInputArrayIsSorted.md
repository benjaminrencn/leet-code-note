# <a id="twoSumIIInputArrayIsSorted"></a>两数之和 II - 输入有序数组&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.twoSumIIInputArrayIsSorted] #

## 描述 ##

给定一个已按照升序排列 的有序数组，找到两个数使得它们相加之和等于目标数。

函数应该返回这两个下标值 index1 和 index2，其中 index1 必须小于 index2。

说明:

* 返回的下标值（index1 和 index2）不是从零开始的。
* 你可以假设每个输入只对应唯一的答案，而且你不可以重复使用相同的元素。

示例:

> 输入: numbers = [2, 7, 11, 15], target = 9  
> 输出: [1,2]  
> 解释: 2 与 7 之和等于目标数 9 。因此 index1 = 1, index2 = 2 。

## 解答 ##

差值

`608ms` `2.06%`

```javascript
/**
 * @param {number[]} numbers
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(numbers, target) {
  let length = numbers.length;
  let answers = [];
  for (let i = 0, j = 0; i < length; i ++) {
    j = numbers.indexOf(target - numbers[i]);
    if (j !== -1 && j !== i) {
      if (i < j) {
        return [i + 1, j + 1];
      } else {
        return [j + 1, i + 1];
      }
    }
  }
};
```

差值 + 哈希

`76ms` `84.02%`

```javascript
/**
 * @param {number[]} numbers
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(numbers, target) {
  let diffIndex = {};
  let length = numbers.length;
  for (let i = 0; i < length; i ++) {
    if (diffIndex[numbers[i]]) { return [diffIndex[numbers[i]], i + 1]; }
    diffIndex[target - numbers[i]] = i + 1;
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 两数之和 II - 输入有序数组  
  <https://leetcode-cn.com/problems/two-sum-ii-input-array-is-sorted/description/>
* LeetCode problems two-sum-ii-input-array-is-sorted  
  <https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.twoSumIIInputArrayIsSorted]: ../../README.md#problemSet.algorithm.twoSumIIInputArrayIsSorted "README"
<!-- 链接 结束 -->