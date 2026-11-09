---
title: 从AppsFlyer平台中删除特定内容
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2018-11-21T16:07:58Z'
  edited_at: '2026-10-14T10:03:13Z'
  id: 360000603117
  locale: zh-cn
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000603117
---
> **概要：** 广告主可以从AppsFlyer平台中删除相关应用、媒体渠道和用户数据。

<Image align="center" alt="shutterstock_699498934.jpg" src="https://files.readme.io/db2cd79f6da6de42042707fb2c8bbfe450a6cdc17a93f7a9dc9ea27d04716ef3-34228068995857.jpg" width="363px" />

<div id="delete-user-history" />

## 删除用户的历史记录

GDPR和CCPA等一部分隐私监管条例规定用户*有权清除*其数据。

**场景：** 某用户要求您删除与其相关的数据。根据GDPR的规定，您必须在30天内完成这项请求。

**必要操作：** 使用<Anchor target="_blank" href="/marketers/zh/docs/send-opendsr-api-requests">OpenDSR API</Anchor>发送数据清除请求。

<div id="stop-attributing-installs-to-a-media-source" />

## 停止对特定渠道进行激活归因

AppsFlyer会根据您配置的媒体渠道收集激活和事件信息。如果您为某个渠道配置了归因，AppsFlyer就会将相关的新增激活归因到该渠道。

**场景：** 假设某个渠道不再产生任何点击、展示或激活，您因而停止在该渠道上投放广告，也不再将新增转化归因到该渠道。但AppsFlyer仍会继续对现有用户的应用内事件进行记录和归因。

**如需停止将新增激活归因到某个渠道，请按以下方式操作：**

* **SKAN（适用于iOS应用）：**
  1. <Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio#disable-skan-measurement">停用SKAN衡量</Anchor>。
  2. 对于<Anchor target="_blank" href="/marketers/zh/docs/get-skan-postback-data-from-google-ads#turning-off-the-skan-integration">Google Ads</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-interoperation-with-meta-ads#turning-off-the-skan-integration">Meta ads</Anchor>，您还必须移除相应的SKAN对接，以停止SKAN数据的记录。
* **SRN：** <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation#停用渠道对接">停用相关渠道的对接</Anchor>。
* **非SRN：**  
  1. <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation#停用渠道对接">停用相关渠道的对接</Anchor>。
  2. 通过相关广告中的AppsFlyer归因链接发送到AppsFlyer的点击和激活仍会得到记录和归因。请确保您通过该渠道向潜在用户展示的广告中不再包含AppsFlyer归因链接。
* **自有媒体：**
  * 停止使用相关的OneLink自定义链接。

<div id="remove-or-delete-an-app" />

## 移除或删除应用

您可以选择暂时移除应用。

<div id="temporarily-removing-an-app" />

#### 暂时移除应用

当应用被暂时移除时，数据记录会停止，应用不会显示在仪表板上，并且在“我的应用”页面上显示为灰色。但是，该应用仍与账户关联，并且可以恢复。恢复应用后，应用设置、已批准代理和令牌等历史数据将被保留。

<div id="note" />

> 📘 **注意**
>
> 移除应用需逐个进行。但是，您可以通过 <Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer#通过-api-批量管理应用">API 移除多个应用</Anchor>。

**删除应用的方法如下：**

1. **在顶部菜单栏中点击***我的应用*。
2. 点击操作图标，打开应用操作菜单。
3. 点击 **移除**，然后确认。  
   该应用删除完毕，不再出现在应用列表中。

**若要恢复已移除的应用：**

* 请联系您的 CSM 或发送电子邮件至 [hello@appsflyer.com](mailto:hello@appsFlyer.com) 以启动该流程。一旦 CSM 恢复了该应用，您就可以将其重新添加到您的账户中。

<div id="transfer-apps-between-accounts" />

## 在不同账户之间迁移应用

详细说明请参见这篇文档：<Anchor target="_blank" href="/marketers/zh/docs/transferring-apps-between-accounts">在不同账户之间迁移应用</Anchor>。

<div id="delete-your-account-or-downgrade-your-subscription-plan" />

## 删除账户或套餐降级

请联系您的CSM或发送邮件至[hello@appsflyer.com](mailto:hello@appsFlyer.com)。

<div data-zendesk-anchors="delete-user-history=%E5%88%A0%E9%99%A4%E7%94%A8%E6%88%B7%E7%9A%84%E5%8E%86%E5%8F%B2%E8%AE%B0%E5%BD%95 h_01HNZ7TNZM4P5APM2B1WQ4X7S5=%E5%88%A0%E9%99%A4%E7%94%A8%E6%88%B7%E7%9A%84%E5%8E%86%E5%8F%B2%E8%AE%B0%E5%BD%95 stop-attributing-installs-to-a-media-source=%E5%81%9C%E6%AD%A2%E5%AF%B9%E7%89%B9%E5%AE%9A%E6%B8%A0%E9%81%93%E8%BF%9B%E8%A1%8C%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 h_01HNZ7VPA16065PGCSZDMQZ3ZC=%E5%81%9C%E6%AD%A2%E5%AF%B9%E7%89%B9%E5%AE%9A%E6%B8%A0%E9%81%93%E8%BF%9B%E8%A1%8C%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 delete-an-app=%E7%A7%BB%E9%99%A4%E6%88%96%E5%88%A0%E9%99%A4%E5%BA%94%E7%94%A8 h_01HNZ7XKEFRNEWGQZ58T7H0KDH=%E7%A7%BB%E9%99%A4%E6%88%96%E5%88%A0%E9%99%A4%E5%BA%94%E7%94%A8 removing-an-app=%E6%9A%82%E6%97%B6%E7%A7%BB%E9%99%A4%E5%BA%94%E7%94%A8 h_01J52J31FDKSPNWSD5J2V5BYTW=%E6%9A%82%E6%97%B6%E7%A7%BB%E9%99%A4%E5%BA%94%E7%94%A8 h_01HYJ5EPX4B1G1SAF6XGZ7ADWZ=%E6%B3%A8%E6%84%8F transfer-apps-between-accounts=%E5%9C%A8%E4%B8%8D%E5%90%8C%E8%B4%A6%E6%88%B7%E4%B9%8B%E9%97%B4%E8%BF%81%E7%A7%BB%E5%BA%94%E7%94%A8 h_01HNZ7ZW7ZKDSD2TTEX55PYB91=%E5%9C%A8%E4%B8%8D%E5%90%8C%E8%B4%A6%E6%88%B7%E4%B9%8B%E9%97%B4%E8%BF%81%E7%A7%BB%E5%BA%94%E7%94%A8 delete-your-account-or-downgrade-your-subscription-plan=%E5%88%A0%E9%99%A4%E8%B4%A6%E6%88%B7%E6%88%96%E5%A5%97%E9%A4%90%E9%99%8D%E7%BA%A7 h_01HNZ81GQ8Z6R8DV8Z6SAXYRB9=%E5%88%A0%E9%99%A4%E8%B4%A6%E6%88%B7%E6%88%96%E5%A5%97%E9%A4%90%E9%99%8D%E7%BA%A7" />
