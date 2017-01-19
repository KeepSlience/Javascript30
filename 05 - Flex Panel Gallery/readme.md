# 05 Flex Panel Gallery

## 任务

点击任意一张图片，图片展开，当图片展开后从图片上下两方分别移入文字

点击已经展开的图片后，图片恢复展开前大小，恢复后该图片上下两端的文字移出

[实现效果](https://miaolegemie.github.io/Javascript30/05%20-%20Flex%20Panel%20Gallery/)

## 任务要点

- 获取所有图片
- 为每张图片绑定 `click` 事件
- 为每张图片绑定 `transitionend` 事件

## 步骤

1. 获取所有图片
  - `document.querySelectorAll('.panel')`
  - [`Document.querySelectorAll`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelectorAll)
2. 为每张图片绑定 `click` 事件
  - `addEventListener('click', toggleOpen)`
  - [`EventTarget.addEventListener()`](https://developer.mozilla.org/zh-CN/docs/Web/API/EventTarget/addEventListener)
  - 点击后应改变其样式，这里通过切换 `class` 来实现
  - `this.classList.toggle('open')`
  - [classList](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/classList)
3. 为每张图片绑定 `transitionend` 事件
  - `addEventListener('transitionend', toggleTranslateY)`
  - [`transitionend`](https://developer.mozilla.org/zh-CN/docs/Web/Events/transitionend)
  - 如果是由含 `flex` 的触发的（本任务中为`flex-grow`），则表示图片放大/缩小已完成，触发文字进入/移出效果

## flex 布局

本任务要求使用的是 `flex` 布局

- [Flex 布局教程：语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?utm_source=tuicool)
- [Flex 布局教程：实例篇](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)

## 一个 bug 修复

由于作者使用了两个 class 来表示 照片的放大/缩小 和 文字的移入/移出 ，因此如果快速点击照片（即在照片还未完全放大/缩小时再次点击），则会导致只触发一次 `transitionend` ，从而使得 文字移入/移出 出现问题

解决方案：

将两个 class 换成同一个class ，同时 文字移入/移出 效果使用 [`transition-delay`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transition-delay) 来确保在 照片的放大/缩小 完成之后才执行
