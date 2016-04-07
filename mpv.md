# MPV

mpv 是 Mplayer 和 Mplayer2 项目的分支，目前活跃的开发者都转向开发 mpv。它以 ffmpeg 为解码器，可以调用 OS X 平台的硬件加速解码，支持 ass 在内的多种字幕，有高级 OpenGL scale 算法，还支持 lua 扩展脚本。

唯一的缺点就是 UI 过于简陋，官方只提供 OSC 用作基本的控制选项，其它所有的设置都需要手动改配置文件，不过作为程序猿这也没关系了。

## 安装

使用 Homebrew 安装就可以了。

```
brew install --HEAD --with-bundle --with-bluray-support --with-libdvdread --with-little-cms2 --with-lua --with-bundle mpv
```

## 配置

如果你想要你的软件列表里面也显示出 mpv 的话。

```
brew linkapps mpv
```


## Reference：

更多高级配置，参见

1. http://bbs.feng.com/read-htm-tid-9633783.html
2. https://coalgirls.wakku.to/faq/playback/compiling-mpv-on-mac-os-x
3. https://mpv.io/