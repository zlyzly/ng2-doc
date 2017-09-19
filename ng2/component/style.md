####常用到样式
 - 使用true-false来控制是否使用该样式
  - [ngClass]添加class类型：
``` 
1.html中(多个一起使用)
<div [ngClass="{'one':true,'two':flase}"]>添加属性</div>
2.css 
.one{
    color:'red';
}
.two{
    font-size:'16px';
}
```