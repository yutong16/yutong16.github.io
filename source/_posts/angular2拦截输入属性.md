---
title: 拦截输入属性
date: 2017-09-08 14:55:46
categories: 前端框架
tags:
- Angular2.0
toc: true
author: yutong16
---
### 拦截输入属性
#### 父组件向子组件传递数据，是通过在父组件的属性绑定将数据流向子组件的。子组件可以拦截输入属性的数据并进行相应的处理。有两种方式可以拦截，一是setter拦截属性，而是ngOnChanges监听数据变化
+ <!-- more -->
<The rest of contents | 余下全文>
1. setter拦截属性 
> getter和setter通常配套使用，用来对属性进行相关约束。
    <pre>
        @Component({
            selector:'list-item',
            template:`
                <div>
                    <label class = "contact-name" >{{contactObj.name}}</label>
                </div>
            `
        })
        export class ListComponent implements OnInit{
            _contact:object={};
            @Input()
            set contactObj(contact:object){
                this._contact.name=(contact.name && contact.name.trim() || 'no name set');
            }
            get contactObj(){ return this._contact}

        }
    </pre>
2. ngOnChanges监听数据变化
> ngOnChanges用于及时响应Angular在属性绑定中发生的数据变化，该方法接受一个对象参数，包含当前值和变化前的值。在ngOnInit之前，或者当数据绑定的输入属性的值发生变化时会触发。ngOnChanges是组件的生命周期钩子之一。
>> SimpleChanges类，是angualer的一个基础类，用于处理数据的前后变化，其中包含两个重要的成员变量，分别是previousValue和currentValue,previousValue是获取变化前的数据，而currentValue是获取变化后的数据。
    <pre>
        ngOnChanges(changes:{[proKey:string]:SimpleChanges}){
            let log:string=[];
            for(let proName in changes){
                let changeProp=changes[propName],
                from=JSON.stringify(changeProp.previousValue),
                to=JSON.stringify(changeProp.currentValue);

                log.push(`${propName} changed from ${from} to ${to}`)
            }
        }
    </pre>