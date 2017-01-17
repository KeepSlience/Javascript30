# 01 JavaScript Dump Kit

## 任务

模拟一个打鼓的页面。用户在键盘上按下 ASDFGHJKL 这几个键时，页面上与字母对应的按钮变大变亮，对应的鼓点声音响起来。
[实现效果](https://miaolegemie.github.io/Javascript30/01%20-%20JavaScript%20Drum%20Kit/)

## 任务要点

- 监听键盘事件
- 播放音频文件
- 动画

## 步骤

1. 监听键盘事件
  - [事件类型一览表](https://developer.mozilla.org/zh-CN/docs/Web/Events)
  - `ketdown`与`keypress`均可在连续按下按键不放时持续出发事件，但存在以下区别
    - `KeyPress` 只能捕获单个字符，而 `KeyDown` 和 `KeyUp` 可以捕获组合键。
    - `KeyPress` 可以捕获单个字符的大小写， 而 `KeyDown` 和 `KeyUp` 则不行
    - `KeyPress` 不区分小键盘和主键盘的数字字符。`KeyDown` 和 `KeyUp` 区分小键盘和主键盘的数字字符。
    - `KeyPress` 返回的是对应的 **ASCII** 字符
    - `KeyPress` 根据 [MDN 文档](https://developer.mozilla.org/zh-CN/docs/Web/Events/keypress)，已不建议使用
  - 如果不做处理，则持续按键音频则会等播放完毕后才重新播放.
    - 因此如果要实现按下后连续快速播放，则需要将按下后的播放进度重置
    - 即 `audio.currentTime = 0`
    - [MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/AudioContext/currentTime)

2. 添加动画事件
  - 设置类名
    - [classList-张鑫](http://www.zhangxinxu.com/wordpress/2013/07/domtokenlist-html5-dom-classlist-%E7%B1%BB%E5%90%8D/)
    - [classList-MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/classList)
    - `add` 会检测添加的类是否已经存在于元素属性中，如果存在则会被忽略。

3. 解除动画事件
  - [`Array.from()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/from) 方法可以将一个类数组对象或可遍历对象转换成真正的数组。
  - [`forEach()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) 方法对数组的每个元素执行一次提供的函数(回调函数)。
  - [`transitionend`](https://developer.mozilla.org/zh-CN/docs/Web/Events/transitionend) 事件会在 CSS transition 结束后触发.
  - 为所有元素绑定 `transitionend` 事件，在触发时删除 `playing` 类
  - 由于在这个页面中触发 `transitionend` 的事件不止一个(`box-shadow`, `transform`, `border-color`,共触发12次)，因此需要添加一个判断，使得每次按键只除去一次

## 疑问（已解决）
本页面中，每次 `transitionend` 触发时间很短(0.07s)，但是如果在此时间内删除掉该样式，则会直接结束还是仍会执行？

**经过测试后发现，会立即结束**
