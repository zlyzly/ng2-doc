#### 常用到样式
 - 使用true-false来控制是否使用该样式
  - [ngClass]添加class类型：
``` 
1. html中(多个一起使用)
<div [ngClass="{'one':true,'two':flase}"]>添加属性</div>
 或者 [ngStyle]="{'background-color':'green'}"
2. css 
.one{
    color:'red';
}
.two{
    font-size:'16px';
}
3. 判断用法
[ngClass]="{'text-success':username == 'zxc'}"
[ngClass]="{'text-success':index == 0}"

4. 例子
const arr = [1, 3, 4, 5, 6]
<ul>
    <li *ngFor="let item of arr, let i = index">
        <span [ngClass]="{'text-danger': i==0}">{{item}}</span>
    </li>
</ul>
```
 - 使用style
 ```
    1. [style.padding-left.px]="obj.treeheight == 2 ? 30 : 0" 
    2. [style.color]="obj.isShow == true ? 'red' : 'pink'"  // [style.color]="obj.isShow ? 'red' : 'pink'" 
 ```