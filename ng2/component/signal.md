### 观察者模式 
  #### 例子：出版社出版的报刊 --被观察者，订阅者(用户) --观察者(多个)，被观察者(会有各种发生变化的事件列表)当发生变化的时候，订阅者如果订阅(注册))了这些事件，当被观察者的这些事件列表中任何一个变化时就会通过消息机制来通知这些订阅者，订阅者会发生变化，这个变化过程或变化结果与被观察者没有任何关系。
   - notifyDataChanged：被观察者事件列表之一。
   - [中文文档] (https://rxjs-cn.github.io/rxjs5-ultimate-cn/content/recipes-auto-complete.html)
   - [观察者模式](https://baike.baidu.com/item/%E8%A7%82%E5%AF%9F%E8%80%85%E6%A8%A1%E5%BC%8F/5881786?fr=aladdin)