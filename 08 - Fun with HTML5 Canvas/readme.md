# 08 Fun with HTML5 Canvas

## 任务

实现一个全屏画板（canvas），画笔粗细，颜色会随鼠标移动而改变

[实现效果](https://miaolegemie.github.io/Javascript30/08%20-%20Fun%20with%20HTML5%20Canvas/)

## 任务要点

1. 获取 canvas 元素并设置其样式以及笔刷等的基本样式
2. 绘制
3. 监听鼠标事件

## 步骤

1. 获取 canvas 元素并设置其样式以及笔刷等的基本样式
  - [canvas 元素有 `height` 和 `width` 两个属性（普通元素上没有这两个属性）](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLCanvasElement)，单位为 px ，而使用 [`style.width/height`](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLElement/style) 设置的话则需添加单位
  - 设置宽高为 `Window.innerWidth` 与 `Window.innerHeight`,则可全屏
    - 此方法会导致出现滚动条，如果想隐藏的话可设置 `overflow: hidden;`
  - [`canvas.getContext('2d')`](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLCanvasElement/getContext)获取上下文后可以设置一些笔刷样式，本任务中使用到了以下设置
    - `lineCap`：笔触的形状，有 round | butt | square 圆、平、方三种
    - `lineJoin`：线条相较的方式，有 round | bevel | miter 圆交、斜交、斜接三种
    - `lineWidth`：线的宽度
    - `strokeStyle`：图形边线的颜色和样式
    - `fillStyle`：图形内部的颜色和样式
2. 绘制
  - 使用以下方式进行绘制
    - `CanvasRenderingContext2D.moveTo()`：将一个新的子路径的起始点移动到(x，y)坐标
    - `CanvasRenderingContext2D.beginPath()`：清空子路径列表开始一个新的路径
    - `CanvasRenderingContext2D.lineTo()`：使用直线连接子路径的最后的点到x,y坐标
    - `CanvasRenderingContext2D.stroke()`：使用当前的样式描边子路径
  - 使用 `hsl` 来制作渐变色
    - [HSL and HSV](https://en.wikipedia.org/wiki/HSL_and_HSV)
      - H(hue) 代表色调，取值为 0~360，专业术语叫色相
      - S 是饱和度，可以理解为掺杂进去的灰度值，取值为 0~1
      - L 则是亮度，取值也是 0~1，或者百分比。
    - [`Color Models: RGB, HSV, HSL`](https://en.wikibooks.org/wiki/Color_Models:_RGB,_HSV,_HSL)

## 注意事项

1. [一份来自 MDN 的 canvas 教程](https://developer.mozilla.org/zh-CN/docs/Web/API/Canvas_API/Tutorial)
2. [行尾最好还是加分号](https://segmentfault.com/q/1010000007877511)，因为有些时候并不会像你以为的一样：
  ````
  a = b
  [x,y] = [1,2]
  会被解释成
  a = b[x,y] = [1,2]
  ````
