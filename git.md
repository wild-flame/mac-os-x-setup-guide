# Git and Github

没有用过 [Git](http://git-scm.com/) ？

还好意思说自己是程序员? 

# 1. 安装

    $ brew install git

测试安装是否成功：

    $ git --version

 `$ which git` 的输出也应该是 `/usr/local/bin/git`.

## 2. 配置

设置用户名和邮箱：

    $ git config --global user.name "Your Name Here"
    $ git config --global user.email "your_email@youremail.com"

之后也可以通过 `.gitconfig` 来查看和修改这些配置。

#### 解决 commit 的时候出现的 vi 编辑器的问题

Mac OS 下面 vi 编辑器和 git 一起用的时候会出问题。

```
error: There was a problem with the editor 'vi'
```
所以需要设置编辑器为 vim。
```
$ git config --global core.editor /usr/bin/vim
```

---

## Advanced Settings

- 进阶请参见 [设置 Git](https://help.github.com/articles/set-up-git/)：包括 SSH，HTTPS。


- 每次都自动添加.gitingore - 
http://stackoverflow.com/questions/16658087/automatically-add-gitignore-and-hooks-on-git-init

## 小抄 | Git Cookbook 

#### 1. 如何把当前的 branch 设置成 master. [^2]

```
git checkout better_branch
git merge --strategy=ours master    # keep the content of this branch, but record a merge
git checkout master
git merge better_branch             # fast-forward master up to the merge
```
或者
```
git checkout new-master
git branch -m master old-master
git branch -m new-master master
# And don't do this part.  Just don't.  But if you want to...
# git branch -d --force old-master
```

# 参考：

1. http://stackoverflow.com/questions/16658087/automatically-add-gitignore-and-hooks-on-git-init

2. http://stackoverflow.com/questions/2763006/change-the-current-branch-to-master-in-git 

3. http://tooky.co.uk/there-was-a-problem-with-the-editor-vi-git-on-mac-os-x/