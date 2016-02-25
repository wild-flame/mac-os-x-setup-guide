# Git and Github

没有用过 [Git](http://git-scm.com/) ？

还好意思说自己是程序员? 

# Install

    $ brew install git

测试安装是否成功：

    $ git --version

 `$ which git` 的输出也应该是 `/usr/local/bin/git`.

设置用户名和邮箱：

    $ git config --global user.name "Your Name Here"
    $ git config --global user.email "your_email@youremail.com"

之后也可以通过 `.gitconfig` 来查看和修改这些配置。

进阶请参见 [设置 Git](https://help.github.com/articles/set-up-git/)：包括 SSH，HTTPS。


# Advanced Settings

每次都自动添加.gitingore - 
http://stackoverflow.com/questions/16658087/automatically-add-gitignore-and-hooks-on-git-init

# 参考：

1. http://stackoverflow.com/questions/16658087/automatically-add-gitignore-and-hooks-on-git-init