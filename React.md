# CH1 React简介

## 什么是React

>  虚拟DOM 

React组件(虚拟DOM)   ->   DOM元素(真实DOM)

React中虚拟组件有变化时, 会生成一个新的虚拟DOM, React会拿新生成的和之前的虚拟DOM比较检测发生了什么变化, 然后更新真实的DOM

React不会直接改变真实DOM

## 配置环境(npm)

>  去node.js官网下载nodejs 用到npm

> install gobally 这个叫c-r-a的包 可以理解为pip install

> 一定要改成国内镜像 不然npm install会变得很慢

https://juejin.cn/post/6844903999515131911

```bash
npm i -g create-react-app@1.5.2
```

## 创建项目

1. 在父级文件夹下 create-react-app react-app:

   ​	创建名为"react-app"的react程序<img src="https://i.loli.net/2020/12/28/p6wxUas7JqX4O1W.png" alt="image-20201008233100546" style="zoom: 50%;" />

2. 进入react-app文件夹 运行npm start

   <img src="https://i.loli.net/2020/12/28/vqJWBSaTQlyw92e.png" alt="image-20201008234746845" style="zoom: 50%;" />


## Hello World

>  jsx表达式

形如: const element = <h1>hello world</h1>    react会把表达式转化为React,createElement 所以要导入React包

下面两个写法等价: <h1>helloworld</h1> == React.createElemment('h1')

>  js和jsx

JS：即JavaScript，一种直译式脚本语言

JSX:即JavaScript XML——一种在React组建内部构建标签的类XML语法。(增强React程序组件的可读性)

> 导入包   render方法

删掉src里面所有的文件  新建index.js文件夹(浏览器默认找index.html)

<img src="https://i.loli.net/2020/12/28/taAkKBY5IwFNJhl.png" alt="image-20201009004456455" style="zoom:50%;" />

index.HTML中有一个id=root的div 这个div就是React的容器

# CH2 ES6

## Let Var Const

用var定义的范围: 整个函数

用let定义的范围: block

用const定义的范围: block

let和const的区别: 用const定义的变量不能再改变

> ==不用var 用let和const==

## Object

**在JS中对象就是一组键值对**

```js
const person = {
    name: 'Mosh',
    walk() {},
    talk() {}
};

person.talk()

person.name = '';//#1

const targetMember = 'name';//想要访问对象中的name属性
person[targetMember.value] = 'john'; //#2和#1等价  将name属性的值改名为john
```

## this 关键字

```js
const person = {
    name: 'Mosh',
    walk() {
        console.log(this); 
    }
};

person.walk(); //返回person对象  >>>{name:"Mosh",walk:f}


const walk = person.walk;
console.log(walk) //walk现在是一个函数
walk(); //>>>undefined   
```

> **如果使用对象调用函数 this返回这个对象**
>
> **如果单独调用在对象外调用函数 this指向全局对象 也就是window**
>
> **在react中==严格模式==是启动的 所以上个代码会显示undefined**

## Binding this

==为了解决上面undefined的问题 无论何时 this 都指向对象本身==

> 在JS中函数是对象(可以使用 .操作符 )

```js
//未定义的写法
const walk = person.walk;

//bind写法
const walk = person.walk.bind(person)
```

## Arrow Function (箭头函数)

```js
//老写法
const square = function(number){
    return number * number;
}

//箭头函数
const square = (number) =>{ //如果只有一个参数 可以不加(),  没有参数: = () =>
    return number * number;
}

//箭头函数更加简化
const square = number => number * number //理解为将number输入到后面的函数体中
console.log(square(5))
```

```js
const jobs = [
    {id: 1, isActive: true}
    {id: 2, isActice: true}//沙雕 自己看看是isActive还是isActice!!!!!
    {id: 3, isActice: false}//沙雕 自己看看是isActive还是isActice!!!!!
]
//原始
const activejobs = jobs.filter(function(job) {return job.isActive})
//箭头函数
const activejobs = jobs.filter((job) => job.isActive)
```

**==>>>[ { id: 1, isActive: true } ]        为什么id2不返回?==**

**==沙雕 自己看看是isActive还是isActice==**

## 箭头函数和this

> 箭头函数不重新绑定this 所以可以用在内嵌函数中访问this

```js
//#1
const person = {
    talk(){
        console.log('this', this)
    }
}
person.talk()//输出person对象

//#2
const person = {
    talk(){
        setTimeout(function(){
            console.log('this', this)
        }, 1000)
        
    }
}
person.talk()//输出window对象, 因为现在输出this的 匿名函数 不属于任何类 是孤立函数


//#3 利用箭头函数
const person = {
    talk(){
        setTimeout(() => {
            console.log('this', this)
        }, 1000)
        
    }
}
person.talk()//输出person对象
```



==在标准函数中，this 引用的是把函数当成方法调用的上下文对象==

==在箭头函数中，this 引用的是定义箭头函数的上下文==

## Array.map

```js
const colors = ['res', 'green', 'blue']
const items = colors.map(color => {return '<li>' + color + '</li>'}) //#1
const items = colors.map(color => '<li>' + color + '</li>') //#1
const items = colors.map(color => `<li>${color}</li>`) //#模板格式写法 ${}是表达式的占位符
```

map() 方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。

## Object Destructuring(对象解构)

