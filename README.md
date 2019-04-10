# LinuxShellTask

后端工程师需要用到的shell知识。

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
