

## 2

<img src="https://i.loli.net/2021/04/07/CrKedLg7QahFxIf.png" alt="image-20210407132919907" style="zoom:50%;" />

```Terminal
# 加入dockerfile之后创建一个image
docker build -t hello-docker .

# ckeck all images
docker image 

docker run hello-docker
```



files + Dockerfile = image (docker build)

image: OS, 运行环境(Node, Python...)

有了image, 我们让docker用一个container运行这个image, ==container就是一个特殊的进程==, (docker run), 在一个隔离的环境中运行image

## 3

```bash
#run指令 = build + start
docker run ubuntu(==docker pull ubuntu + docker run ubuntu)

# iteract 交互进入命令行
docker run -it ubuntu 

# check running process(container)
docker ps

# all process(container)
docker ps -a

echo hello

# current user
whoami

# location of this shell program
echo $0
>> /bin/bash
```

`bash`: bourne again shell

```bash
# ckeck history and run #2 command
history
!2
```



### package

`apt`: advanced package tool

```bash
apt update

#install nano(a text editor)
apt install nano

apt remove nano
```

> install package 之前一定要 update package data base



`dev`: devices

`etc`: editable text configuration

`home`: 每个user都会有一个home

`root`: root用户的home

`proc`: process



`pwd`: print working directory

```bash
#home路径
cd ~

touch hello.txt

cat hello.txt

# 不能上滑 用less代替
more hello.txt

# space enter q
less /etc/adduser.conf 

#first few lines
head -n 5 /etc/adduser.conf

tail -n 5 /etc/adduser.conf
```



```bash
cat file1.txt > file2.txt

# output concat result 
cat file1.txt file2.txt

cat file1.txt file2.txt > combined,txt

echo hello > hello.txt

ls -l > currentfiles.txt

# > 会覆盖文件内容 >> append
echo DB_USER=mosh >> .bashrc
```



`grep`: global reregular expression print

```bash
grep hello file1.txt

#case insensitive
grep -i hello file.txt

grep -i hello file*

# for file: recursively
grep -i -r hello . == grep -ir hello .
```



```bash
# recursively 不指定路径就是从当前文件夹开始
find

find /etc 

#searching for "d"irectories
find -type d

#searching "f"ile which file name are start with"f"
find -type f -name "f*"

#case insensitive
find -type f -iname "F*"

# 查看当前镜像中所有的python文件 (注意从/根目录开始 不然默认是从当前目录开始)
find / -type f -name "*.py"
```



```bash
#连续执行 一个出错 后面不影响接着执行
mddir ; cd test ; echo  done

#连续执行 出错停止
mddir && cd test && echo done

#如果前面的执行了 后面的就不会执行
mkdir test || echo "directory exists"

# pipeing(pipe): 将第一个命令的执行结果发送给下一个命令
#使用less查看存在的文件(可以使用上下键导航)
ls /bin | less

#现实文件前五行
ls /bin | head -n 5

#多个命令换行
mkdir hello;\
> cd hello;\
> echo done
```





```bash
printenv

# 打印某一个环境变量(比如PATH这个环境变量)
printenv PATH == echo $PATH

#只存在在当前session
export DB_USER=mosh
printenv DB_USER

#永久导入环境环境变量
echo DB_USER=mosh >> .bashrc
```



```bash
# 退出当前session (停止当前container进程)
exit

# start container
docker start -i 2f......
```



## 4 

```bash
#alpine do not have bash, but has shell
docker run -it react-app sh

将 p.j and R.md copy to directory "/app/"
COPY package.json README.md /app/ 
```

