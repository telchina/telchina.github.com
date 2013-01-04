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

<img src="ilus/AddSoftwareSite.png" style="float:right" width="50%"/>

RTC客户端默认情况下没有添加来自Eclipse.org的可用软件站点列表。通过下面的步骤可以完成添加。

* 打开RTC客户端，访问菜单：帮助(Help) -> 安装新软件(Install New Software)。
* 单机右侧添加(Add)按钮下方的可用软件站点(Available Software Sites)链接。打开可用软件站点管理设置项。
* 将附件中给出的bookmarks.xml文件源码复制到一个文本文件中，并保存为`bookmarks.xml`。通过导入(Import)工具，打开bookmarks.xml，导入Eclipse软件安装站点列表并保存设置后回到安装新软件(Install New Software)窗口。

> **注意！** 每个Eclipse发行版本的可用软件站点列表并不相同，请勿混用。

### 安装Java EE Development插件

<img src="/images/ilus/SelectPlugins.png" style="float:left" width="50%"/>

Java EE开发的主要插件在Eclipse Helios站点下，在安装新软件(Install New Software)窗口中选择使用下面的站点。

```
Helios - http://download.eclipse.org/releases/helios
```

获取可用软件列表需要一段时间，等待结束后将看到所有可用的软件列表。

Eclipse.org发行的Java EE Development版本包含了35个插件，均可以在此站点中找到并安装。这35个插件的详细信息请参阅附件中的Eclipse Java EE Plug-ins 列表。

参照文档选中这35个产插件进行安装，完成后重启RTC客户端即完成安装。

## 修改项目类型

在进行下面步骤时，我们假定你已经成功的在RTC中源码流中创建了组件并建立了本地存储库。

完成Java EE Development插件安装并建立本地存储库后将Eclipse切换至Java EE透视图。在此透视图中的“项目管理器”视图中可以看到我们创建了本地存储库的Eclipse项目。此时的Eclipse项目尚未不具备任何类型信息，不能用于开发。我们需要为其添加Project Facets来满足Java EE开发需要。

<img src="/images/ilus/ProjectProperties.png" style="float:right; width:50%;"/>

* 在“项目管理器”视图中右键单击选择属性(Properties)，打开项目属性信息窗口。
* 选择Project Facets属性。

> 第一访问Project Facets时会提醒：“当前项目尚未配置项目Facets，转换成配置Facets的项目后可以轻松控制项目可用的技术。”，此时单击“转换项目Facets”的链接即可打开Facets配置界面。

<img src="/images/ilus/SelectFacets.png" style="float:left; width:50%;"/>

* 将项目配置为Java EE项目前首先要将项目转换为Java项目。勾选Java并将版本选择为1.6后保存。之后再次勾选Dynamic Web Module版本3.0和JavaScript版本1.0，保存成功后项目项目类型即可转换为Java EE Web项目。

> 在这里你还可是试着添加其他的项目能力。比如添加Axis支持Web Service开发。添加JPA支持等等。

* 将修改后的项目可以Check in and Deliver提交到RTC服务器。

## 附件

### bookmark.xml

```
<?xml version="1.0" encoding="UTF-8"?>
<bookmarks>
   <site url="http://download.eclipse.org/releases/helios" selected="true" name="Helios"/>
   <site url="http://download.eclipse.org/tools/mylyn/update/helios" selected="true" name="Mylyn for Eclipse Helios"/>
   <site url="http://download.eclipse.org/eclipse/updates/3.6" selected="true" name="The Eclipse Project Updates"/>
   <site url="http://download.eclipse.org/webtools/repository/helios" selected="true" name="The Eclipse Web Tools Platform (WTP) software repository"/>
</bookmarks>

```

### Eclipse Java EE Plug-ins List

