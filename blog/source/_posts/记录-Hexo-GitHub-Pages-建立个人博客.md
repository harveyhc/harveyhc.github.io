---
title: 记录 Hexo + GitHub Pages 建立个人博客
date: 2017-04-16 09:13:26
tags: [GitHub Pages,Hexo]
categories: Blog
---

​		本次记录在Windows上执行，其他平台未测试。


## 环境搭建

* ### 1 [安装 node.js](http://www.runoob.com/nodejs/nodejs-install-setup.html)  

* ### 2 [安装 git](https://git-scm.com/)

* ### 3 安装[hexo](https://hexo.io/)

  ​	node.js和git安装好后,打开cmd命令:

```
  $ cd e:hexo   #进入需要安装的目录
  $ npm install hexo-cli -g 
  $ hexo init blog   #blog代表要创建的文件夹
  $ cd blog
  $ npm install
  $ hexo g
  $ hexo s
```
  hexo 几个常用命令 :
* 1 hexo g  (hexo generate) 用于生成静态文件
* 2 hexo s  (hexo server) 启动web服务
* 3 hexo d  (hexo deply) 部署到远端(比如github)
* 4 hexo new [layout] "postName" 新建文章
* 5 hexo new page "pageName" 新建页面

    执行到这里打开浏览器[http://localhost:4000/](http://localhost:4000/) 就可以看到一篇内置blog——Hello World

    ![hello world](http://oohcvxj2i.bkt.clouddn.com/blogindex.jpg)

***

## 主题设置

在这里选用的是[next](http://theme-next.iissnan.com/)主题

具体设置方法参考[next 开始使用](http://theme-next.iissnan.com/getting-started.html)

## GitHub Pages 设置

​	——下面提到的[userName]代表GitHub的用户名。

​	创建一个仓库来存放个人主页，仓库的名字必须是[userName]/[userName].github.io，这是特殊的命名约定。这样就可以通过http://username.github.io](http://username.github.io/) 来访问个人主页。需要注意随后提交的主页内容必须放在master分支。

***

## 部署Hexo到Github Pages

### 使用hexo deploy部署

​	在配置文件_config.xml(源码的根目录下)中作如下修改：

```
deploy:
  type: git
  repo: git@github.com:[userName]/[userName].github.io.git
  branch: master
```

​	在命令中执行:

```
$ npm install hexo-deployer-git --save
$ hexo d
```

### 使用git命令行部署

```
$ cd d:/hexo/blog
$ git clone https://github.com/[userName]/[username].github.io.git .deploy/[userName].github.io
```



***



END......