## localStorage主要有以下几种方法：

1. setItem(“key”,“value”)：存储名字为key的一个值value，如果key存在，就更新value
2. getItem(“key”)：获取名称为key的值，如果key不存在则返回null
3. removeItem(“key”)：删除名称为“key”的信息，这个key所对应value也会全部被删除
4. clear()：清空localStorage中所有信息
5. key()：键的索引
```
一个简单的例子：
localStorage.setItem(“name”,“panda”);//设置name为panda
localStorage.setItem(“name”,“Jane”);//覆盖之前的值，现在name所对应的值是Jane
localStorage.getItem(“name”);//获取name的值，即Jane
localStorage.removeItem(“name”);//删除name以及name的值
localStorage.clear();//清除localstorage里边所有数据
function forEachKey(callback) {//遍历显示localStorage中的key
  for (var i = 0; i < localStorage.length; i++) {
    callback(localStorage.key(i));
  }
}
```