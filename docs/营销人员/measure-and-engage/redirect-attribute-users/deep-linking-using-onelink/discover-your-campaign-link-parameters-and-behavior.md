---
title: 解析广告链接参数和行为
metadata:
  keywords:
    - Marketers
    - discover
    - Social-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Social-to-App
  created_at: '2023-07-03T11:56:14Z'
  edited_at: '2026-10-14T10:12:47Z'
  id: 16678138044689
  locale: zh-cn
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/zh-cn/articles/16678138044689
---
> **概要：** 通过解析AppsFlyer广告链接中所包含的参数，了解该链接可实现的用户体验和链接行为。

## 关于链接解析

链接解析（Link Discovery）功能可帮助您查看AppsFlyer广告链接的相关信息，包括链接参数以及可实现的用户体验。

### 优势

链接解析（Link Discovery）页面可以帮助广告主：

* 深入理解链接的含义和行为。
* 更有效地与负责创建链接的团队沟通需求。
* 确认链接的详细信息后再投入使用。
* 排查反常的链接行为。
* 了解归因参数，更有针对性地查看面板数据。

### 链接解析（Link Discovery）页面中的可用信息

您可以通过链接解析（Link Discovery）页面查看某条具体链接的下列信息：

* **基本信息**：包括该链接所属的应用、链接来源（OneLink管理页或API）、创建该链接时使用的OneLink模板以及该链接的失效日期和续期时长。
* **参数**：**参数**：分类显示该链接中所包含的各种参数以及对应的参数值。   
  **请注意：** 如跳转至未<Anchor target="_blank" href="/marketers/zh/docs/set-up-your-domain-redirect-allowlist">加入白名单</Anchor>的域名，则系统将出现警报。
* **功能**：该链接中配置的各种功能，如再营销、深度链接、社交媒体预览以及社交媒体落地页等。
* **跳转**：简要说明该链接的跳转逻辑，即如何根据用户的设备、操作平台即相关应用激活状态等跳转到对应的终点。

## 链接解析（Link Discovery）的用法

**使用链接解析（Link Discovery）页面获取具体链接信息的方法如下：**

1. 从AppsFlyer后台的侧边栏中选择**互动** > **链接解析**。
2. 输入链接，并点击**解析**。

## 特点与局限性

| 维度 | 说明 |
| --- | --- |
| 可解析的链接 | <ul><li>通过AppsFlyer平台创建的短链或长链，包括单平台和多平台的OneLink链接。</li><li>在AppsFlyer面板中创建的链接，包括通过API、SDK和批量创建的链接。</li><li>带有品牌域名的链接。</li></ul> |
| 代理 | 不支持 |
| 广告平台 | 不支持 |
| 展示链接 | 不支持 |
| 跨平台链接 | 不支持 |

<div data-zendesk-anchors="what-is-app-attribution=%E5%85%B3%E4%BA%8E%E9%93%BE%E6%8E%A5%E8%A7%A3%E6%9E%90 h_01HKW0CMGXXFKEY7W0NCN1SH76=%E5%85%B3%E4%BA%8E%E9%93%BE%E6%8E%A5%E8%A7%A3%E6%9E%90 benefits=%E4%BC%98%E5%8A%BF h_01HKW0CMGXEAYPDFMR4QCS9F52=%E4%BC%98%E5%8A%BF information-available-via-link-discovery=%E9%93%BE%E6%8E%A5%E8%A7%A3%E6%9E%90link-discovery%E9%A1%B5%E9%9D%A2%E4%B8%AD%E7%9A%84%E5%8F%AF%E7%94%A8%E4%BF%A1%E6%81%AF h_01HKW0CMGXHZ2NYP6YVPW6QNX3=%E9%93%BE%E6%8E%A5%E8%A7%A3%E6%9E%90link-discovery%E9%A1%B5%E9%9D%A2%E4%B8%AD%E7%9A%84%E5%8F%AF%E7%94%A8%E4%BF%A1%E6%81%AF using-link-discovery=%E9%93%BE%E6%8E%A5%E8%A7%A3%E6%9E%90link-discovery%E7%9A%84%E7%94%A8%E6%B3%95 h_01HKW0CMGXD4Z0J7CCKJFZNVCG=%E9%93%BE%E6%8E%A5%E8%A7%A3%E6%9E%90link-discovery%E7%9A%84%E7%94%A8%E6%B3%95 specifications-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HKW0CMGXX4VXBHFGG3TGGPRV=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
