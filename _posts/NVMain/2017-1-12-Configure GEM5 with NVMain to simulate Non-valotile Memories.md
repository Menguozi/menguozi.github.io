---
layout: post
comments: true
categories: GEM5 NVMain

---

[NVMain](http://wiki.nvmain.org/)是一个体系结构级的非易失内存模拟器，可以准确地模拟内存系统的时序和能耗。NVMain需要放在[GEM5](http://www.m5sim.org/Main_Page)全系统模拟器中运行。


> #### 1 安装Mercurial

集成NVMain到GEM5中需要用到一个源代码控制管理工具：[Mercurial](https://www.mercurial-scm.org/),请自行安装并学习使用方法。

	
> #### 2 安装GEM5

推荐使用最新版本的GEM5，可直接用以下命令下载：

     hg clone http://repo.gem5.org/gem5
	
配置GEM5的运行环境，可参照该[教程](http://pfzuo.github.io/2016/04/30/Install-and-Run-GEM5-in-Unbuntu-14.04/)。

> #### 3 配置hgrc文件

3.1 打开hgrc文件：

     vim ~/.hgrc

3.2 把以下内容加入到hgrc文件中，并将相关配置（如：`username`，`style`，`from`）修改成自己的信息：

     [ui]
     # Set the username you will commit code with
     username=Your Name <your@email.address>
     ssh = ssh -C
     # Always use git diffs since they contain permission changes and rename info
     [defaults]
     qrefresh = --git
     email = --git
     diff = --git
     [extensions]
     # These are various extensions we find useful
     # Mercurial Queues -- allows managing of changes as a series of patches
     hgext.mq =
     # PatchBomb -- send a series of changesets as e-mailed patches
     hgext.patchbomb =
     # External Diff tool (e.g. kdiff3, meld, vimdiff, etc)
     hgext.extdiff =
     # Fetch allows for a pull/update operation to be done with one command and automatically commits a merge changeset
     hgext.fetch =
     # Path to the style file for the M5 repository
     # This file enforces our coding style requirements
     style = /path/to/your/m5/util/style.py
     [email]
     method = smtp
     from = Your Name <your@email.address>
     [smtp]
     host = your.smtp.server.here

> #### 4 下载

4.1 注册[bitbucket](https://bitbucket.org/)账号；
4.2 按照[NVMain网站](http://wiki.nvmain.org/index.php?n=Site.GettingNVMain)上的说明获取NVMain的使用权；
4.3 进入GEM5主目录，使用`hg clone`命令下载NVMain；

    





	
	
	