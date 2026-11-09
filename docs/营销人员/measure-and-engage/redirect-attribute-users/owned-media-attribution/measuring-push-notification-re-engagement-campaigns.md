---
title: 消息推送型再营销广告的衡量方式
metadata:
  keywords:
    - Re-Engagement
    - push
    - notifications
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2016-01-18T10:03:11Z'
  edited_at: '2026-10-14T10:12:35Z'
  id: 207364076
  locale: zh-cn
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/zh-cn/articles/207364076
---
> **概要：** 本文介绍了iOS和安卓平台中消息推送型广告的衡量方式。

<div id="overview" />

## 速览

AppsFlyer可以衡量所有推送服务平台的推送消息广告，以及直接通过Firebase Cloud Messaging或Apple Push Notification Services（APNS）投放的广告。

对接方式分为以下两种：

* 在推送消息的有效信息（payload）中发送带有`af`参数JSON对象（早前方式）。

配置完成后，您就可以在数据总览面板的“统一”或“再营销”视图中看到相关转化。

<div id="how-does-it-work" />

## 原理

完成本文所述的对接流程后，相关应用即可支持以下链路：

1. 您触发一个推送消息，其有效信息（payload）中包含OneLink模板**或**`af`参数。
2. 应用用户收到该消息，并完成点击。
3. 应用加载并启动AppsFlyer SDK。
4. SDK处理推送消息的payload，进而调起应用。
5. SDK提取归因数据，并发送给AppsFlyer。

如果您使用OneLink并为其配置了应用中具体页面的跳转，上述链路会触发深度链接流程。

<div id="prerequisites" />

## 前期准备

在进入下一个环节之前，请先确保您已在相关应用中<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide">接入AppsFlyer SDK</Anchor> **，并且**该应用可以接收推送消息。

<div id="steps" />

## 步骤

如需设置推送消息的衡量，必须完成以下步骤：

