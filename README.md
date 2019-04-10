# LinuxShellTask

后端工程师需要用到的shell知识。

#### 如何登陆远程服务器？

``` bash
$ ssh -o ServerAliveInterval=60 root@142.93.21.228
```

- `o`: 每隔60s发送数据包以保持和服务器的连接，不然shell会失效

