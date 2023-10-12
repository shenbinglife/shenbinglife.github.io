# 个人博客
基于hexo和next主题

hexo: 6.3.0  
next: 8.18.2

## 安装
```shell
# install nodejs
nvm install 20.8.0
nvm use 20.8.0

# install hexo and next theme
npm install -g hexo-cli
npm install hexo-theme-next
```

## 配置
修改_config.yml

```yaml
title: 散步留馨的博客
subtitle: ''
description: '唯美食与爱不可辜负'
keywords:
author: 散步留馨
language: zh-CN
timezone: ''

url: https://shenbinglife.github.io
permalink: :title/

post_asset_folder: true

theme: next
```

创建_config.next.yml

```yaml
scheme: Pisces

# 需要创建新的favicon文件名，否则默认next favicon会覆盖手动上传的favicon图片
favicon:
  small: /images/favicon-16x16.png
  medium: /images/favicon-32x32.png
  apple_touch_icon: /images/apple-icon.png
  safari_pinned_tab: /images/logo-512.svg

menu:
  home: / || fa fa-home
  about: /about/ || fa fa-user
  tags: /tags/ || fa fa-tags
  categories: /categories/ || fa fa-th
  archives: /archives/ || fa fa-archive

avatar:
  # Replace the default image and set the url here.
  url: /images/avatar.jpg
  # If true, the avatar will be displayed in circle.
  rounded: true

social:
GitHub: https://github.com/shenbinglife || fab fa-github
E-Mail: mailto:shenbinglife@163.com || fa fa-envelope
```

创建about，tags，categories文件夹

```shell
hexo new page about
hexo new page tags
hexo new page categories
```

打开每个文件夹的index.md，添加对应的type类型，例如`tags/index.md`
```markdown
---
title: tags
date: 2023-10-11 18:29:52
type: tags
---
```

上传favicon，推荐从[https://yesicon.app](https://yesicon.app)下载
```shell
mkdir source/images

# 将_config.next.yml中定义的favicon和avatar图片都上传到该文件夹中
```

## 本地运行
```shell
# 生成静态文件
hexo g

# 启动服务
hexo s
```

## Github Action 自动发布
参考[GitHub Actions 自动部署 Hexo 博客](https://blog.zhanganzhi.com/zh-CN/2022/06/0800d76d306e/)

