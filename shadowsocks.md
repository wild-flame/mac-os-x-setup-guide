# Shadowsocks

ShadowSocks是用来科学上网的利器。

ShadowSocks可以说是其中一把功能齐全的瑞士军刀。服务器端提供了各种版本，如Python、Nodejs、Go、C libev等等，安装配置过程极其简单。

pip 和 python 使用包管理工具安装即可。

## 服务器端

首先你需要有一个VPS。我用的是 DigitalOcean 的VPS。


```
$ ssh user@128.199.xxx.xxx
```

检查 python 的版本
```
$ python --version
Python 2.6.8
```
安装 Shadowsocks
```
$ pip install shadowsocks
```


## 用户端