# iTerm2

## 安装

直接在官网 http://iterm2.com/ 下载并安装即可。

## 配置

### 配色方案

选用 [solarized](http://ethanschoonover.com/solarized) 即好。

### zsh

zsh 的使用和 bash 区别不大，大部分功能都很简单而且自然。

为了使 `.zshrc` 尽可能的简洁。我们会新建一个叫 `env.sh`的文件，用来保存如`alias`,`exports`,`path`等环境变量。这样做的另外一个好处是，这个文件可以放在 Dropbox 里在不同电脑上进行同步。

#### 1. 安装

1. 安装 zsh：
```
brew install zsh zsh-completions
```

2. 安装 oh-my-zsh：
```
wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O - | sh
```

#### 2. 配置

配置`.zshrc`文件：

```
ZSH_THEME=agnoster

# Add env.sh

. ~/Dropbox/config/env.sh
plugins=(git colored-man colorize github jira vagrant virtualenv pip python brew osx zsh-syntax-highlighting)

# Use macvim for editing config files, you can set it to whatever editor you want 
    alias zshconfig="gvim ~/.zshrc"
    alias envconfig="gvim ~/Projects/config/env.sh"
```

配置`.env.sh`文件：

```
alias evil='open -a /Applications/Emacs.app $1'
alias ec='/Applications/Emacs.app/Contents/MacOS/bin/emacsclient'
alias ls='gls' # require to install 
```

#### 主题

上面的例子使用了 `agnoster` 作为主题的话，就需要安装 `Powerline-patched` 字体。

- [Meslo](https://github.com/Lokaltog/powerline-fonts/blob/master/Meslo/Meslo%20LG%20M%20DZ%20Regular%20for%20Powerline.otf) 点击 view raw 来下载。
- [Others](https://github.com/powerline/fonts) @ powerline fonts
    
下载好后打开，然后点击“安装字体”。

之后按照 iTerm -> preferences -> profiles -> text 修改字体即可。

---

##### oh my zsh 哪些主题比较好看、有特点？

`agnoster` 是一个很好看的主题。

但是经过一段时间的试用比较了一些 zsh 的主题之后，发现好看的主题并不是很实用，特别是有时候要在服务器上使用或者在 win 环境下面使用的时候。

如果考虑实用性推荐使用`ys` 这个 zsh 主题，详见 [my-ys-terminal-theme](http://blog.ysmood.org/my-ys-terminal-theme/)。

```
ZSH_THEME=ys # 将上面的配置里的 agnoster 改成 ys 就好了
```

---

## *附注：

如果你以前安装过 rvm 的话，配置好 oh-my-zsh 以后，你可能会看到如下的错误信息： 
```
Warning: PATH set to RVM ruby but GEM_HOME and/or GEM_PATH not set, see:
    https://github.com/wayneeseguin/rvm/issues/3212
```
解决办法详见 [疑难杂症](appendix.md) 。

## 参考

- [iTerm2 + oh my zsh + solarized + Meslo powerline font (OSX)
Raw](https://gist.github.com/kevin-smets/8568070)
- https://www.zhihu.com/question/33277508 