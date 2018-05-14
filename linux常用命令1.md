linux常用命令1

# 基础知识点
1. linux大小写敏感
2. 文件名最多256个字符，包括：数字 . _ -等
3. 文件名前带 . 表示隐藏文件
4. 配置文件中，#表示注释。修改配置文件时，尽量不要删除，使用#注释掉。
5. linux是继承性的多用户操纵系统，你的个人设定（配置文件）放在你的个人主目录下
6. 整个系统范围的设定一般放在/etc下。


# 常用命令

### 查看端口号是否被占用，杀死进程
```
netstat -antup | grep 3306      可以查询到PID

kill -9 PID             根据查询到的PID杀死进程
```
kill和kill -9都可以杀死进程，但是kill可能不会立刻杀死进程（先进行释放内存等），kill -9能立刻顺利的杀死进程。

### 端口号、PID
```
sudo netstat -antup			         显示端口号、PID号

netstat -antup |grep 3360          查看端口是否被占用，a显示所有，p显示程序名和进程PID，n域名解析

sudo netstat -antup |grep 端口号		根据端口号查询PID号 sudo netstat -antup |grep 3306

sudo netstat -antup |grep PID号		根据PID号查询端口号 sudo netstat -antup |grep 2040

sudo ps -ef |gref 进程名		        根据进程名查看PID

shift + PaUp                           向前翻页

shift + PaDn                           向后翻页

killall mysqld                     杀掉所有以mysqld命名的进程。
```

### 用户
```
w - Show who is logged on and what they are doing.

who - show who is logged on

whoami - print effective userid

who am i - When a user logs in as a root across the network, both the command

whoami and who am i will show you root. However, when a user abc logs in remotely and runs su – root, whoami will show root whereas who am i will show abc

pkill -kill -t tty1        kill登录的用户

sudo                输入当前管理员用户的密码就可以获得超级用户权限，默认5分钟后root权限失效

su                  输入root权限就切换到root用户
```

### 目录常用命令

```linux
cd /	切换到根目录

cd ..	切换到上一层目录

cd 或者 cd ~        切换到当前用户的主目录下

mkdir	创建目录 -p 补全所缺失的路径

rmdir	删除空目录

rm -rf	删除非空目录

cp	复制目录

tar	压缩、解压缩目录，压缩 -zcvf、解压 -zxvf

chmod -R	以递归的方式

PS：目录就是特殊的文件，操作文件的命令也可以用来操作目录，只是需要加些额外的参数。目录文件只能创建软链接。
```

### 文件常用命令
```linux
touch	创建文件

cp	复制文件

mv	移动文件，cp和mv在移动复制过程中可以修改文件名，mv可以完成重命名的功能

rm	删除文件，删除后不经过回收站，直接删除，基本无法找回

find	查找文件，-name 以文件名查找

chmod	修改文件权限（r4 w2 x1）

例如：chmod 644 文件名

显示：类型 | 所有者 | 同组 | 其他

ln 		创建链接文件硬链接
```

软链接：如果目标文件删除，则链接文件就不能访问

硬链接：硬链接链接的是文件的内容，所以即使目标文件删除，链接文件也可以访问。

### head 和 tail：（head、tail分别用来查看文件的开头和结尾）
```
head -3 test.log        //查看文件的前3行

tail -3 test.log            //查看文件的最后3行

tail -f text.log            //把文件最尾部的内容显示在屏幕上，并不断刷新，使你看到最新的文件内容（常用来查看服务器上的日志文件）

head -20 text.log | tail -10        //查看文件的第11行到第20行
```

### 网络相关命令
```
ifconfig			查看或设置网络配置信息（ip addr centos7）

ping 				测试网络是否连通

ping localhost		会一直ping下去，ctrl+c停止

ping www.baidu.com

ping -c N ip/网址		其中N表示ping的次数
```

### 重定向
```
> 以清空方式创建一个新文件来存储
>> 以追加方式定入，在原来的基础上添加。
```