# ECharts 配置项

[配置项](http://echarts.baidu.com/option.html#title)

先基于准备好的dom初始化一个echart实例

var myChart = echarts.init(document.getElementById('main'));

再定义配置项和数据

var option = {
    ...
}

然后通过

myChart.setOption (option)

来显示配置的图表;

=================================================================================

## 配置项的详细介绍

## title

   标题组件，包含主标题和副标题。

在ECharts3中可以存在任意多个标题组件

##### 属性

* title.show 是否显示标题

  boolean | default: true

* title.text 主标题文本,支持\n换行

  string | default: ''

* title.link 主标题文本超链接

  string | default: ''

* title.target 指定窗口打开主标题链接

  string | default: 'blank'

  'self'  'blank'

* title.textAlign 标题文本水平对齐，支持 'left', 'center', 'right'，默认根据标题位置决定。

  string | default: 根据标题位置决定

=================================================================================================

## legend

  图例组件：展现了不同系列的标记(symbol)，颜色和名字。可以通过点击图例控制哪些系列不显示。

  ECharts3中单个echarts实例可以存在多个图例组件，会方便多个图例的布局。


===========================================================================================================

## grid

直角坐标系内绘图网络，单个grid内最多可以放置下两个X轴，左右两个Y轴。可以在网格上绘制折线图，柱状图，散点图（气泡图）。

在ECharts3以下一个ECarts实例中只可以存在一个grid组件，在ECharts3中可以存在任意多个grid组件。

==========================================================================================================

## xAxis

直角坐标系grid中的x轴，单个grid组件最多只能放下两个x轴；

## yAxis

直角坐标系grid中的y轴，一般情况下单个grid组件最多只能放左右两个y轴，多于两个y轴需要通过配置offset属性防止同个位置多个Y轴的重叠。

===========================================================================================================


## polar

极坐标系，可以用于散点图和折线图。每个极坐标系拥有一个角度轴和一个半径轴。

## radiusAxis

极坐标系的半径轴

## angleAxis

极坐标系的角度轴

========================================================================================

## radar

雷达图坐标系组件，只适用于雷达图

> 雷达图坐标系与极坐标系的不同的是它的每一个轴（indicator指示器）都是一个单独的维度.可以通过name, axisLine, axisTick, axisLabel, splitLine, splitArea几个配置项配置指示器坐标轴线的样式。

## dataZoom[i]

dataZoom组件用于区域缩放，从而能自由关注细节的数据信息，或者概览数据整体，或者去除离群点的影响。

dataZoom组件

  * dataZoomInside(内置型数据区域缩放组件)：内置于坐标系中，使用户可以在坐标系上通过鼠标拖拽、鼠标滚轮、手指滑动（触屏上的）来缩放或漫游坐标系

  * dataZoomSlide(滑动条形数据区域缩放组件)：有单独的滑动条，用户在滑动条上进行缩放和漫游。

  * dataZoomSelect(dataZoomSelect)：提供一个选框进行数据区域缩放。

## visualMap[i]

视觉映射组件，将数据映射到视觉元素（视觉通道）。

视觉元素可以是：

  * symbol:图元的图形类别

  * symbolSize:图元的大小

  * color:图元的颜色

  * colorSAlpha:图元的颜色的透明度

  * opacity:图元以及其附属物（如文字标签）的透明度

  * colorLightness:颜色的明暗度

  * colorSaturation:颜色的饱和度

  * colorHue:颜色的色调

visualMap组件可以定义多个，从而可以同时对数据中的多个维度进行视觉映射。

visualMap组件可以定义为分段型(visualMapPiecewise)或连续型(visualMapContinuous),通过type来区分

``` javascript
option = {
    visualMap: [
        { // 第一个 visualMap 组件
            type: 'continuous', // 定义为连续型 viusalMap
            ...
        },
        { // 第二个 visualMap 组件
            type: 'piecewise', // 定义为分段型 visualMap
            ...
        }
    ],
    ...
};
```

## tooltip

提示框组件

## toolbox

工具栏。内置有导出图片，数据视图，动态类型切换，数据区域缩放，重置五个工具。

## brush

区域选择组件，用户可以选择图中一部分数据，从而便于向用户展示被选中数据，或者他们的一些统计计算结果。

## geo

地理坐标系组件：用于地图的绘制，支持在地理坐标系上绘制散点图，线集。

## parallel

平行坐标系：一种常用的可视化高维数据的图表

## parallelAxis

平行坐标系中的坐标轴。

## singleAxis

单轴，可以被应用到散点图中展示一维数据。

## timeline

timeline组件，提供了在多个ECharts option间进行切换、播放等操作的功能。

## series[i]

系列列表，每个系列通过type决定自己的图表类型

## textStyle

全局的字体样式

  * textStyle.fontStyle 字体风格 normal

  * textStyle.fontWeight 文字字体的粗细 normal

  * textStyle.fontFamily 文字的字体系列 'sans-serif'

  * textStyle.fontSize 文字的字体大小

## animation

是否开启动画，默认开启

## animationThreshold = 2000

是否开启动画的阈(yu)值,当单个系列显示的图形数量大于这个阈值时会关闭动画。

## animationDuration

初始动画的时长

## animationEasing

初始动画的缓动效果

## aniamationDelay

初始动画的延迟，支持回调函数，可以通过每个数据返回不同的delay时间更戏剧的初始动画效果

## animationDurationUpdate

数据更新动画的时长

## animationEasingUpdate

数据更新动画的缓动效果

## animationDelayUpdate

数据更新动画的延迟，支持回调函数，可以通过每个数据返回不同的delay时间实现更戏剧的更新动画效果

## progressive

> 渐进式渲染时每一帧绘制图形数量，设为 0 时不启用渐进式渲染，支持每个系列单独配置。

> 在图中有数千图形甚至好几万图形的时候，一下子把图形绘制出来，或者交互重绘的时候可能会造成界面的卡顿甚至假死，因此 ECharts 从 3.2.0 开始支持大量图形的渐进式渲染（progressive rendering），渲染的时候会把创建好的图形分到数帧中渲染，每一帧渲染只渲染指定数量的图形。

> 该配置项就是用于配置该系列每一帧渲染的图形数，默认是 400 个，可以根据图表图形复杂度的需要适当调整这个数字使得在不影响交互流畅性的前提下达到绘制速度的最大化。比如在 lines 图或者平行坐标中线宽大于 1 的 polyline 绘制会很慢，这个数字就可以设置小一点，而线宽小于等于 1 的 polyline 绘制非常快，该配置项就可以相对调得比较大。

## progressiveThreshold

启用渐进式渲染的图形数量阈值，在单个系列的图形数量超过该阈值时启用渐进式渲染

## blendMode

图形的混合模式

## hoverLayerThreshold

图形数量阈值，决定是否开启单独的hover层，在整个图表的图形数量大于该阈值时开启单独的hover层。

单独的hover层主要是为了在高亮图形的时候不需要重绘整个图表，只需要把高亮的图形放入单独的一个canvas层进行绘制，防止在图形数量很多的时候因为高亮重绘所有图形而导致卡顿











































