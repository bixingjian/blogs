## 写在前面

之前很多的mosh课程都有记笔记, 但是有时候记笔记反而听得不是很认真, 这次是第一次用苹果系统写程序, 笔记还是很重要的.

- ziprecruiter.com 查看薪资
- 学习方法:
  边看视频边做笔记, 但是不要照着写代码. 看完一章(或者一节)之后自己写代码, 不会的话可以查看自己记得笔记. 
  如果还不会重新看视频, 并完善笔记



## Django基础

### 网络如何工作

- Client端(客户端) 和 Server端(服务器端) 的交互方式
  - 服务器发送整个HTML文件
  - 服务器只发送data, 客户端生成HTML**(更好的方式)**
- 客户端生成网页的工具
  - React
  - Angular
  - Vue
- 服务器端的工具
  - **Django**
  - Express
  - ASP.net core

### 3|4|5 设置工作环境

```bash
pip3 install pipenv

#如果是自己使用:
pip3 install --user pipenv

#创建文件
mkdir storefront
pipenv install django
cd storefront

#activate 虚拟环境 这样用的就是虚拟环境中的python 而不是global的
pipenv shell

#运行程序
(这样写会创建多个文件夹层级)django-admin startproject storefront
django-admin startproject storefront . #最后的"."表示将当前文件夹设置为项目文件夹

#runsercer
python manage.py runserver 9000
```

> 其它问题
> 

- permission denied
  https://stackoverflow.com/questions/46391721/pipenv-command-not-found/46396136

  ```bash
  sudo -H pip install -U pipenv
  ```

- zsh(zshell) 
  `open .` 就可以在Finder中打开终端路径
  按住command 可以点击链接或者文件夹

- `django-admin` `django-admi manage` 可以查看允许的命令

### 6 vscode python 运行

- 找到当前运行的pipenv

  ```bash
  pipenv --venv
  ```

  这是python路径为虚拟环境中的路径

### 7 第一个app

> 一个django project是由一对不同的app组成的

```python
python manage.py startapp playground
```

**注意: 这里使用的startapp, 之前创建store项目用的是`startproject`, 两个目录包含的东西是不同的**

项目文件夹下每个文件的作用

在installed app中注册自己定义的app(:playground)

**每创建一个app都要添加到setting.py中的installed app**

### 8 写view

- view是一个request handler的函数

```python
from django.http import HttpResponse
```



### 9 mapping a url to view

> 目标: 浏览器中输入: 8000/playground/hello 就会给用户返回hello, 也就是到固定的位置, 执行view函数的过程

> 创建urls.py

```python
from django.urls impot path
from . import views

#URl config
urlpatterns =[
  #path("playground/hello/", view.say_hello)
  #在主urls中注册之后就可以简化
  path("hello/", view.say_hello)
]
```

- 将url(/hello) -> say_hello这个view函数

> 将playground中的url注册到项目的主url config中(在./storefornt/urls.py)

- playground是我们自己新创建的, storefront是我们创建的时候就有的

```python
# 在主url中加入 记得import include函数

path("playground/", include("playground/urls"))
```

例如浏览器收到playground/hello的请求, 就会把hello发送到playground/urls.py中处理

**注意: 任何路由的路径后面后要加"/"**

### 10 template

> 目标: 在前端显示template, {{}}动态展示信息 {% %}展示逻辑

一般别的语言中的view(展示给用户的), 在django中成为template, 在现实中不是很经常使用template, 我们用django返回data, 不很常返回template

> 创建template文件夹 

- 收到请求
- 发送到view
- view中将template(一个html文件)返回给用户

在

```python
return render(request, "hello.html")
```

注意HTML的模板语法 endif



### 12 django debug toolbar

这个toolbar类似于是一个app

首先使用pip安装 **注意要使用pipenv安装`pipenv install django-debug-toolbar`**

在使用的时候, 记得html要返回标准的(有body , 头文件不是很重要)

结果: 

