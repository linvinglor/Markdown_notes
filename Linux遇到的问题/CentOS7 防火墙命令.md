CentOS7 防火墙命令

查询防火墙状态：firewall-cmd --state

关闭防火墙：systemctl stop firewalld.service

开启防火墙： systemctl start firewalld.service

禁止firewall开机启动：systemctl disable firewalld.service