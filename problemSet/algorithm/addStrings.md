# <a id="addStrings"></a>字符串相加&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.addStrings] #

## 描述 ##

给定两个字符串形式的非负整数 num1 和num2 ，计算它们的和。

注意：

1. num1 和num2 的长度都小于 5100.
2. num1 和num2 都只包含数字 0-9.
3. num1 和num2 都不包含任何前导零。
4. 你不能使用任何內建 BigInteger 库， 也不能直接将输入的字符串转换为整数形式。

## 解答 ##

两个数组进行计算

`108ms` `47.42%`

```javascript
/**
 * @param {string} num1
 * @param {string} num2
 * @return {string}
 */
var addStrings = function(num1, num2) {
  let nums, nLength, adds, sum;
  
  if (num1.length >= num2.length) {
    nums = ('0' + num1).split('');
    nums.reverse();
    nLength = nums.length;
    adds = num2.split('');
    adds.reverse();
  } else {
    nums = num2.split('');
    nLength = nums.length;
    nums.reverse();
    adds = num1.split('');
    adds.reverse();
  }
  for (let i = 0; i < nLength - 1; i ++) {
    sum = +nums[i] + (+adds[i] || 0);
    nums[i] = sum % 10;
    nums[i + 1] = Math.floor(sum / 10) + +nums[i + 1];
  }
  nums.reverse();
  if (nums[0] == 0) { nums.splice(0 ,1); }
  
  return nums.join('');
};
```

双指针

`88ms` `90.72%`

```javascript
/**
 * @param {string} num1
 * @param {string} num2
 * @return {string}
 */
var addStrings = function(num1, num2) {
  let index1, index2, sum = '', temp, add = 0;

  index1 = num1.length - 1;
  index2 = num2.length - 1;
  while (index1 >= 0 || index2 >= 0) {
    temp = (+num1[index1] || 0) + (+num2[index2] || 0) + add;
    add = Math.floor(temp / 10);
    temp = temp % 10;
    sum = temp + sum;
    index1 --;
    index2 --;
  }
  if (add) { sum = add + sum; }
  return sum;
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 字符串相加  
  <https://leetcode-cn.com/problems/add-strings/description/>
* LeetCode problems add-strings  
  <https://leetcode.com/problems/add-strings/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.addStrings]: ../../README.md#problemSet.algorithm.addStrings "README"
<!-- 链接 结束 -->