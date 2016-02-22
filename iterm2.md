# iTerm2

## 安装 | Install

直接在官网 http://iterm2.com/ 下载并安装即可。

## 配置 | Settings

### zsh

zsh 的使用和 bash 区别不大，大部分功能都很简单而且自然。

为了使 `.zshrc` 尽可能的简洁。我们会新建一个叫 `env.sh`的文件，用来保存如`alias`,`exports`,`path`等环境变量。

#### 安装

1. 安装 zsh：
```
brew install zsh zsh-completions
```

2. 安装 oh-my-zsh：
```
wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O - | sh
```

*注：
如果你以前安装过 rvm 的话，你可能会看到如下的错误信息： 

```
Warning: PATH set to RVM ruby but GEM_HOME and/or GEM_PATH not set, see:
    https://github.com/wayneeseguin/rvm/issues/3212
```

3. 配置 `.zshrc`

```
    ZSH_THEME=pygmalion
    # Use sublimetext for editing config files
    alias zshconfig="gvim ~/.zshrc"
    alias envconfig="gvim ~/Projects/config/env.sh"
    plugins=(git colored-man colorize github jira vagrant virtualenv pip python brew osx zsh-syntax-highlighting)
    # Add env.sh
    . ~/Projects/config/env.sh
```

#### 

