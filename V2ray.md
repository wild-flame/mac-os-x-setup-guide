---
title: V2ray 指南
---

ss 被堵得实在是太厉害了，不得已只能在电脑上使用 V2ray 了。 尽管 V2ray 兼容 ss 协议，但为了不被封锁，我们会完全弃用 shadowsocks 协议，仅使用 Vmess 协议。

## 服务器端

参考部署 ss 的经验，服务器端的部署用 docker 更快。

```
docker run -v /etc/v2ray:/srv/docker/v2ray -p 16823:16823 v2ray/official:latest v2ray -config /etc/v2ray/config.json
```

### config.json :

```
{
  "inbounds": [
    {
      "port": 16823, // 服务器监听端口
      "protocol": "vmess",    // 主传入协议
      "settings": {
        "clients": [
          {
            "id": "b831381d-6324-4d53-ad4f-8cda48b30811",  // 用户 ID，客户端与服务器必须相同
            "alterId": 64
          }
        ]
      }
    }
  ],
  "outbounds": [
    {
      "protocol": "freedom",  // 主传出协议
      "settings": {}
    }
  ]
}

```

## UUID的生成

>由于 id 使用的是 UUID 的格式，我们可以使用任何 UUID 生成工具生成 UUID 作为这里的 id。比如 [UUID Generator](https://www.uuidgenerator.net/) 这个网站，只要一打开或者刷新这个网页就可以得到一个 UUID，如下图。或者可以在 Linux 使用命令 `cat /proc/sys/kernel/random/uuid` 生成。
>
![](https://toutyrater.github.io/resource/images/generate_uuid.png)

参考：

- https://v2ray.com/chapter_02/protocols/vmess.html 
- https://toutyrater.github.io/basic/vmess.html

## 客户端

以下是客户端配置，将客户端的 config.json 文件修改成下面的内容，修改完成后要重启 V2Ray 才会使修改的配置生效。

```
{
  "inbounds": [
    {
      "port": 1080, // 监听端口
      "protocol": "socks", // 入口协议为 SOCKS 5
      "domainOverride": ["tls","http"],
      "settings": {
        "auth": "noauth"  //socks的认证设置，noauth 代表不认证，由于 socks 通常在客户端使用，所以这里不认证
      }
    }
  ],
  "outbounds": [
    {
      "protocol": "vmess", // 出口协议
      "settings": {
        "vnext": [
          {
            "address": "serveraddr.com", // 服务器地址，请修改为你自己的服务器 IP 或域名
            "port": 16823,  // 服务器端口
            "users": [
              {
                "id": "b831381d-6324-4d53-ad4f-8cda48b30811",  // 用户 ID，必须与服务器端配置相同
                "alterId": 64 // 此处的值也应当与服务器相同
              }
            ]
          }
        ]
      }
    }
  ]
}

```

在配置当中，有一个 id (在这里的例子是 `b831381d-6324-4d53-ad4f-8cda48b30811`)，作用类似于 Shadowsocks 的密码(password), VMess 的 id 的格式必须与 UUID 格式相同。
