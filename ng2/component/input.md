### 父子传值 @Input @Ouput 
- 父---子@Input/子--父@Ouput
    1. 首先引入Input、Output
```
    import { Component, OnInit,Input, Output, EventEmitter,OnChanges,SimpleChanges} from '@angular/core';
```
- 
    2. 传递的值A(数组)起初在父组件，在子组件间中定义@Input 
```
     @Input() value;
     @Output() childEvent = new EventEmitter<any>(); 
```
- 
    3. 子组件的html模板在父组件中使用 值A被绑在子组件定义的value上。

```
     selector: 'app-zi',
     `<app-zi [value]='A' (childEvent)="getChildEvent($event)"></app-zi>`
```
- 
    4. 子组件的html同时子组件有一个点击事件用来像父组件发射数据。
```
    <!--如果父组件的值能传过来 ，子组件就能用了-->
    <p *ngFor="let item of value;let i= index" (click)="fireChildEvent(i)">
        {{ item }}
    </p>
```
```
    // 子组件的点击
    fireChildEvent(i){
     console.log(i)//这个数组的索引值，我要传给父组件，让其来操作这个list数组。
     this.childEvent.emit(i);//childEvent:事件监听者。
    }
```
- 
    5. childEvent:事件发射者也绑了一个事件来检测子组件通过发射A的索引，父组件得到索引对A值进行（处理）。事件执行之后会触发父组件的
```  
    // 通过子组件的方法把索引传过来对A(list数组)进行处理。
    getChildEvent(i) {
    this.list.splice(i, 1)
    }
```
- 
    6. 单独使用@Input @Output 
```
    子传父 用事件监听者。把父元素需要的数据发射到父组件。
    还是在子组件中运用，子组件中有一个点击者，把值传过去,
    在父组件中用子组件时把点击事件绑定事件监听者，参数带上($event)，多个参数时可以放进一个对象中，比较方便。
    子组件.html
    <button (click)='three(obj)'>点击</button>
    子组件.ts
    @Output() threeEvent = new EventEmitter<any>();
    <!--点击事件-->
    three(obj: Object) {
         obj = {
            hide:this.hide,
            list:this.list,
        }
        this.threeEvent.emit(obj);
    }
    
    父组件.html
    <zi-three (threeEvent)="getThreeEvent($event)"></zi-three>
    父组件.ts
    getThreeEvent(obj:Object){
    console.log(obj);
    console.log(obj['list'])
    this.hide = obj['hide'];
    }
    
```