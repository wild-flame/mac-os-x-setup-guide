# Ruby

### 配置安装 

- [如何快速正确的安装 Ruby, Rails 运行环境](https://ruby-china.org/wiki/install_ruby_guide)

### *如果你人在国内的话

 ```
$ gem update --system # 这里请翻墙一下
$ gem -v
2.6.3
```

```
$ gem sources --add https://gems.ruby-china.org/ --remove https://rubygems.org/
$ gem sources -l
https://gems.ruby-china.org
# 确保只有 gems.ruby-china.org
```

## rvm 的配置和使用

### rvm 的安装

```
$ gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
$ \curl -sSL https://get.rvm.io | bash -s stable
$ source ~/.bashrc
$ source ~/.bash_profile
```

修改 RVM 的 Ruby 安装源到 Ruby China 的 Ruby 镜像服务器，这样能提高安装速度

$ echo "ruby_url=https://cache.ruby-china.org/pub/ruby" > ~/.rvm/user/db

### Ruby 的安装与切换

列出已知的 Ruby 版本
```
rvm list known
```
安装一个 Ruby 版本

    rvm install 2.2.2 --disable-binary

这里安装了最新的 2.2.2, `rvm list known` 列表里面的都可以拿来安装。

切换 Ruby 版本

    rvm use 2.2.2

如果想设置为默认版本，这样一来以后新打开的控制台默认的 Ruby 就是这个版本

    rvm use 2.2.2 --default 

查询已经安装的ruby

    rvm list

卸载一个已安装版本

    rvm remove 1.9.7

升级 

    rvm upgrade 1.9.7 2.2.2

## 附：单元测试

从 Ruby 2.2 开始，test::Unit 不再和 Ruby 的标准库一起发行。你可以单独安装：

```
$ sudo gem install test-unit
```

## Reference

- [Gem 的国内镜像](https://gems.ruby-china.org/)
- [rvm 指南](https://ruby-china.org/wiki/rvm-guide)

## 相关资源

- [Ruby 的语法总结](http://yunfengsa.github.io/blog/2015/10/30/ruby-jichuyufa/) 
- [*Ruby 推荐的代码风格](https://ruby-china.org/wiki/coding-style) —— 个人觉得很优质的内容