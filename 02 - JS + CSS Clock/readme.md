# 02 CSS and JS Clock

## 任务

实现一个钟表的表盘，表盘上通过时针，分针，秒针来显示当前时间，并能够实时更新

[实现效果](https://miaolegemie.github.io/Javascript30/02%20-%20JS%20+%20CSS%20Clock/)

## 任务要点

- 获取当前时间
- 更改时针，分针，秒针的角度
- 设置定时器实时更新

## 步骤

1.获取当前时间
  - 通过 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象获取当前时间
2.更改时针，分针，秒针的角度
  - 通过 [`transform`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform) 来设置旋转角度(rotate)
  - 如 `transform: rotate(90deg)`
  - `transform` 动画默认以元素的中心(`center center`)为原点，在本任务中需要使用 [`transform-origin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform-origin) 来将源点置于 `(right center)` 处
3.设置定时器实时更新
  - 通过 [`setInterval`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/setInterval) 来设置定时任务

### 作者源码

作者在其源码中有这样一行代码

 `transition-timing-function: cubic-bezier(0.1, 2.7, 0.58, 1);`

- [`transition-timing-function`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transition-timing-function)
-   [`timing-function`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/timing-function)

目的是为了模拟秒针抖动的动画

### 其他

[这里](https://github.com/soyaine/JavaScript30/tree/master/02%20-%20JS%20%2B%20CSS%20Clock)有一份更加完善的笔记，作者不但美化了样式，还有一些奇怪的 bug 修复与探讨
