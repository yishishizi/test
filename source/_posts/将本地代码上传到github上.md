---
title: 将本地代码上传到github上
date: 2021-07-12 16:46:13
tags: 随笔
---
使用git将本地代码上传到github上
<!-- more -->
## 1、安装git客户端：

	1.1 下载git
		官网：git-scm.com/download/
		镜像：https://npm.taobao.org/mirrors/git-for-windows/?utm_source=qq&utm_medium=social&utm_oi=793691189428776960
	2.2 安装git
	2.3 绑定用户
		git config --global user.name "username"
		git config --global user.email "useremail"

## 2、设置ssh密钥：

    2.1 生成ssh密钥
        在git bash中输入ssh-keygen -t rsa -C "useremail"，一直按回车，不要输入yes。
    2.2 在C:\Users\user\.ssh路径下找到.pub结尾的文件，并用记事本打开，复制里面的内容.
    2.3 打开个人github界面，进入setting-SSH and GPG keys,点击new ssh key,title内容随意，key里面复制.pub文件的内容。
    2.4 在git中输入ssh -T git @github.com，看密钥配置是否成功。

## 3、上传项目到github

    3.1 在本地项目中右击鼠标，打开git bash。
    3.2 输入
        git config --global user.name "username"
		git config --global user.email "useremail"
    3.3 输入git init进行初始化
    3.4 输入git add .注意add后面有空格
    3.5 输入git commit -m "first commit"，对本次上传进行一下说明。
    3.6 输入git remote add origin git@github.com:547343578/xxx.git关联github仓库。github仓库地址一定要选择ssh。
    3.7 输入git push -u origin master上传本地代码
    注：若步骤3.7出错，查看github仓库里面是否有readme文件，如果有，需要先将readme文件拿下来，下载到本地仓库中。
    3.7.1 输入 git pull --rebase origin master
    若对代码进行了更新，需要再次重新上传的，先执行3.7.1，再执行3.7即可。
    master是默认的分支，如果上传到其他分支，需要改成对应的名字。

## 4、创建仓库分支
    4.1 执行git branch test 创建一个test分支
    4.2 输入git checkout test 切换到test分支
    4.3 输入git add .
    4.4 输入git commit -m "first commit"，对本次上传进行一下说明。
    4.5 输入git remote add origin git@github.com:547343578/xxx.git关联github仓库。github仓库地址一定要选择ssh。
    4.6 输入git push -u origin master上传本地代码
    4.7 githu仓库主页上此时会显示compare&pull request，点击进去点击create pull reques，点击merge pull request，点击confirm merge。

## 5、删除项目中的多余分支
    5.1 输入git push origin :test

## 6、删除库
    进入要删除库中的setting，页面最后点击delete即可。

## 参考教程：
[B站-【程序员一定要掌握的技巧】使用Git上传本地代码到GitHub教程](https://www.bilibili.com/video/BV195411t7tA?from=search&seid=9459704741008066552)

[B站-如何像程序员一样帅气地使用github？十分钟学会上传项目!](https://www.bilibili.com/video/BV1eV411s73X?from=search&seid=9459704741008066552)

[浮生.若梦博客](https://www.cnblogs.com/fqlife/p/8493745.html)

