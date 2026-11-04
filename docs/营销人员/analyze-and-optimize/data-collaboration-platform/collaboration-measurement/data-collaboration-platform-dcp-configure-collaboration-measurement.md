---
title: 数据协作平台（DCP） - 协作衡量 - 概览
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2025-01-27T09:58:46Z'
  edited_at: '2026-10-14T10:15:47Z'
  id: 32147174933905
  locale: zh-cn
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/zh-cn/articles/32147174933905
---
**概要：** 学习如何配置DCP以根据转化、参与和活动映射数据执行SKU级归因。

<div id="overview" />

## 速览

在<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement">准备转化、参与和活动映射</Anchor>数据后，您可以配置DCP以使用它们进行测量和归因：

1. [**定义活动类型**](#选择活动类型现场非现场或两者) – 选择现场、非现场或组合。这决定了DCP如何处理您的数据并设置所需的配置任务。
2. [**分配任务**](#分配配置任务) – 拥有者将每个配置任务分配给具有相关数据访问权限的合作者。
3. [**配置任务**](#站内与站外广告系列归因) – 合作者配置转化、参与和活动映射。这包括设置现场和非现场活动，以便所有数据都连接、映射并准备好进行归因。
4. <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-run-and-manage-measurement">**运行和管理测量**</Anchor> - 运行实时或历史测量，复制它们，重新运行它们或更改其范围。

<div id="start-the-measurement-setup" />

## 开始测量设置

要开始测量设置，请按照以下步骤操作：

1. 在AppsFlyer中，从侧边菜单转到**协作**> **数据清理室**。
2. 在**数据协作平台**页面上，选择您要设置的协作。
3. 在协作页面上，执行**以下其中一步**：
   * 如果这是您在协作中设置的第一个测量，请单击<strong>设置测量。</strong>将显示**创建测量**页面。
   * 如果您在协作中已经有一个测量，请单击测量选择面板中的加号。将显示**创建测量**页面。

[![start-measurement.png](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)

<div id="select-campaign-type-on-site-off-site-or-both" />

## 选择活动类型：现场、非现场或两者。

由于现场和非现场活动类型在转化发生的位置和归因处理方式上有所不同，因此协作拥有者必须在配置协作测量之前指定活动类型。详情请见：<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaign-measurement">现场与。站外活动测量</Anchor>。

要选择活动类型，请按照以下步骤操作：

1. [开始测量设置](#开始测量设置)。
2. 在**创建测量**页面上，选择<Image alt="现场图标.png" src="https://files.readme.io/c9ff0bb1e2c31527ee38a9403a6180e3ecd4c3ad105935fb59ed14c2474f6039-32148924980113.png" width="3.27%" /> **现场, <Image alt="离线图标.png" src="https://files.readme.io/6de5841985237de221c74d427ad06f719572000aafe8077c7cef64e53ee8caf5-32156666763921.png" width="3.3%" /> 离线**，或两者。继续进行**以下之一**：
   * [配置现场活动](#站内与站外广告系列归因)，
   * [配置离线活动](#configure-offsite-campaign-measurement)，
   * [配置结合现场和离线活动](#configure-combined-onsite-and-offsite-campaign-measurement)。

<div id="assign-configuration-task" />

## 分配配置任务

测量设置页面包括五个关键任务：转化、参与、活动映射、媒体合作伙伴和回溯窗口配置。

DCP账户所有者可以将任务分配给合作者，以确保数据隐私并反映责任的分配。例如，一位合作者可能处理参与数据，而另一位合作者处理转化。合作者仅能访问分配给他们的任务。

<div id="assign-a-configuration-task-to-a-collaborator" />

<Accordion title="将配置任务分配给合作者">

要分配上述任何任务，请按照以下步骤操作：

1. [打开测量设置](#开始测量设置)。
2. 在上述四个任务中，从**受托人**列表中选择将处理该任务的合作者。
   * **转化任务：** 分配给托管转化的平台的合作者。
   * **活动任务：** 将任务分配给托管转换的合作者。
   * **参与任务:** 将任务分配给用户参与发生的合作者。
   * **媒体合作伙伴任务:** 将任务分配给用于外部活动的媒体合作伙伴账户的合作者。
   * **回顾窗口任务**– 自动分配给协作所有者。您可以选择性地分配其他合作者。

</Accordion>

<div id="remove-the-configuration-task-assignment-from-a-collaborator" />

<Accordion title="从合作者中移除配置任务分配。">

在某些情况下，可能需要撤销合作者的配置任务分配。当协作所有者移除分配时，会发生以下情况：

* 合作者立即失去对未分配任务的访问权限。
* 合作者之前为该任务提供的任何配置将被丢弃。
* 协作测量停止。

要移除配置任务分配，请按照以下步骤操作：

1. 转到协作测量，查看打开测量设置。
2. 在相关配置步骤中，从**受托人**列表中移除已分配的合作者。

</Accordion>

<div id="configure-on-site-and-off-site-campaign-measurement" />

## 站内与站外广告系列归因

在测量设置中配置活动测量设置。根据您的测量是现场、外部还是结合现场和外部设置，使用以下步骤。

<div id="configure-onsite-campaign-measurement::4f9b35af" />

<Accordion title="配置现场活动测量。">

要设置<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-campaigns">现场活动</Anchor>，请按照以下步骤操作：

1. [开始测量设置](#开始测量设置)。
2. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-campaigns-task">设置广告活动任务</Anchor>
3. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-conversions-task">设置转化任务</Anchor>
4. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-engagements-task">设置互动任务</Anchor>
5. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-lookback-windows-task">设置回溯窗口任务</Anchor>

</Accordion>

<div id="configure-offsite-campaign-measurement" />

<Accordion title="配置站外广告活动测量">

要设置一个<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">站外广告活动</Anchor>，请按照以下步骤进行：

1. [开始测量设置](#开始测量设置)。
2. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-campaigns-task">设置广告活动任务</Anchor>
3. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-conversions-task">设置转化任务</Anchor>
4. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-media-partners-task">设置媒体合作伙伴任务</Anchor>
5. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-lookback-windows-task">设置回溯窗口任务</Anchor>

</Accordion>

<div id="configure-combined-onsite-and-offsite-campaign-measurement" />

<Accordion title="配置综合的站内和站外广告活动测量">

要设置一个<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">综合的站内和站外广告活动</Anchor>，请按照以下步骤进行：

1. [开始测量设置](#开始测量设置)。
2. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-campaigns-task">设置广告活动任务</Anchor>
3. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-conversions-task">设置转化任务</Anchor>
4. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-engagements-task">设置互动任务</Anchor>
5. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-media-partners-task">设置媒体合作伙伴任务</Anchor>
6. <Anchor target="_blank" href="/marketers/zh/docs/set-up-the-lookback-windows-task">设置回溯窗口任务</Anchor>

</Accordion>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01K3EHANCCZ703MMMM5PTEF68B=%E9%80%9F%E8%A7%88 open-measurement-settings=%E5%BC%80%E5%A7%8B%E6%B5%8B%E9%87%8F%E8%AE%BE%E7%BD%AE h_01JJKK3CQ8F9Q7VM7MM9AFKNN5=%E5%BC%80%E5%A7%8B%E6%B5%8B%E9%87%8F%E8%AE%BE%E7%BD%AE select-campaign-type-onsite-offsite-or-both=%E9%80%89%E6%8B%A9%E6%B4%BB%E5%8A%A8%E7%B1%BB%E5%9E%8B%E7%8E%B0%E5%9C%BA%E9%9D%9E%E7%8E%B0%E5%9C%BA%E6%88%96%E4%B8%A4%E8%80%85 h_01K3EHANCCW8PQ8NWC6ZHWCMGT=%E9%80%89%E6%8B%A9%E6%B4%BB%E5%8A%A8%E7%B1%BB%E5%9E%8B%E7%8E%B0%E5%9C%BA%E9%9D%9E%E7%8E%B0%E5%9C%BA%E6%88%96%E4%B8%A4%E8%80%85 assign-configuration-task=%E5%88%86%E9%85%8D%E9%85%8D%E7%BD%AE%E4%BB%BB%E5%8A%A1 h_01K3EHANCCW97TV88ECVMQKF2N=%E5%88%86%E9%85%8D%E9%85%8D%E7%BD%AE%E4%BB%BB%E5%8A%A1 h_01K3EHANCD71R47V88DR61CTMV=assign-a-configuration-task-to-a-collaborator h_01K3EHANCDF1HMTV8X35Q1RHTS=remove-the-configuration-task-assignment-from-a-collaborator configure-onsite-campaign-measurement=%E7%AB%99%E5%86%85%E4%B8%8E%E7%AB%99%E5%A4%96%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E5%BD%92%E5%9B%A0 h_01K3EHANCD936QN2MKFY5QSDBZ=%E7%AB%99%E5%86%85%E4%B8%8E%E7%AB%99%E5%A4%96%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E5%BD%92%E5%9B%A0 h_01KJWCMN3XRTS3361N08RT1SD6=configure-onsite-campaign-measurement::4f9b35af h_01KJWCMN3XRXW6A71P5678AHH1=configure-offsite-campaign-measurement h_01KJWCMN3XKD8YJVPQEZ53K819=configure-combined-onsite-and-offsite-campaign-measurement" />
