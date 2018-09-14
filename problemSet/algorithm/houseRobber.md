# <a id="houseRobber"></a>打家劫舍&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.houseRobber] #

## 描述 ##

你是一个专业的小偷，计划偷窃沿街的房屋。每间房内都藏有一定的现金，影响你偷窃的唯一制约因素就是相邻的房屋装有相互连通的防盗系统，如果两间相邻的房屋在同一晚上被小偷闯入，系统会自动报警。

给定一个代表每个房屋存放金额的非负整数数组，计算你在不触动警报装置的情况下，能够偷窃到的最高金额。

示例 1:

> 输入: [1,2,3,1]  
> 输出: 4  
> 解释: 偷窃 1 号房屋 (金额 = 1) ，然后偷窃 3 号房屋 (金额 = 3)。  
> 偷窃到的最高金额 = 1 + 3 = 4 。

示例 2:

> 输入: [2,7,9,3,1]  
> 输出: 12  
> 解释: 偷窃 1 号房屋 (金额 = 2), 偷窃 3 号房屋 (金额 = 9)，接着偷窃 5 号房屋 (金额 = 1)。  
> 偷窃到的最高金额 = 2 + 9 + 1 = 12 。

## 解答 ##

动态规范法

`80ms` `27.54%`

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var rob = function(nums) {
  let dp = [[]];
  for (let i = 1; i <= nums.length; i ++) {
    dp[i] = [];
    dp[i][0] = Math.max(dp[i - 1] && dp[i - 1][0] || 0, dp[i - 1]  && dp[i - 1][1] || 0);
    dp[i][1] = nums[i - 1] + (dp[i - 1] && dp[i - 1][0] || 0);
  }
  return Math.max(dp[nums.length][0] || 0, dp[nums.length][1] || 0);
};
```

动态规范法

`64ms` `94.20%`

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var rob = function(nums) {
  let dp = [{
    no: { value: 0, houses: [] },
    yes: { value: 0, houses: [] }
  }];
  let i = 0;
  for (i = 1; i <= nums.length; i ++) {
    dp[i] = {};
    dp[i].no = dp[i - 1].no.value >= dp[i - 1].yes.value ? 
      new Object({ value: dp[i - 1].no.value, houses: dp[i - 1].no.houses }) : 
      new Object({ value: dp[i - 1].yes.value, houses: dp[i - 1].yes.houses });
    dp[i].yes = { value: dp[i - 1].no.value + nums[i - 1], houses: dp[i - 1].no.houses.concat(i) };
  }
  console.log(dp);
  return Math.max(dp[i - 1].no.value, dp[i - 1 ].yes.value);
};
```

## 参考 ##

* LeetCode (中国) 题库 算法 打家劫舍  
  <https://leetcode-cn.com/problems/house-robber/description/>
* LeetCode problems house-robber  
  <https://leetcode.com/problems/house-robber/description/>
* LeetCode problems house-robber Discuss Java O(n) solution, space O(1) - tusizi  
  <https://leetcode.com/problems/house-robber/discuss/55681/Java-O(n)-solution-space-O(1)>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.houseRobber]: ../../README.md#problemSet.algorithm.houseRobber "README"
<!-- 链接 结束 -->