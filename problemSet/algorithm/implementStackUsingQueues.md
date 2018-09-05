# <a id="implementStackUsingQueues"></a>用队列实现栈&nbsp;&nbsp;[:point_left:][readme.problemSet.algorithm.implementStackUsingQueues] #

## 描述 ##

使用队列实现栈的下列操作：

* push(x) -- 元素 x 入栈
* pop() -- 移除栈顶元素
* top() -- 获取栈顶元素
* empty() -- 返回栈是否为空

注意:

* 你只能使用队列的基本操作-- 也就是 push to back, peek/pop from front, size, 和 is empty 这些操作是合法的。
* 你所使用的语言也许不支持队列。 你可以使用 list 或者 deque（双端队列）来模拟一个队列 , 只要是标准的队列操作即可。
* 你可以假设所有操作都是有效的（例如, 对一个空的栈不会调用 pop 或者 top 操作）。

## 解答 ##

Array.unshift Array.pop

`68ms` `71.43%`

```javascript
/**
 * Initialize your data structure here.
 */
var MyStack = function() {
  this.stack = [];
};

/**
 * Push element x onto stack.
 * @param {number} x
 * @return {void}
 */
MyStack.prototype.push = function(x) {
  this.stack.unshift(x);
};

/**
 * Removes the element on top of the stack and returns that element.
 * @return {number}
 */
MyStack.prototype.pop = function() {
  let length = this.stack.length;
  let queue = [];
  let result;

  for (let i = 0; i < length - 1; i ++) {
    queue.unshift(this.stack.pop());
  }
  result = this.stack.pop();
  this.stack = queue;
  
  return result;
};

/**
 * Get the top element.
 * @return {number}
 */
MyStack.prototype.top = function() {
  return this.stack[0];
};

/**
 * Returns whether the stack is empty.
 * @return {boolean}
 */
MyStack.prototype.empty = function() {
  return !this.stack.length;
};
/**
 * Your MyStack object will be instantiated and called as such:
 * var obj = Object.create(MyStack).createNew()
 * obj.push(x)
 * var param_2 = obj.pop()
 * var param_3 = obj.top()
 * var param_4 = obj.empty()
 */
```

## 参考 ##

* LeetCode (中国) 题库 算法 用队列实现栈  
  <https://leetcode-cn.com/problems/implement-stack-using-queues/description/>
* LeetCode problems implement-stack-using-queues  
  <https://leetcode.com/problems/implement-stack-using-queues/description/>

<!-- 链接 开始 -->
[readme.problemSet.algorithm.implementStackUsingQueues]: ../../README.md#problemSet.algorithm.implementStackUsingQueues "README"
<!-- 链接 结束 -->