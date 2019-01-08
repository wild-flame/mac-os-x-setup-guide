---
title: Shadowsocks
---

> 最近 ss 被封锁的太严重了，我已经改用 [V2ray](V2ray) 了。我自己有搭好服务器，感兴趣的小伙伴可以联系我分摊费用 wechat: heromartin666

ShadowSocks是用来科学上网的利器。

ShadowSocks可以说是其中一把功能齐全的瑞士军刀。服务器端提供了各种版本，如Python、Nodejs、Go、C libev等等，安装配置过程极其简单。

## 服务器端

> 服务器端的部署用 docker 更快，可以参考文末 docker 部分。

1. 首先你需要有一个VPS。我用的是 [DigitalOcean](https://m.do.co/c/48f3c6e48721) 的VPS。

   ```
   $ ssh user@128.199.xxx.xxx
   ```

2. pip 和 python 使用包管理工具安装即可: `apt-get`, `yum`, etc...

   ```
   eg. $ apt-get install python-pip
   ```

3. 检查 python 的版本

   ```
   $ python --version
   Python 2.6.8
   ```

4. 安装 Shadowsocks

   ```
   $ pip install shadowsocks
   ```

### Usage

```
ssserver -p 443 -k password -m aes-256-cfb
```

后台运行：

```
sudo ssserver -p 443 -k password -m aes-256-cfb --user nobody -d start
```

停止：

```
sudo ssserver -d stop
```

查看 log 文件：

```
sudo less /var/log/shadowsocks.log
```

查看帮助使用 `-h`. 参考配置文件 [Configuration](https://github.com/shadowsocks/shadowsocks/wiki/Configuration-via-Config-File) 在这里。

p.s. 原版的服务器端 python 代码在Git 上被删除了，源代码请查看备份[ziggear/shadowsocks](https://github.com/ziggear/shadowsocks)

## 客户端

mac 上面直接使用 ShadowsocksX 就好了，在这里 [下载](https://shadowsocks.org/en/download/clients.html) 。

p.s. 上面同样有iOS，Android，Windows 以及 Openwrt 下面的客户端可以找到。

另外 ios 上也推荐使用 surge，除了费用略高其余都还不错。

## 如何让终端也走代理

在终端中直接运行命令

```
$ export http_proxy=http://proxyAddress:port
```

这个办法的好处是简单直接，并且影响面很小（只对当前终端有效，退出就不行了）。

如果你用的是ss代理，在当前终端运行以下命令，那么`wgetcurl`这类网络命令都会经过ss代理

```
$ export ALL_PROXY=socks5://127.0.0.1:1080
```

> 也可以使用 proxifier 这个软件

## 如何让 ssh 走代理

添加这两行到 `~/.ssh/config`

```
Host * 
    ProxyCommand nc -X connect -x 127.0.0.1:1080 %h %p
```



## Docker

```
docker run -d -p 1984:1984 oddrationale/docker-shadowsocks -s 0.0.0.0 -p 1984 -k $SSPASSWORD -m aes-256-cfb
```

# 其他参考资料

* 用 Docker：[30秒部署多用户Shadowsocks服务端](http://www.jianshu.com/p/4e3b54367991/) 
* [UFOVPS](http://www.ufovps.com/aff.php?aff=122) 不错，有CN2加速直连。



