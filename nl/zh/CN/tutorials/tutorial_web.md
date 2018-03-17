---

copyright:
  years: 2016, 2017
lastupdated: "2017-06-12"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Web 基本入门模板端到端教程
{: #tutorial}

以下端到端教程将引导您完成通过“Web 基本入门模板”创建项目的步骤。步骤包括安装必备工具以及如何运行项目代码。


## 安装开发者工具
{: #dev_tools}

确保安装[必备开发者工具 ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](get_code.html#prereq-dev-tools "外部链接图标"){: new_window}。


## 选择创建项目的方式
{: #choose_how}

您可以使用基于 Web 的 [{{site.data.keyword.dev_console}}](#create-devex) 或通过命令驱动的 [{{site.data.keyword.dev_cli_notm}}](#create-cli) 来创建项目。创建项目后，您可以[运行项目](#run)。


## 使用 {{site.data.keyword.dev_console}} 创建项目
{: #create-devex}

1. 在 {{site.data.keyword.Bluemix}} {{site.data.keyword.dev_console}} 中创建项目：

	1. 在 {{site.data.keyword.dev_console}} 中的[**入门** ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](https://console.ng.bluemix.net/developer/getting-started/ "外部链接图标") 页面中，单击**创建项目**。

		或者，您可以从**项目**页面单击**创建项目**。

	2. 选择 **Web 应用程序**并单击**下一步**。

	3. 选择**基本 Web** 并单击**下一步**。

	4. 输入项目名称。对于本教程，请使用 `WebBasicProject`。   

	5. 输入唯一主机名，如您的首字母缩写加 `-devhost`。例如：
	
	 ```
	 abc-devhost
	 ```

	6. 选择语言平台。对于本教程，请使用 `Swift`。
   
	7. 单击**创建**。

2. 可选：添加数据功能：

	1. 在**项目概述**页面上，针对**数据**单击**查看**。

      或者，可在**功能 > 数据**页面上选择**创建**或**添加现有项**。

   2. 输入服务名称并单击**创建**。

3. 生成项目代码：

	1. 单击**项目概述**页面上的**获取代码**，以选择语言。
   
		或者，您可以在**代码**页面上单击。
      
	2. 单击**生成代码**。
   
	3. 项目代码完成生成后，单击**下载代码**以下载项目归档。

4. 开始使用下载的项目：

	1. 解压缩归档文件。
	
	2. 浏览到新项目目录。
	
	3. 使用 {{site.data.keyword.dev_cli_notm}} 以继续。

5. 可选：[更新项目](project_overview_page.html#update_language)以生成新语言。


## 使用 {{site.data.keyword.dev_cli_notm}} 创建项目
{: #create-cli}

1. 确保安装 [{{site.data.keyword.dev_cli_short}}](dev_cli.html)。

2. 在“终端”提示符处，浏览到所选的本地目录并运行以下命令。
  
	```
	bx dev create
	```
	{: codeblock}

3. 在系统提示时提供以下值：

	* 选择模式：1 (Web)
	* 选择入门模板：1（“基本 Web”）
	* 选择语言：2 (Swift)
	* 输入项目的名称：`WebBasicProjectCLI`
	* 输入项目的主机名：`abc-devhost`
	  * 输入唯一主机名，如您的首字母缩写加 `-devhost`。例如：
	
	     ```
	     abc-devhost
	     ```

4. 成功保存 `WebBasicProjectCLI` 项目后，浏览到 `WebBasicProjectCLI` 文件夹。

5. 添加您自己的代码、构建项目，然后运行项目。
	
	1. 使用以下命令构建项目：
 
		```
		bx dev build
	```
		{: codeblock}
	 
	2. 使用以下命令运行项目：
 
		```
		bx dev run
		```
		{: codeblock}


## 运行 Web 项目
{: #run}

如果您安装了必要构建工具，那么您可以在主机系统上本地运行应用程序，或者使用 {{site.data.keyword.dev_cli_notm}} 中可用的容器支持。


### 使用 {{site.data.keyword.dev_cli_short}}
{: #dev notoc}

1. 安装节点依赖关系：

  ```
  npm install
  ```
  {: codeblock}

2. 将前端代码绑定到模块：

  ```
  gulp
  ```
  {: codeblock}

3. 要在当前项目目录中构建项目，请输入以下命令：

  ```
bx dev build
```
  {: codeblock}

4. 要在当前项目目录中运行项目，请输入以下命令：

  ```
  bx dev run
  ```
  {: codeblock}

5. 在浏览器中打开 `http://localhost:8080`。


## 在 Xcode 中运行项目
{: #Xcode}

1. 创建 Xcode 项目。

	需要先使用 Swift 软件包管理器构建 Xcode 项目，然后才能使用 Xcode 进行开发。
	
	```
	swift project generate-xcodeproj
	```
	{: codeblock}

2. 将活动目标更改为可执行对象：

	然后，在 Xcode 中打开项目，确保活动目标可执行。您可以按住 option 键并单击下拉菜单，以选择所需的活动可执行对象。

3. 按**运行**。

4. 在浏览器中打开 `http://localhost:8080`。

