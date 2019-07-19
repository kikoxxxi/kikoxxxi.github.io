---
layout:     post
title:      "搭建Gitpage博客"
subtitle:   ""
date:       2019-07-19
author:     "kikoxxxi"
catalog: true
description :  搭建jekyll 和 gitpage 的小白过程
keywords: gitpage,jekyll，gitpage评论，gitment替代，gittalk，gitpage图片，gitpage模板
tags: 搭建gitpage+jekyll博客
---


# Jekyll+GitPages搭建个人博客

## 一、GitPages创建

### 本地项目上传（远程仓库已有文件的情况）

```bash
$  git init
$  git add .
$  git remote add origin https://github.com/kikoxxxi/kikoxxxi.github.io.git
$  git pull origin master --allow-unrelated-histories
$  git push -u origin master
```

## 二、Gem下载Jekyll

### 替换源

```bash
$  gem source l
*** CURRENT SOURCES ***

https://rubygems.org/
$  gem source -r https://rubygems.org/
https://rubygems.org/ removed from sources
$  gem source -a https://gems.ruby-china.com
https://gems.ruby-china.com added to sources
```

### 下载Jekyll

```{bash}
$  sudo gem install jekyll
$  sudo gem install jekyll-paginate
```

- #### 报错（原因是ffi版本过高）

```{bash}
ERROR: Error installing jekyll:
ERROR: Failed to build gem native extension.
To see why this extension failed to compile, please check the mkmf.log which can be found here:

  /Library/Ruby/Gems/2.3.0/extensions/universal-darwin-17/2.3.0/ffi-1.11.1/mkmf.log
  
$  vi /Library/Ruby/Gems/2.3.0/extensions/universal-darwin-17/2.3.0/ffi-1.11.1/mkmf.log
conftest.c:3:10: fatal error: 'ffi.h' file not found
```

- #### ffi版本过高冲突解决

```bash
$  sudo gem install ffi -v '1.9.21'
```

