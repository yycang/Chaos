# 如何在餐眼团队中写一篇你自己的技术博客


### 1. 安装项目

首先从github上clone项目
```
git clone git@github.com:kaoputou/Chaos.git
```
因为这是kaoputou唯一的公有项目，所以不用邀请成贡献者

> 此项目使用的`Sphinx`，一种文档工具，可以轻松写出清晰且优美的文档，是python项目首选的文档工具，想了解的可参考
> [Sphinx使用手册](https://zh-sphinx-doc.readthedocs.io/en/latest/index.html)


### 2. 环境搭建

启动项目前，本地需要安装python3，mac中可以用`brew install python3`安装即可

接下来使用`python3 -m venv venv`创建一个独立的python运行环境，`source venv/bin/activate`来进入该环境

下面正常安装Sphinx所使用到的依赖，依赖都存放在requirements.txt中，直接运行
```
pip3 install -r requirements.txt
```

当依赖安装完成后，准备工作就完成了，可以新开启一个分支来写东西了。


### 3. 启动项目

使用刚刚已经安装过的`sphinx-autobuild`工具启动服务

```
 sphinx-autobuild source build/html
```

整个项目的目录结构在`source/index.rst`文件中，在第9行的`.. toctree::`声明了一个树状结构，下面的`growth/index`路径信息就对应着文件夹`growth`里面的`index.rst`文件，在这个文件里可以继续声明树状目录。

所以你想要写一篇文章又想新建一个主题，就可以在项目中新建文件并在`source/index.rst`中声明即可。

如果你想在对应主题中写，那就在该主题文件夹中新建文件，并在此文件夹中的`index.rst`中声明路径就行了。


### 4. 开始创作

你可以用`reST`语法来写文章，当然你也可以用`markdown`语法来写，无论你是哪种程序员，markdown都是你应该掌握的技能，它用途广泛，在任意一个文档平台都获得了支持，而且它也不难掌握。

[reST的语法介绍](https://zh-sphinx-doc.readthedocs.io/en/latest/rest.html)

[markdown语法介绍](https://www.markdown.xyz/basic-syntax/)

如果你想在插入本地图片，把图片放在`source/media`中然后在文章中填入相对路径。

![logo](../../media/cylogo.png)


创作完成后，提交合并main分支的pr就可以了。

一些事项：
1. 写的文章在开始要加上你的署名哦
2. 因为这是公开项目，所以不要暴露业务中的私密事项。