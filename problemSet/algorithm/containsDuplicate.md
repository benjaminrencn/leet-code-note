# <a id="containsDuplicate"></a>存在重复元素&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.containsDuplicate] #

## 描述 ##

给定一个整数数组，判断是否存在重复元素。

如果任何值在数组中出现至少两次，函数返回 true。如果数组中每个元素都不相同，则返回 false。

示例 1:

> 输入: [1,2,3,1]  
> 输出: true

示例 2:

> 输入: [1,2,3,4]  
> 输出: false

示例 3:

> 输入: [1,1,1,3,3,4,3,2,4,2]  
> 输出: true

## 解答 ##

哈希法

`120ms` `68.44%`

```javascript
/**
 * @param {number[]} nums
 * @return {boolean}
 */
var containsDuplicate = function(nums) {
  let itemMap = {};
  for (let i = 0; i < nums.length; i ++) {
    if (itemMap[nums[i]]) {
      return true;
    } else {
      itemMap[nums[i]] = true;
    }
  }
  return false;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 存在重复元素  
  <https://leetcode-cn.com/problems/contains-duplicate/description/>
* LeetCode problems contains-duplicate  
  <https://leetcode.com/problems/contains-duplicate/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.containsDuplicate]: ../../README.md#problemSet.algorithm.containsDuplicate "README"
<!-- 链接 结束 -->