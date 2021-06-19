---
title: "Hugo+Github静态网页部署"
date: 2021-06-19T10:45:00+08:00
description: ""
categories: []
toc: false
dropCap: false
displayInMenu: false
displayInList: true
draft: false
resources:
- name: featuredImage
  src: "img.jpg"
  params:
    description: ""
    attribution:
      name: "aether"
      link: ""
---
# Build new site with github
1. 构建本地静态网页
```  
# 新建site
hugo new site newSite
# 进入newSite
cd newSite

# 新建blog，并添加内容
hugo new posts/newPost_1/hello.md
# 本地预览网页效果
hugo server -D
# 本地生成静态网页，内容存储在/public中
hugo

```

2. 创建Github仓库，利用[Github Pages](https://pages.github.com/)进行网页部署
+ 在Github中新建个人仓库`username.github.io`  
+ 在本地/public文件夹中，将内容push至远程仓库  
```
cd public
git init
git add .
git commit -m "hello Hugo"
git remote add origin https://github.com/username/username.github.io.git
git push -u origin master
```

3. 打开网页`https://username.github.io/`便可对部署网页进行访问了，快向小伙伴安利一下吧
