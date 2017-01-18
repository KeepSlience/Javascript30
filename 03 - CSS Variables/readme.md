# 03 Playing with CSS Variables and JS

## 任务

使用 CSS Variable 并通过滑块与色板来控制图片的 padding, blur 和 背景及的一部分文字的 color

[实现效果](https://miaolegemie.github.io/Javascript30/03%20-%20CSS%20Variables/)

## 任务要点

- 监听 `input` 修改事件
- 更新对应的`css`

## 步骤

1. 监听 `input` 修改事件
  - `addEventListener('input', function)`
  - [`addEventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)具体用法
  - `input` 事件和 `change` 事件的区别
    - `change` 比 `input` 触发的次数会少一些：仅触发于用户提交更改之后。
  - 因此如果在本任务中监听 `change` 事件则还需要监听 `mousemove` 事件
2. 更新对应的`css`
  - 首先来看一下 [`CSS Variable`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Using_CSS_variables)
  - 同时使用了 [`:root`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:root) 伪类
    - `:root`匹配文档树的根元素应用到 HTML ，`:root` 即表示为 `<html>` 元素，除了优先级更高外，相当于html标签选择器。
  - 触发事件后，先判断是否需要添加单位(px)
    - 此处使用到了 [`dataset`](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLElement/dataset) 属性，可以用来储存一些信息，并通过 `dataset` 来访问
  - 然后修改根元素的 `CSS Variable`
    - 使用 [`documentElement`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/documentElement) 来获得根元素
    - 然后使用 [`CSSStyleDeclaration`](https://developer.mozilla.org/zh-CN/docs/Web/API/CSSStyleDeclaration) 中的 `setProperty` 来更新样式

## 其他
1. `Nodelist` 与 `Array` 的区别
  - `Nodelist` 并不是 `Array` ，原因如下
    - myArray --> Array.prototype --> Object.prototype --> null
    - myNodeList --> NodeList.prototype --> Object.prototype --> null
  - `Nodelist` 具有实时性，即 DOM 更新后会实时展示在 `Nodelist` 中
2. [`filter`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/filter)
