---
title: 设备标识符
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
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
  created_at: '2021-10-12T14:16:09Z'
  edited_at: '2026-10-14T09:59:50Z'
  id: 4408847686161
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/4408847686161
---
> **概要：** 概要：本文主要说明了AppsFlyer SDK中支持的设备标识符。

## 速览

AppsFlyer SDK会收集设备标识符，用于归因。这些标识符能帮助您构建用户链路，并了解用户的行为习惯。

该SDK会自动收集AppsFlyer ID和Google Advertising ID等标识符。您也可以根据实际需求为相关应用收集其他的标识符（如针对在中国市场投放的应用，收集第三方安卓应用商店的标识符）。

## 适用于所有平台的设备标识符

AppsFlyer SDK支持以下全平台设备标识符：

| 设备标识符 | 作用 |
| --- | --- |
| <span id="appsflyer-id"></span>AppsFlyer ID | AppsFlyer ID会在每次发生应用激活时自动生成。您可以使用该标识符来完成下列事项：<ul><li>发送<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S应用内事件</Anchor> 。</li><li>将AppsFlyer ID与您后台的用户记录进行匹配。</li><li>合并来自Pull API和Push API的数据时进行映射。</li></ul> |
| <span id="customer-user-id"></span>Customer User ID（客户用户ID） | <Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">客户用户ID（CUID）</Anchor>字段是由应用所有者或网站所有者设定的一种唯一标识符。在AppsFlyer SDK中设置CUID后，您就可以在CUID、AppsFlyer ID和其他ID（如设备ID等）之间进行交叉索引。您可以在AppsFlyer的原始数据报告中查看CUID，还能在回传API中使用该ID与您的内部ID进行交叉索引。 |

## 安卓设备标识符

AppsFlyer SDK支持以下安卓设备标识符：

#### 对于在Google Play中上架的应用

| 设备标识符 | 作用 |
| --- | --- |
| <span id="gaid"></span>GAID | 一种可由用户重置的标识符，适用于Google Play安卓用户。<br /><br />从SDK V4.8.0开始，AppsFlyer会自动收集这个设备标识符。 |

#### 对于在第三方应用商店上架的应用

| 设备标识符 | 作用 |
| --- | --- |
| <span id="amazon-advertising-id"></span>Amazon Advertising ID | Amazon Fire TV使用的一种唯一标识符，可由用户重置。详情请见CTV概览。 |
| <span id="oaid"></span>OAID | 部分第三方安卓应用商店使用的一种唯一标识符，可由用户重置。  详情请见OAID使用指南。 |
| <span id="imei"></span>IMEI | 一种不可重置的移动设备唯一标识符，适用于不支持Google Play的市场。AppsFlyer SDK不会自动收集IMEI。但如果您需要收集该标识符，可以让您的开发人员配置相关的信息收集功能。<br /><br />**请注意：**<ul><li>安卓10及以上版本会限制IMEI的读取权限。</li><li>IMEI不能与GAID同时使用。</li></ul> |
| <span id="android-id"></span>Android ID | 一种不可重置的移动设备唯一标识符，适用于第三方应用商店。AppsFlyer SDK不会自动收集Android ID。但如果您需要收集该标识符，可以让您的开发人员配置相关的信息收集功能。<br /><br />**请注意：** 请注意：Android ID不能与GAID同时使用。 |

## Apple设备标识符

AppsFlyer SDK支持以下iOS设备标识符：

| 设备标识符 | 作用 |
| --- | --- |
| <span id="idfa"></span>IDFA | 用于Apple iOS或tvOS（Apple TV）用户的一种唯一标识符，可由用户重置。iOS 14.5及以上版本中，用户必须在ATT弹窗中选择同意授权，SDK才能读取到其设备的IDFA。 |
| <span id="idfv"></span>IDFV | **同一家厂商**的所有应用在同一台设备上都具有相同的IDFV。用户激活某厂商的首个应用后，系统会给该应用分配一个IDFV，之后再激活该厂商的其他应用时，这些应用也会得到相同的IDFV。其他厂商的应用则会分配到不同的IDFV。<br /><br />此外，如果用户将某个厂商的所有应用全部从其设备中删除，则相应的IDFV也会被一并删除。之后，如果用户再次激活该厂商的应用，系统会为其分配一个新的IDFV。 |