* sCollaboration    
    * Eclipse CVS Client	1.2.1.r362_v20101111-7B77FKv99HL0GvIAF99I8H14B7E
    * Mylyn Bridge: Eclipse IDE	3.4.3.v20110131-0100-e3x-7G7J5BgJ9EC9QKN49E997JSm
    * Mylyn Bridge: Java Development	3.4.3.v20110131-0100-e3x-7D7F-AkF7B77V7c37B775eMp
    * Mylyn Bridge: Team Support	3.4.3.v20110131-0200-e3x-4327w31221242012110f4y
    * Mylyn Connector: Bugzilla	3.4.3.v20110131-0100-e3x-7D774BgJ9DI9YFV4CICE2KAv
    * Mylyn Task List (Required)	3.4.3.v20110131-0100-e3x-7Z7f7AFBBoPbVQ7iNFebXJDypa
    * Mylyn Task-Focused Interface (Recommended)	3.4.3.v20110131-0100-e3x-777728s73543D6D135332KAv
    * Mylyn WikiText	1.3.2.v20100916-0100-e3x-7F7e1FC7sReRSnX-DReRRMHHM
* General Purpose Tools
    * Eclipse Plug-in Development Environment	3.6.2.r362_v20110203-7b7mFL2FET3dhHalh1iNZtL
    * Marketplace Client	1.0.1.v20100826-2143
    * Remote System Explorer End-User Runtime	3.2.2.R32x_v201102130925-7L78FA58SreKCHr_JG7UA8bra19p
    * Remote System Explorer User Actions	1.1.200.v201005221100-31A78s733L3D7H7933
    * Usage Data Collector	1.3.1.R201102081640
* Programming Languages
    * Eclipse Java Development Tools	3.6.2.r362_v20101117-0800-7z8XFW6FLFlmjJcvz03jyeFBLS_F
    * Eclipse XML Editors and Tools	3.2.3.v201102160550-7H7AFUWDxumQJOi9ghcTb5YgkwEZ
    * JavaScript Development Tools	1.2.3.v201102160540-7C78FGUF9JgLWNO2UCNqfa
* Web, XML, and Java EE Development
    * Apache MyFaces Trinidad Tag Support (Optional)	2.2.101.v20100906-208_7w31211A17
    * Axis2 Tools	1.1.100.v201005241530-78-FF0DZRDKDDePSKwHj
    * CXF Web Services	1.0.2.v201008232129-7H777DFAKlRiOX8lGdRoz0878J
    * Dali Java Persistence Tools	2.3.3.v201010220000-7N7UF77FD3wTgcVbmmf0cT
    * Dali Java Persistence Tools - EclipseLink Support (Optional)	2.3.3.v201102072310-7778BkBgJ9EA9VGcDFBA
    * Eclipse Faceted Project Framework	3.2.3.v201101121727-377AC8s73543C6H4A5H
    * Eclipse Faceted Project Framework JDT Enablement	3.2.2.v201008170019-377AB8s73533J5J759F
    * Eclipse Java EE Developer Tools	3.2.3.v201011031800-7b7GHfIFSK2WBRT6E1mcyFXGPnSh
    * Eclipse Web Developer Tools	3.2.3.v201102160541-7O7CFbWEMf84qYjGDyP3DNEwcgFU
    * Eclipse XSL Developer Tools	1.1.3.v201102102045-7S7WFASFIpS-21NUD58xfPVDTLR
    * JavaServer Faces Tools (JSF) Project	3.2.3.v201101112207-7E7I7BF9JgLWPMz0VyDEHH
    * JAX-WS DOM Tools	1.0.0.v201005241530-5--AkF7B77NBZBgBg
    * JAX-WS Tools	1.0.1.v201008232129-7E777CF8NcJSSK-UBTwXn
    * JST Server Adapters	3.2.3.v20110111-777HFGSCcNBDjBdHV4BA8
    * JST Server Adapters	3.2.0.v201005241530-208Z7w31211419
    * JST Server UI	3.2.2.v20100908-7A5FEi9xFc7RCJMToAIOJC43A
    * JST Web UI	3.2.3.v201101262333-7F77FJ_C25TkfyypjhqQuxNYsMrJ
    * Web Page Editor (Optional)	2.3.2.v201101112207-4619oB5865D8I2331
    * WST Server Adapters	3.2.0.v201005241510-51EoAkF77g8HBSc 	