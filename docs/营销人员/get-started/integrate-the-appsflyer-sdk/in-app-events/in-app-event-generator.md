---
title: 应用内事件生成器
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-08T12:47:30Z'
  edited_at: '2026-10-14T10:12:07Z'
  id: 10457123447953
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/10457123447953
---
> **概要：** 概要：本文介绍了如何使用应用内事件生成器来自动生成应用代码（安卓和iOS原生代码以及Unity代码），根据您的业务需求定义相关事件的名称和内容，用于应用内事件的发送。

<div id="introduction" />

## 简介

应用内事件可衡量应用激活后的用户行为，是**广告主评估各渠道用户质量**的主要途径，常用于CPA营销推广中。

但应用内事件的定义和接入通常需要涉及到多方人员。市场人员/产品经理会根据业务需求定义事件内容，而应用内事件API在应用中的部署则通常需要一个或多个移动端开发人员的参与。

AppsFlyer的<Anchor target="_blank" href="https://evgen.appsflyer.com/">应用内事件生成器</Anchor>**正可以帮助市场和开发人员解决这类必要协作中所存在的一些固有难题**。

市场人员可以通过应用内事件生成器完成以下工作：

* 使用分垂类的预定义**推荐事件组合**和参数。
* 添加或移除预定义或自定义事件/参数、描述说明、触发机制以及参考示例。
* 将**自动生成的代码发送**给相关的安卓和iOS移动端开发人员——**这可以节省数天的工作量，避免无效沟通和潜在坑点。**
* **重复利用工作成果**，应对后续的事件更新和新增，以及新应用的需求。

<div id="using-the-in-app-event-generator" />

## 应用内事件生成器的使用方法

您使用应用内事件生成器为新应用创建事件或更新现有的事件组合。

<div id="creating-a-new-event-set" />

### 创建新的事件组合

**请按以下方式创建新的事件组合：**

1. 进入<Anchor target="_blank" href="https://evgen.appsflyer.com/">应用内事件生成器</Anchor>并输入相关应用的名称。
2. 选择一个垂类或导入同类应用的事件组合（需事先导出到JSON文件）。
3. 根据您的业务需求添加或移除事件和参数。
5. 点击**下载zip文件**，将事件组合保存下来，以备后用，或同步给开发等人员，以便协调工作。

<div id="updating-an-existing-event-set" />

### 更新现有的事件组合

**请按以下方式更新现有的事件组合：**

1. 进入<Anchor target="_blank" href="https://evgen.appsflyer.com/">应用内事件生成器</Anchor>。
2. 导入您事先导出到JSON文件的相关应用事件组合。
3. 根据您的业务需求添加或移除事件和参数。
5. 点击**下载zip文件**，将事件组合保存下来，以备后用，或同步给开发等人员，以便协调工作。

<div id="adding-events" />

### 添加事件

**请按以下方式在事件组合中添加新的事件：**

3. 输入该事件的目的并描述相关的业务场景。
4. 输入该事件的触发操作，说明该事件用户链路中的发送节点。我们会将这部分说明以备注的形式添加到生成的代码中，便于开发人员参考。
5. 【可选】在该事件中添加一个或多个参数。

<div id="adding-parameters" />

### 添加参数

**请按以下方式在相关事件组合中添加新的参数：**

1. 点击相关事件的 **+ 添加参数**按钮。
2. 从推荐参数列表中选择一个**预定义**参数。
3. 您也可以点击**自定义**按钮，设定您专属的参数名称，然后按**回车**。
4. 输入一个或多个典型参数值作为参考。
5. 输入简要介绍、字段类型或应用中参数值的来源，便于开发人员理解。这部分说明会以备注的形式呈现在生成的代码中。

**请注意**：请注意：<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#predefined-and-custom-events">预定义名称</Anchor>/span>支持事件和参数的自动映射，这也是我们推荐的映射方式。

<div id="see-also" />

> 📄 **相关文档**
>
> * 事件面板

<div data-zendesk-anchors="introduction=%E7%AE%80%E4%BB%8B h_01HE7T0ZA12E7KHS7WBQ757KF1=%E7%AE%80%E4%BB%8B using-the-inapp-event-generator=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%94%9F%E6%88%90%E5%99%A8%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95 h_01HE7T0ZA2A1KS4NF43GRZB87X=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%94%9F%E6%88%90%E5%99%A8%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95 creating-a-new-event-set=%E5%88%9B%E5%BB%BA%E6%96%B0%E7%9A%84%E4%BA%8B%E4%BB%B6%E7%BB%84%E5%90%88 h_01HE7T0ZA2KQ44P40Y028VVA4K=%E5%88%9B%E5%BB%BA%E6%96%B0%E7%9A%84%E4%BA%8B%E4%BB%B6%E7%BB%84%E5%90%88 updating-an-existing-event-set=%E6%9B%B4%E6%96%B0%E7%8E%B0%E6%9C%89%E7%9A%84%E4%BA%8B%E4%BB%B6%E7%BB%84%E5%90%88 h_01HE7T0ZA2P2WZ07CT880ZSK0Z=%E6%9B%B4%E6%96%B0%E7%8E%B0%E6%9C%89%E7%9A%84%E4%BA%8B%E4%BB%B6%E7%BB%84%E5%90%88 adding-events=%E6%B7%BB%E5%8A%A0%E4%BA%8B%E4%BB%B6 h_01HE7T0ZA2Z3D3J014E7E0T13X=%E6%B7%BB%E5%8A%A0%E4%BA%8B%E4%BB%B6 adding-parameters=%E6%B7%BB%E5%8A%A0%E5%8F%82%E6%95%B0 h_01HE7T0ZA2KAH7N44EQ9W5BH5G=%E6%B7%BB%E5%8A%A0%E5%8F%82%E6%95%B0 h_01HE7T4ZR4AY2J71B3PJKJP490=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
