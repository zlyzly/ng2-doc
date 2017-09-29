#### ng2中的表单
  1. 表单注意事项
  ```
    1.必须引入 ,验证要引入ReactiveFormsModule 和一个服务(可单独文件或与module同级)
        import { FormsModule, ReactiveFormsModule } from '@angular/forms';
        import { ForbiddenValidatorDirective } from './forbidden-name.directive'; 
       1.1 forbidden-name.directive.ts
        import { Directive, Input, OnChanges, SimpleChanges } from '@angular/core';
        import { AbstractControl, NG_VALIDATORS, Validator, ValidatorFn, Validators } from '@angular/forms';

        /** A hero's name can't match the given regular expression */
        export function forbiddenNameValidator(nameRe: RegExp): ValidatorFn {
        return (control: AbstractControl): {[key: string]: any} => {
            const forbidden = nameRe.test(control.value);
            return forbidden ? {'forbiddenName': {value: control.value}} : null;
        };
        }

        @Directive({
        selector: '[forbiddenName]',
        providers: [{provide: NG_VALIDATORS, useExisting: ForbiddenValidatorDirective, multi: true}]
        })
        export class ForbiddenValidatorDirective implements Validator {
        @Input() forbiddenName: string;

        validate(control: AbstractControl): {[key: string]: any} {
            return this.forbiddenName ? forbiddenNameValidator(new RegExp(this.forbiddenName, 'i'))(control)
                                    : null;
        }
        }

    <!-- 2.组件在使用的时候，同样引入两个 -----()
    import { FormControl, FormGroup, Validators } from '@angular/forms';
    import { ForbiddenValidatorDirective } from './forbidden-name.directive';  -->
    2.html 中注意较多 
        2.1 双向绑定 1.name='aa' 属性 ，2.[(ngModule)]='obj.aa',
        (obj):ts要有模型字段设置, obj = new MoXing(); 构造函数可随意用this.obj 。
        2.2 form标签要有id #heroForm="ngForm" 接着[hidden]="heroForm.submitted"控制提交按钮待验证全部通过才可以点击 [disabled]="heroForm.invalid" 提交按钮起初是失效的
        2.3 样式 
        [ngClass]='{special:jbqt ==="jbxx"}' / [ngClass]="{'special': isSpecial}" / [class.special]="isSpecial"(一正一反)true的时候加上false去掉 
        用变量的值控制是否显示.select的样式
        [ngStyle]="{'background-color':'green'}" 
        [style.color]="isSpecial ? 'red' : 'green'">
        [style.style-property] / [style.font-size.em]="isSpecial ? 3 : 1" /[style.font-size.%]="!isSpecial ? 150 : 50"  em/px/%单位 
     
    3. 复制表单
        input: [value]="obj.name" 
        * select:
        <select name="aaa" class="form-control" id="input09" [(ngModel)]='userObj.aaa'>
        选中: <option value="全部部门" [selected[='true'  >全部部门</option> 
        赋值: <option [value]='bm' *ngFor="let bm of bumenArr;let i=index;">{{bm}}</option>
        </select>
        * checkout :
 ```
