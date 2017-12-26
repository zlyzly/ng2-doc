## 项目部署
#### 1.需要
 #### 1.1 a:BtMstsc（链接服务器工具）- [地址](https://share.weiyun.com/11e46c7bb28b2640c01015d63edec65e)
 #### 1.2 b:FlashFxp （把本地打包好的文件上传到服务器的工具 - [地址](https://share.weiyun.com/7307c7463763352ce3f659b81868dca8)

 #### 1.3操作
 ```
 a:解压后一个文件node服务器壳 需要放在服务器上的文件打包 build 生成一个dist文件夹 
   先删掉node文件中的app文件 把dist改名成app 放进node文件中 。
   在重新给这个项目起名 cest 。
 b:首先连接到公司的服务器地址，成功之后 把cest 拖进到右边点击传输队列。
   或者在左边找到cest往右边拖

 ```
 #### 2.上传
  - 2.1 文件上传成功后，ls查看当前目录，cd 进入项目文件夹，npm install
 ``` 
     1.vi xxx.xxx 比如 text.txt 如果该文件已存在则打开文件，否则创建并进入文件
	    主要是去修改端口号。。。
     2.进入文件后 处于查看模式， i 进入编辑模式
     3.编辑完后 esc 退出当前模式，然后shlft + : 进入指令模式
     4.w 保存， q 退出， wq保存退出 q! 强退。
     5.mkdir xxx 创建文件夹
     6.mv 指令移动 相当于改名
     7.rm -rf 删除目录
 ```
 - 2.2 文件上传成功后，ls查看当前目录，cd 进入项目文件夹，npm install
 - 2.3 把项目挂上后，需要开启防火墙。
  - 2.4 sudo firewall-cmd --list-all 查看当前已开启的端口
 - 2.5 sudo firewall-cmd --add-port=8000/tcp --permanent （--permanent表示永久开放）remove对应删除
 - 2.6 sudo firewall-cmd --reload 开放端口后，需要重启下端口   之前的添加删除才会重新刷新
  - 2.7 启动好后，可直接打开 xxx.xxx.xxx.xxx:8000 打开项目了

 #### 3.删除
```
   3.1删除必须先要停止这个端口号的服务，然后在删掉。pm2 stop 0 # 停止ID为0的进程  
    、、pm2 delete 0 # 删除ID为0的应用程序
   3.2 然后把b中的文件删除掉，不可手动删除，首先切出到这个项目外操作 
   rm -rf 删除目录 这才删掉

```
#### 4.pm2常用命令
 ```
$ pm2 list 列出所有以PM2开始的进程
$ pm2 show [app-name] ＃ 显示应用程序的所有信息
$ pm2 flush 刷新
$ pm2 start app.js --name ='first-table' ＃ 启动应用程序并将其命名为“first-table”
$ pm2 stop all # 停止所有应用程序
$ pm2 stop 0 # 停止ID为0的进程
$ pm2 restart all # 重新启动所有应用程序
$ pm2 gracefulReload all # 重新加载所有应用程序
$ pm2 delete all # 删除所有的应用程序
$ pm2 delete 0 # 删除ID为0的应用程序

 ```


