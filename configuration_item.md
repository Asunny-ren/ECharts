# ECharts ������

[������](http://echarts.baidu.com/option.html#title)

�Ȼ���׼���õ�dom��ʼ��һ��echartʵ��

var myChart = echarts.init(document.getElementById('main'));

�ٶ��������������

var option = {
    ...
}

Ȼ��ͨ��

myChart.setOption (option)

����ʾ���õ�ͼ��;

===============================================================

## ���������ϸ����

## title

    �������������������͸����⡣

��ECharts3�п��Դ����������������

##### ����

* title.show �Ƿ���ʾ����

  boolean | default: true

* title.text �������ı�,֧��\n����

  string | default: ''

* title.link �������ı�������

  string | default: ''

* title.target ָ�����ڴ�����������

  string | default: 'blank'

  'self'  'blank'

* title.textAlign �����ı�ˮƽ���룬֧�� 'left', 'center', 'right'��Ĭ�ϸ��ݱ���λ�þ�����

  string |