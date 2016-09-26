# ECharts ѧϰ

[ECharts](http://echarts.baidu.com/index.html)

[EChartsʵ��](http://echarts.baidu.com/examples.html)

### ECharts:һ����javascript��ͼ��⣬����PC���ƶ��豸����������ݣ�IE8���ϣ�chrome��firefox��safari�ȣ����ײ�����������������canvas���ZRender��

### �ḻ��ͼ������

�ṩ�˳��������ͼ����״ͼ��ɢ��ͼ����ͼ��K��ͼ������ͳ�Ƶĺ���ͼ�����ڵ������ݿ��ӻ��ĵ�ͼ������ͼ����ͼ�����ڹ�ϵ���ݿ��ӻ��Ĺ�ϵͼ��treemap����ά���ݿ��ӻ���ƽ�����꣬�������� BI ��©��ͼ���Ǳ��̣�����֧��ͼ��ͼ֮��Ļ�

### ������ϵ��֧��

ECharts 3 ��ʼ�������ˡ�����ϵ���ĸ��֧����ֱ������ϵ��catesian��ͬ grid����������ϵ��polar������������ϵ��geo��


## ��ȡECharts

1. [����ECharts](http://echarts.baidu.com/download.html)

2. node��װ

   npm install echarts --save

3. cdn

   https://cdnjs.com/libraries/echarts

   https://unpkg.com/echarts@3.2.3/dist/

   http://www.bootcdn.cn/echarts/

## ����ECharts

``` html
<!DOCTYPE html>
<html>
<header>
    <meta charset="utf-8">
    <!-- ���� ECharts �ļ� -->
    <script src="echarts.min.js"></script>
</header>
</html>
```

## ����һ���򵥵�ͼ��

�ڻ�ͼǰ������ҪΪ ECharts ׼��һ���߱��߿�� DOM ����(��ȡ���dom������ʱ�����Ϊdom���󣬲�������jquery������������)��

�������DOM�����ڸտ�ʼ���붨��ʵ�ʵĸ߿��������ðٷֱ�

``` html
<body>
    <!-- Ϊ ECharts ׼��һ���߱���С����ߣ��� DOM -->
    <div id="main" style="width: 600px;height:400px;"></div>
</body>
```

Ȼ��Ϳ���ͨ�� echarts.init ������ʼ��һ�� echarts ʵ����ͨ�� setOption ��������һ���򵥵���״ͼ���������������롣

``` html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>ECharts</title>
    <!-- ���� echarts.js -->
    <script src="echarts.min.js"></script>
</head>
<body>
    <!-- ΪECharts׼��һ���߱���С����ߣ���Dom -->
    <div id="main" style="width: 600px;height:400px;"></div>
    <script type="text/javascript">
        // ����׼���õ�dom����ʼ��echartsʵ��
        var myChart = echarts.init(document.getElementById('main'));

        // ָ��ͼ��������������
        var option = {
            title: {
                text: 'ECharts ����ʾ��'
            },
            tooltip: {},
            legend: {
                data:['����']
            },
            xAxis: {
                data: ["����","��ë��","ѩ����","����","�߸�Ь","����"]
            },
            yAxis: {},
            series: [{
                name: '����',
                type: 'bar',
                data: [5, 20, 36, 10, 10, 20]
            }]
        };

        // ʹ�ø�ָ�����������������ʾͼ��
        myChart.setOption(option);
    </script>
</body>
</html>
```