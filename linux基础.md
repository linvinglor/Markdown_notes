linux基础

# 基础知识点
1. linux大小写敏感
2. 文件名最多256个字符，包括：数字 . _ -等
3. 文件名前带 . 表示隐藏文件
4. 配置文件中，#表示注释。修改配置文件时，尽量不要删除，使用#注释掉。
5. linux是继承性的多用户操纵系统，你的个人设定（配置文件）放在你的个人主目录下
6. 整个系统范围的设定一般放在/etc下。


# 常用命令

### 与目录相关的命令

/	根目录

~	当前用户的主目录

..	当前目录的上一级

.	代表当前目录

mkdir	创建目录 -p 补全所缺失的路径

rmdir	删除空目录

rm -rf	删除非空目录

cp	复制目录

tar	压缩、解压缩目录，压缩 -zcvf、解压 -zxvf

chmod -R	以递归的方式

PS：目录就是特殊的文件，操作文件的命令也可以用来操作目录，只是需要加些额外的参数。目录文件只能创建软链接。

### 文件相关命令
touch	创建文件

cp	复制文件

mv	移动文件，cp和mv在移动复制过程中可以修改文件名，mv可以完成重命名的功能

rm	删除文件，删除后不经过回收站，直接删除，基本无法找回

find	查找文件，-name 以文件名查找

chmod	修改文件权限（r4 w2 x1）

例如：chmod 644 文件名

显示：类型 | 所有者 | 同组 | 其他

ln 创建链接文件硬链接

软链接：如果目标文件删除，则链接文件就不能访问

硬链接：硬链接链接的是文件的内容，所以即使目标文件删除，链接文件也可以访问。

### 网络相关命令
ifconfig	查看或设置网络配置信息（ip addr centos7）

ping 测试网络是否连通

Linux默认会一直执行，需要用Ctrl+c退出。

windows默认只执行4次，/t会一直执行。

### 重定向
```
> 以清空方式创建一个新文件来存储
>> 以追加方式定入，在原来的基础上添加。
```

### 其他命令
clear	清屏

pwd	(print working directory)	显示当前所在的路径

file filename  显示详细信息（编码、类型等）

stat filename  查看更多信息（大小、atime、mtime、ctime等）

Ctrl+Alt+F1 / F2	图形用户界面和shell页面切换

date -R		查看系统时间

查看版本位数

uname -a

getconf LONG_BIT

file /sbin/init

file /bin/ls

uname -a	查看kernel的版本

cat /etc/issue		查看linux的发行版本

w

who

who am i

pkill -kill -t tty1

### 修改密码

修改root用户密码：
```
# passwd

然后输入两次新密码即可
```

修改用户oracle的密码：
```
# passwd oracle

然后输入两次新密码即可
```

### 端口号、PID
sudo netstat -antup			显示端口号、PID号

sudo netstat -antup |grep 端口号		根据端口号查询PID号 sudo netstat -antup |grep 3306

sudo netstat -antup |grep PID号		根据PID号查询端口号 sudo netstat -antup |grep 2040

sudo ps -ef |gref 进程名		根据进程名查看PID

