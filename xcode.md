# Xcode



## 安装

1. 如果正常使用 Homebrew 的话，是需要 xcode 的，但是其实很多人并不需要使用 xcode 的那么多功能，那么可以只是安装**Command Line Tools**：

  ```
$ xcode-select --install
  ```

2. 如果要完整安装的话，可以在 [这里](https://developer.apple.com/xcode/)
查看并安装Xcode。

## 配置

安装 Xcode 并没有什么困难的，下面我们来进行一些个性化的配置吧。

比方说我是一个 vimer，所以在 IDE 上要做的第一件事情就是开启 vi 模式 ：D，那么我们就需要一个插件叫做 [xvim](https://github.com/XVimProject/XVim)。

插件安装的过程如下：

1. 首先下载插件的源代码：
```
$ git clone https://github.com/XVimProject/XVim
```

2. 确保 xcode-select 的路径是指向 Xcode 的：
```
$ xcode-select -p
/Applications/Xcode.app/Contents/Developer
```
如果路径不对，可以使用`$ xcode-select -s`来指定

3. 编译：
```
$ make
```
如果提示
```
XVim hasn't confirmed the compatibility with your Xcode, Version X.X
Do you want to compile XVim with support Xcode Version X.X at your own risk? 
```
可以按 Y 继续

*4. 可以在用户的家目录创建`.xvimrc`来定制XVim的配置。


### Reference

- [大家用xcode开发的时候都会用到什么插件？](https://www.zhihu.com/question/24859067/answer/61763219)
- [Vim命令图解和XVim使用](http://blog.csdn.net/totogo2010/article/details/8220484)

-----

TODO：

- [ ] 整理插件列表


