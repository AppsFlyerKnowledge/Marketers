---
title: 基于用户的归因（PBA）Google Analytics
metadata:
  keywords:
    - Google Analytics
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-03-28T07:22:04Z'
  edited_at: '2026-10-14T10:00:06Z'
  id: 360001305617
  locale: zh-cn
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001305617
---
> **概要：**


* <span id="pba-compared-to-google-analytics"></span>PBA是一个独立的，公正的归因机构，专注于归因评估。PBA将转化和收入归因于将用户吸引到您的网站的媒体来源和广告系列。

<div id="benefits-of-pba-over-google-analytics" />

### 与Google Analytics（分析）相比，PBA的优势

以下是PBA相对于Google Analytics（分析）的优势：

* * H3 ：网页至应用的衡量方案

<div id="reasons-for-differences" />

### 差异的原因

如果您比较PBA和Google Analytics（分析）中的数据，请参阅以下数据差异原因。

<div id="sdk-implementation" />

#### SDK 安装

实施PBA和Google Analytics（分析）的方式可能会影响数据收集。

<div id="google-analytics-shows-more-sessions-and-visitors" />

<Accordion title="Google Analytics（分析）显示了更多的会话和访问者">

<div id="cause" />

#### 原因

如果Google Analytics（分析）在Web SDK反弹的用户或在您的网站上停留时间短的用户之前加载，则不会计入PBA。这会导致会话和访问者的数据不一致。

<div id="solution" />

#### 解决方法

强烈建议放置Web SDK，以使其尽早加载。

</Accordion>

<div id="google-analytics-shows-more-data-for-sessions-campaign-and-conversions" />

<Accordion title="Google Analytics（分析）显示有关会话，广告系列和转化的更多数据">

<div id="cause-1" />

#### 原因

Web SDK仅在某些页面上存在。所有页面上都存在Google Analytics（分析）。结果，Google Analytics（分析）从您的整个网站收集数据，而Web SDK仅从某些页面收集数据。这会导致会话，访问者，广告系列和转化的数据出现差异。

<div id="solution-1" />

#### 解决方法

在网站的所有页面上实施Web SDK。

</Accordion>

<div id="dashboard-settings" />

### 资讯主页设定

<div id="timezone-settings-discrepancies-in-data" />

<Accordion title="时区设置-数据差异">

<div id="cause-2" />

#### 原因

如果Google Analytics的时区设置与PBA面板的时区设置不同，则可能会出现差异。

> 📄 **示例**
>
> 假设AppsFlyer后台设置为UTC时区，而GA后台设置为UTC +13时区。这意味着GA面板比AppsFlyer面板领先一天。
>
> 因此，在GA面板选择3月3日，实际上对应的是AppsFlyer面板上3月2日的数据。

<div id="solution-2" />

#### 解决方法

确保AppsFlyer和Google Analytics的时区设置相同。

</Accordion>

<div id="data-filters--discrepancies-in-data" />

<Accordion title="数据筛选-数据差异">

<div id="issue" />

#### 问题

AppsFlyer和Google Analytics都可以根据日期、归因媒体渠道、广告系列和事件来筛选数据。同一组数据在不同的筛选条件下会呈现不同的视图。

<div id="solution-3" />

#### 解决方法

当比较两个后台的数据时，请确保没有对数据进行筛选。

</Accordion>

<div id="conversions-and-events" />

### 转化和事件

归因模型、回溯窗口期、事件发送方式以及cookie设置不同都会影响数据的收集和处理。

<div id="lookback-window-discrepancies-in-conversion-measurement" />

<Accordion title="回溯窗口期-转化率测量中的差异">

<div id="cause-3" />

#### 原因

如果您在Google Analytics和PBA中使用不同的回溯窗口期，则归因数据可能会出现差异。

<div id="solution-4" />

#### 解决方法

PBA的回溯窗口期始终为30天。当您在Google Analytics中<Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189">选择归因模型</Anchor>时，请确保回溯窗口期设置为30天。

</Accordion>

<div id="attribution-model--discrepancies-in-conversion-measurement" />

<Accordion title="归因模型-转化计量中的差异">

<div id="cause-4" />

#### 原因

PBA和Google Analytics采用不同归因模型也可能会导致归因数据出现差异。

<div id="solution-5" />

#### 解决方法

Google Analytics有多种<Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189?hl=en">默认归因模型</Anchor> 供您选择。PBA的归因模型是30天回溯窗口期内的最后一次非直接接触。确保在Google Analytics中选择一个以最后一次非直接接触为准的归因模型。

</Accordion>

<div id="sending-events" />

<Accordion title="发送事件">

<div id="issue-1" />

#### 问题

