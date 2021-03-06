tinydump
========

基于golang的嗅探抓包工具, 类似tcpdump


### 使用方式

> 环境依赖: libpcap  
安装参考: http://www.blogjava.net/huyi2006/articles/127361.html

#### 直接使用

在 `release` 文件夹提供了mac和linux的release版本,可以直接使用 (需要以sudo权限运行)

#### 手动构建

```
go build
```

生成 `tinydump` 执行文件

#### 命令参数

```
sudo ./tinydump -h

 [ -i interface ]
 [ -t timeout ]
 [ -c count ]
 [ -s snaplen ]
 [ -X hexdump ]
 [ -d dump file ]
 [ -r read file ]
 [ -h show usage]
 [ expression ]
```

![sample](sample.png)


使用范例:

1.直接使用

```
$ sudo ./tinydump 
```

2.host过滤

```
$ sudo ./tinydump 'src 192.168.1.101 or dst 192.168.1.101'
```

3.端口过滤

```
$ sudo ./tinydump 'port 8000'
```

4.超时捕获 (时间单位为秒)

```
$ sudo ./tinydump -t 60
```

5.生成快照文件

```
$ sudo ./tinydump -d /tmp/test.cap
```

6.读取快照文件

```
$ sudo ./tinydump -r /tmp/test.cap
```

7.捕获指定行数的包

```
$ sudo ./tinydump -c 10
```
