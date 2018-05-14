Linux常用命令2

### 目录切换
```
cd /                返回根目录
cd ..               返回上一级目录
cd 或者 cd ~        返回到当前用户的主目录下
```

### 系统
查看版本位数4种方法：

1. uname -a
2. getconf LONG_BIT
3. file /sbin/init
4. file /bin/ls

```
hostname           查看主机名

date -R			查看系统时间

uname -a			查看kernel的版本

cat /etc/issue		查看linux的发行版本

shutdown -h now       关闭系统

shutdown -r now      重启

logout               注销
```

### 修改密码
```
1、修改root用户密码：

# passwd     然后输入两次新密码即可

2、修改用户oracle的密码：

# passwd oracle    然后输入两次新密码即可
```

### 其他命令
```
clear	清屏

pwd	(print working directory)	显示当前所在的路径

file filename  显示详细信息（编码、类型等）

stat filename  查看更多信息（大小、atime、mtime、ctime等）

Ctrl+Alt+F1 / F2	图形用户界面和shell页面切换
```

```
mkdir 001                新建一个目录001
mkdir 002 003              新建两个目录002、003

rmdir 001                删除空目录001
rmdir -p 001                在子目录被删除后，如果父目录也变成空目录，就连父目录一起删除

rm 001                   删除文件或目录001
rm -i 001                 删除前询问确认
rm -r 001                向下递归删除，删除目录及目录下的所有文件
rm -f 001                直接强制删除，不做任何提示（即使文件属性是只读也会删除）
```

```
vi打开文件
:w                            保存文件
:q                             退出文件
:wq                          先保存，然后退出
:wq!
```

### cat
```
cat filenaem                  一次性显示整个文件的内容
cat>filename                创建新文件，不能编辑已有文件（我使用时发现可以覆盖原来的内容）
cat file1 file2>file         将几个文件合并为一个文件（原来file的内容会被覆盖）
cat -b filename             对非空输出行编号
cat -n filename             对所有输出行编号
cat -s filename             有连续两行以上的空白行，就替换为一行空白行（不会修改原文件内容）
```


### more
```
more filename                         分页显示文件内容
more +n filename                    从第n行显示
more -n filename                     每页显示n行（最后一页不满n行就不显示）
more -c filename                      清屏然后显示文件内容
more +/pattern filename        查找第一次出现“pattern”的行，从该处前两行开始显示
```

```
ls -l | more -5            分页列出一个目录下的文件，使用more分页，和管道 | 结合。
Enter                      向下1行
Ctrl+F、空格键              向下滚动一屏
Ctrl+B                     返回上一屏
=                          输出当前行的行号
:f                         输出文件名和当前行的行号
q                          退出more
```

### tail
```
tail -f filename      把filename里最尾部的内容显示在屏幕上，并不断刷新，使你看到最新的文件内容（常用来查看服务器上的日志文件）
命令参数：
-f                  循环读取
-q                  不显示处理信息
-v                  显示详细的处理信息
-c<数目>            显示的字节数
-n<行数>            显示行数
```


