Linux下，MySQL新建用户、数据库并授权

### 1、新建用户
```
//创建用户
mysql>use mysql
insert into user(Host,User,Password) values ('localhost','Barry',password('123456'));
//刷新系统权限表
mysql>flush privileges;
```
这样就创建了一个用户：Barry，密码是：123456.

### 2、登录测试
```
mysql>exit;
# mysql -uroot -p
```
密码输入：123456

### 3、用户授权
```
//为用户创建一个数据库（barry_data）
msyql>create database barry_data default charset utf8 ;
//授权用户Barry使用密码123456拥有barry_data数据库的所有权限，并从任何主机可以连接。
mysql>grant all privileges on barry_data.* to Barry@'%' identified by '123456' with grant obtion;

//如果想限制用户只能从192.168.200.101的主机连接到mysql服务器，授权语句如下：
mysql>grant all privileges on barry_data.* to Barry@'192.168.200.101' identified by '123456'

//部分授权，语句如下：
mysql>grant select,update on barry_data.* to Barry@localhost identified by '123456';

//授予权限后，刷新系统权限表
mysql>flush privileges;
```

注意：with grant obtion 和 with admin obtion

* with grant obtion：授予给A权限，A将权限授予B；revoke授予给A的权限时，B的权限也会被级联回收。
* with admin obtion：授予给A权限，A将权限授予B；revoke授予给A的权限时，B的权限不会被级联回收。

### 4、删除用户
```
mysql>delete from user where user='Barry';
msyql>flush privileges;
```

### 5、删除数据库
```
mysql>drop database barry_data;
```

### 6、修改密码
```
mysql>use mysql
mysql>update user set password=password('新密码') where User='Barry' and Host='localhost';
msyql>flush privileges;
```