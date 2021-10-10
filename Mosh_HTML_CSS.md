# Part 1 

### 网络如何工作

> 浏览器(客户端) 向 谷歌(服务器) 发送请求想要一个文件
>
> 文件是html文件 服务器返回给浏览器
>
> 返回按照dom树返回 先返回整体文本 然后再次返回图片 视频等等

![image-20210130184110802](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130184110802.png)

### HTML基础

> 为什么img标签没有closing tag: 因为img下面不能有子元素

### 利用dev tools检查网页

这是浏览器向谷歌请求的信息(请求了document 一堆图像等等)

![image-20210130183904018](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130183904018.png)

### 网页验证

> 验证写的HTML和CSS代码有没有问题

> HTML验证: validator.w3.org

> CSS验证: jigsaw.w3.org/css-validator  谷歌有所css-validator



## 3 HTML基础

### 头文件

> "viewpoint": 在显示器中显示的界面

>  "description": 被人在搜索的时候看见的内容



快捷键 基础HTML模板: ! + Tab



### 文本

>  标签\<em> : 强调 Italic字体 

​	和 标签\<i>一样 但不推荐使用(因为样式是CSS做的事情)

​	可以更改默认的Italic样式

```html
<style>
    em{
        color: red;
    }
</style>
```



>  标签\<strong>:  默认加粗

​	和 标签\<b>效果一样

> 快捷键 包裹一段文字用html标签: 选中 | command palette | wrap |使用缩写包围 | 标签名称

### 实体 entities

>  \&lt; == <

>  \&lt; == >

> \&nbsp; == 确保两个词不会分开 在两个词之间使用 无空格 (none breaking space)

> 快捷键: lorem50  生成50个词烂七八糟的文本

搜索html entiites : dev.w3.org

==基本用不到==



### 超链接

>  跳转到另一个文件

\<a href = "about.html">About\</a>

标签\<a> anchor

href = hypertext reference

> 使照片可以下载

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130000310152.png" alt="image-20210130000310152"  />

> 跳转到固定章节

​						 

