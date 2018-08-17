# <a id="rotateArray"></a>旋转数组&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.rotateArray] #

## 描述 ##

给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。

示例 1:

> 输入: [1,2,3,4,5,6,7] 和 k = 3  
> 输出: [5,6,7,1,2,3,4]  
> 解释:  
> 向右旋转 1 步: [7,1,2,3,4,5,6]  
> 向右旋转 2 步: [6,7,1,2,3,4,5]  
> 向右旋转 3 步: [5,6,7,1,2,3,4]

示例 2:

> 输入: [-1,-100,3,99] 和 k = 2  
> 输出: [3,99,-1,-100]  
> 解释:  
> 向右旋转 1 步: [99,-1,-100,3]  
> 向右旋转 2 步: [3,99,-1,-100]

说明:

尽可能想出更多的解决方案，至少有三种不同的方法可以解决这个问题。  
要求使用空间复杂度为 O(1) 的原地算法。

## 解答 ##

pop unshift

`172ms` `24.35%`

```javascript
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var rotate = function(nums, k) {
  for (let i = 0; i < k; i ++) {
    nums.unshift(nums.pop());
  }
};
```

slice concat 遍历赋值

`116ms` `68.89%`

```javascript
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var rotate = function(nums, k) {
  k = k % nums.length;
  let temp = nums.slice(-k).concat(nums.slice(0, -k));
  for (let i in nums) {
    nums[i] = temp[i];
  }
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 旋转数组  
  <https://leetcode-cn.com/problems/rotate-array/description/>
* LeetCode problems rotate-array  
  <https://leetcode.com/problems/rotate-array/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.rotateArray]: ../../README.md#problemSet.algorithm.rotateArray "README"
<!-- 链接 结束 -->