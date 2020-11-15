##### 1.net view 查看局域网内的其他计算机名和ip地址

​	1）net view:查看局域网内其所有主机名   
​	2）ping 主机名   

![](/images/net_view.png)    

##### 2.mstsc:连接远程电脑    

​	1）mstsc 然后根据远程电脑主机名或ip地址，输入登录密码进入 
​	2) 确保被连接的电脑设置了允许远程控制：桌面计算机右键----->属性----->远程设置

##### 3.ipconfig:查看本机ip地址 

##### 4.systeminfo:查看本机计算机信息（包括主机名、主板信号、内存、硬盘等）  

​	systeminfo  

##### 5.ping : 发送数据包测试网络通信 

​	eg:  ping www.baidu.com

##### 6.cls :清屏命令

##### 7.tasklist:查看运行的进程

```bash
#查看chrome是否正在运行，用 | findstr 进行过滤，类似linux中的 | grep 用法
tasklist | findstr chrome
```

##### 8.netstat -ano：查看端口运行情况

```bash
#查看12306端口是否被占用
netstat -ano | findstr 12306
```

##### 9.tskill:杀死进程

```bash
#杀掉chrome进程
tskill chrome
```

##### 10.taskkill -F /pid xxx:根据pid强制杀死进程

```bash
#强制杀死pid为12306的进程
taskkill -F /pid 12306
```

