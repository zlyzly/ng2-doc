#### 先打开数据库，重开窗口开启服务--命令操作
```
 1. 选择安装路径，d盘。路径不要放太深，d:mongodb，新建mongodb文件夹。
 2. 在mongodb下新建一个data文件夹。
 3. cmd进入到mongodb\bin下指定路径mongod.exe --dbpath "D:\mongodb\data" 
 4.数据库已经启动。新打开一个命令工具，
 5.进到mongodb\bin下 输入mongo 启动服务。
 6.使用数据库时必须要先完成1,2,3步骤，开启服务。
```

#### express 创建node+mongo项目
```
1. npm全局安装 express、express-generator
2. 生成项目基本框架 命令: express hello,4.x版本的express默认页面模板引擎是jade,如果想用ejs,命令应该是这样的: express -e hello
3. 项目运行 命令:  cd hello && npm install
4. bin下的www是项目入口
5. node_moduls 项目所需模块
6. public 静态资源,如图片,js,css
7. routes 路由文件
8. views 页面文件
9. app.js 项目需要的中间件等基本配置
10. package.json 定义项目的基本信息等,包括项目所需要的模块名和版本

```