# .gitignore

这份 `.gitignore` 包含了 Mac 会生成一些特有的文件：

```
# Folder view configuration files
.DS_Store
Desktop.ini

# Thumbnail cache files
._*
Thumbs.db

# Files that might appear on external disks
.Spotlight-V100
.Trashes

# Compiled Python files
*.pyc

# Compiled C++ files
*.out

# Application specific files
venv
node_modules
.sass-cache

# Temp File
*.swp
*.swa
```

## 进阶

除了`.gitignore`还有一个文件`~/.gitignore_global`，用法相同，可以把全局配置文件写在这里面

```
.\#* # Emacs生成的lock文件。
```

## 附录

GitHub 已经写好了一份 `.gitignore` 供大家使用，连接如下：

https://github.com/github/gitignore
