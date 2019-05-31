# LinuxShellTask

作为一个程序员，总是要有自己的云服务器，那就免不了做一个运维工作。

笔者以前在学习linux、shell的时候，发现学了好长时间结果好像什么都没有学到。反省了下，发现自己学习效率很低，具体为

- 遇到某个需求，但是不知道如何做，只能google半天，还不一定找到答案
- 抱着一个Linux脚本编程硬啃，但是发现好多命令根本用不上，过一段时间也就忘记了

shell中的各种命令怎么也有上千个了，每个命令还有可能有各种选项，对于非运维人员来说，其实是没必要全部掌握的。

所有有了这个项目

> 面向一般的开发人员，维护一个个人的云服务器所需要的用到的shell命令

这些都是自己在实践过程中常用的命令的总结。

#### 如何登陆远程服务器？

``` bash
$ ssh -o ServerAliveInterval=60 root@142.93.21.228
```
通过ssh登录ip地址为142.93.21.228的主机的root账户

- `o`: 每隔60s发送数据包以保持和服务器的连接，避免shell失效


#### 如何将服务器的文件复制到本地？
``` bash
$ scp -r root@142.93.21.228:/etc/nginx ./DeskTop/a
```
将本地./DeskTop/a 目录下的所有文件上传到服务器/etc/nginx目录下

- `r`: 递归复制，将文件夹下所有内容都复制到本地

同理，上传文件
```bash
$ scp -r target/forum-1.0.jar root@142.93.21.228:/root/java/forum
```

#### 如何让一个进程在后台运行？
使用`nohup &`包裹

假设原来的命令是`node index.js`, 那么使用`nohup node index.js &`可以让它以后台的方式运行

#### 如何查看本机中，所有jvm进程？
```bash
ps -ef|grep java
```

#### 如何关闭一个进程?
```bash
kill 7777
```
关闭pid为777的进程

#### 如何查询某域名对应的IP地址？
``` bash
$ nslookup github.com
Server:		8.8.8.8
Address:	8.8.8.8#53

Non-authoritative answer:
Name:	github.com
Address: 52.74.223.119 
```
可以通过nslookup这个命令查看github对应的ip地址


#### 如何修改本机域名-ip的映射关系？
``` bash
# 打开hosts文件
$ sudo vi /etc/hosts

# 添加域名-ip的映射关系
```
不同系统的hosts文件的位置可能不同
