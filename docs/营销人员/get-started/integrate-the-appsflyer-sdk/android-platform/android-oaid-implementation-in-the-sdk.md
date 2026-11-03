---
title: 在安卓SDK中集成OAID
metadata:
  keywords:
    - China
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2020-02-27T20:21:05Z'
  edited_at: '2026-10-14T10:11:32Z'
  id: 360006278797
  locale: zh-cn
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/zh-cn/articles/360006278797
---
> **概要：** 概要：本文介绍了如何收集安卓OAID，从而对第三方安卓应用商店带来的激活进行归因。

## OAID简介

匿名设备标识符（Open Anonymous Device Identifier，简称OAID）是一种用于安卓设备的唯一标识符，可由用户重置。该标识符由移动安全联盟（MSA）、中国信息通信研究院以及设备厂商合力推出，旨在替代IMEI等不可重置的设备标识符，以保护用户隐私。

OAID通常用于不支持Google Play Services的设备（即没有Google Advertising ID的设备），以对其进行广告衡量及激活归因。

<span id="supported-devices"></span>MSA提供了专门的SDK，可读取所有设备的OAID。对于华为设备，则可以使用HMS Core SDK。

## 对接

OAID的集成分为3步：

1. 接入SDK，用以生成并发送OAID（MSA SKD或华为HMS SDK均可）。
2. 接入AppsFlyer OAID插件模块。
3. 接入AppsFlyer SDK。

**请注意**：

* 对于面向中国市场的应用，必须使用MSA SDK。
* 对于在华为设备上使用的、面向全球市场的应用，建议使用华为HMS SDK。

<div id="msa-sdk" />

<Accordion title="MSA SDK">

**请按以下步骤接入并使用MSA SDK**：

1. 按照[MSA网站](http://www.msa-alliance.cn/col.jsp?id=120)上的指南注册您的应用。
   * 注册后即可下载SDK。
   * 在注册过程中您会收到一个证书文件，您需要将该证书文件添加到相关应用中。
2. 让您的开发人员按照<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#msa-sdk-integration">集成指南</Anchor>完成相关操作。

</Accordion>

<div id="huawei-hms-sdk" />

<Accordion title="华为HMS SDK">

**请按以下步骤接入并使用华为HMS SDK**：

* 让您的开发人员按照<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#huawei-hms-sdk-integration">集成指南</Anchor>完成相关操作。

</Accordion>

## 其他相关信息

<div id="opting-out-of-oaid-collection" />

<Accordion title="拒绝收集OAID">

完成OAID集成后，SDK会自动收集OAID。如果您需要避免收集某些用户的OAID，请让您的开发人员使用下列方法：

<Tabs>
<Tab title="安卓">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid">setCollectOAID(false) API</Anchor>或<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>

<Tab title="Unity">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectoaid">setCollectOAID(false) API</Anchor>或<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>
</Tabs>

<div id="setting-oaid-manually" />

<Accordion title="手动设置OAID">

如果您的应用已可收集OAID，则不必接入AppsFlyer OAID插件，请使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#setting-oaid-manually">setOaidData API</Anchor>直接手动在AppsFlyer SDK中设置OAID值。

</Accordion>

</Accordion>

<div data-zendesk-anchors="about-oaid=oaid%E7%AE%80%E4%BB%8B h_01HG8PXBZS1SN3SY3AAH1EKMNP=oaid%E7%AE%80%E4%BB%8B integration=%E5%AF%B9%E6%8E%A5 h_01HG8PXBZS26P9X1TQ7J4WQNF5=%E5%AF%B9%E6%8E%A5 h_01HG8PXBZSM0QYQE4C9S1FBFB1=msa-sdk h_01HG8PXBZS3HP9X1AZ7HQ8C34Y=huawei-hms-sdk additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HG8PXBZSW5HNTTDRQ7DFFF4D=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HG8PXBZS8Z3MTQWFN5R6FFA8=opting-out-of-oaid-collection h_01HG8PXBZSYNS8R1PCW4YXHFBA=setting-oaid-manually" />
