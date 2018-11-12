### ng2(动画可用多个)
- 定义一个组件文件并导出 
- 进场：void => * 离场：* => void 
```
    -----------飞入--------------
    import { trigger, state, style, transition, animate, keyframes } from '@angular/animations';

    export const flyIn = trigger('flyIn', [
    state('in', style({transform: 'translateX(0)'})),
    transition('void => *', [
        animate(300, keyframes([
            style({opacity: 0, transform: 'translateX(-100%)', offset: 0}),
            style({opacity: 1, transform: 'translateX(25px)',  offset: 0.3}),
            style({opacity: 1, transform: 'translateX(0)',     offset: 1.0})
        ]))
    ]),
    transition('* => void', [
            animate(300, keyframes([
            style({opacity: 1, transform: 'translateX(0)', offset: 0}),
            style({opacity: 1, transform: 'translateX(-25px)', offset: 0.7}),
            style({opacity: 0, transform: 'translateX(100%)',  offset: 1.0})
        ]))
    ])
    ]);
    ------------显隐----------------
    import { trigger, state, style, transition, animate, keyframes } from '@angular/animations';

    export const fadeIn = trigger('fadeIn', [
    transition("void => *", [
        style({ opacity: 0 }),
        animate(2000, style({ opacity: 1 }))
    ]),
    transition("* => void", [
        animate(2000, style({ opacity: 0 }))
    ])
    ]);
```
- 在使用的组件中引入 import { flyIn } from './flyin';
- html模板最外层 div 上添加[@flyIn]="'active'";

### ng2(文字滚屏)
```
import { trigger, state, style, animate, transition } from '@angular/animations';
export const SingalAnimate = trigger('signal', [
    state('go1', style({ 'margin-top': '0px' })),
    state('go2', style({ 'margin-top': '-144px' })),
    state('go3', style({ 'margin-top': '-288px' })),
    state('go4', style({ 'margin-top': '-432px' })),
    transition('go1 => go2', animate(300)),
    transition('go2 => go3', animate(300)),
    transition('go3 => go4', animate(300)),
    transition('go4 => go1', animate(0)),
]);
```
- 使用方法同上[@signal]="'go1'" // 或者变量 赋初始值

