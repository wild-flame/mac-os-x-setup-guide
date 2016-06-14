# Shadowsocks

ShadowSocks是用来科学上网的利器。

ShadowSocks可以说是其中一把功能齐全的瑞士军刀。服务器端提供了各种版本，如Python、Nodejs、Go、C libev等等，安装配置过程极其简单。

## 服务器端

1. 首先你需要有一个VPS。我用的是 DigitalOcean 的VPS。
  
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