#### 项目用到socket来接収通知
- [socket文档](https://socket.io/docs/client-api/)
- [学习demo](https://www.cnblogs.com/lxxhome/p/5980615.html)
```
  配置开发环境链接后端api时 添加socketApi:'122.2.67:8080' 接口地址
  创建一个socket.service.ts
  socket 方法
   1.连接socket(调用)
   init() {} 
   2.断开socket
   this.socket.disconnect();
   3.solket状态
    connect：连接成功
    connecting：正在连接
    disconnect：断开连接
    connect_failed：连接失败
    error：错误发生，并且无法被其他事件类型所处理
    message：同服务器端message事件
    anything：同服务器端anything事件
    reconnect_failed：重连失败
    reconnect：成功重连
    reconnecting：正在重连
    当第一次连接时，事件触发顺序为：connecting->connect；当失去连接时，事件触发顺序为：disconnect->reconnecting（可能进行多次）->connecting->reconnect->connect。

    demo:
    建立一个socket连接
    var socket = io(“ws://103.31.201.154:5555”);
    监听服务消息
    socket.on('msg',function(data){
        socket.emit('msg', {rp:"fine,thank you"}); //向服务器发送消息
        console.log(data);
    });
    socket.on(“String”,function(data)) 监听服务端发送的消息 Sting参数与服务端emit第一个参数相同
    监听socket断开与重连。
    socket.on('disconnect', function() {
        console.log("与服务其断开");
    });
    socket.on('reconnect', function() {
        console.log("重新连接到服务器");
    });
```