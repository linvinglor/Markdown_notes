Linux安装jdk

### 1、下载jdk

`# getconf LONG_BIT`    //查看Linux是32位还是64位。

然后到jdk官网下载合适的版本。

### 2、切换到root用户
`# su root`    //获取root权限，当前工作目录不变。

### 3、将 jdk-8u161-linux-x64.rpm 拷贝到 /usr/local/include 目录下

### 4、安装jdk

`# rpm -ivh jdk-8u161-linux-x64.rpm`

### 5、配置环境变量（rpm命令安装的jdk不需要配置环境变量，直接java -version即可显示版本信息）

`# vi /etc/profile`

添加如下内容：JAVA_HOME根据实际目录来
```
export JAVA_HOME=/usr/java/jdk1.8.0_161
export CLASSPATH=$JAVA_HOME/lib/
export PATH=$PATH:$JAVA_HOME/bin
```

### 6、使保存的环境变量生效

`# source /etc/profile`

### 7、测试安装成功

`# java -version`

返回了jdk的版本信息，表示安装成功。
注意：如果出现错误，请确保你没有在32位的Linux上安装64位的jdk（反之亦然）
