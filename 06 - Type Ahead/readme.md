# 06 Type Ahead

## 任务

从一个接口处获取一些城市的信息，然后实时相应用户输入来查询所需内容（不区分大小写），并将查询所得展示出来。需要展示的有城市名（如果有，则需要高亮被查询信息），洲名（如果有，则需要高亮被查询信息），人口（需要自己添加千位分隔符）

[实现效果](https://miaolegemie.github.io/Javascript30/06%20-%20Type%20Ahead/)

## 任务要点

- 使用`fetch`请求数据
- 监听用户输入事件
- 根据用户输入的数据来查询
- 展示数据

## 步骤

1. 使用 `fetch` 请求数据
  - [`fetch`](https://developer.mozilla.org/zh-CN/docs/Web/API/Fetch_API)
  - `fetch` 返回一个 [`promise`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise)对象
  -
  - 使用[`Response`](https://developer.mozilla.org/zh-CN/docs/Web/API/Response)的 `json` 方法来将 `Response` 转换为 `json` 对象。读取以后会被设置为已读（因为 Responses 对象被设置为了 stream 的方式，所以它们只能被读取一次）
  - [使用扩展运算符储存返回的数据](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Spread_operator#%E6%9B%B4%E5%A5%BD%E7%9A%84_push_%E6%96%B9%E6%B3%95)
  - 注意错误处理
2. 监听用户输入事件
  - 在这里因为要实时响应用户输入，因此选择监听 [`input`](https://developer.mozilla.org/zh-CN/docs/Web/Events/input) 事件
  - `change` 事件触发情况
    - `<input type="radio">` 和 `<input type="checkbox">` 的默认选项被修改时（通过点击或者键盘事件）;
    - 当用户完成提交动作时 (例如：点击了 `<select>` 中的一个选项，从 `<input type="date">` 标签选择了一个日期，通过 `<input type="file">` 标签上传了一个文件，等 );
    - 当标签的值被修改并且失焦后，但并未进行提交 (例如：对 `<textarea>` 或者 `<input type="text">` 的值进行编辑后。).
  - `input` 事件触发情况
    - 当 `<input>` or `<textarea>` 的值变更时将触发 DOM 的 `input` 事件
    - 对于含有 `contenteditable` 属性的编辑器，内容变更时也会触发
3. 根据用户输入的数据来查询
  - 新建一个[`正则表达式`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Regular_Expressions)
  - 使用[`match()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/match) 来确定是否出现有用户查询的信息
    - **注意，`includes` 和 `indexOf` 都区分大小写，因此不能在此处使用**
4. 展示数据
  - 使用`[replace()]`(https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/replace) 来将用户查询的信息高亮
  - **使用[`toLocaleString()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString) 来为人口数据加上千位分隔符**
    - 此方法会返回这个数字在特定语言环境下的表示字符串，默认返回默认的语言环境和默认选项的格式化字符串
    - 此处还可以使用正则 `number.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',')`
    - 使用 `innerHTML` 将数据放入页面中

## 注意事项

`let` 和 `const` 所声明的不会出现在 `window` 对象上

ES6 规定，`var` 命令和 `function` 命令声明的全局变量，属于全局对象的属性；`let` 命令、`const` 命令、`class` 命令声明的全局变量，不属于全局对象的属性。理论上是Web页面中运行的所有JS代码的外层块。

[一篇博客](https://woozy.im/articles/declare-global-variables/)
