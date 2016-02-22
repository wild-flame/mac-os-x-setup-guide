# Homebrew

## 安装 | Install

Homebrew 的安装非常简单。
 
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## 使用 | Usage
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
