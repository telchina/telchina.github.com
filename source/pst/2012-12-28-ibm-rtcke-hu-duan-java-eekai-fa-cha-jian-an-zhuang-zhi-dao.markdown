---
layout: post
title: "IBM RTC客户端Java EE开发插件安装指导"
date: 2012-12-28 19:36
comments: true
author: i47
categories: [rtc, java, eclipse]
---

## 安装与使用指南

本文所使用IBM Retional Team Concert Clien(以下简称RTC客户端)版本为4.0。后续版本安装可作参考。

RTC客户端 4.0基于Eclipse 3.6 SR2开发，代号Helios。
<!--more-->
## 安装

### 导入Eclipse软件安装与更新站点

<img src="/images/ilus/AddSoftwareSite.png" style="float:right" width="50%"/>

RTC客户端默认情况下没有添加来自Eclipse.org的可用软件站点列表。通过下面的步骤可以完成添加。

* 打开RTC客户端，访问菜单：帮助(Help) -> 安装新软件(Install New Software)。
* 单机右侧添加(Add)按钮下方的可用软件站点(Available Software Sites)链接。打开可用软件站点管理设置项。
* 通过导入(Import)工具，打开附件提供的bookmarks.xml，导入Eclipse软件安装站点列表并保存设置后回到安装新软件(Install New Software)窗口。

> **注意！** 每个Eclipse发行版本的可用软件站点列表并不相同，请勿混用。

### 安装Java EE Development插件

<img src="/images/ilus/SelectPlugins.png" style="float:left" width="50%"/>

Java EE开发的主要插件在Eclipse Helios站点下，在安装新软件(Install New Software)窗口中选择使用下面的站点。

```
Helios - http://download.eclipse.org/releases/helios
```

获取可用软件列表需要一段时间，等待结束后将看到所有可用的软件列表。

Eclipse.org发行的Java EE Development版本包含了35个插件，均可以在此站点中找到并安装。这35个插件的详细信息请参阅附件中的Eclipse Java EE Plug-ins List文档。

参照文档选中这35个产插件进行安装，完成后重启RTC客户端即完成安装。

## 修改项目类型

在进行下面步骤时，我们假定你已经成功的在RTC中源码流中创建了组件并建立了本地存储库。

完成Java EE Development插件安装并建立本地存储库后将Eclipse切换至Java EE透视图。在此透视图中的“项目管理器”视图中可以看到我们创建了本地存储库的Eclipse项目。此时的Eclipse项目尚未不具备任何类型信息，不能用于开发。我们需要为其添加Project Facets来满足Java EE开发需要。

<img src="/images/ilus/ProjectProperties.png" style="float:right; width:40%;"/>

* 在“项目管理器”视图中右键单击选择属性(Properties)，打开项目属性信息窗口。
* 选择Project Facets属性。

> 第一访问Project Facets时会提醒：“当前项目尚未配置项目Facets，转换成配置Facets的项目后可以轻松控制项目可用的技术。”，此时单击“转换项目Facets”的链接即可打开Facets配置界面。

<img src="/images/ilus/SelectFacets.png" style="float:left; width:60%;"/>

* 将项目配置为Java EE项目前首先要将项目转换为Java项目。勾选Java并将版本选择为1.6后保存。之后再次勾选Dynamic Web Module版本3.0和JavaScript版本1.0，保存成功后项目项目类型即可转换为Java EE Web项目。
* 将修改后的项目提交到RTC服务器。



