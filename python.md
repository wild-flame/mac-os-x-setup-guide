# Python



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

如果你使用了 Homebrew 来安装 python 的话，就会遇到一个错误[^1]。


Reference: 

1. [Spacemacs with Python layer](http://www.slant.co/topics/366/viewpoints/13/~python-ides~spacemacs-with-python-layer)
2. [Fullstack Python - Emacs](http://www.fullstackpython.com/emacs.html)




[^1] You will encounter an erorr like this: https://github.com/proofit404/anaconda-mode/issues/114