---
title: AppsFlyer中的Steam对接配置说明
metadata:
  keywords:
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2022-11-06T08:13:09Z'
  edited_at: '2026-10-14T10:07:43Z'
  id: 10400222972433
  locale: zh-cn
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/zh-cn/articles/10400222972433
---
> **概要：**


<span id="about-vidaa-ctv-attribution"></span>在PC端运行的应用可以通过S2S API或SDK与AppsFlyer对接，从而获得归因数据和投放效果指标，了解应用打开和应用内事件的流量来源和带量广告。这些关键信息能够帮助营销人员评估并优化其市场推广工作。

* （即在用户的Xbox设备上进行归因和记录）。

<div id="integration-procedures" />

## 对接流程

下表列出了Steam应用对接到AppsFlyer时需要完成的工作。请下载这张Excel表，以便记录您的对接进度。

| 事项 | 可用操作 | 人员 |
| --- | --- | --- |
| 设置应用 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">创建一个AppsFlyer帐户</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/user-management">在账户下添加用户，并为其开放必要权限</Anchor></li></ul> | 营销人员 |
| 为您的应用配置API对接（通过S2S发送数据） | 在您的应用中<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">接入AppsFlyer API</Anchor>，使其向AppsFlyer上报下列事件：<ul><li>首次打开</li><li>应用内事件</li><li>应用打开（Sessions）</li></ul>**请注意**：<ul><li>应用首次打开（first open）必须在应用内事件和应用打开（session）之前上报。</li><li>通过该API发送事件。请向开发人员说明您需要发送的事件。 对于要发送到AppsFlyer的事件，请务必在配置API时完成这些事件的设置和映射。</li><li>使用参数时，请选择`device_ids`类型。</li></ul>如需上报自有媒体中的广告互动，请对接<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API。</Anchor> | 应用开发人员 |
| 链接设置 | 了解直接归因链接的创建方式 | 营销人员 |
| 报告设置/查看数据 | <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts#数据可用性">了解面板与报告中的数据可用性</Anchor> | 营销人员/数据工程师 |

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
|  | 即将更新 |
| 再营销 | 目前尚不支持 |
| 成本数据 | 必须使用<Anchor target="_blank" href="/marketers/zh/docs/import-cost-data">成本导入</Anchor>功能，通过邮件上传数据文件，以实现成本数据的发送。 |

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC和主机平台简介</Anchor>

<div data-zendesk-anchors="01H7Z180QRR77E1GBQ0P0RHVN5=about-vidaa-ctv-attribution integration-procedures=%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B 01H7Z180QR6HT4R3N9DYSM8WB9=%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B 01H7Z180QR0QQ0HK3N5N1G4ENZ=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
