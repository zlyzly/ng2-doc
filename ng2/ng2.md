#### ng2项目的一些命令
```
1. 安装过node,typescript,python,angular-cli.cnpm.
  - 1.1 可能使用淘宝镜像安装依赖包会比较快，但是还是npm install 比较靠谱，安装的文件比较少 最重要的是没有问题项目能运行起来。
  - 1.2 出现的问题 appModule isnot ngModule 项目样式不兼容 typescript(2.2.2)版本与rxjs(5.4.0)冲突 这些问题都是使用cnpm安装出现的.
  - 1.3 安装angular环境 
  npm install -g @angular/cli@latest 最新的版本
2. 使用new新建一个angular项目 ng new myporject 
3. cnpm i --save  需要的插件 cnpm install 
4. ng serve /npm start 
5. 使用命令添加组件  ng g component 组件名
6. 提交代码合并之前 构建项目 npm run build:prod 避免 ng serve 不能暴露的错误。
7. 注意代码规范，不使用的虽没有报错，但是最好不要保留到代码中。
```
#### ng2用到知识点
  - [ng2-常用样式](component/style.md)
  - [ng2-动画](component/animation.md)
  - [ng2-localStroage](component/local.md)
  - [ng2-图表](component/charts.md)
  - [echarts图表插件](component/echarts.md)
  - [Input父传子](component/input.md)
  - [ng2-form表单](component/validatar.md)
  - [观察者模式理解](component/signal.md)
  - [项目中英文版](component/i18n.md)
  - [长连接](component/socket.md)
