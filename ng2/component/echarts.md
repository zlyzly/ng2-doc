### echarts-ng2
- [githubdemo](https://github.com/zlyzly/echarts-ng2)
1. 先要安装插件  cnpm install echarts-ng2 --save
2. 使用
```
    1.如果使用组件的父组件是不是是根组件,在其父组件的module中引入
    import { EchartsNg2Module } from 'echarts-ng2';
    2.在本组件中引入
    import { EChartOption } from 'echarts-ng2';//数据
    import 'echarts/theme/dark';//主题样式
    3.配置图表数据 
    option: EChartOption = {
        title: {
            text: 'ECharts 入门示例'
        },
        tooltip: {},
        legend: {
            data: ['销量']
        },
        xAxis: {
            data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
        },
        yAxis: {},
        series: [{
            name: '销量',
            type: 'line',
            data: [5, 20, 36, 10, 10, 20]
        }]
    };
    4.模板html文件
    <echarts-ng2 [option]="option"></echarts-ng2> 
    或者这个作为模板，父组件的html中引入子组件的标签。`<event-charts></event-charts>`
```