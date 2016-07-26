# Node.js

安装 Node.js 的最佳方式是使用 nvm。

cURL:

```
$ curl https://raw.github.com/creationix/nvm/master/install.sh | sh
```

或 Wget:
```
$ wget -qO- https://raw.github.com/creationix/nvm/master/install.sh | sh
```
安装完成后，重启终端并执行下列命令即可安装 Node.js。

```
$ nvm install 4
```

或者您也可以下载 [安装程序](https://nodejs.org/en/) 来安装。

## 配置

#### 配置`./node_module/.bin` 进环境变量 `$PATH` 里

方案一：

具体看你自己的配置了，可以加在 `.profile`, `.bash_profile`, etc...

如果你按照之前的配置了 zsh 的话，按照下面的操作就好：

```
$ envconfig
```
添加上
```
export PATH="$PATH:./node_modules/.bin" # Add local node module to PATH
```
在文件里即可

方案二：

参见这个答案下面，有一个很好的配置方案，可以避免每次执行都要回到项目的根目录下面。

[How to use package installed locally in node_modules](http://stackoverflow.com/questions/9679932/how-to-use-package-installed-locally-in-node-modules)