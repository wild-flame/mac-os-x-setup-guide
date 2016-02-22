# Vim

自从有了 vundle 以后，重新配置 vim 的的工作就变得简单了很多，所以我们要做的首先就是安装 vundle 。

```
$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle
```

#

`.vimrc` 文件如下。

```
"-------------Vundle的配置文件-----------------

 set nocompatible               " 设置 vim 为不兼容 vi 模式
 filetype off                   " 必须的

 set rtp+=~/.vim/bundle/vundle/
 call vundle#rc()

 " 让 Vundle 管理 Vundle
 " 此条必须有
 Bundle 'gmarik/vundle'

 " 代码源在 github 上的
 " Bundle 'mattn/zencoding-vim' Zencoding has been removed
 Bundle 'mattn/emmet-vim'
 Bundle 'gregsexton/MatchTag'
 Bundle 'tpope/vim-rails'
 Bundle 'othree/html5.vim' 
 Bundle 'kien/ctrlp.vim'
 Bundle 'vim-scripts/vimwiki'
 Bundle 'pangloss/vim-javascript'
 Bundle 'guileen/vim-node-dict'
 Bundle 'scrooloose/nerdtree'

 " Don't forget to install ack http://beyondgrep.com/install/
 Bundle 'mileszs/ack.vim' 

 " vim自动补全的插件
 " Bundle 'Valloric/YouCompleteMe'
 
 " 代码源在script 上的
 Bundle 'mru.vim'
 Bundle 'surround.vim'
 
 "
 "  Brief help
 " :BundleList          - list configured bundles
 " :BundleInstall(!)    - install(update) bundles
 " :BundleSearch(!) foo - search(or refresh cache first) for foo
 " :BundleClean(!)      - confirm(or auto-approve) removal of unused bundles
 "
 " see :h vundle for more details or wiki for FAQ
 " NOTE: comments after Bundle command are not allowed..

"-------------个人配置文件-----------------

colorscheme desert           " 适合Ruby开发的蓝色主题
set guifont=Monaco           " 适合Ruby开发的字体 && 字号
set tabstop=2                " 设置tab键的宽度
"set shiftwidth=2             " 换行时行间交错使用4个空格
set autoindent               " 自动对齐
set expandtab                " 设置Tab为空格
set backspace=2              " 设置退格键可用
set cindent shiftwidth=2     " 自动缩进4空格
set smartindent              " 智能自动缩进
set ai!                      " 设置自动缩进
set nu!                      " 显示行号
set mouse=a                  " 启用鼠标
set ruler                    " 右下角显示光标位置的状态行
set incsearch                " 查找book时，当输入/b时会自动找到
set hlsearch                 " 开启高亮显示结果
set incsearch                " 开启实时搜索功能
set wrapscan                 " 搜索到文件两端时重新搜索
set nocompatible             " 关闭兼容模式
set vb t_vb=                 " 关闭提示音
"set hidden                   " 允许在有未保存的修改时切换缓冲区
set list                     " 显示Tab符，使用一高亮竖线代替
set listchars=tab:\|\ ,
syntax enable                " 打开语法高亮
syntax on                    " 开启文件类型侦测
filetype indent on           " 针对不同的文件类型采用不同的缩进格式
filetype plugin on           " 针对不同的文件类型加载对应的插件
filetype plugin indent on    " 用自动补全，必须有

au FileType javascript set dictionary+=$HOME/.vim/bundle/vim-node-dict/dict/node.dict
au FileType javascript set tabstop=4 
au FileType javascript set cindent shiftwidth=4     " 自动缩进4空格


"emmet的配置
let g:user_emmet_expandabbr_key = '<s-tab>'
```