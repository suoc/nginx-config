# nginx-config
内外网 多网环境 多服务器 单点登陆配置


应用服务器专注于考虑业务逻辑的处理, 网络环境等问题放在nginx代理中处理.


1. 环境描述

内网应用服务器:
server1: 192.168.0.1:80 (业务1);
server2: 192.168.0.2:8080 (业务2);
....
serverN: 192.168.0.10:8888 (单点登陆);

本地nginx代理服务器: (本地的意思是应用服务器之间可以自由通过ip访问或属同一网段)
192.168.0.100:8088

公网nginx代理服务器: (放在公网服务器,或通过映射访问)
192.168.0.110:8188

内网环境1 nginx代理:
192.168.0.120:8288

内网环境2 nginx代理:
192.168.0.130:8388

2.应用服务器配置文件配置:(包含单点登陆,其它业务服务器的网络配置)
  应用服务器的网络地址配置全部配置成本地nginx代理服务器的地址.
