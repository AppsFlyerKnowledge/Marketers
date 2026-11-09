---
title: Google Ads（AdWords）— 成本与广告收入
metadata:
  keywords:
    - Advertisers
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-20T10:01:42Z'
  edited_at: '2026-10-14T10:06:04Z'
  id: 4417309205521
  locale: zh-cn
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/zh-cn/articles/4417309205521
---
> **概要：概览：本文介绍了如何将Google Ads的成本和广告收入数据同步到AppsFlyer。**

<div id="cost-clicks-and-impressions" />

## 成本、点击和展示

成本对接可提供下列汇总数据：

* 广告系列、广告组、国家/地区和流量入口维度的成本数据。详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">广告平台成本对接表</Anchor>，其中详细说明了适用维度、指标和功能。  
  **请注意：** 您需要购买<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>才能获得成本数据。
* 点击、展示数据以及扩充数据（关键词、广告系列名称以及广告组）。

<div id="tip" />

<div id="note" />

> 📘 **注意**
>
> * 支持MCC账户。
> * 请确保您在Google Ads中将广告系列配置为仅针对iOS或安卓应用投放，不要设置多平台的广告系列，否则AppsFlyer无法分应用拆解成本数据，并会合并呈现两个应用的成本数据。
> * 由于受到Google Ads API的限制，目前预注册广告的成本、点击和展示数据不可用。

要在AppsFlyer面板上查看Google Ads费用、点击和展示数据，请通过Google Ads配置页进行连接。连接完成后，AppsFlyer将开始查询所有Google Ads现有广告系列的成本、点击和展示数据。

如需进一步了解如何在Google Ads中设置成本，请参见<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">此文档</Anchor>。

如需进一步了解Google对点击和展示的定义，请参见此文档。

如需进一步了解Google Ads数据的局限性，请参见<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6163740">此文档</Anchor>。

**设置后数小时内，数据就会传通** 。

> 👍 **提示**
>
> 用户可以通过显示在Google Ads面板右上角的登录电子邮件地址来确认他们使用Google Ads帐号是否正确。
>
> <Image align="center" alt="short.png" src="https://files.readme.io/512cc4bf1cfb1b269e9bb4a4fa0028f615de7a1a9e832d835f2632c2412124d0-51911559512337.png" />
>  如果相关Google Ads帐号是某个MCC帐号的子帐号，则面板右上角的ID是MCC帐号的ID，子帐号的ID在左上角。
>
> 如果账号不正确，请先登出当前账号，然后换一个邮箱地址登入其他Google账号。

<div id="cost-data-sync-status" />

### 成本数据同步状态

<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">您可以在成本（及广告收入）对接状态面板或单独的广告平台面板中查看AppsFlyer最近一次获取匹配成本数据的时间以及</Anchor> API状态。

Google Ads允许您同步多个帐户以获取成本数据。对于已完成对接的账户，AppsFlyer会显示成本对接的状态以及最近一次拉取到匹配成本数据的时间。

<div id="stopping-google-cost-sync" />

### 停止Google成本同步

**如需停止同步Google的成本数据，请删除相关的Google账户连接：**

* <Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">进入成本选项卡，将鼠标悬停在相关账户的“操作”栏，然后点击“删除连接”。</Anchor> 连接删除后，AppsFlyer就不会再接收成本数据，但不影响历史数据。

<div id="recording-ad-revenue-with-google-ads" />

## 记录Google Ads的广告收入

Google Ads（AdWords）的收入对接已于2020年11月30日下线。如需获取广告收入数据，AdWords客户需要迁移到<Anchor target="_blank" href="/marketers/zh/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>。

<div id="faq" />

<Accordion title="常见问题解答">