| <span id="ctv-device-identifiers"></span>Platform（系统平台） | 设备 ID |
| --- | --- |
| Android TV | advertising\_id |
| tvOS（Apple TV） | idfa |
| Amazon Fire TV | amazon\_fire\_id |
| Chromecast | advertising\_id |
| Roku | rida |
| Vizio | vida |
| Samsung | tifa |
| LG | <ul><li>LG WebOS=lgudid</li></ul> |
| Xbox | custom |
| Vidaa | vidaaid |
| Steam | steamid |
| Meta Quest（Oculus） | custom |
| Epic Games | epicid |
| PlayStation | psid |
| PC端原生应用（Native PC） | custom |
|  | 安卓标识符 |

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01H9YXEYC3PA271B3G3Y3GM9PS=%E9%80%9F%E8%A7%88 device-identifiers-for-all-platforms=%E9%80%82%E7%94%A8%E4%BA%8E%E6%89%80%E6%9C%89%E5%B9%B3%E5%8F%B0%E7%9A%84%E8%AE%BE%E5%A4%87%E6%A0%87%E8%AF%86%E7%AC%A6 h_01H9YXEYC3RCB3RDBKRW19WYQD=%E9%80%82%E7%94%A8%E4%BA%8E%E6%89%80%E6%9C%89%E5%B9%B3%E5%8F%B0%E7%9A%84%E8%AE%BE%E5%A4%87%E6%A0%87%E8%AF%86%E7%AC%A6 android-device-identifiers=%E5%AE%89%E5%8D%93%E8%AE%BE%E5%A4%87%E6%A0%87%E8%AF%86%E7%AC%A6 h_01H9YXEYC3D95A6G70EGNR8ENK=%E5%AE%89%E5%8D%93%E8%AE%BE%E5%A4%87%E6%A0%87%E8%AF%86%E7%AC%A6 apps-published-on-google-play=%E5%AF%B9%E4%BA%8E%E5%9C%A8google-play%E4%B8%AD%E4%B8%8A%E6%9E%B6%E7%9A%84%E5%BA%94%E7%94%A8 h_01H9YXEYC3RG2XCVVW8MJ5VZSC=%E5%AF%B9%E4%BA%8E%E5%9C%A8google-play%E4%B8%AD%E4%B8%8A%E6%9E%B6%E7%9A%84%E5%BA%94%E7%94%A8 apps-published-in-thirdparty-app-stores=%E5%AF%B9%E4%BA%8E%E5%9C%A8%E7%AC%AC%E4%B8%89%E6%96%B9%E5%BA%94%E7%94%A8%E5%95%86%E5%BA%97%E4%B8%8A%E6%9E%B6%E7%9A%84%E5%BA%94%E7%94%A8 h_01H9YXEYC3JA3DPN6P43J1ZXR9=%E5%AF%B9%E4%BA%8E%E5%9C%A8%E7%AC%AC%E4%B8%89%E6%96%B9%E5%BA%94%E7%94%A8%E5%95%86%E5%BA%97%E4%B8%8A%E6%9E%B6%E7%9A%84%E5%BA%94%E7%94%A8 apple-device-identifiers=apple%E8%AE%BE%E5%A4%87%E6%A0%87%E8%AF%86%E7%AC%A6 h_01H9YXEYC3733B1A85TEF35EAY=apple%E8%AE%BE%E5%A4%87%E6%A0%87%E8%AF%86%E7%AC%A6 h_01H9YXEYC3DFPWVXA5Y3XANQ3P=ctv-device-identifiers" />
