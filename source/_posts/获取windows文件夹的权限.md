---
title: 获取windows文件夹的权限
date: 2022-07-08 11:15:01
tags: windows文件夹权限
categories: windows
---

#### 取得windows下受保护文件及文件夹的权限的方法

(总体思路：1、先成为该对象的所有者。2、再获取该对象的所有操作权限。将当前用户设置为文件夹或者文件所有者，然后获取全部权限。）

如果不清楚当前的用户名，可以在cmd窗口下使用 whoami 命令显示出当前登陆windows的用户名

> whoami     不是英文语句> who am i 

1.文件夹点击右键，查看属性。再点安全→高级→所有者 
2.点编辑→其他用户或组，在输入选择的对象名称里面输入你的用户名，再确定 
3.选择替换子容器和对象的所有者 
4.点确定，会弹出一个对话框，继续点确定！这样我们就拥有了这个文件夹的所有权 
特别提醒：不勾选“替换子容器和对象的所有者”，我们就只有这个文件夹的所有权，不会取得子文件夹和子文件夹里面所有文件的所有权 
5.再点权限→编辑→添加，把你的用户名填入，点确定 
6.再点击你的用户名→编辑，再勾选“完全控制/允许”，确定 
7.再勾选“把使用可从此对象继承的权限替换所有后代上现有的可继承权限”。然后点应用、确定、确定、再确定。这样，我们就完全拥有了对这个文件夹的所有权限。