| **为什么看不到成本数据？**<br /><br />这可能是由以下几种原因造成的：<ul><li>登录时，务必确保使用正确的Google帐户。<br />如果您使用的Google账号不正确，则无法拉取或显示任何成本数据。如果发生这种情况，您必须从Google应用权限中删除相关应用，并使用正确的帐户登录，具体操作如下：<ol><li>点击下列链接: <Anchor target="_blank" href="https://myaccount.google.com/permissions">https://myaccount.google.com/permissions</Anchor></li><li>在Google后台删除“AppsFlyer Cost”，然后重新登录。</li></ol></li><li>某些情况下，虽然代理的成本对接已打开，但仍拉不到成本数据，这是因为该代理用户没有权限访问正确的Google Ads Customer ID。这会导致广告主看到的成本数据不完整。</li></ul>确保登录到成本选项卡中的代理用户可以访问对接选项卡中的Google Ads Customer ID。<br /><br />[<Image alt="" src="https://files.readme.io/2d17b3dad78e02c76253f30db0c15c18eb837b531becabc07ccad274258c2c61-49938966132753.png" width="457px" />](https://files.readme.io/2d17b3dad78e02c76253f30db0c15c18eb837b531becabc07ccad274258c2c61-49938966132753.png)<ul><li>在iOS搜索或Android着陆页广告系列中使用空格或特殊字符可能会导致成本数据与点击数据匹配问题并造成成本数据缺失。</li><li>若代理在收集到成本数据后关闭成本对接，但广告主的成本对接仍处于活跃状态，则从代理关闭对接之日起，成本数据仅关联到广告主。</li></ul> |
| --- |
| **分地理位置的点击数据是怎么来的？**<br /><br />在某些情况下，AppsFlyer会从Google收到不完整的地理位置点击数据。发生这种情况时，AppsFlyer会从其他Google渠道获取缺失的地理位置点击信息。因此，按地理位置分组时，来自Google广告系列的总点击次数可能与另一分组维度的总点击次数不同。 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 活跃及不活跃的广告系列 | <ul><li>应用激活广告（ACI类广告系列）</li><li>应用互动广告（ACE类广告系列）</li></ul> |
|  |  |

</Accordion>

> 📄 **相关文档**
>
> * 请参考<Anchor target="_blank" href="/marketers/zh/docs/get-skan-postback-data-from-google-ads">Google Ads与AppsFlyer的SKAN互动设置</Anchor>，了解iOS 14的相关注意事项。

<div data-zendesk-anchors="cost-clicks-and-impressions=%E6%88%90%E6%9C%AC%E7%82%B9%E5%87%BB%E5%92%8C%E5%B1%95%E7%A4%BA h_01HDP2SMHJ26S1BCER3KKZ8H14=%E6%88%90%E6%9C%AC%E7%82%B9%E5%87%BB%E5%92%8C%E5%B1%95%E7%A4%BA h_01HDP2SMHJB5YE5PCWVJVBAKHD=%E6%B3%A8%E6%84%8F h_01HDP2SMHJF86QK9CJTVABKTYW=%E6%8F%90%E7%A4%BA cost-data-sync-status=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E5%90%8C%E6%AD%A5%E7%8A%B6%E6%80%81 h_01HDP2SMHJT8Z6DP7BHC0Y5RRN=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E5%90%8C%E6%AD%A5%E7%8A%B6%E6%80%81 stopping-google-cost-sync=%E5%81%9C%E6%AD%A2google%E6%88%90%E6%9C%AC%E5%90%8C%E6%AD%A5 h_01HDP2SMHJPEDKKZF9SBXW56KG=%E5%81%9C%E6%AD%A2google%E6%88%90%E6%9C%AC%E5%90%8C%E6%AD%A5 recording-ad-revenue-with-google-ads=%E8%AE%B0%E5%BD%95google-ads%E7%9A%84%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5 h_01HDP2SMHKC9TSZZZPFFNK8TPH=%E8%AE%B0%E5%BD%95google-ads%E7%9A%84%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5 h_01HDP2SMHK8NH6M4T1A2Y79P55=faq h_01HDP2SMHKPDEE07H8WAP212TZ=traits-and-limitations h_01HDP2XBSEJVQ5G0MD0V5R05CM=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
