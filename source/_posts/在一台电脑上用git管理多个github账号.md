---
title: 在一台电脑上用git管理多个github账号
date: 2022-07-05 20:05:35
tags: git github ssh
categories: git 
cover: 
---

#### 在一台电脑上使用git 管理多个github账号

> **使用ssh-keygen 生成管理多个github的密钥**
>
> * ssh-keygen -t rsa -f id_rsa_hexo
>
> * ssh-keygen -t rsa -f id_rsa_tiddlywiki
>
> * ssh-keygen -t rsa -f id_rsa_hugo 
>
> * 这三条命令完成后，会产生3对密钥，分别是
>
>   > id_rsa_hexo,id_rsa_hexo.pub
>   >
>   > id_rsa_tiddlywik ,id_rsa_tiddlywiki.pub
>   >
>   > id_rsa_hugo,id_rsa_hugo.pub
