---
title: Hexo+GitHub搭建站点
date: 2019-11-16 17:00:36
tags: Hexo
---
之前使用jekyll搭建过,很久没使用过了,当时搭建的站点也不是很美观,重新再搭一个吧,
随便找了一个使用Hexo,页面还可以吗！小样就用你了。


## 1.上主站看看教程
https://hexo.io/zh-cn/
快速、简洁且高效的博客框架

安装前提    
    Node.js (Node.js 版本需不低于 8.6，建议使用 Node.js 10.0 及以上版本)
    Git

这里我使用的系统为:
CentOS release 6.10 32bit

## 2.开始愉快的安装前奏
事实证明这个对于32位的老操作系统来说实在是太难了...

### 1). yum install git(没毛病)


### 2). 安装node.js
最新的版本为13,折中下选择12 ，希望能安装成功吧

```bash 
$curl -sL https://rpm.nodesource.com/setup_12.x | bash -
Your distribution, identified as centos-release-6-10.el6.centos.12.3.i686, is not currently supported
```

devtools安装编译环境手动编译源码，失败！
换个node版本，失败！！
重新手动编译gcc编译环境，make了一夜，抱错，失败！！！

进入第三天，直接下载 8.9.3的版本，因为这个是有32位Linux版本的，[直接下载](https://nodejs.org/dist/v8.9.3/node-v8.9.3-linux-x86.tar.xz)

将文件解压到 /usr/local下
同时将 /usr/local/node-v8.9.3-linux-x86 添加到 .bashrc的 PATH 里


$ node -v
v8.9.3


完成！！！！

## 3. hexo 安装配置
官网写的很详细，就不多说了，[到这里](https://hexo.io/zh-cn/docs/)


## 4. 站点简单配置
```bash 
$hexo init myblog
$cd myblog
$npm install
$git clone https://github.com/fi3ework/hexo-theme-archer.git themes/archer --depth=1 下载找到的theme
$vi _config.yml  找到theme替换成下载的 archer
```


主题来[这里](https://hexo.io/themes)去找
``` bash
npm install hexo-server --save
hexo server
```
需要到网站目录下执行 ，默认开启的是4000端口
编辑器的话可以使用 sublime ，加装插件：Markdown Editing + MarkdownLivePreview

新增页面文章:
    hexo new post filename

删除发布的界面，直接找到md文件删除(有说还需要 hexo g 和 hexo d 更新下)

历时3天真是难死了。。。。。

github就先暂时不搞了。
