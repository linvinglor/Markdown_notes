Linux常用命令2

shutdown -h now            关闭系统
shutdown -r now             重启
logout                             注销
su - root                          切换到root用户
hostname                        查看主机名

netstat -na |grep 3360       查看端口是否被占用

pwd                        查看当前路径

cd ..                            返回上一级目录
cd 或者 cd ~        返回到当前用户的主目录下
cd /                            返回根目录

mkdir 001                新建一个目录001
mkdir 002 003              新建两个目录002、003

rmdir 001                删除空目录001
rmdir -p 001                在子目录被删除后，如果父目录也变成空目录，就连父目录一起删除

rm 001                   删除文件或目录001
rm -i 001                 删除前询问确认
rm -r 001                向下递归删除，删除目录及目录下的所有文件
rm -f 001                直接强制删除，不做任何提示（即使文件属性是只读也会删除）


vi打开文件
:w                            保存文件
:q                             退出文件
:wq                          先保存，然后退出
:wq!


ping 10.20.13.101                ping命令会一直ping下去，ctrl+c停止
ping www.baidu.com
ping -c N ip/网址                 其中N表示ping的次数

使用"killall mysqld"命令，可以杀掉所有已mysqld命名的进程。


cat
cat filenaem                  一次性显示整个文件的内容
cat>filename                创建新文件，不能编辑已有文件（我使用时发现可以覆盖原来的内容）
cat file1 file2>file         将几个文件合并为一个文件（原来file的内容会被覆盖）
cat -b filename             对非空输出行编号
cat -n filename             对所有输出行编号
cat -s filename             有连续两行以上的空白行，就替换为一行空白行（不会修改原文件内容）


more
more filename                         分页显示文件内容
more +n filename                    从第n行显示
more -n filename                     每页显示n行（最后一页不满n行就不显示）
more -c filename                      清屏然后显示文件内容
more +/pattern filename        查找第一次出现“pattern”的行，从该处前两行开始显示
ls -l | more -5                           分页列出一个目录下的文件，使用more分页，和管道 | 结合。
Enter                             向下1行
Ctrl+F、空格键              向下滚动一屏
Ctrl+B                            返回上一屏
=                                    输出当前行的行号
:f                                    输出文件名和当前行的行号
V                                    调用vi编辑器
q                                    退出more


tail
tail -f filename            把filename里最尾部的内容显示在屏幕上，并不断刷新，使你看到最新的文件内容（常用来查看服务器上的日志文件）
命令参数：
-f                        循环读取
-q                        不显示处理信息
-v                        显示详细的处理信息
-c<数目>            显示的字节数
-n<行数>            显示行数

head 和 tail 命令：
    head -3 test.log        //查看文件的前3行
    tail -3 test.log            //查看文件的最后3行
    head、tail分别用来查看文件的开头和结尾
    tail -f text.log            //用来循环查看动态的日志文件
    head -20 text.log | tail -10        //查看文件的第11行到第20行
