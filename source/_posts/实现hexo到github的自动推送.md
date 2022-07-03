---
title: 实现hexo到github的自动推送
date: 2022-07-03 18:17:13
tags: hexo github action
categories: hexo 
---

#### 实现hexo到github的自动推送

博客搭建有一年多了吧，平时记录内容的工具有两个，最初是使用tiddlywiki,通过github的personal access token实现在线自动保存到github。后来接触到hexo，属于当下流行的静态站点生成器，把记录的内容发布到自己熟悉的web服务器上，这里还是选择github。平时记录内容很简单，使用下面几条命令：

> hexo new "tittle"
>
> git add .
>
> git commit -m "your commit "
>
> git push origin 

很顺利的记录的内容发布到github page，通过指定的域名浏览自己的博客。时间长了也感觉很方便，可是时间久了，居然忘记了当时是怎么搭建的这个流程^-^。这里简单回忆一下，再次忘记的时候查看一下。

安装heox需要的环境这里就省略了。搭建好hexo的环境之后，一般是hexo g ,生成静态站点；再使用hexo d，也即是deploy的意思，当然是要在后缀为yml的配置文件中设置好发布的相关参数。

> hexo  clean   （清理以前生成的静态文件）
>
> hexo   g       （重新生成静态站点文件）
>
> hexo   d       （发布站点）

更详细的内容可以参考hexo官方的文档：[文档 | Hexo](https://hexo.io/zh-cn/docs/)

但是利用git命令把hexo 所有目录和文件推送到github的仓库，利用后台设置好的github workflow action 自动调用hexo 生成、发布站点的命令，把静态站点发布到github的pages。尴尬，自己搭建的流程，现在居然连actions里设置的流程代码都找不到了^-^,感觉现在懂的没有初学的时候多，看来笔记是要及时跟上才能提高效率。休息一下在完成。。。。。

```

```

