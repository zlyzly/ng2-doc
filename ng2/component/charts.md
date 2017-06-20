### ng2中使用了什么图表
- 定义图表的模板 ba-chartist-chart
- 还有图标的分类  lines/bars/pies ...chart.simple_line_chart 、chart.simple_bar_chart、chart.simple_pie
- 定义了图标的样式 baChartistChartClass
- 定义了type类型  baChartistChartType
- 定义了数据data  [baChartistChartData]="data['areaLineData']"
- 定义了options   [baChartistChartOptions]="data['areaLineOptions']"  ---除了data外数据都在这里，还有图标的背景大小，位置。
```
    样式吧：：：baChartistChartClass="ct-chart stacked-bar" ，，stacked-bar：图的宽度间距
    图标的类型：：：baChartistChartType="Bar" 图的类型只要修改就可以了Line、Bar

    数据：：[baChartistChartData]="data['simpleBarData']",,simpleBarData，数据对象，

    X,Y轴数据(间隔值)设置：：：[baChartistChartOptions]="data['simpleBarOptions']"

    是否是放在一个对象中(分开)，还是一个值上(叠加)：：：[baChartistChartResponsive]="data['multiBarResponsive']"

    子组件绑定的值，传到父组件的[baChartistChartData]，[baChartistChartOptions]
```
 


