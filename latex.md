# Latex

Latex的配置：

不推荐使用 `Homebrew` 来安装 Latex。

    Error: No available formula with the name "latex"
    Installing TeX from source is weird and gross, requires a lot of patches,
    and only builds 32-bit (and thus can't use Homebrew deps on Snow Leopard.)

    We recommend using a MacTeX distribution: https://www.tug.org/mactex/
    
请使用这个网站 MacTex 的发行包来安装：
<https://www.tug.org/mactex/>

## Cheatsheat

### Org-mode

- 预览 Latex 公式： `C-c C-x C-l` [^1]
- 按照 UTF-8 显示： `C-c C-x \`
- 输出 `.org` 文件至 pdf 或其他格式： `C-c C-e`


[^1]:http://orgmode.org/worg/org-tutorials/org-latex-preview.html 

贡献者：

- [TerenceLiu98](https://github.com/TerenceLiu98) 以及他的 [如何用 macOS 优雅的敲 LaTeX](https://www.jianshu.com/p/b1e3b029ded5)

    - 提出了 LaTex 的拼法应为 LaTeX