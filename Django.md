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

### 设置工作环境

```bash
pip3 install pipenv

#如果是自己使用:
pip3 install pipenv --version

#创建文件
mkdir storefront
pipenv install django
cd storefront

#activate 虚拟环境
pipenv shell

#运行程序
(不要这样写 会创建多个文件夹层级)django-admin startproject storefront
django-admin startproject storefront . #最后的"."表示将当前文件夹设置为项目文件夹

#runsercer
python manage.py runserver 9000
```

- 无法安装homebrew
  换成中科大镜像

  ```bash
  /bin/bash -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
  ```

- permission denied
  https://stackoverflow.com/questions/46391721/pipenv-command-not-found/46396136

  ```bash
  sudo -H pip install -U pipenv
  ```

- zsh(zshell) 
  `open .` 就可以在Finder中打开终端路径
  按住command 可以点击链接或者文件夹

- `django-admin` `django-admi manage` 可以查看允许的命令

- 找到当前运行的pipenv

  ```bash
  pipenv --venv
  ```

  
