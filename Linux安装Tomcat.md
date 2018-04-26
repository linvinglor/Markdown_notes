Linux安装Tomcat

### 1、安装jdk
Tomcat需要java环境运行，所以安装Tomcat之前需要先安装配置jdk，步骤如下：
http://www.jianshu.com/p/4393b63269eb

### 2、下载Tomcat
在Tomcat官网下载最新的Tomcat（不区分Windows/Linux） https://tomcat.apache.org/download-80.cgi

### 3、将Tomcat压缩包上传至Linux
将Tomcat压缩包 apache-tomcat-8.5.24.tar.gz  拷贝到 /usr/local/include 目录下，然后：

解压 `# tar -zxvf apache-tomcat-8.5.24.tar.gz`

重命名 `mv apache-tomcat-8.5.24 tomcat8`

### 4、启动Tomcat
`# /usr/local/tomcat8/bin/start.sh`

或者：

```
# cd /usr/local/tomcat8/bin
# ./start.sh
```

出现以下信息，说明启动成功：
```
[root@iZgmi6cswarimeZ bin]# ./startup.sh
Using CATALINA_BASE:   /usr/local/include/tomcat8
Using CATALINA_HOME:   /usr/local/include/tomcat8
Using CATALINA_TMPDIR: /usr/local/include/tomcat8/temp
Using JRE_HOME:        /usr/java/jdk1.8.0_161
Using CLASSPATH:       /usr/local/include/tomcat8/bin/bootstrap.jar:/usr/local/include/tomcat8/bin/tomcat-juli.jar
Tomcat started.
```

### 5、检查Tomcat是否可以正常访问

在浏览器中访问 http://IP:8080/

其中ip是你的虚拟机的ip，看到Tomcat系统界面，说明安装成功。

### 6、停止Tomcat
`# /usr/lcoal/tomcat/bin/shutdown.sh`

### 7、修改tomcat默认端口
`# vim /usr/local/tomcat8.5.24/conf/server.xml`

将8080修改为8082（修改完成后重启tomcat）

### 8、、修改防火墙

Tomcat默认使用8080端口，需要修改防火墙规则，开放8080端口。

`# vi /etc/sysconfig/iptables`

增加以下代码：

-A INPUT -m state --state NEW -m tcp -p tcp --dport 8080 -j ACCEPT

然后保存退出，重启防火墙：

`# service iptables restart`