Google Analytics SDK和Web SDK均支持发送事件。如果以一种逻辑将事件发送给Google Analytics，又以另一种逻辑将事件发送给PBA，则可能会出现差异。

<div id="solution-6" />

#### 解决方法

发送事件时，请确认以下内容：

* 确保两个平台的事件触发机制相同
* 确保将事件同时发送到Google Analytics和PBA

单击<Anchor target="_blank" href="/marketers/zh/docs/pba-web-sdk-integration-guide#事件记录原则">这里</Anchor>了解如何使用Web SDK发送事件。

</Accordion>

<div id="cookies" />

<Accordion title="Cookies">

PBA和Google Analytics均使用Cookies来识别用户。

<div id="cookie-settings-in-google-analytics" />

#### Google Analytics中的Cookie设置

一般建议让Google Analytics SDK自动处理Cookie设置，但是您仍然可以<Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/analyticsjs/cookies-user-id">配置和更改Cookie设置</Anchor> 。Cookie设置的任何变动都可能导致差异。

<div id="setting-cookie-expiration" />

#### 设置Cookie期限

Google Analytics支持设置Cookie有效期。如果Google Analytics的cookie有效期在Web SDK cookie有效期之前，则可能会导致差异。

> 📄 **示例**
>
> Mark一年多来一直是您网站的常客，并考虑订阅高级内容。
>
> 如果开发人员将Google Analytics的Cookie设置为一年后过期。但是，Web SDK将cookie设置为两年后过期。
>
> 当Mark最终订阅并记录为转化后，Google Analytics的Cookie不再有效，而是设置了另一个Cookie。
>
> 最终结果是Google Analytics显示为两个用户，尽管他们两个都是Mark，却只有一个转化与之关联。但是，PBA会显示一个名为Mark的用户，并把该转化与之关联。
>
> 这意味着Google Analytics的转化率低于PBA的转化率。

<div id="setting-cookie-subdomain" />

#### 设置Cookie子域名

Google Analytics允许您为子域名设置cookie，而PBA仅在顶级域名上设置cookie。

> 📄 **示例**
>
> 假设您给子域名**store.mywebsite.com**设置了一个Cookie 。Sharon访问您的网站，然后前往位于**store.mywebsite.com**的网店。Google Analytics将其**视为两个不同的用户** 。
>
> 由于PBA仅在顶级域名**mywebsite.com**上设置cookie，它将**mywebsite.com**和**store.mywebsite.com**中的Sharon视为同一用户。
>
> 最终结果是Google Analytics中有两个用户，PBA中有一个用户。

</Accordion>

<div data-zendesk-anchors="benefits-of-pba-over-google-analytics=%E4%B8%8Egoogle-analytics%E5%88%86%E6%9E%90%E7%9B%B8%E6%AF%94pba%E7%9A%84%E4%BC%98%E5%8A%BF reasons-for-differences=%E5%B7%AE%E5%BC%82%E7%9A%84%E5%8E%9F%E5%9B%A0 sdk-implementation=sdk-%E5%AE%89%E8%A3%85 cause=%E5%8E%9F%E5%9B%A0 solution=%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95 cause::49d3e519=%E5%8E%9F%E5%9B%A0-1 solution::447e7ac9=%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95-1 dashboard-settings=%E8%B5%84%E8%AE%AF%E4%B8%BB%E9%A1%B5%E8%AE%BE%E5%AE%9A cause::30244d2c=%E5%8E%9F%E5%9B%A0-2 solution::f1a0e066=%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95-2 data-filters-%C2%A0discrepancies-in-data=data-filters--discrepancies-in-data issue=%E9%97%AE%E9%A2%98 solution::df8f3921=%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95-3 conversions-and-events=%E8%BD%AC%E5%8C%96%E5%92%8C%E4%BA%8B%E4%BB%B6 cause::b346571c=%E5%8E%9F%E5%9B%A0-3 solution::4bb14ac9=%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95-4 attribution-model%C2%A0-discrepancies-in-conversion-measurement=attribution-model--discrepancies-in-conversion-measurement cause::2296f6c1=%E5%8E%9F%E5%9B%A0-4 solution::b2be4a33=%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95-5 issue::b412f5ba=%E9%97%AE%E9%A2%98-1 solution::39b4d7d6=%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95-6 cookie-settings-in-google-analytics=google-analytics%E4%B8%AD%E7%9A%84cookie%E8%AE%BE%E7%BD%AE setting-cookie-expiration=%E8%AE%BE%E7%BD%AEcookie%E6%9C%9F%E9%99%90 setting-cookie-subdomain=%E8%AE%BE%E7%BD%AEcookie%E5%AD%90%E5%9F%9F%E5%90%8D" />