![image-20210130000611190](https://i.loli.net/2021/01/30/Kcn7aoJdzhIvNHk.png)

![image-20210130000638090](https://i.loli.net/2021/01/30/bnOqWUyzIjh6w1A.png)

\# : pound sign

> 回到顶部

![image-20210130001142628](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130001142628.png)

> 跳转到其他网站

![image-20210130001246027](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130001246027.png)

target部分: 在新标签页打开

### 列表

> 无序列表

![image-20210130001416330](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130001416330.png)

un-ordered list

list item

![image-20210130001513600](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130001513600.png)更改小圆点的样式 square 或者 None

> 快捷键 快速生成列表 \<li>\*3
>
> 更快捷键 列表+项目

![image-20210130001811625](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130001811625.png)

> 有序列表

![image-20210130001832836](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130001832836.png)

> 描述列表

dl: description list

dt: description term

dd: description detail

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130001940543.png" alt="image-20210130001940543" style="zoom:67%;" />![image-20210130001948542](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130001948542.png)



## 4 CSS基础

###  使用CSS

> 引用外部CSS

  rel: relationship 指向的文件是什么类型

![image-20210130004015057](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130004015057.png)

> 何时使用嵌入的CSS: 重写外部的CSS

![image-20210130004154441](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130004154441.png)

> inline CSS 行内CSS

 每个html元素都有一个style元素

尽量避免使用 很丑

![image-20210130004313558](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130004313558.png)

### Normalize.css

> 作用: 让不同的浏览器表现得一直 在之后一直用

> GitHub下载n.css   添加到项目文件

![image-20210130024756890](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130024756890.png)

### 选择器

> 分类

类型type | ID | 类| 属性Attribute

> 快捷键 zen coding(一大类)  https://www.smashingmagazine.com/2009/11/zen-coding-a-new-way-to-write-html-code/

![image-20210130025143729](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130025143729.png)=>![image-20210130025153611](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130025153611.png)

![image-20210130025556273](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130025556273.png)=>![image-20210130025611409](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130025611409.png)

> 类型选择器: 直接类型名

![image-20210130025352736](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130025352736.png)

> ID选择器: # 不能有多个

![image-20210130025641359](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130025641359.png)

> 类选择器 .   多个标签可以有同一个类型

![image-20210130025653137](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130025653137.png)

> 属性选择器:  a[属性]  不是很常见

![image-20210130025900253](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130025900253.png)

![image-20210130025830224](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130025830224.png)

选择所有有target属性的元素

==含有特性字符  \*\===

![image-20210130030045182](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030045182.png)

==特定字符开头 \^\===

![image-20210130030141158](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030141158.png)

==特定字符结束 \&\===

![image-20210130030237595](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030237595.png)

可以组合使用

![image-20210130030255478](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030255478.png)

### 关系选择器

> 目标: 为了选中p: section带有id, 利用section和p的关系

![image-20210130030338337](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030338337.png)

> 所有子元素 空格

​                                       <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030438130.png" alt="image-20210130030438130" />

例子:

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030651633.png" alt="image-20210130030651633" style="zoom:80%;" />![image-20210130030719542](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030719542.png)

> ==紧接着的子元素 >==

​                                         ![image-20210130030557175](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030557175.png)

例子:

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030651633.png" alt="image-20210130030651633" style="zoom:80%;" />![image-20210130030809266](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030809266.png)

> 所有兄弟元素 ~

​                                         ![image-20210130031211674](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130031211674.png)

例子:

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130031233190.png" alt="image-20210130031233190" style="zoom:80%;" />![image-20210130031252597](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130031252597.png)

> ==紧接着的兄弟元素 +== 

 											![image-20210130030839184](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030839184.png)  

例子:

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130030833398.png" alt="image-20210130030833398" style="zoom:80%;" />![image-20210130031023336](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130031023336.png)

> 关系选择器的缺点

不够快: 没啥影响

更改位置之后容易错

### 伪-类选择器(:)

> 目标: 将第一个p改变字体

![image-20210130032036801](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130032036801.png)

> first-child

![image-20210130031953829](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130031953829.png)

> first-of-type: 对于每个不同类型首个出现的元素选择

![image-20210130032106168](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130032106168.png)

例子: h2和p都被选中

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130032218354.png" alt="image-20210130032218354" style="zoom:80%;" />![image-20210130032229633](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130032229633.png)

> p: first-of-type: 首个出现的该类型元素

![image-20210130032304921](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130032304921.png)

> p: last-of-type

![image-20210130032354608](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130032354608.png)

> 快捷键: ul

![image-20210130032557150](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130032557150.png)![image-20210130032603999](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130032603999.png)

> nth-child

![image-20210130032712168](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130032712168.png)

> 改变超链接样式(visted, link, hover, focus(用tab选中时))

![image-20210130033022999](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130033022999.png)

### 伪-元素选择器(::)

> p元素的首个字母

![image-20210130033223546](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130033223546.png)![image-20210130033432580](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130033432580.png)

> p元素的首行首行

![image-20210130033258291](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130033258291.png)

> 选中内容并且类型为p改变颜色

![image-20210130033322226](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130033322226.png)![image-20210130033413161](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130033413161.png)

> 不加类型 选中所有

![image-20210130033557496](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130033557496.png)

> 将内容插入到之前  

![image-20210130033628227](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130033628227.png)

将inline元素转化为block元素(新启一行,占用整行)

![image-20210130033717946](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130033717946.png)

### 明确选择器

> 目标: 当多个选择器作用于同一个元素 该使用哪个方案

> 权重

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130035211123.png" alt="image-20210130035211123" style="zoom: 150%;" /><img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130035610716.png" alt="image-20210130035610716" style="zoom: 67%;" />优先级1,10,100

> 当两个选择器权重一样的时候 使用后写的

选brown

![image-20210130035504340](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130035504340.png)

> 更改优先级: important 尽量避免!!!

![image-20210130035731620](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130035731620.png)

> 更改优先级: 多个选择器联用

 ![image-20210130035841257](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130035841257.png)权重:110

### 继承

> 目标: strong元素继承p元素 所以所有对于p的样式对strong也适用 但想要是strong不受父级元素样式影响

![image-20210130040232813](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130040232813.png)

> 使用initial

![image-20210130040259768](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130040259768.png)

> 目标有时子元素不继承父元素的样式(比如父元素周围加上框, 不能给子元素加上框)  但想要强制子元素加上框

> 使用 inherit 继承

![image-20210130040437555](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130040437555.png)

> 不用记住 什么继承什么不继承 一般来说 typography相关的被继承(字体, 大小, 对其, 颜色, 间距)



# Part 2

## 2 布局

### 盒子模型

> 模型:  content和border是实物  padding和margin是空间

![image-20210130194353127](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130194353127.png)

 例子: 蓝色的是content  橘色的是margin 这个例子没有padding和border

![image-20210130194523212](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130194523212.png)

> padding: 顺序: 上右下左 trbl | 或者两个参数(竖向+横向)

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130194738785.png" alt="image-20210130194738785" style="zoom: 67%;" />==<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130194846594.png" alt="image-20210130194846594" style="zoom: 67%;" />

  

> margin消失 (margin collapse)

如果两个margin碰到一起 margin会合并成为一个

![image-20210130195220531](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130195220531.png)

> 总结: 使用margin分开元素, 使用padding分开border和content

### 改变元素大小

> 总览: content-box  border-box

> 默认情况下: width和height是content的大小

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130195554908.png" alt="image-20210130195554908" style="zoom: 80%;" /><img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130195542085.png" alt="image-20210130195542085"  />

> margin不计入盒子大小, 移动盒子

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130195721134.png" alt="image-20210130195721134" style="zoom:80%;" /><img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130195732159.png" alt="image-20210130195732159" style="zoom: 50%;" />

> box-sizing: 默认是content-box 可以设置为border-box

这样height和weight就是按照border计算而不是content计算

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130195840006.png" alt="image-20210130195840006" style="zoom: 67%;" />

> 使用全局选择器将box-sizing设置为border-box 

!!!全局选择器不常用

![image-20210130200023133](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130200023133.png)

> 对于伪选择器也适用

![image-20210130201029206](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130201029206.png)

> 块元素与行内元素

块级元素：(独占一行)	h1~h6 、p、div、 列表…

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130203000378.png" alt="image-20210130203000378" style="zoom:50%;" />

行内元素：(不独占一行)	span、a、img、strong

![image-20210130203033803](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130203033803.png)

> display: inline-block	给行内元素width和height; 给块级元素并排

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130203235239.png" alt="image-20210130203235239" style="zoom:80%;" />![image-20210130203244697](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130203244697.png)

如果要将两个hello之间的空格取消, 将两个span元素代码紧挨着写

![image-20210130203402715](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130203402715.png)

### 内容溢出

​            <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130203747913.png" alt="image-20210130203747913" style="zoom:80%;" />                       

> overflow属性 默认是visible

: hidden, 不显示溢出内容

![image-20210130203956000](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130203956000.png)

: scroll 滑动(一直有滑动条 不管有没有溢出)

![image-20210130204040729](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130204040729.png)![image-20210130204111008](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130204111008.png)

:auto 只有溢出时显示滑动条

![image-20210130204148683](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130204148683.png)

: 横方向和竖方向

![image-20210130204302186](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130204302186.png)

### 调整时使用的单位(像素,百分比...)

![image-20210130204408158](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130204408158.png)

> %: 相对于父级元素的百分比

width正常

height默认的高度是0: 解决方法->vh

> vw vh  viewwidth viewheight

width% == vw

width% 0 vh 一半

> em rem  element   root element

![image-20210130223013291](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130223013291.png)

root element(html元素) 默认font size是16 可以在chrom设置里面调

![image-20210130223120640](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130223120640.png)

###  改变位置(Positioning)

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130230217751.png" alt="image-20210130230217751" style="zoom:67%;" />

> 平面上移动

要改变位置 首先要将position设置为relative(默认是static)

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130230313790.png" alt="image-20210130230313790" style="zoom:50%;" />![image-20210130230324372](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130230324372.png)

> z轴移动

z-index 默认是0

![image-20210130230641771](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130230641771.png)<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130230647086.png" alt="image-20210130230647086" style="zoom:67%;" /> 

> 绝对位置 absolute

==如果要自己的位置是absolute, 自己的父级的position必须是relative; 因为absolute: 对于父级来说的relative==

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130230908889.png" alt="image-20210130230908889" style="zoom:67%;" /><img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130230914701.png" alt="image-20210130230914701" style="zoom:67%;" /> 

绝对位置会让父级元素"当自己不存在"

> 固定位置 

对于viewport来说一直钉住

比如顶部一直有一条

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130231245990.png" alt="image-20210130231245990" style="zoom: 67%;" /><img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130231310099.png" alt="image-20210130231310099" style="zoom:67%;" /> 

> 总结

![image-20210130231504276](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210130231504276.png)

### 浮动元素

> 将图标float到左边 后面接着的内容会漂浮在图标周围

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131213412699.png" alt="image-20210131213412699" style="zoom:67%;" /><img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131213428052.png" alt="image-20210131213428052" style="zoom:67%;" />

> 清除float

clear：
right：右侧不允许有浮动元素
left：左侧不允许有浮动元素
both：两侧不允许有浮动元素(比较常用)

![image-20210131213823979](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131213823979.png)

> 父级塌陷 parent collapsing

![image-20210131213854227](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131213854227.png)

浮动元素对于父级元素"透明"

解决方法:

![image-20210131214038216](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131214038216.png)![image-20210131214048815](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131214048815.png) 

> 现在flexbox和grid比较常用

### Flex(伸缩盒布局) 

> 一个帮助理解的游戏网站: https://flexboxfroggy.com/#zh-tw

> display: flex 总览 flex就是可以将元素按照一个方向排列(比如导航栏)

![image-20210131214246378](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131214246378.png)

> flex使用  默认的direction是row

column-reverse & row-reverse

> 对其元素

flex的轴: main和cross两个轴

如果将direction设置为row, 那row就是main轴, column就是cross轴

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131214755547.png" alt="image-20210131214755547" style="zoom:50%;" />

对齐的两个步骤: main轴的内容和cross轴的内容

![image-20210131214840547](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131214840547.png)

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131215559989.png" alt="image-20210131215559989" style="zoom:67%;" /><img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131215610038.png" alt="image-20210131215610038" style="zoom:67%;" /> 

justify-content和align-items很多中样式, 可以在浏览器里面调着玩

> flex-wrap 默认nowrap

将参数改为wrap, 就不会出现一排方块为了挤在一起改变大小

> align-content: 可对于多行内容调整

align-content的效果与align-items类似，差别在于align-content适用于多行元素，如设置flex-wrap: wrap;时产生的的多行元素。

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131230615216.png" alt="image-20210131230615216" style="zoom: 25%;" />  变为<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131230709618.png" alt="image-20210131230709618" style="zoom:25%;" />

> align-self: 对于单个flex元素进行样式重写

![image-20210131220048547](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131220048547.png)![image-20210131220056916](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131220056916.png)

> 改变flex item的大小(对于item不是container)

![image-20210131220141131](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131220141131.png)

flex-basis

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131220219327.png" alt="image-20210131220219327" style="zoom: 67%;" />对于width(main方向)元素大小重写

flex-grow: 没有单位

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131220523851.png" alt="image-20210131220523851" style="zoom:67%;" />增加一倍<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131220534920.png" alt="image-20210131220534920" style="zoom:67%;" />

flex-shrink: flex-grow的对立 没有单位

> flex: flex-basis+flex-grow+flex-shrink快捷方式

![image-20210131223212523](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131223212523.png)

### Grid(网格布局)

> 总览: display: grid

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131223826823.png" alt="image-20210131223826823" style="zoom:50%;" />                         <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131223952381.png" alt="image-20210131223952381" style="zoom:50%;" />

> 定义grid 

![image-20210131224017713](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131224017713.png)

三行, 每行两个块

 <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131225145336.png" alt="image-20210131225145336" style="zoom:67%;" />== <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131225455734.png" alt="image-20210131225455734" style="zoom: 67%;" />

> justify-items | align-items对齐元素: 对于每个网格内的元素 默认是stretch(填满整个方向)

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131225836046.png" alt="image-20210131225836046" style="zoom:80%;" />

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131225925754.png" alt="image-20210131225925754" style="zoom: 67%;" />=<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210219173817310.png" alt="image-20210219173817310" style="zoom: 50%;" />

每个方块都在自己的网格的正中间

> justify-content | align-content 对于内容对齐: 对于整个网格在页面的中间

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131230101215.png" alt="image-20210131230101215" style="zoom:67%;" />= <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131230115618.png" alt="image-20210131230115618" style="zoom:67%;" />

> 其他方式定义格子大小

- 百分比:![image-20210131231147618](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131231147618.png)

fr: fraction, 剩余空间的30% 70%

- auto![image-20210131231320759](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131231320759.png)

> 格子间的gap

![image-20210131231417360](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131231417360.png)

gap是前两个的快捷方式

> 放置元素到格子

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131232107159.png" alt="image-20210131232107159" style="zoom:80%;" />

grid-row: 

1/3 | 1/-1 | 1/span2

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131232445530.png" alt="image-20210131232445530" style="zoom: 80%;" />=<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131232500318.png" alt="image-20210131232500318" style="zoom:67%;" />

grid-column: 和grid-row语法一样

grid-area: 不太常用

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131232557712.png" alt="image-20210131232557712" style="zoom:67%;" />从(1,1)格子到(1,3)格子

> 利用命名格子来放置元素(定义模板然后使用)

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131232804534.png" alt="image-20210131232804534" style="zoom:67%;" />

使用: 

模板: 引号 分行 每个格子 

用的时候不加" "

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131232959366.png" alt="image-20210131232959366" style="zoom: 80%;" /> <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131233019748.png" alt="image-20210131233019748" style="zoom:80%;" />

定义空白区域(".":<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210131233234403.png" alt="image-20210131233234403" style="zoom:80%;" />

### 隐藏元素

> display: none

隐藏的部分不占空间

> visibility: hidden

隐藏部分的空间仍然在

### Media query

> mobile first & desktop first

先适配mobile, 然后再用media query适配desktop

> media query

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204202524544.png" alt="image-20210204202524544" style="zoom:80%;" />

> 在打印机上 printer

一般用绝对单位

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204203157332.png" alt="image-20210204203157332" style="zoom:80%;" />







## 3 字体

### 字体样式

> font-family:

三类字体

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202020028920.png" alt="image-20210202020028920" style="zoom:80%;" />

字体栈: 浏览器从前向后找看哪个合适

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202020215817.png" alt="image-20210202020215817" style="zoom:80%;" />

> font-weight

bold == 700 

norma=400

> font-style

italic...

> font-size

30px, 1rem...

> color 默认是纯黑 #000

一般body部分的字体不设置为纯黑

#111或者333比较好

### 自定义字体 Embedding Web Fonts

> 很多自带的字体不会出错 但很无聊

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202021638452.png" alt="image-20210202021638452" style="zoom:67%;" /><img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202021643084.png" alt="image-20210202021643084" style="zoom:67%;" />

> 下载并转化

==web中使用woff和woff2, 比较小 比较容易打开==

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202021759550.png" alt="image-20210202021759550" style="zoom:50%;" />

将ttf字体转化为woff字体

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202021931199.png" alt="image-20210202021931199"  />

> 放入项目

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202022123951.png" alt="image-20210202022123951" style="zoom:80%;" />

> !!!注册字体

解压后有一个css文件, 里面是open-sans字体的"规则", 放到项目css文件的最前面, 因为要先注册这些字体才能够使用

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202022529737.png" alt="image-20210202022529737" style="zoom:67%;" />

可以改变font-family的名字

> 更新url到自己的文件夹

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202022640219.png" alt="image-20210202022640219" style="zoom:67%;" />

然后即可使用:

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202022744768.png" alt="image-20210202022744768" style="zoom:50%;" />

### Flash of Un-styled Text (FOUT)

> 当我们使用自定义的字体, 浏览器下载的时候会先使用别的字体代替

> 定义代替字体方式为fallback(备选之物)  optional也可以

使用font-display

给一个窗口时间让浏览器下载自定义字体, 如果没下好就是用fallback备选字体

### Font services

> 一般字体需要购买 但可以使用服务免费或者很少费用

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202025145878.png" alt="image-20210202025145878" style="zoom:50%;" />

> 使用google web fonts

选好字体 拷贝链接 放在html文件中

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202025541860.png" alt="image-20210202025541860" style="zoom:50%;" />

> 视频后段 解释url的参数

### 各个系统的字体

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202034344726.png" alt="image-20210202034344726" style="zoom:67%;" /><img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202034354108.png" alt="image-20210202034354108" style="zoom:80%;" />

> 使用系统字体

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202034456379.png" alt="image-20210202034456379" style="zoom:80%;" />

 苹果的系统字体 -apple-system

可以直接使用, 在电脑中看到的就和苹果设备上的字体一样

### 改变字体大小

不能用px, 显示效果不一样

==使用rem== 

> media query

https://www.w3schools.com/css/css_rwd_mediaqueries.asp

> type-scale.com

查看字体大小

### 竖向空间

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202035917260.png" alt="image-20210202035917260" style="zoom:50%;" />



> margin

上margin大(分开), 下margin小(和内容更紧凑)

margin:使用trbl

![image-20210202040131297](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202040131297.png)

注意用rem 

> line-height 行间距

一般将line-height设置为font-size的1.5倍

font-size: 1rem		line-height:1.5rem

> 如果line-height不设置单位, 默认是一个乘数, 和字体大小的关系恒定

### 纵向距离

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202040456971.png" alt="image-20210202040456971" style="zoom: 67%;" />

> letter space

使用px 不用rem

> width

一行一般60-70字母合适

with: 50ch == 50个"0" (一些字母占的空间比较小)

### formatting text

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202041010558.png" alt="image-20210202041010558" style="zoom:80%;" />

> text-alingn

横向的对其

比较好的是: left

> text-indent

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202041140726.png" alt="image-20210202041140726" style="zoom:80%;" />

关系选择器: 跟在一个 p 后面的 p 首行会有缩进

>text-decoration

underline, line-through

> text-transform 大小写

capitalize

> white-space

处理换行(wrap)

截断文本(nowrap放在一行, hidden使得溢出不可见, text-overflow:ellipsis加上...)

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202041530149.png" alt="image-20210202041530149" style="zoom:67%;" /><img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210202041554024.png" alt="image-20210202041554024" style="zoom:50%;" />  

> column-count 分栏

分栏的间隔 column-gap

加入line column-rule: 3px dotted #999

> direction

用于从右到左的语言

## 4 图像

### 图像类别和格式

> raster光栅图和矢量图

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203203232858.png" alt="image-20210203203232858" style="zoom:67%;" />



<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203203247754.png" alt="image-20210203203247754" style="zoom:67%;" />

> 格式

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203203314699.png" alt="image-20210203203314699" style="zoom:67%;" />

> 背景透明

直接可以放在图像上面, 不在底背景

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203203135590.png" alt="image-20210203203135590" style="zoom:67%;" />

### 内容图像

### 背景图像

> background: url()

> background-repeat

> background-position

> background-size

> background-attachment: fixed

### CSS精灵 CSS sprites

> CSS精灵: 每个网页有很多个图像, 每次都发一个请求太慢, CSS精灵将这些图像合并成一个图像

> CSS sprites generator

图像+ CSS文件(copy到项目文件)

> 问题: 最好直对logo和图标使用

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203203850130.png" alt="image-20210203203850130" style="zoom:67%;" />

### Data URLs (不常用 缺点较大)

> CSS精灵之外另一个优化HTTP请求的方法

> ![image-20210203204018173](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203204018173.png)

图像直接嵌入在html文件中 不需要下载

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203204507262.png" alt="image-20210203204507262" style="zoom:67%;" />



<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203204446605.png" alt="image-20210203204446605" style="zoom:67%;" />

> 问题

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203204609680.png" alt="image-20210203204609680" style="zoom:67%;" />

### 剪裁(Clipping)

> CSS clip generator

![image-20210203204744151](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203204744151.png)

会生成css属性

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203204830127.png" alt="image-20210203204830127" style="zoom:67%;" />

### 滤波器 Filters

> filter属性

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203205021196.png" alt="image-20210203205021196" style="zoom:80%;" />

> css filter functions

查看所有的滤波器

### 支持高密度屏幕

> 对高密度(清晰)的屏幕提供高质量的图片
>
> 不需要所有图片都用, 对于好的背景, sharp的图片使用

> 分辨率的名词

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203205352864.png" alt="image-20210203205352864" style="zoom:80%;" />

CSS运用logical resolution

高密度: 物理分辨率 比 逻辑分辨率 多

> 使用PS 从3X的图像开始, 生成2X, 1X图像

> srcset

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203205947411.png" alt="image-20210203205947411" style="zoom:80%;" />

### 分辨率转换问题

> 不同设备显示图像的分辨率不同, 我们提供三个图像, 让浏览器选择最好的

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203210528584.png" alt="image-20210203210528584" style="zoom:80%;" />

> 在不同设备上显示不同的大小

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203210647570.png" alt="image-20210203210647570" style="zoom:80%;" />

> responsive image breakpoints

### 现代图像格式

> 转化为webp格式

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203212451022.png" alt="image-20210203212451022" style="zoom:80%;" />



![image-20210203212526983](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203212526983.png)网站

> 不支持的网站使用方法

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203212748593.png" alt="image-20210203212748593" style="zoom:80%;" />

记得加上img标签

### 图像方向 Art direction

> 不同设备 不同的图像大小

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203213331395.png" alt="image-20210203213331395" style="zoom:80%;" />

pad上显示完整, 手机上显示残缺的图像

### 字体图标(font Icons) 

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210203213947821.png" alt="image-20210203213947821" style="zoom:80%;" />

https://fontawesome.com/

> i 标签

使用i元素和span都可以



## 5 表单

### 创建基本表单

> 基础表单

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204003111264.png" alt="image-20210204003111264" style="zoom:80%;" />

label的for 和 input的id是对应的

![image-20210204003101324](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204003101324.png)

> 多个表单

将每个表单放在div里面

> submit按钮

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204003311296.png" alt="image-20210204003311296" style="zoom:80%;" />

> 总结: 多个表单+按钮

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204003611589.png" alt="image-20210204003611589" style="zoom:80%;" />

### 表单样式

> 很麻烦 很多人直接用css框架

> 目标

![image-20210204003418652](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204003418652.png)

原始

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204003627882.png" alt="image-20210204003627882" style="zoom:80%;" />

> body部分

font-family: -apple(自动补充)

line-height: 1.5

> label部分

display: block #表单在label下面一行

> 给每个表单的div一个class: form-group

.margin-bottom: 1rem

> input[type='text']
>
> input[type='email']
>
> 
>
> #这是attribute selector 有一些input不需要下面的css
>
> 

border: 1px solid #ccc

border-radius: 5px

padding: 0.5rem 0.7rem #text离表格框远一点

transition: border-color 0.15s, box-shadow: 0.15s 

> input[type='text']: focus
>
> input[type='email']: focus

border-color: #7db0fb

outline: 0 #不然无法覆盖chrom默认的

box-shadow: 0 0 0 4px rgba(24, 117, 255 0.25)

> button

background: #蓝色

color: 白色

border: 0  #不然黑色框

padding: 0.5rem 0.6rem

border-radius: 5px

outline: 0

### CSS框架

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204005410118.png" alt="image-20210204005410118" style="zoom:80%;" />

> Bootstrap

CDN: content delivery network

给form样式

详细的官网上看看吧

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204011435491.png" alt="image-20210204011435491" style="zoom:80%;" />

> Milligram

不用导入类 默认就很好

### Text Fields

> input按钮

https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input

> textarea

### 输入提示(提示)

> datalist

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204013936484.png" alt="image-20210204013936484" style="zoom:80%;" />



### 下拉菜单

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204014831961.png" alt="image-20210204014831961" style="zoom:80%;" />

>  设置默认: option标签加上selected

> 多选: select后面加上multiple

> optgroup

 <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204015028844.png" alt="image-20210204015028844" style="zoom:80%;" />



<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204015040421.png" alt="image-20210204015040421" style="zoom:80%;" />

### 选项框 check-box

> 快捷键: input: checkbox  =>  <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204015158314.png" alt="image-20210204015158314" style="zoom:50%;" />

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204015529348.png" alt="image-20210204015529348" style="zoom:80%;" />

!!!class="label-inline" 是因为 milligram默认check box占一行, 用这个类改一下

### 单选按钮

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204015736178.png" alt="image-20210204015736178" style="zoom:80%;" />

### 范围拖杆 slider

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204020133044.png" alt="image-20210204020133044" style="zoom:80%;" />

想要显示value: CSS单独不行, 要用JS

### 上传文件

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204020420098.png" alt="image-20210204020420098" style="zoom:80%;" />

multiple

accept: audio/**

### 相关内容一组输入

> fieldset legend

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204020555224.png" alt="image-20210204020555224" style="zoom:80%;" />



<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204020606299.png" alt="image-20210204020606299" style="zoom:80%;" />

> section h2

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204020700535.png" alt="image-20210204020700535" style="zoom:80%;" />

###   隐藏fields

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204153706475.png" alt="image-20210204153706475" style="zoom:80%;" />

检查网页能看到, 不要存储敏感信息

?一般用来存储被编辑的ID

### 数据验证 data validation

> input type = text, data email

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204154034447.png" alt="image-20210204154034447" style="zoom:80%;" />

required

minlength

maxlength

> input type = numbers

required

min

max

### submit表单

> 两种submit按钮的格式(一般用button标签)

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204154253748.png" alt="image-20210204154253748" style="zoom:80%;" />

区别:

input标签 value只能是文本, 不能是图标

button标签 显示可以是标签 如

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204154421941.png" alt="image-20210204154421941" style="zoom:80%;" />

> form action="" (要提交到的url) | method  
>
> 每个input filed要有一个name

后端如: Node, django

我们使用一个模拟的表单提交后端(formspree): 

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204154721171.png" alt="image-20210204154721171" style="zoom:80%;" />

> method方法区别
>
> https://medium.com/%E5%B0%8F%E5%B0%8F%E8%AA%AA%E6%9B%B8%E4%BA%BA/%E7%B6%B2%E9%A0%81get-%E8%88%87-post-%E5%B7%AE%E7%95%B0-%E7%A7%91%E6%99%AE%E5%A3%B9%E9%BB%9E%E9%80%9A-94cbaa666fdb

POST: 

value会被显示到http请求中

大多数时候使用POST

GET: 

value会被放在url里面

当我们想bookmark这个url, 随时可以返回这个url的时候使用

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204155040772.png" alt="image-20210204155040772" style="zoom:80%;" />

## 6 变化 过渡 动画 transformation transition animation

### Transformation

![image-20210201012630846](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201012630846.png)

> rotate

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201013752876.png" alt="image-20210201013752876" style="zoom:80%;" />

> skew

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201013805662.png" alt="image-20210201013805662" style="zoom:80%;" />

> translate

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201013941714.png" alt="image-20210201013941714" style="zoom:80%;" />

hover时右移10px, 下移动10px

> 可以组合使用: 顺序很重要

![image-20210201014135540](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201014135540.png)

translate时translateX+translateY的简化版

### 过渡 Transition

> 变化发生的太快了 transition可以调整发生速度

 <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201015036652.png" alt="image-20210201015036652" style="zoom:80%;" />

注意: transition要写在box类里面, 对transform进行过渡

持续时间为0.5s | 提供过渡的快慢(linear默认, ease-in, 或者cubic-bezier函数) | 延迟

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201014836438.png" alt="image-20210201014836438" style="zoom: 33%;" /><img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201014904947.png" alt="image-20210201014904947" style="zoom: 67%;" />

> 对多个属性进行变化

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201015132902.png" alt="image-20210201015132902" style="zoom:80%;" />

### 动画(animation)

> 定义动画: 一系列transform的集合

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201020102407.png" alt="image-20210201020102407" style="zoom:67%;" />

25% 代表第25%的时间点

pop就是我们animation的名字

> 使用

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201020221557.png" alt="image-20210201020221557" style="zoom:80%;" />

animation-delay	|	animation-iteration-count: run几次这个animation	|	animation-timing-function: 快慢变化效果(ease-out, linear...)	| 	animation-direction: 正向的时间轴还是反向的时间轴

> 输入animation 就会自动出现这些属性 :)

![image-20210201020622095](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201020622095.png)

![image-20210201020626469](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201020626469.png)

### 可复用的动画(animation)

> 利用类

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201020802408.png" alt="image-20210201020802408" style="zoom:80%;" />

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201020815516.png" alt="image-20210201020815516" style="zoom:80%;" />

> animate.style 一堆好用的动画

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201020851607.png" alt="image-20210201020851607"  />![image-20210201020920304](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201020920304.png)

### <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201020851607.png" alt="image-20210201020851607"  />![image-20210201020920304](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210201020920304.png)

## 如何写出简洁可维护CSS

### CSS best practice

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204175529166.png" alt="image-20210204175529166" style="zoom:80%;" />

> 快捷键:selection, add cursor below

> 命名

nav-item 而不是 item

> 快捷键

全选 command palette sort lines ascending

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204175647506.png" alt="image-20210204175647506" style="zoom:80%;" />![image-20210204175847465](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204175847465.png)

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204175847465.png" alt="image-20210204175847465" style="zoom:80%;" />



### CSS变量

> 在:root里面定义变量  :root matches the html element

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204180105189.png" alt="image-20210204180105189" style="zoom:80%;" />

### BEM命名规范(Block Element Modifier)

BEM将网页看成由很多个block组成, block中有其他bloack

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204182232942.png" alt="image-20210204182232942" style="zoom:80%;" />

> BEM命名规则

element: \__

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204182618116.png" alt="image-20210204182618116" style="zoom:80%;" />

modifier: -- (上图中的popular)

 <img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204182814170.png" alt="image-20210204182814170" style="zoom:80%;" />

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204182825190.png" alt="image-20210204182825190" style="zoom:80%;" />

# Part 3

### 工具

> CSS Peek

按住CTRL 点击class等属性, 查看定义的CSS样式 

> Highlight matching tag

> todo  highlight

<img src="C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210204204650596.png" alt="image-20210204204650596" style="zoom:80%;" />

### 项目环境

> normalize.css

> 一般项目写很多个css文件 然后使用css预处理器合并起来

> !!!使用vscode git图标 初始化存储库  ==创建git仓库

> 安装字体

### 7 PS

按下Z(放大镜): 点击放大; alt+点击缩小

空格键可以拖动

### 10 字体

> 快捷键: h\$\{Heading \$\}3

### 12 badges

> 面向对象CSS

![image-20210210034045966](C:\Users\bixingjian\AppData\Roaming\Typora\typora-user-images\image-20210210034045966.png)

一般命名规范"--"

就是组件化 然后复用

!!!BEM 命名规范

### 14 Icons

> 快捷键: 不用输入var  直接输入color 编辑器会自动补全



