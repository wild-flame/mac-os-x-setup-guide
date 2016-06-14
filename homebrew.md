# Homebrew

包管理工具让软件的安装（升级）和卸载都变得简便了许多。Homebrew 就是 Mac 下面的这样一个包管理工具（类似于 apt-get, yum)。


## 安装

Homebrew 的安装非常简单。
 
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

*** 注意：** 

Homebrew 的一个依赖（Dependency）是 Xcode，但是其实很多人并不需要使用 Xcode 的，那么可以只是安装**Command Line Tools**就行了，参见 [Xcode](xcode.md) 章节。

## 使用
```
$ brew install wget
```

Homebrew 会把文件安装在自己的目录下面，然后再用符号链接 (Symbolic Link) 链接到 /usr/local:

```
$ cd /usr/local
$ find Cellar
Cellar/wget/1.16.1
Cellar/wget/1.16.1/bin/wget
Cellar/wget/1.16.1/share/man/man1/wget.1

$ ls -l bin
bin/wget -> ../Cellar/wget/1.16.1/bin/wget
```

Homebrew 背后使用的是是 ruby 和 github，所以使用 Homebrew 必须要先配置好 Ruby（其实 Mac 就自带了 ruby ）。
