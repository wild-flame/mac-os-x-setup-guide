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

Reference: 

1. [Spacemacs with Python layer](http://www.slant.co/topics/366/viewpoints/13/~python-ides~spacemacs-with-python-layer)
2. [Fullstack Python - Emacs](http://www.fullstackpython.com/emacs.html)