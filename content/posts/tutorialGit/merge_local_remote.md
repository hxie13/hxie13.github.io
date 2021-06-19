---
title: "Merge_local_remote"
date: 2021-06-19T21:54:09+08:00
description: ""
categories: []
toc: false
dropCap: true
displayInMenu: false
displayInList: true
draft: false
resources:
- name: featuredImage
  src: ""
  params:
    description: ""
    attribution:
      name: ""
      link: ""
---
## 问题背景  
- 当Github上的仓库与本地仓库不同步，存在差异时，在本地向remote执行push操作会出现差错，这是本地与remote仓库历史记录不同产生的问题.

## 问题复现
```
git remote add origin git@github.com:username/repostotyname.git
git remote -v
# 拉取remote的master分支至本地
git pull origin master
# 产生"拒绝合并不相关的历史"
```

## 解决方案
- 采取强制方式拉取合并，`git pull origin master --allow-unrelated-histories`，仓库便在本地合并，可进一步推送至remote，`git push -u origin master`

