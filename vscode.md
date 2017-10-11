# Visual Studio Code

## 安装

1. 下载适用于 Mac OS X 的 [Visual Studio Code](https://go.microsoft.com/fwlink/?LinkID=534106)。
2. 双击下载的存档展开内容。
3. 拖动 Visual Studio Code.app 至 Applications 文件夹。

## 配置

### 1. 配置从命令提示行启动`vscode`

> **TIPS: 新版本的 vscode 可以直接在程序里进行配置了。**
>
> 如果您希望能够在终端中输入‘code’就能运行VS Code，VS Code有一条命令，**Shell Command: Install 'code' command in PATH**可以将‘code’添加至您的`$PATH`中。
>
> 安装完成之后，运行VS Code。现在，打开命令面板（按F1键）输入`Shell 命令`找到`Shell 命令: 在PATH中安装“code”命令`。
>
> ![](https://jeasonstudio.gitbooks.io/vscode-cn-doc/content/images/md_editor_setup_01.png "Shell 命令：在PATH中安装“code”命令")
>
> 命令执行完成之后，重启终端工具使新的`$PATH`可用。现在，您可以简单地在终端中任意文件夹下输入‘code .’来编辑该文件夹下的文件了。

~~添加如下命令到 ~~`env.sh` 里。~~~~

```
alias vscode='open -a "Visual Studio Code" $1'
```

~~注：`env.sh`~~ 的具体配置参见 `iTerm2` 章节。~~~~

### \*2. 安装 vim 插件

打开 vscode，按住 `command + shift + p` 然后在输入框中输入「扩展」。

![](/assets/vscode-extension.png)

在应用商店里搜索名为`Vim`的扩展，安装即可。

![](/assets/install-vim.png)

## \*3. 安装 tslint, typescript 插件

## More Reference:

* [https://jeasonstudio.gitbooks.io/vscode-cn-doc/content/md/编辑器/安装.html](https://jeasonstudio.gitbooks.io/vscode-cn-doc/content/md/编辑器/安装.html)



