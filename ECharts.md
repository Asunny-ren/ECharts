# ECharts 学习

[ECharts](http://echarts.baidu.com/index.html)

[ECharts实例](http://echarts.baidu.com/examples.html)

### ECharts:一个纯javascript的图表库，兼容PC和移动设备，浏览器兼容（IE8以上，chrome，firefox，safari等），底层依赖的是轻量级的canvas类库ZRender。

### 丰富的图标类型

提供了常规的折线图，柱状图，散点图，饼图，K线图，用于统计的盒形图，用于地理数据可视化的地图，热力图，线图，用于关系数据可视化的关系图，treemap，多维数据可视化的平行坐标，还有用于 BI 的漏斗图，仪表盘，并且支持图与图之间的混搭。

### 多坐标系的支持

ECharts 3 开始独立出了“坐标系”的概念，支持了直角坐标系（catesian，同 grid）、极坐标系（polar）、地理坐标系（geo）


## 获取ECharts

1. [下载ECharts](http://echarts.baidu.com/download.html)

2. node安装

   npm install echarts --save

3. cdn

   https://cdnjs.com/libraries/echarts

   https://unpkg.com/echarts@3.2.3/dist/

   http://www.bootcdn.cn/echarts/

## 引入ECharts

``` html
<!DOCTYPE html>
<html>
<header>
    <meta charset="utf-8">
    <!-- 引入 ECharts 文件 -->
    <script src="echarts.min.js"></script>
</header>
</html>
```

## 绘制一个简单的图表

在绘图前我们需要为 ECharts 准备一个具备高宽的 DOM 容器(获取这个dom容器的时候必须为dom对象，不可以是jquery或者其他对象)。

并且这个DOM容器在刚开始必须定义实际的高宽，不可以用百分比

``` html
<body>
    <!-- 为 ECharts 准备一个具备大小（宽高）的 DOM -->
    <div id="main" style="width: 600px;height:400px;"></div>
</body>
```

然后就可以通过 echarts.init 方法初始化一个 echarts 实例并通过 setOption 方法生成一个简单的柱状图，下面是完整代码。

``` html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>ECharts</title>
    <!-- 引入 echarts.js -->
    <script src="echarts.min.js"></script>
</head>
<body>
    <!-- 为ECharts准备一个具备大小（宽高）的Dom -->
    <div id="main" style="width: 600px;height:400px;"></div>
    <script type="text/javascript">
        // 基于准备好的dom，初始化echarts实例
        var myChart = echarts.init(document.getElementById('main'));

        // 指定图表的配置项和数据
        var option = {
            title: {
                text: 'ECharts 入门示例'
            },
            tooltip: {},
            legend: {
                data:['销量']
            },
            xAxis: {
                data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
            },
            yAxis: {},
            series: [{
                name: '销量',
                type: 'bar',
                data: [5, 20, 36, 10, 10, 20]
            }]
        };

        // 使用刚指定的配置项和数据显示图表。
        myChart.setOption(option);
    </script>
</body>
</html>
```