1. [创建一个推送消息](/docs/measuring-push-notification-re-engagement-campaigns#1-creating-the-push-notification)，其中包含带有OneLink模板的自定义参数，**或者**以JSON对象为参数值的`af`参数。
2. [配置SDK，用于解析自定义参数](/docs/measuring-push-notification-re-engagement-campaigns#2-configuring-the-sdk)（由应用开发人员完成）。
3. 触发该推送消息，[测试对接](/docs/measuring-push-notification-re-engagement-campaigns#3-testing-the-integration)。
4. 在面板中[查看推送消息的投放效果](/docs/measuring-push-notification-re-engagement-campaigns#4-viewing-push-notification-campaigns-in-the-dashboard)。

<div id="1-creating-the-push-notification" />

<Accordion title="1. 创建推送消息">

首先，请使用以下任一方式创建一个带有归因数据的推送消息。

<div id="note" />

> 📘 **注意**
>
> 在下文示例中，我们使用Firebase作为消息推送平台。但本文说明适用于任何推送服务平台，各平台之间一般没有或仅有略微差异。详情请参考您使用的推送服务平台所提供的说明问文档。

<Tabs>
<Tab title="OneLink（推荐方式）">

<div id="using-onelink-recommended" />

#### **OneLink（推荐方式）**

我们建议您使用这种方式完成推送消息的AppsFlyer对接。

1. 创建一条<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">用于再营销的OneLink链接，并完成相应设置。</Anchor>  
   **请注意**：OneLink长链和短链均可使用。
2. 在推送消息的自定义数据中，添加该Onelink链接，确保链接中包含您想要发送到AppsFlyer的归因数据。

<div id="note-1" />

> 📄 **Firebase示例**
>
> Firebase中的配置界面如下：
>
> <Image align="center" alt="appsflyer-push-custom-data-firebase.png" src="https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png" />

</Tab>

<Tab title="JSON（早前方式）">

<div id="using-json-legacy" />

<div id="using-json" />

#### **JSON（早前方式）**

<div id="note-2" />

> 📘 **注意**
>
> 这是我们早前针对推送消息配置AppsFlyer对接的方式。为了保证向后兼容性，这一方式仍然可用。如果您要针对新的应用完成相关配置，建议使用[我们推荐的OneLink方案](/docs/measuring-push-notification-re-engagement-campaigns#onelink推荐方式)。

在推送消息的自定义数据中，添加一个名为`af`的自定义参数，确保该参数中包含您想要发送到AppsFlyer的归因数据（JSON格式）。该JSON对象中必须配置下列归因参数：

* `pid`
* `is_retargeting`
* `c`

<div id="note-3" />

> 📄 **Firebase示例**
>
> Firebase中的配置界面如下：
>
> <Image align="center" alt="appsflyer-push-custom-data-firebase-json.png" src="https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png" />

</Tab>
</Tabs>

</Accordion>

<div id="2-configuring-the-sdk" />

<Accordion title="2. 配置SDK">

在这一步中，您需要让应用开发人员修改应用代码。请按以下说明配置SDK：

* 在部署OneLink方案时：
  1. 向应用开发人员提供您在推送消息中添加的自定义参数名称。在本文示例中，该参数的名称为`af_push_link`。
  2. 向开发人员发送<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-using-onelink-recommended">相关说明</Anchor>。
* 在部署早前的JSON方案时，请向您的开发人员发送<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-legacy">相关说明</Anchor>。

</Accordion>

<div id="3-testing-the-integration" />

<Accordion title="3. 测试对接">

如需测试推送消息的对接配置是否正确无误，只需触发您在广告中设置的推送消息（第1步）。

在配置正确的情况下，SDK会：

1. 监听推送消息。
2. 处理嵌入该推送消息的归因数据，并将其发送到AppsFlyer。
3. 如果推送消息的衡量通过OneLink实现，则SDK会启动常规的深度链接流程。

</Accordion>

<div id="4-viewing-push-notification-campaigns-in-the-dashboard" />

<Accordion title="4. 在面板中查看推送消息的投放数据。">

您可以在<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide#retargeting-dashboard">再营销面板</Anchor>中看到推送消息产生的数据。

**请注意**：AppsFlyer会对推送消息的数据进行去重。也就是说，如果AppsFlyer多次接收到同一个payload，则该payload只记录一次。

</Accordion>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01J5XFSEG9DR31DP73KTAGQPFW=%E9%80%9F%E8%A7%88 how-does-it-work=%E5%8E%9F%E7%90%86 h_01J5XFSEG967HXNT3GFSC2AQYE=%E5%8E%9F%E7%90%86 prerequisites=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01J5XFSEG91SER3JKB3RKK6B6G=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 steps=%E6%AD%A5%E9%AA%A4 h_01J5XFSEG9W3RTP62NW7SV4D0F=%E6%AD%A5%E9%AA%A4 h_01J5XFSEG9PXHTD4C9XCDC01DH=1-creating-the-push-notification h_01J5XFSEG9C2C1Z8HK4R1V03H1=%E6%B3%A8%E6%84%8F using-onelink-recommended=onelink%E6%8E%A8%E8%8D%90%E6%96%B9%E5%BC%8F h_01J5XFSEG9W73JYPHH9VRZSTZ8=onelink%E6%8E%A8%E8%8D%90%E6%96%B9%E5%BC%8F h_01J5XFSEG97PMRHV20V1VG0SP4=firebase%E7%A4%BA%E4%BE%8B h_01J5XFSEG9V46T6XSG31J4AVET=using-json-legacy h_01J5XFSEG9G7QV4N4JATS8W3MX=%E6%B3%A8%E6%84%8F h_01J5XFSEG9XAQ1KMB088GFK4YS=firebase%E7%A4%BA%E4%BE%8B h_01J5XFSEG9GYMKAT27AWTN1WZZ=2-configuring-the-sdk h_01J5XFSEG91NH41QMV9K3S4F18=3-testing-the-integration h_01J5XFSEG904NC72K8MWX9YM06=4-viewing-push-notification-campaigns-in-the-dashboard" />
