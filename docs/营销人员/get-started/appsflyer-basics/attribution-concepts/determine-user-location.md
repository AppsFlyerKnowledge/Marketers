---
title: 识别用户位置
metadata:
  keywords:
    - IPs
    - Advertisers
    - Agencies
    - Ad Networks
    - ip
    - digital element
    - zip
    - dim
    - zip code
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2019-01-29T12:52:11Z'
  edited_at: '2026-10-14T10:12:15Z'
  id: 360000847378
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000847378
---
> **概要：** 设备的IP地址可用于识别用户的大致位置，包括城市、州/省和国家等信息。用户的位置会影响素材选择、广告成本、互动效果和用户质量等关键因素。

<Image align="center" alt="5888ResolveIpAddress_us-en.png" src="https://files.readme.io/166e48fb0bb90b627bc51e29b53a556b71939749ab3e5eadff7d6edf0f0dfd25-360011758517.png" />

<div id="determining-user-location" />

## 用户位置的识别方式

用户在设备上的行为会被上报给AppsFlyer，这些行为（事件）中包含多个数据字段，包括设备IP地址。

在某些情况下，真实的设备IP会被VPN、iOS 15私密中继（Private Relay）或SKAN回传代理服务器等机制掩盖。由于以上因素不在AppsFlyer的控制范围内，因此本文中描述的IP地址到地理位置的转换可能不准确或存在误导性。

AppsFlyer使用全球领先的IP定位数据服务商<Anchor target="_blank" href="http://www.digitalelement.com/">Digital Element</Anchor>提供的数据，将IP地址转换为地理位置。

* 地理位置信息可能包括以下字段：
  * 国家/地区：使用ISO 3166（alpha-2）编码。如果无法提供具体国家信息，则显示为EU（欧洲）或AS（亚洲）。
  * 城市：可对应城市内的街区或区域，而非城市的行政边界。
  * DMA（指定市场区域）： 由<Anchor target="_blank" href="https://www.nielsen.com/us/en/solutions/nielsen-global-connect/">Nielsen</Anchor>公司定义的电视市场区域，在导出CSV文件中显示为<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012539677">Metro codes</Anchor>。
  * 地区：地理区域或大洲。
  * 州或省：请参见<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012615238">CSV文件中的本地化州/省名称表</Anchor>。我们使用该表中的地区字段，最多为3位字母或数字。
  * 邮政编码
* AppsFlyer定期更新IP地址与地理位置对应表，通常每周一次。

**示例：将IP地址转换为地理位置**![IPTables_us-zh.png](https://files.readme.io/0d7d4d4190face77e18476bdb9e47fdd26ed62ab91cd641f76f728d9a7c8d005-360011787798.png)

<div id="note-regarding-the-united-kingdom-uk" />

> 📘 **关于英国（UK）的说明**
>
> <Image align="center" alt="blobid0.png" src="https://files.readme.io/33ed45ea49e3308e17a237400ea6c6e9d33c495a9c83197041fdae282f9c65a4-360006637538.png" width="62px" />
>
> * 在AppsFlyer平台中，英国的国家代码为UK。
> * 但根据ISO 3166标准，英国的正式代码为“GB”。尽管“UK”在ISO中被保留用于代表英国，但UK并不是ISO中英国的官方代码。

<div id="location-discrepancies" />

### 位置差异

有时，虽然其他平台也使用Digital Element提供的IP数据，但AppsFlyer与其他平台得出的用户位置信息仍可能存在差异。造成这种差异的可能原因包括：

* **数据库更新：** 为实现快速归因，AppsFlyer内部将IP地址解析为位置信息，并定期从Digital Element获取最新数据，但不是实时更新。如果AppsFlyer和其他平台获取数据的时间不同，就可能会导致差异。
* **ISP变更：** 当服务提供商（ISP）更改其IP映射时，Digital Element的数据库也会快速发生变化。
* **方案/使用方式差异：** Digital Element提供多种不同的服务方案，以满足不同的数据层级的需求。不同平台可能使用不同版本的数据包，或采用不同方式来识别设备，从而导致差异。
* **代理或VPN：** 如果用户使用VPN或代理，AppsFlyer无法识别其真实IP，所显示的位置将对应于VPN或代理服务器的IP地址。
* **了解更多：** <Anchor target="_blank" href="https://www.digitalelement.com/blog/the-tricky-science-behind-ip-geolocation/">IP地理定位背后的复杂原理</Anchor>

<div data-zendesk-anchors="determining-user-location=%E7%94%A8%E6%88%B7%E4%BD%8D%E7%BD%AE%E7%9A%84%E8%AF%86%E5%88%AB%E6%96%B9%E5%BC%8F h_01HDP1SA5YV96YMPPFGN9H6RGE=%E7%94%A8%E6%88%B7%E4%BD%8D%E7%BD%AE%E7%9A%84%E8%AF%86%E5%88%AB%E6%96%B9%E5%BC%8F h_01HDP1SA5YR7JWDHX2BNXXTKT9=%E5%85%B3%E4%BA%8E%E8%8B%B1%E5%9B%BDuk%E7%9A%84%E8%AF%B4%E6%98%8E location-discrepancies=%E4%BD%8D%E7%BD%AE%E5%B7%AE%E5%BC%82 h_01HDP1SA5YNA9N4P9AD4RHWS0J=%E4%BD%8D%E7%BD%AE%E5%B7%AE%E5%BC%82" />
