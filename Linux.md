## 写在前面

- 菜鸟教程 https://www.runoob.com/linux/linux-command-manual.html

## 关机/重启/注销

- `shutdown -h now `
  立即关机
- `shutdown -h 10`
  预定关机时间(10分钟后)
- `shutdown -h 11:00`
  预定关机时间11:00
- `shutdown -c`
  取消预订时间关机 [cancel] 
- `shutdown -r now`
  --reboot



- `reboot`
  重启

## 系统信息和性能查看

- `uname -a`
  查看内核/OS/CPU信息(Unix name --all)
- `uname -r`
  查看内核版本 --release 
- `uname -m`
  查看处理器架构 --machine 
- `arch`
  查看处理器架构

- `who`	 `who am i`
  查看登录时的用户 / 查看当前用户
- `uptime`
  查看系统运行时间, 用户数, 负载
- `grep MemTotal /proc/meminfo`
  查看总内存
- `grep MemFree /proc/meminfo`
  查看空闲内存容量
- `data`
  查看系统时间
- `cal 2021`
  显示2021日历表
- `top`
  动态显示cpu/内存/进程等情况 (按`q`退出)



## 磁盘和分区

- `fdisk -l`
  查看所有磁盘分区
- `df -h`
  查看磁盘使用情况和挂载点
- `du -sh ~/bixingjian`
  查看指定文件夹的大小 [disk usage] --summarize --human-readable 
- `du -sk * | sort -rn` 
  从高到低依次显示文件和目录大小 --summarize --kilobytes [reverse] [number按照数值大小] ![image-20211009141320297](https://i.loli.net/2021/10/09/NdTDsurOntyHvfW.png)



## 文件和目录操作

- `ls -a`
  查看隐藏文件
- `rmdir dir1`
  删除dir1目录

## 文件查看和处理

- `grep test test2.txt`
  在`test2.txt`文件中查找包含`test`的行
- `grep [0-9] test2.txt`
  在`test2.txt`文件中查看包含数字的行
  ![image-20211009142555616](https://i.loli.net/2021/10/09/PDB25F7G1kRtpc9.png)
- `sed 's/s1/s2/g' hello.txt`
  [**s**tream **ed**itor] [substitution] [global replacement] 将``hello.txt`文件中的s1替换成s2
  `sed`命令的使用: https://www.geeksforgeeks.org/sed-command-in-linux-unix-with-examples/
- `comm -1 file1 file2`
  比较两个文件的内容(去除file1所含内容) 注意文件内容要求是是字典排序的![image-20211009142348359](https://i.loli.net/2021/10/09/7ioyJMzusTH84fY.png)











## mosh-docker中的笔记

### package

`apt`: advanced package tool

```bash
apt update

#install nano(a text editor)
apt install nano

apt remove nano
```

> install package 之前一定要 update package data base

### `/`目录下面的文件夹

`dev`: devices

`etc`: editable text configuration

`home`: 每个user都会有一个home

`root`: root用户的home

`proc`: process

### 文本编辑

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



## 情景

### 查找并 跳转/显示 到包含指定名称的 文件夹/文件

```bash
cd $(find ~/bixingjian -type d -name info_save))
```

- `cd` 到  在`~/bixingjian`路径下, `-type`是`d`(文件夹), `-name`(名称)是`info_save` 的文件夹
- 如果find结果为空, 就会转到用户目录

```bash
cd $(find ~/bixingjian -type d -name "info_s*") 
```

-name 可以用 `""`  使用正则表达式

```bash
cat $(find ~/bixingjian/git/dmd/ -type f -name "test.py")
```

显示 `dmd/`下的test.py的内容



> 懒人工具 autojump

mac和linux下都可以使用

https://www.jianshu.com/p/15f0ffaa88d7

### 返回上一个路径

比如千辛万苦进入了一个很多层的目录下了，一不小心输入了cd一下子回到了用户目录下，怎么找回去呢

```bash
cd -
```

== `cd &OLDPWD`

### nohup命令

[no hang up]

https://www.runoob.com/linux/linux-comm-nohup.html

Linux后台运行命令nohup实现屏幕输出记录到日志文件 https://blog.csdn.net/sitebus/article/details/100554789

https://zhuanlan.zhihu.com/p/59297350

```bash
nohup python test.py &

# !!!但是上面的语句python有缓冲 没法实时查看 使用下面的语句取消缓冲
nohup -u python test.py

# !!!在另一个窗口 使用如下命令 实时监控nohup
tail -f nohup.out

#重定向到另一个文件而不是默认的nohup.out
nohup yourcommand > myout.log 2>&1 &

#中断
ps -ef|grep "python test.py"
kill -9 PID
```