---
title: Salesforce Marketing Cloud MobilePush对接指南
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-14T06:37:05Z'
  edited_at: '2026-10-14T10:15:26Z'
  id: 10590769196817
  locale: zh-cn
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/zh-cn/articles/10590769196817
---
> **概要：概要：Salesforce Marketing Cloud MobilePush是一个用户互动平台，适用于营销、用户增长和促活工作。该平台是AppsFlyer的对接渠道之一。**

<div id="overview" />

## 速览

广告主可以利用Salesforce Marketing Cloud MobilePush，根据跨渠道的用户数据，针对指定用户群体创建并发送推送消息。这种营销方式能够引导用户使用相关应用，并提升其ROI。您可以通过MobilePush掌握用户在您应用中的行进轨迹，了解他们浏览的商品以及在各个页面上停留的时间等等。对接MobilePush后，您就可以：

* 提升用户互动和移动电商效益
* 获得关键的用户信息
* 轻松投放跨渠道广告
* 分组定时发送推送消息

<div id="important" />

> 🚧 **重要提示！**
>
> 部分渠道限制第三方的数据共享。

<div id="setting-up-salesforce-marketing-cloud-mobilepush" />

## Salesforce Marketing Cloud MobilePush的设置方法

大部分的设置工作都集中在Salesforce后台（第1-4步），只有第5步需要在AppsFlyer后台完成。

<div id="step-1-set-up-mobilepush-sdk" />

### 第1步：

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_get_started.htm&type=5">接入MobilePush SDK设置</Anchor>

<div id="step-2-provision-for-push-notifications" />

### 第2步：第2步：使用推送通知之前的准备工作

<div id="step-3-enable-app-push-notifications" />

### 第3步：第3步：启用应用推送通知

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-configureforpush.html">启用推送通知</Anchor>

<div id="step-4-set-up-app-push-notifications" />

### 第4步：第4步：设置应用推送通知

* 创建并向移动端推送消息。

<div id="note" />

> 📘 **注意**
>
> 在Salesforce Marketing Cloud上创建推送通知时，必须添加<Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_custom_keys.htm&type=5">custom key</Anchor>（自定义密钥），这样AppsFlyer才能使用正确的PID和投放参数正常地完成归因。

<div id="step-5-set-up-push-notifications-in-appsflyer" />

### 第4步：第5步：在AppsFlyer平台中设置推送通知

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications-ios#addpushnotificationdeeplinkpath-recommended">使用OneLink配置iOS SDK（链接文档中的第3步）</Anchor>

<div id="note-1" />

> 📘 **注意**
>
> 请确保您在`AF_xxxxxxxxx`第4步AF\_xxxxxxxxx中输入的[AF\_xxxxxxxxx](/docs/salesforce-marketing-cloud-mobilepush-integration-setup#第4步第4步设置应用推送通知)自定义密钥与您在`addPushNotificationDeepLinkPath`中使用的密钥值一致。

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01H9HWK3F5TQZ8YQZBHGBZACPG=%E9%80%9F%E8%A7%88 h_01H9HWK5DM87JTDVFND0KB965G=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA setting-up-salesforce-marketing-cloud-mobilepush=salesforce-marketing-cloud-mobilepush%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%96%B9%E6%B3%95 h_01H9HWK3F52YGQPX4B82N40PPD=salesforce-marketing-cloud-mobilepush%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%96%B9%E6%B3%95 step-1-set-up-mobilepush-sdk=%E7%AC%AC1%E6%AD%A5 h_01H9HWK3F5HCVZ0225MFRYRW5Q=%E7%AC%AC1%E6%AD%A5 step-2-provision-for-push-notifications=%E7%AC%AC2%E6%AD%A5%E7%AC%AC2%E6%AD%A5%E4%BD%BF%E7%94%A8%E6%8E%A8%E9%80%81%E9%80%9A%E7%9F%A5%E4%B9%8B%E5%89%8D%E7%9A%84%E5%87%86%E5%A4%87%E5%B7%A5%E4%BD%9C h_01H9HWK3F5RNCZG340E0CT5XJC=%E7%AC%AC2%E6%AD%A5%E7%AC%AC2%E6%AD%A5%E4%BD%BF%E7%94%A8%E6%8E%A8%E9%80%81%E9%80%9A%E7%9F%A5%E4%B9%8B%E5%89%8D%E7%9A%84%E5%87%86%E5%A4%87%E5%B7%A5%E4%BD%9C step-3-enable-app-push-notifications=%E7%AC%AC3%E6%AD%A5%E7%AC%AC3%E6%AD%A5%E5%90%AF%E7%94%A8%E5%BA%94%E7%94%A8%E6%8E%A8%E9%80%81%E9%80%9A%E7%9F%A5 h_01H9HWK3F5E4W8FG35V4JTFN7F=%E7%AC%AC3%E6%AD%A5%E7%AC%AC3%E6%AD%A5%E5%90%AF%E7%94%A8%E5%BA%94%E7%94%A8%E6%8E%A8%E9%80%81%E9%80%9A%E7%9F%A5 step-4-set-up-app-push-notifications=%E7%AC%AC4%E6%AD%A5%E7%AC%AC4%E6%AD%A5%E8%AE%BE%E7%BD%AE%E5%BA%94%E7%94%A8%E6%8E%A8%E9%80%81%E9%80%9A%E7%9F%A5 h_01H9HWK3F5K8V8AVADXNNG25GY=%E7%AC%AC4%E6%AD%A5%E7%AC%AC4%E6%AD%A5%E8%AE%BE%E7%BD%AE%E5%BA%94%E7%94%A8%E6%8E%A8%E9%80%81%E9%80%9A%E7%9F%A5 h_01H9HWK3F5VG2GBCE93B69AADH=%E6%B3%A8%E6%84%8F step-5-set-up-push-notifications-in-appsflyer=%E7%AC%AC4%E6%AD%A5%E7%AC%AC5%E6%AD%A5%E5%9C%A8appsflyer%E5%B9%B3%E5%8F%B0%E4%B8%AD%E8%AE%BE%E7%BD%AE%E6%8E%A8%E9%80%81%E9%80%9A%E7%9F%A5 h_01H9HWK3F5YJ71YCWHV4B02VYP=%E7%AC%AC4%E6%AD%A5%E7%AC%AC5%E6%AD%A5%E5%9C%A8appsflyer%E5%B9%B3%E5%8F%B0%E4%B8%AD%E8%AE%BE%E7%BD%AE%E6%8E%A8%E9%80%81%E9%80%9A%E7%9F%A5 h_01H9HWK3F5T67NSPE9CVPS1KTA=%E6%B3%A8%E6%84%8F-1" />
