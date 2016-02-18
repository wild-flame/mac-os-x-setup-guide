# 附：疑难杂症等

### Battle.net

如果使用国服下载 Battle.net 并且运行以后，就再也看不到其他的地区了，使用美帝的安装器安装也无能为力。网上有一些修改config 的解决办法，但已经过时了。

在 `/Applications/Battle.net.app/Contents/Battle.net.app/Contents/MacOS`这个文件夹下面，打开终端（Terminal / iTerm 2）。

```
$ ./Switcher --setregion=US
```

问题解决。：D