---

layout: post
title: "Eclipse安装IBM RTC客户端插件指南"
date: 2012-12-29 11:37
comments: true
author: i47
categories: [rtc, eclipse, plugin, p2]

---

在[前文](http://telchina.github.com/blog/2012/12/28/ibm-rtcke-hu-duan-java-eekai-fa-cha-jian-an-zhuang-zhi-dao/)中，我们介绍了如何将RTC客户端作为开发环境，安装使用Eclipse Java EE开发工具的方法。但是，很多时候开发者已有配置完备使用良好的开发环境，不便迁移到RTC客户端上。例如有的开发者使用了更高版本的Eclipse 3.7或者基于3.7版本的插件，又比如使用了Flash Builder这种重量级的Eclipse插件。这时候之前的方法就不再适用了。

鉴于此，本文将讨论如何将IBM RTC客户端以插件形式安装到已有Eclipse中的方法。

<!--more-->
## 关于IBM RTC自带插件集成安装

在IBM提供的IBM Installation Manager中提供了集成到现有Eclipse的相关选项。但是很多同学反映安装失败（必须失败，不然不会有本文了。XD），尤其是对于Eclipse 3.7或者Flash Builder。因此这里提供一篇p2安装的教程。

## 关于“p2 Install Repository”

说到Eclipse插件安装，必须先提一下p2。

`p2`即Provisioning Platform的缩写，是Eclipse 3.4开始提供的插件包分发平台。很多使用Eclipse3.2/3.3老版本的用户还保留着复制插件到Eclipse相关目录的习惯。但是发展到今天，`p2`俨然已经是Eclipse平台下最方便通用的插件分发、管理、安装的途径。

关于p2的简介可以参阅[Eclipse.org官方的帮助信息](http://help.eclipse.org/galileo/index.jsp?topic=/org.eclipse.platform.doc.isv/guide/p2_overview.htm)或者InfoQ的文章：[P2为Eclipse准备好了吗？](http://www.infoq.com/cn/news/2008/05/eclipse-p2)

在[前文](http://telchina.github.com/blog/2012/12/28/ibm-rtcke-hu-duan-java-eekai-fa-cha-jian-an-zhuang-zhi-dao/)中，我们“导入Eclipse软件安装与更新站点”的操作其实就是在添加Eclipse.org官方的`p2`**在线软件安装仓库**。除了**在线软件安装仓库**之外，p2也支持**本地软件安装仓库**。

开发者可以在Eclipse.org官方或者第三方的插件发布者那里获得软件安装仓库（`zip`格式的压缩包）。在前文所述**可用软件站点管理**界面中可以添加单独的软件安装仓库。你可以选择本地目录（Local）或者直接选择zip压缩包（Archive）将本地软件安装仓库导入到Eclipse的**可用软件站点管理器**中。后面安装插件的步骤与前文所述一直。

这里单独拿出段落来强调`p2 Install Repository`不是想跟大家玩儿“吊书袋”，而是希望大家能注意到这个Eclipse平台的“术语”。因为很多开发工具都在使用Eclipse平台，其分发形式各不相同，但是p2作为Eclipse.org官方使用的通用分发方式还是被广泛支持的。

## 获取IBM RTC客户端的p2 Install Repository

事实上这篇教程**最水的部分**就在于如果你看完了p2的介绍，后面几乎不用看了=。=!!!。

在[IBM RTC的官方网站](http://jazz.net)上提供了各种下载。其中就包括`p2 Install Repository`的发行。

进入RTC官网后选择你需要的RTC版本（必须吐槽的是这个需要非常严格的版本号，4.0.0.1的客户端跟4.0的RTC服务器都不兼容）后，找到All Downloads页面，在里面查找`p2 Install Repository`的相关链接下载即可。p2发行是全平台通用的。

需要注意的是在jazz.net上下载虽然免费但是你需要注册jazz.net的账号。

## 安装

根据前面p2介绍中和[前文](http://telchina.github.com/blog/2012/12/28/ibm-rtcke-hu-duan-java-eekai-fa-cha-jian-an-zhuang-zhi-dao/)所述的插件安装方法。把刚才下载的RTC p2 Install Repository添加到Eclipse的**可用软件站点管理器**中，选中所有插件安装即可。

