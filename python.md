---
title: Python
---

# 安装与配置

## 在 macOS 中 安装 python 3

macOS 中其实是自带 python 的，不过版本是 `python 2.x`，而现在的大趋势是在使用 `python 3`，所以我们需要安装 python 3 呀。

### Homebrew 安装

~~Homebrew 安装 python 3 只需要一行代码 `brew install python3`，如果是因为权限问题，`sudo brew install python3` 即可。~~

使用 `brew install python` 默认就是安装的 python 3 了

如果已经安装过，会提示:

```
Error: python 2.7.11 is already installed
To upgrade to 3.7.2, run `brew upgrade python`
```

> Tips: 如果想要安装 python2

```
brew install python@2
```
### 官网安装
在 [python download]("https://www.python.org/downloads/") 中选择版本，然后下载安装即可。

## 验证安装
在 terminal 中输入：

```
python3 -V
```

可以查到 python 的版本号，如果出现：

```
python 3.x.x
```

这样的字样说明安装成功了。

> `which python3` 可以查到 python **安装的路径**。

## 调整默认 python 版本

可以试试在 terminal 中输入 `python`，就会进入 python 的交互模式:

```{shell}
Python 2.7.15 (default, Jul 10 2018, 12:31:08)
[GCC 4.2.1 Compatible Apple LLVM 10.0.0 (clang-1000.10.38)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
> 这时候默认的 `python` 版本还是默认版本，如何改成 `python3` 呢？

在 `.profile` 中加入 `python3` 的路径即可。通过 `which python3` 查到 python 3 的路径，例如：`/usr/local/Homebrew/bin/python3`，则修改 `~/.bash_profile`，加入这一行:

```
alias python="/usr/local/Homebrew/bin/python3"`
```

然后用 `source` 重新执行这个文档：`source ~/.bash_profile`

这样就可以了。

### * 设置 python 的 shell 在启动的时候读取的脚本。

```
$ export PYTHONSTARTUP=$HOME/.pythonrc.py
```

`~/.pythonrc.py`:

```
try:
    import readline
except ImportError:
    print("Module readline not available.")
else:
    import rlcompleter
    readline.parse_and_bind("tab: complete")
```

## 问题 | Issues

在使用 emacs 的 anaconda-mode 的时候，如果你使用了 Homebrew 来安装 python 的话，就会遇到一个错误[^1]。

---

[^1] You will encounter an erorr like this: https://github.com/proofit404/anaconda-mode/issues/114

