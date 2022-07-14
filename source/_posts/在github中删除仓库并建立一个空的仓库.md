---
title: 在github中删除仓库并建立一个空的仓库
date: 2022-07-14 06:44:15
tags: 
  - 删除仓库
  - 空的仓库
  - 仓库
categories: github 
---

#### 在github中新建一个仓库（空仓）

* 如何创建一个空的仓库
  ![img](/images/new-repository.png)
  ![img](/images/create-new-repository.png)

在仓库的基本信息区只输入username.github.io即可，选择不添加readme.md文件，确认后就建立一个空的仓库，完成之后，系统显示如何使用git 命令来快速设置和这个仓库的关联。

> 从上图可以看出，共有四种方法操作新建的这个空的仓库
>
> * 虽然可以在github上新建文件或者上传文件，但还是通过下面两种方法通过实现git与github通讯更方便
>
> * 
>
> * 
>
> * 



![img](/images/github-quick-setup.png)

~~~ create a new repository on the command line
echo "# lsgxs.github.io" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/lsgxs/lsgxs.github.io.git
git push -u origin main
本地新建立的目录、关联一个新建的空的仓库的方法
~~~


~~~push an existing repository from the command line

git remote add origin https://github.com/lsgxs/lsgxs.github.io.git
git branch -M main
git push -u origin main
把现有的本地项目推送到新建的空的仓库的方法
~~~

#### 如何删除一个仓库
* * 登录github之后打开这个仓库，点击这个仓库的settings

  ![img](/images/repository-settings.png)

  <!--more-->

* 在窗口的最下部区域选择删除这个仓库

  ![img](/images/delete-repository.png)

根据系统提示确认之后就可以删除这个仓库的所有内容
