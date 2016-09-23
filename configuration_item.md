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

===============================================================

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

  string |