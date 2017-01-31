# 07 Array Cardio Day 2

## 任务

1. people 数组的人中是否有人大于等于19岁
2. people 数组的人中是否所有人大于等于19岁
3. 找出 comments 数组中 id 为 823423 的信息
4. 删除 comments 数组中 id 为 823423 的信息

[实现效果](https://miaolegemie.github.io/Javascript30/07%20-%20Array%20Cardio%20Day%202/)

## 任务要点

1. 使用 `Array.prototype.some()` 来确定数组中是否有人大于等于 19 岁
2. 使用 `Array.prototype.every()` 来确定数组中是否所有人大于等于19岁
3. 使用 `Array.prototype.find()` 来寻找数组中 id 为 823423 的信息
4. 使用 `Array.prototype.findIndex()` 和 `Array.prototype.splice()` 来删除数组中 id 为 823423 的信息


## 步骤

1. 使用 `Array.prototype.some()` 来确定数组中是否有人大于等于 19 岁
  - [`Array.prototype.some()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/some)
     - 注意，some 遍历的元素的范围在第一次调用 callback. 时就已经确定了。在调用 some 后被添加到数组中的值不会被 callback 访问到。如果数组中存在且还未被访问到的元素被 callback 改变了，则其传递给 callback 的值是 some 访问到它那一刻的值。
2. 使用 `Array.prototype.every()` 来确定数组中是否所有人大于等于19岁
  - [`Array.prototype.every()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/every)
    - 同样的，every 遍历的元素范围在第一次调用 callback 之前就已确定了。在调用 every 之后添加到数组中的元素不会被 callback 访问到。如果数组中存在的元素被更改，则他们传入 callback 的值是 every 访问到他们那一刻的值。那些被删除的元素或从来未被赋值的元素将不会被访问到。
3. 使用 `Array.prototype.find()` 来寻找数组中 id 为 823423 的信息
  - [`Array.prototype.find()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/find) 返回的是 满足提供的测试函数的第一个元素的值
    - [`Array.prototype.includes()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) 返回的是 `true` or `false`
4. 使用 `Array.prototype.findIndex()` 和 `Array.prototype.splice()` 来删除数组中 id 为 823423 的信息
  - [`Array.prototype.findIndex()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex) 返回数组中满足提供的测试函数的第一个元素的索引。否则返回-1
    - 和 [`Array.prototype.indexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf) 的区别在于 能正确识别 `NaN`
    - `[NaN].indexOf(NaN) // -1 `
    - `[NaN].findIndex(y => Object.is(NaN, y)) // 0`
  - [`Array.prototype.splice()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) 可以用来 删除现有元素和/或添加新元素来**更改**数组的内容，返回 由被删除的元素组成的一个数组

## 注意事项


原作者在最后 删除数组中 id 为 823423 的信息 的时候使用的是 [`Array.prototype.slice()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) 方法 与 [扩展语句](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Spread_operator) 来实现的

```
const newComments = [
  ...comments.slice(0, index),
  ...comments.slice(index + 1)
];
```

[大漠的一篇博客-ES6数组方法](https://www.w3cplus.com/javascript/es6-array-methods.html)
