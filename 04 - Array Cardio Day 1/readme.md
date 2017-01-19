# 04 Array Cardio, Day 1

## 任务

1. 筛选 16 世纪出生的发明家
2. 展示发明家的全名
3. 把发明家按照出生先后从前到后进行排序
4. 计算所有的发明家加起来一共活了多少岁
5. 按照发明家活了多久来进行排序
6. 筛选出一个网页里含有某个词语的标题
7. 按照姓氏来对一些人进行排序
8. 统计给出数组中各个物品的数量

[实现效果](https://miaolegemie.github.io/Javascript30/04%20-%20Array%20Cardio%20Day%201/)

## 任务要点

无

## 步骤
1. 筛选 16 世纪出生的发明家
  - 使用 [`Array.prototype.filter()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) 来完成
2. 展示发明家的全名
  - 使用 [`Array.prototype.map()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/map) 来完成
  - 字符串拼接采用 模板字符串 来完成
3. 把发明家按照出生先后从前到后进行排序
  - 使用 [`Array.prototype.sort()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) 来完成
4. 计算所有的发明家加起来一共活了多少岁
  - 使用 [`Array.prototype.reduce()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce) 来完成
5. 按照发明家活了多久来进行排序
  - 使用 [`Array.prototype.sort()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) 来完成
6. 筛选出一个网页里含有某个词语的标题
  - 找出某一网站下需要信息可能存在的集合
  - 使用 [`Array.from()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/from) 将该集合(是一个 NodeList )转换成数组
  - 再使用 [`Array.prototype.map()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/map) 和 [`Array.prototype.filter()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
  - 最后使用 [`String.prototype.includes()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/includes) 来判断一个字符串是否含有该标题
  - **链式调用**
7. 按照姓氏来对一些人进行排序
  - 使用 [`String.prototype.split()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/split) 来分割字符串以获得姓氏
  - 使用 [`Array.prototype.sort()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) 来进行排序
8. 统计给出数组中各个物品的数量
  - 使用 [`Array.prototype.reduce()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce) 来“遍历”数组
  - 访问对象属性的点表示法和方括号表示法的区别
    - 建议使用点表示法
    - 方括号表示法可以 通过变量来访问属性 或 访问带有关键字或特殊符号的属性 或 在程序运行时创建和修改属性
  - [`Array.prototype.reduce()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce) 传入的最后一个参数为初始值，在本任务中需要传入一个空对象才可正常运行

## 其他
[Chrome DevTools](https://developer.chrome.com/devtools)

以及 [chrome 插件开发](https://developer.chrome.com/extensions/getstarted)

还有[中文文档](https://crxdoc-zh.appspot.com/apps/about_apps)
