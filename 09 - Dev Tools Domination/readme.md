# 09 Dev Tools Domination

## 任务

继续使用更多的 `console` 技巧

[实现效果](https://miaolegemie.github.io/Javascript30/09%20-%20Dev%20Tools%20Domination/)

## 任务要点

1. 添加断点
2. 格式化打印
3. 为 console 定义样式
4. 使用 `warn`, `error`, `info`
5. 使用 断言 (assert)
6. 打印 DOM 元素
7. 打印树状结构
8. 使用 `count` 计数
9. 使用 `time`, `timeEnd` 计时

## 步骤

1. 添加断点
  -  打开 Chrome 开发者工具，在 Elements 选项卡之中，选择页面的某个标签（以 <p>为例），右键 → Break on → Attributes modifications。即可为该元素添加断点，当它的属性发生改变时，会自动定位到页面代码中的对应行。
  - 也可以在 Sources 选项卡中，通过点击代码行号来添加断点（如 16行）
  - 本任务中添加断点后可以点击页面中文字来观察效果
2. [格式化打印](https://developer.mozilla.org/zh-CN/docs/Web/API/Console#格式化打印)
  - `%o`	打印javascript对象，可以是整数、字符串以及JSON数据
  - `%d` or `%i`	打印整数
  - `%s`	打印字符串
  - `%f`	打印浮点数
3. [为 console 定义样式](https://developer.mozilla.org/zh-CN/docs/Web/API/Console#为console定义样式)
  - 如 `console.log("%cMy stylish message", "color: red; font-style: italic")`
4. 使用 `warn`, `error`, `info`
  - `console.warn("三角感叹号图标，淡黄色背景，同时有额外提示")`
  - `console.error("红叉图标，红字红色背景，同时有额外提示")`
  - `console.info("蓝色圆形感叹号图标")`
5. 使用 [断言 (assert)](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/assert)
  - 当断言结果为假的时候向控制台输出消息，如果断言为真则什么都不做
  - `console.assert(assertion, obj1 [, obj2, ..., objN])`
  - `console.assert(assertion, msg [, subst1, ..., substN])`
  - **输出的消息作为错误信息**
6. 打印 DOM 元素
  - `console.log()` 会打印出这个 DOM 的 HTML 标签
  - `console.dir()` 会打印出该 DOM 的所有属性和属性值
7. 打印树状结构
- `console.group()/console.groupCollapsed()` 与 `console.groupEnd()` 来表示分组的开始与结束
  - `console.groupCollapsed()` 会自动折叠，而 `console.group()` 不会
8. 使用 [`count`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/count) 计数
  - 输出 count() 被调用的次数。此函数接受一个可选参数 label
    - 如果有 label，此函数输出为那个指定的 label 和 count() 被调用的次数
    - 如果 label 被忽略，此函数输出 count() 在其所处位置上被调用的次数
9. 使用 `time`, `timeEnd` 计时
  - 用 `time('name')` 和 `timeEnd('name')` 分别控制开始点和结束点，它们两的参数表示当前计时器的名称
  - 如果 timeEnd 中的名称所表示的计时器如果没有启动过，得到的数据是系统当前时间换算后的毫秒值

## 注意事项

- [Chrome 开发者控制台中，你可能意想不到的功能](http://web.jobbole.com/90300/)
