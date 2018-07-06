# <a id="minStack"></a>最小栈&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.minStack] #

## 描述 ##

设计一个支持 push，pop，top 操作，并能在常数时间内检索到最小元素的栈。

* push(x) -- 将元素 x 推入栈中。
* pop() -- 删除栈顶的元素。
* top() -- 获取栈顶元素。
* getMin() -- 检索栈中的最小元素。

示例:

> MinStack minStack = new MinStack();  
> minStack.push(-2);  
> minStack.push(0);  
> minStack.push(-3);  
> minStack.getMin();   --> 返回 -3.  
> minStack.pop();  
> minStack.top();      --> 返回 0.  
> minStack.getMin();   --> 返回 -2.

## 解答 ##

Array.splice()

`284ms` `18.31%`

```javascript
/**
 * initialize your data structure here.
 */
var MinStack = function() {
  this.value = [];
};

/**
 * @param {number} x
 * @return {void}
 */
MinStack.prototype.push = function(x) {
  this.value.splice(this.value.length, 0, x);
};

/**
 * @return {void}
 */
MinStack.prototype.pop = function() {
  this.value.splice(this.value.length - 1, 1);
};

/**
 * @return {number}
 */
MinStack.prototype.top = function() {
  return this.value[this.value.length - 1];
};

/**
 * @return {number}
 */
MinStack.prototype.getMin = function() {
  return Math.min.apply(Math, this.value)
};

/**
 * Your MinStack object will be instantiated and called as such:
 * var obj = Object.create(MinStack).createNew()
 * obj.push(x)
 * obj.pop()
 * var param_3 = obj.top()
 * var param_4 = obj.getMin()
 */
```

Array.push() Array.pop() 最小值栈

`92ms` `90.14%`

```javascript
/**
 * initialize your data structure here.
 */
var MinStack = function() {
  this.value = [];
  this.mins = [];
};

/**
 * @param {number} x
 * @return {void}
 */
MinStack.prototype.push = function(x) {
  this.value.push(x);
  let minsLength = this.mins.length;
  if (minsLength === 0 || this.mins[minsLength - 1] >= x) {
    this.mins.push(x);
  }
};

/**
 * @return {void}
 */
MinStack.prototype.pop = function() {
  let element = this.value.pop();
  if (element === this.mins[this.mins.length - 1]) {
    this.mins.pop();
  }
};

/**
 * @return {number}
 */
MinStack.prototype.top = function() {
  return this.value[this.value.length - 1];
};

/**
 * @return {number}
 */
MinStack.prototype.getMin = function() {
  return this.mins[this.mins.length - 1];
};

/**
 * Your MinStack object will be instantiated and called as such:
 * var obj = Object.create(MinStack).createNew()
 * obj.push(x)
 * obj.pop()
 * var param_3 = obj.top()
 * var param_4 = obj.getMin()
 */
```

## 参考 ##

* LeetCode (中国) 题库 算法 最小栈  
  <https://leetcode-cn.com/problems/min-stack/description/>
* LeetCode problems min-stack  
  <https://leetcode.com/problems/min-stack/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.minStack]: ../../README.md#problemSet.algorithm.minStack "README"
<!-- 链接 结束 -->