```js
const address = {
    street: "",
    city: "",
    country: ""
}

//抽出属性 存到新变量中
const street = address.street
const city = address.city
const country = address.country

const { street, city, country} = address//和上面三行等价 将street属性从address对象中抽取出来 存到street常量
const { street: st, city, country} = address//取出+重命名
```

红宝书8.1.7

## spread operator(展开 操作符 ... )

```js
const first = [1,2,3]
const second = [4,5,6]

const combined = [...first, 'a', 'b', ...second]//...表示展开数组
```

> ...也可以展开对象

```js
const first = {name: "mosh"}
const second = {job: "instructor"}

const combined = {...first, ...second, location: "Australia"}

```

## 类

```javascript
class Person{
    constructor(name){
        this.name = name
    }
    walk(){
        console.log("walk")
    }
}

const person = new Person("mosh")
```

## 继承

```js
class Person{
    constructor(name){
        this.name = name
    }
    walk(){
        console.log("walk")
    }
}

class Teacher extends Person{
    constructor(name, degree){
        super(name);//父函数的
        this.degree = degree
    }
    teach(){
        console.log("teach")
    }
}
```



## 模块 Module

> 使用其他模块之前要导入 import

```js
import { Person } from './person';
```



> 创建一个模块 这个模块默认是private的  使用export编程public的

```js
export class Teacher extends Person{
    ......
```

> index里面看不到 因为不支持es6的es module, 在index.js里面写完之后, 要到浏览器的console里面看输出结果.

## named export 和 default export(命名导出和默认导出)

> 如果加入了default 就不用再加大括号 因为大括号是import named export的

```js
//in Teacher.js
export default class Teacher extends Person

//in index.js
import Teacher from "./teacher"

```

> 两种export方式的导入

```js
//default:
import ... from " "
//named
import {} from " " 
```

> React模块导入方式

```js
import React, {Component} from 'react'
```

解释

react是模块 不用./ 应为./是对于自己定义的模块使用的 react是第三方模块

Component是named export 我们想要自己定义的模块继承Component 所以导入

React是default export

> 关于export报错(不支持es module)   可能是react导入的时候没有导入好bable
>
> 可以使用mjs 还是没法像mosh视频里那样不用任何操作直接使用index.js

![image-20201229214020279](https://i.loli.net/2020/12/29/AlpksViUIG1Qq3X.png)

# CH3 组件

## 2 搭建环境

```bash
create-react-app counter-app
cd counter-app/
npm start
```

>  小技巧: vscode快速查找文件 ctrl+P

> 安装bootstrap

<img src="https://i.loli.net/2020/12/28/WdbJuiMpLnUTwl1.png" alt="image-20201009003546854" style="zoom:50%;" />

>   导入bootstrap(在index.js中)

```js
import "bootstrap/dist/css/bootstrap.css"
```

## 3 第一个React组件 Counter.jsx

>  simple react snippets快捷键

快捷键  ==imrc==: 快速导入react组件(import react component)   ==cc==: 创建类(create Class) ==记住类的名字要大写==

<img src="https://i.loli.net/2020/12/28/gH2ty1pCUGkaiOm.png" alt="image-20201206220735172" style="zoom: 80%;" />

React是react.js包的默认导出 Component是命名导出

> 在index.js中使用

<img src="https://i.loli.net/2020/12/28/1hAcaCO7x6TzPfS.png" alt="image-20201206221740207" style="zoom:80%;" />

**关于render的部分: 是html标记语法(you are extending the html vocabulary), 我们调用Component组件 就会返回出组件渲染的内容** ?

:自定义html标签:http://www.ruanyifeng.com/blog/2017/06/custom-elements.html

将Counter组件的输出render到id为root的html部分中

## 4 specifying children

> Js表达式中只能有一个parent元素

所以不能写成下面的形式

```js
return <h1>helloword</h1><button>Increment</button>
```

改正:套在div里面

<img src="https://i.loli.net/2020/12/28/GDqp9tuNLos5QeE.png" alt="image-20201207212512813" style="zoom:80%;" />

![image-20201207213003711](https://i.loli.net/2020/12/28/SLANkrUey3pYswa.png)

缺点: 出现了一个没啥用的div

更好的改正: react.Fragment

>  顶部导入了react react有一个子类叫fragment, 用其代替div

<img src="https://i.loli.net/2020/12/28/Ztsjy9NFMJxVAXl.png" alt="image-20201207213121044" style="zoom: 80%;" />

## 5 embedding expression

==目标: 我们想将上图的hello动态展示==

创建一个state对象

> html span

The `<span>` tag is an inline container used to mark up a part of a text, or a part of a document.

The `<span>` tag is much like the div element, but <div> is a block-level element and `<span>` is an inline element.

<img src="https://i.loli.net/2020/12/28/3t7GbS1Uv4uLnEj.png" alt="image-20201207214500512" style="zoom: 80%;" />

> JS块级作用域

块由左花括号开始，由右花括号结束 ,即 { } 中间的部分是一个块级作用域。 例如：for循环、if逻辑判断、while 循环等语句后面的{ } 都是一个块级作用域。

https://www.jianshu.com/p/3282ba63bbfe

> 嵌入表达式记得加大括号 否则就是文本

![image-20201207215758626](https://i.loli.net/2020/12/28/bx2nHvDmrcTua9g.png)



