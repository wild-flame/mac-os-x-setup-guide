---
title: 开机启动项的管理
---

开机项的管理也是一个重要的部分，这里给出两种方法。

## 1、直接通过设置来管理

- https://jingyan.baidu.com/article/73c3ce28dee1a1e50343d9f8.html

--- 

## 2、通过 plist 来管理

### macOS 系统的启动项会以 .plist 的文件存在于以下目录中：

- /Library/LaunchDaemons：系统启动时运行，用户不登录也会运行。
- /Library/LaunchAgents：用户登录后运行。
- ~/Library/LaunchAgents：用户自定义的用户启动项
- /System/Library/LaunchDaemons：系统自带的启动项
- /System/Library/LaunchAgents：系统自带的启动项

### 每个 .plist 文件中，有 3 个属性控制着是否会开机自动启动。

- KeepAlive：决定程序是否需要一直运行，如果是 false 则需要时才启动。默认 false
- RunAtLoad：开机时是否运行。默认 false。
- SuccessfulExit：此项为 true 时，程序正常退出时重启（即退出码为 0）；为 false 时，程序非正常退出时重启。此项设置时会隐含默认 RunAtLoad = true，因为程序需要至少运行一次才能获得退出状态。

### 所以其实针对这三项，不同的值有不同的表现：
- 如果 KeepAlive = false：
    - 当 RunAtLoad = false 时：程序只有在有需要的时候运行。
    - 当 RunAtLoad = true 时：程序在启动时会运行一次，然后等待在有需要的时候运行。
    - 当 SuccessfulExit =  true / false 时：不论 RunAtLoad 值是什么，都会在启动时运行一次。其后根据 SuccessfulExit 值来决定是否重启。 
- 如果 KeepAlive = true ：不论 RunAtLoad/SuccessfulExit 值是什么，都会启动时运行且一直保持运行状态。

如果不希望开机自动运行，则需要：
1. 找到对应程序的 .plist 文件 
2. 删除 SuccessfulExit 属性。
3. 将 RunAtLoad / KeepAlive 均设为 <false/>

## Reference

- https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLaunchdJobs.html
- https://developer.apple.com/library/content/technotes/tn2083/_index.html