![image-20211013135800248](https://tva1.sinaimg.cn/large/008i3skNly1gvdn78e17bj61nq0u0tbt02.jpg)



## Building a Data Model 

### 关系图

![image-20211013161804301](https://tva1.sinaimg.cn/large/008i3skNly1gvdr914hd6j61jg0tw41502.jpg)

```python
python manage.py startapp store

python manage.py startapp tags
```



<img src="https://tva1.sinaimg.cn/large/008i3skNly1gve2amc9vqj61h00poab902.jpg" alt="image-20211013224014847" style="zoom:25%;" />=<img src="https://tva1.sinaimg.cn/large/008i3skNly1gve2g08xuuj61fm0r4wfv02.jpg" alt="image-20211013224526309" style="zoom:25%;" />

<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211013224317990.png" alt="image-20211013224317990" style="zoom: 25%;" />

### 5 creating models

在store的models.py中

各种filed type参考: https://docs.djangoproject.com/en/3.2/ref/models/fields/

<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211013163453670.png" alt="image-20211013163453670" style="zoom: 25%;" />

<img src="https://tva1.sinaimg.cn/large/008i3skNly1gvdrqwjmbzj61ne0j0n1j02.jpg" alt="image-20211013163517252" style="zoom: 33%;" />

- lasttime是datetimefield, birth_data是datefield
- 单格数值一定使用DecimalField
- DecimalField的参数 例如9999.99 max_digits = 4+2 =6, decimal_places = 2
- id是自动生成的, 并且是主键 可以自己设置主键, 这样id就不会自动生成



### 6 choice field

使用大写, 代表这个field不能被改变

<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211013164301766.png" alt="image-20211013164301766" style="zoom:25%;" />

将属性单独写出来, 这样方便更新

<img src="https://tva1.sinaimg.cn/large/008i3skNly1gvds023y4pj61tc05udgv02.jpg" alt="image-20211013164406942" style="zoom:25%;" />

### 7 定义一对一关系

customer和address是1对1关系

```python
class Address(models.Model):
  streeet = models.CharField(max_length=255)
  city = models.CharField(max_length=255)
  customer = models.OneToOneField(Customer, on_delete=models.CASCADE, primary_key=True)
```

- OneToOneField参数解释:
  - Type[Model]: Customer
    父model的类型, 这里是前面定义的Customer model
  - on_delete = models.CASCADE
    如果父model(customer)消失了, 这个address该如何处理
    - cascade
      子model也删除
    - set_nul
      子model不被删除, 数据库中这个customer属性变成空的
    - set_default
    - protect
      删除collecton, 里面的product被保护不被删除
  - primary_key = True
    因为有Customer才会有地址\
    如果不将customer设置为主键, 每个address就会有一个自己的id, 这样就是cus->add 1对n的关系了
    设置了True, 每个cus只能有一个add
- **在address设置了customer 1对1, 不需要在customer中设置address属性, django自动搞好了, 不管是什么数量对应关系都是这样, 只用在一个class中设置**

### 8 一对多关系

customer能够有多个地址:

把customer变成foreignkey, 取消主键设定 

<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211013171150029.png" alt="image-20211013171150029" style="zoom:25%;" />

这样一个customer属性能够有多个address值(**customer是1, address类是多**)

**外来的key做主, 统治当前的类, 比如一个class有多个student, 正是因为class这个foreign可以作为key来区分不同学生**

**foreignkey里面的是1**

### 9 多对多关系

促销(promotion)和产品(product)

一个产品可以有不同的促销方式

一个促销方式可以应用于不同的产品

在product类中设置:

```python
promotions = model.ManyToManyField(Promotion)
```



扩展:

```Python
promotions = model.ManyToManyField(Promotion, related_name="products")
```

因为数量对应关系, 在product中设置了, 在promotion中会自动设置. 在promotion中默认的product的属性名称是product_set, 你可以改变related_name, 但是如果改了最好对于所有的关系都遵循.

关于reverse query name: https://docs.djangoproject.com/zh-hans/3.2/topics/db/queries/

### 10 解决循环依赖 (circular dependency)

下面的图应是**双向的一对多关系** 所以相互依赖 

<img src="https://tva1.sinaimg.cn/large/008i3skNly1gvdtapsx0dj61cy0owjt102.jpg" alt="image-20211013172857049" style="zoom:25%;" />

> 快捷键: F2重命名一个东西(类...)

解决方法: (对于上图中的featured_product, 在Collection中)

```python
featured_product = models.ForeignKey("Product", ondelete=SET_NULL, null=True, related_name="+")
```

> 关于reverse query name到底叫什么:
>
> 其实应该是..._set, 但是django为了安全起见不让这么相似名字的设置(毕竟是有隐患), 最好可以设置成诸如related_name='featured_product_for_categories'

https://stackoverflow.com/questions/69558903/what-exactly-the-reverse-query-name-in-its-related-model-in-django/69559615#69559615

**collection->product: 应该是1->n的关系**

> 双向关系的属性命名(猜测)

1->n: 属性名称是: name->name_set 

> 基于上面的猜测, 循环依赖出现原因

在Collection中定义了和Product(属性featured_product)的 1->n关系, 这样的话在Product中的会有一个collection名称(因为collection是一个,所以不是collection_set), 但是在Product中我们已经自己定义了一个叫collection的属性(上面1->n的时候定义的), 所以名字重复. 只要将这个P->C的关系和上一个P->C的关系属性名称不一样就行.



### 11 通用关系 generic relationship

<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211013175830960.png" alt="image-20211013175830960" style="zoom:25%;" />

tags就是一个通用关系, tag是一个具体的标签, taggeditem可以使Product, collection, ...

<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211013180131828.png" alt="image-20211013180131828" style="zoom:25%;" />



**(balabala) 的tag是 (balabala) : 这就是一个通用关系**

<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211013180641749.png" alt="image-20211013180641749" style="zoom:25%;" />

> 注意: 记得每次创建app都要导入!!!!!!!!



## 设置数据库

### 3 创建迁移(migrations)(类似于git中的commit)

>rename unit_price
>
>add slug

```python 
python manage.py makemigrations
```

**每次改变model之后, 都要用makemigrations更新迁移**

> 快捷键: cmd+t 快速查找并跳转

如果生成的migration名字不喜欢, 可以更改, 但是在所有其他migration文件的dependences有依赖的也要全部改名.

```python
#slug
slug = models.SlugField()
```

### 4 运行迁移(类似于git中的push)

```python
python manage.py migrate
```

> 使用sqlite查看数据库

命令面板中输入sqlite open database, 然后目录栏就会出现sqlite explorer, 选择表单, 右键show table

```shell
#查看django给数据库发送的sql代码
python manage.py sqlmigrate store 0003
```

### 5 自定义数据库schema

例如: 给表更改名称, 添加索引

<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211014133543014.png" alt="image-20211014133543014" style="zoom:25%;" />

### 6 撤回迁移

> 目标, 将下图中的第4次迁移, 撤回到第3次迁移

<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211014133751199.png" alt="image-20211014133751199" style="zoom:25%;" />

```bash
python manage.py migrate store 0003
```

将store migrate到0003次迁移

然后需要手动删除0004的py文件和在代码中的更改部分(使用git 回到上一次)

> 撤回之后使用git删除相关提交文件, 直接使用git 回滚到上一次的提交

```bash
git log --oneline

git reset --hard HEAD~1
```



### 链接django

mysql登录

https://www.jianshu.com/p/07a9826898c0

> 快捷键: cr+D 退出mysql
>
> go to symbal in editor: command+shift+o

<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211014205446192.png" alt="image-20211014205446192" style="zoom:25%;" />



之后运行`migrate`, 因为之前是在sqlite中, 现在迁移到mysql中

如果出现问题"_mysql未找到": https://stackoverflow.com/questions/63109987/nameerror-name-mysql-is-not-defined-after-setting-change-to-mysql

### 10 running custom SQL

```python
#创建空的migration
 blabla store --empty

```

<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211014214518450.png" alt="image-20211014214518450" style="zoom:25%;" />



<img src="/Users/bixingjian/Library/Application Support/typora-user-images/image-20211014214539653.png" alt="image-20211014214539653" style="zoom:25%;" />
