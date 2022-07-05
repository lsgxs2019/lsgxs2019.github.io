---
title: 在一台电脑上用git管理多个github账号
date: 2022-07-05 20:05:35
tags: git github ssh
categories: git 
cover: 
---

#### 在一台电脑上使用git 管理多个github账号

##### 一、取消全局配置

> 如果想在一台电脑上使用多个 GitHub 账号，如果使用全局配置的话，那么每次使用 git 命令时都会使用这个全局的用户名和邮箱，就没有办法区分不同的 GitHub 账号了，因此这里取消全局配置。在刚开始安装git并配置ssh时，大部分都使用过下面这两条语句：
>
> git conig --global user.name "yourusername"
>
> git config --global user.email "your mailbox"
>
> 其实也可以使用git config --list 来显示当前的全局参数列表，如果发现有自己用的github用户,就说明以前配置的参数是全局的，现在使用下面两条语句取消全局配置：
>
> git config  --global  --unset user.name
>
> git config --global   --unset user.email

<!--more-->

> **使用ssh-keygen 生成三个github账号对应的密钥**
>
> * ssh-keygen -t rsa -f id_rsa_hexo
>
> * ssh-keygen -t rsa -f id_rsa_tiddlywiki
>
> * ssh-keygen -t rsa -f id_rsa_hugo 
>
>   这里的-t指定的是rsa加密方式，-f 指定具体的密钥文件名
>
> * 这三条命令完成后，会产生3对密钥，分别对应自己现在使用的三个github账号
>
>   > id_rsa_hexo,id_rsa_hexo.pub       ----hexo静态站点 lsgxs2019.github.io
>   >
>   > id_rsa_tiddlywik ,id_rsa_tiddlywiki.pub  ----tiddlywiki在线笔记  tiddlywiki2021.github.io
>   >
>   > id_rsa_hugo,id_rsa_hugo.pub    ----hugo 静态站点   lsgxs.github.io

##### 二、生成并添加ssh密钥

> 添加密钥
>
> * 首先添加公钥到github的ssh
>
>   在git bash 命令窗口下，使用clip < id_rsa_hexo.pub 把公钥的文本输出到粘贴板，然后在windows下建立一个文本文件，粘贴公钥的文本并保存，当然也可以直接登录github，点击右上角的用户图标，选择弹出菜单底部的settings，然后再点击窗口左边的ssh，选择新建ssh，粘贴公钥的文本后选择Add ssh即可。这里依次添加好三个公钥到githbub的ssh。
>
> * 添加私有密钥。由于现在取消了全局配置，所以需要将私钥加到 ssh 中，这样当用到的时候 ssh 才能够识别出来。
>
>   eval $(ssh-agent -s )   注意这里-s是小写,启动ssh agent
>
>   ssh-add ~/.ssh/id_rsa_hexo
>
>   ssh-add ~/.ssh/id_rsa_tiddlywiki2021
>
>   ssh-add ~/.ssh/id_rsa_hugo
>
>   这三条语句是添加在前面生成的三个私钥

三、创建config

> 使用touch config可以在~/.ssh目录下创建config，使用文本编辑打开，输入下面的内容：

~~~
#first
Host hexo
HostName github.com
User lsgxs2019
IdentityFile ~/.ssh/id_rsa_hexo
# second
Host tiddlywiki
HostName github.com
User tiddlywiki2021
IdentityFile ~/.ssh/id_rsa_tiddlywiki
#Third
Host hugo
HostName github.com
User lsgxs
IdentityFile ~/.ssh/id_rsa_hugo

~~~

这里的总共记录了三个账号对应的信息，其中Host实际上个别名，可以替代ssh协议中git@host：写法的主机名称部分。

config编辑完成后，可以使用

ssh -T git@hexo

ssh -T git@tiddlywiki

ssh -T git@hugo

三条语句分别测试一下，出现You've successfully authenticated,......的字样就说明配置成功。

四、从远程仓库clone仓库并配置本地项目

```
git clone git@hexo:username/username.github.io.git 
git clone git@tiddlywiki:username/username.github.io.git 
git clone git@hugo:username/username.github.io.git 

```

######  修改本地仓库的用户名和邮箱

git config user.name   username

git config user.email   yourmailbox

到这里就算成功了，可以新增加一下文件，然后正常的提交：

>git add .
>
>git commit -m "注释"
>
>git push origin
>
>
