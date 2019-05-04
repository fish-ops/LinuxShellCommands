# LinuxShellTask

#### 如何登陆远程服务器？

``` bash
$ ssh -o ServerAliveInterval=60 root@142.93.21.228
```

- `o`: 每隔60s发送数据包以保持和服务器的连接，不然shell会失效

#### 如何将服务器的文件复制到本地？
``` bash
$ scp -r root@142.93.21.228:/etc/nginx ./DeskTop/a
```

- `r`: 递归复制，将文件夹下所有内容都复制到本地

#### 如何查询某域名对应的IP地址？
``` bash
$ nslookup github.com
Server:		8.8.8.8
Address:	8.8.8.8#53

Non-authoritative answer:
Name:	github.com
Address: 52.74.223.119 
```

#### 如何修改本机域名-ip的映射关系？
``` bash
# 打开hosts文件
$ sudo vi etc/hosts

# 添加域名-ip的映射关系
```
