---
title: 用户级别数据的保留政策
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2020-02-23T15:35:57Z'
  edited_at: '2026-10-14T09:59:10Z'
  id: 360006091197
  locale: zh-cn
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/zh-cn/articles/360006091197
---
> **概要：** 用户级别原始数据的保留政策取决于相关法律以及AppsFlyer和SRN（**渠道**）的使用条款。

<div id="caution" />

> ❗️ **注意事项**
>
> AppsFlyer在本文中提供的数据限制说明仅供参考。  *本文所述的所有内容仅供参考，不构成法律建议。*

<div id="data-retention-and-deletion-obligations" />

## 数据保留与删除义务

AppsFlyer接收到的用户级数据来自应用、渠道以及其他数据来源。

<div id="availability-of-user-level-data-to-advertisers" />

### 广告主可访问的用户级别数据

通常情况下，如果广告主订阅的套餐包含原始数据访问权限，并且仍在90天访问期内（详见<Anchor target="_blank" href="/marketers/zh/docs/data-availability-windows">数据可访问时间窗口</Anchor>），就可以通过原始数据报表工具访问用户级数据。不过在某些情况下，<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">原始数据</Anchor>也可能受到限制。

<div id="data-retention" />

### 数据保留

AppsFlyer会在有限的时间内保留用户级数据。原始数据的保留期限根据数据传输方式和合作渠道的要求而有所不同。一般来说：

* **用户级别原始数据**的保留期限取决于对接类型以及合作渠道的要求；
* **汇总数据**最长可保留5年。

该保留期限结束之前，用户完成的事件会被归因到带来该用户的渠道。保留期限结束后，用户事件会被归因为自然量。

制定数据保留期限的依据包括：

* <Anchor target="_blank" href="https://www.appsflyer.com/legal/processing-customer-data/">AppsFlyer服务隐私政策</Anchor>
* 按照法律指示、要求或允许的处理方式
* 渠道的使用条款以及留存期限，详见下文表格。

注意事项：

* 数据访问窗口期以及数据保留期限在不同情况下可能会有所变化
* 在某些情况下，AppsFlyer可能会延长数据访问窗口期
* 数据保留期限会按带量渠道不同而有所变化
* 部分用户级别数据会被归因到<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">受限的媒体渠道</Anchor>，这种情况下，这部分归因数据不会出现在原始数据中。发生这种情况的原因包括：
  * 渠道的数据共享政策
  * <Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">汇总层级的高级隐私保护</Anchor>（AAP）处于启用状态

<div id="partner-data-retention-periods" />

#### 渠道的数据保留期限

| SRN/渠道 | 渠道ID（PID） | 用户激活的[x]月之后删除数据 |
| --- | --- | --- |
| Amazon Ads | amazondsp\_int | 12 |
| Apple Search Ads | Apple Search Ads | 无限制 |
| Discord |  | 3 |
| DV360 | dv360\_int、doubleclick\_int | 6 |
| Google Ads | googleadwords\_int（所有流量入口） | 6 |
| Hotstar | hotstar\_int | 6 |
| Meta ads* | facebook\_int（所有流量入口） | 6 |
| Microsoft | Microsoftdisplay\_int和bingsearch\_int | 13 |
| pinterest | pinterest\_int | 6 |
| Samsung DSP | samsungdsp\_int | 3 |
| Snapchat（<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">TOS</Anchor>） | snapchat\_int | 6 |
| TikTok for Business | tiktokglobal\_int | 13 |
| X Ads（原Twitter） | twitter\_int | 3 |

<div id="note" />

> 📘 **注意：**
>
> 对于SRN，此表中的保留期限仅适用于SRN直接提供的数据。它们不适用于通过AppsFlyer W2A归因链接所做的归因（`googleads_int`，`metaweb_int`，`tiktokweb_int`，`snapweb_int`）。

> 📄 **相关文档**
>
> <Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">原始数据限制——媒体渠道或设备标识符</Anchor>

<div data-zendesk-anchors="h_01H95FY07TRAAD3K0A0TSG3RB6=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 data-retention-and-deletion-obligations=%E6%95%B0%E6%8D%AE%E4%BF%9D%E7%95%99%E4%B8%8E%E5%88%A0%E9%99%A4%E4%B9%89%E5%8A%A1 h_01H95FY07TABPC769R7TYGY5DD=%E6%95%B0%E6%8D%AE%E4%BF%9D%E7%95%99%E4%B8%8E%E5%88%A0%E9%99%A4%E4%B9%89%E5%8A%A1 availability-of-userlevel-data-to-advertisers=%E5%B9%BF%E5%91%8A%E4%B8%BB%E5%8F%AF%E8%AE%BF%E9%97%AE%E7%9A%84%E7%94%A8%E6%88%B7%E7%BA%A7%E5%88%AB%E6%95%B0%E6%8D%AE h_01H95FY07T2Q9QAGW5A5S6KP6J=%E5%B9%BF%E5%91%8A%E4%B8%BB%E5%8F%AF%E8%AE%BF%E9%97%AE%E7%9A%84%E7%94%A8%E6%88%B7%E7%BA%A7%E5%88%AB%E6%95%B0%E6%8D%AE data-retention=%E6%95%B0%E6%8D%AE%E4%BF%9D%E7%95%99 h_01H95FY07TXS63FVDJC2NEFXYC=%E6%95%B0%E6%8D%AE%E4%BF%9D%E7%95%99 partner-data-retention-periods=%E6%B8%A0%E9%81%93%E7%9A%84%E6%95%B0%E6%8D%AE%E4%BF%9D%E7%95%99%E6%9C%9F%E9%99%90 h_01H95FY07TZ4N0RRJRGJ6FN2EK=%E6%B8%A0%E9%81%93%E7%9A%84%E6%95%B0%E6%8D%AE%E4%BF%9D%E7%95%99%E6%9C%9F%E9%99%90 h_01KRKAWSHH2WFZT9Q5M0FSBBAB=%E6%B3%A8%E6%84%8F h_01HE7S5A2Q8GFEKD8M7C2RZ40W=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
