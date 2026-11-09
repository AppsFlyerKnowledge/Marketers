---
title: Google Analytics (GA4) 对接
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
  created_at: '2024-06-06T15:26:00Z'
  edited_at: '2026-10-14T10:02:40Z'
  id: 25707682812561
  locale: zh-cn
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/zh-cn/articles/25707682812561
---
> **概要：** 广告主可以借助AppsFlyer与Google Analytics (GA4)的对接，将归因数据及部分选定的应用内事件从AppsFlyer发送至GA4。此对接适用于已部署[Google Analytics for Firebase SDK](https://firebase.google.com/docs/analytics)的iOS和Android应用。

<div id="important" />

> 🚧 **重要提示！**
>
> 此对接适用于已部署[Google Analytics for Firebase SDK implemented](https://firebase.google.com/docs/analytics)的iOS和Android应用。 为确保对接成功，AppsFlyer SDK必须从Firebase SDK收集`app_instance_id`值。请参见相关说明，了解如何[从FirebaseSDK 获取应用实例ID](#5-retrieve-app-instance-id-in-appsflyer-sdk)。

<div id="how-does-it-work" />

## 工作原理

* **发生新的激活**时，AppsFlyer会将触点详情（媒体渠道、广告活动名称和广告活动ID）发送至GA4。同时还会发送Firebase SDK的`app_instance_id`，确保该用户的触点被GA4记录。
* **发生应用内事件**时，GA4会将该事件归因于最后触点。

<div id="set-up-google-analytics-ga4-integration" />

## 设置Google Analytics (GA4)对接

按照以下说明配置与Google Analytics (GA4)的对接。

<div id="1-select-google-analytics-ga4-in-the-partner-marketplace" />

<Accordion title="1. 在Partner Marketplace中选择Google Analytics (GA4)">

**前提条件：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。**修改方式**：从AppsFlyer面板左侧的菜单栏中选择**协作** > **活跃对接**。
2. 搜索并选择**Google Analytics (GA4)**。
3. 点击**设置对接**，界面会跳转到对接设置页。

Google Analytics配置仅包括**对接**选项卡。

请点击<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">此处</Anchor>查看渠道配置页Header的详细描述。

</Accordion>

<div id="2-set-ga4-integration-in-appsflyer" />

<Accordion title="2. 在AppsFlyer中设置GA4对接">

请进行以下设置：

1. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。

   **注意：** 在您与该渠道合作期间，请确保该开关始终处于打开 <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">（启用）</Anchor>状态。

   有关渠道激活的详细说明请参见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。
2. 在**Firebase应用ID**中输入Firebase应用标识符。如需查找Firebase应用ID，请参见<Anchor target="_blank" href="https://firebase.google.com/support/faq#find-app-id">Firebase文档</Anchor>。
3. 在**API Secret**字段中，输入用于验证发送至Google Analytics回传的API Secret。API Secret可通过Google Analytics界面生成。如需查看、编辑或创建Secret，请按照<Anchor target="_blank" href="https://support.google.com/analytics/answer/9814495?sjid=5179426966283787649-EU">Google文档</Anchor>中的说明操作。**当提示您选择web数据流时，应选择Android或iOS数据流。**
4. 开启**客户用户ID**以发送客户用户ID（CUID），而不是广告ID（IDFA）。
5. 在**默认回传**部分，在<strong>来自（for users from）</strong>中选择**所有媒体来源，包括自然流量**。

   <div id="note" />

   > 📘 **注意**
   >
   > 激活回传仅包含触点详情（媒体渠道、广告活动名称和广告活动ID）。


</Accordion>

<div id="3-set-in-app-event-postbacks" />

<Accordion title="3. 应用内事件回传">

在**对接**选项卡中，将AppsFlyer应用内事件映射到Google Analytics（GA4）事件，并通过回传发送。

<div id="note-1" />

> 📘 **注意**
>
> * 通过 S2S 发送的移动应用内事件的回调不受支持。
> * GA4不会对同时来自Firebase SDK和AppsFlyer的事件进行去重。因此，建议仅为尚未通过Firebase SDK发送至GA4的事件配置应用内事件回传。

1. 打开**应用内事件回传**开关。
2. 点击**添加事件**，将SDK事件添加到列表中。下表列出了必须配置的字段：

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，来自集成到您应用中的 AppsFlyer SDK。<br /><br />**提示**：如果下拉菜单中没有您要查看的事件：<ul><li>请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。</li><li>在**AppsFlyer事件**中输入该事件的名称，然后点击**创建自定义事件**。</li></ul>详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">自定义事件映射</Anchor>。 |
| **渠道映射事件** | 渠道侧为每个事件定义的专属名称或ID。映射配置包括以下几种：<ul><li>**文本字段：** 从渠道处获取相应的事件ID。</li><li>**下拉菜单：** 选择最合适的AppsFlyer预定义事件。</li><li>**按原样**：按原样发送事件，不进行名称映射。</li></ul> |
| **事件来源** | 选择事件回传的范围：<ul><li>**所有媒体渠道，包括自然流量**：回传所有带量渠道的事件，以及自然量。</li></ul> |
| **回传内容** | <ul><li>**不发送值与收入（默认）**： 仅发送事件本身，不带任何事件值。</li><li>**值和收入**： 发送所有事件参数，**包括**收入（若有）。</li><li>**仅发送值**： 发送**除**收入以外的所有参数。</li></ul> |

3. 【可选】点击**添加条件**图标 (<Image alt="condition-2.png" src="https://files.readme.io/959329be2b1286507b5c87b033785e91ab135592ae37cf3200539400832490c0-25709762755857.png" width="19px" />)，设置事件的<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">映射条件</Anchor>。
4. 点击**保存对接**。
5. 发送事件回传映射

</Accordion>

<div id="4-send-your-developer-the-postback-event-mapping" />

<Accordion title="4. 将事件回传映射发送给您的开发者">

设置应用内事件映射后，请向您的开发人员发送一个表格，每个映射事件对应一行，包含以下列：

* **AF event：** AppsFlyer事件名称。
* **Mapped to Google event：** Google Analytics中的事件名称。

  <div id="important-1" />

  > 🚧 **重要提示！**
  >
  > 请勿使用任何[Google保留事件](#google保留事件名称)为自定义Google Analytics事件命名。

* **AF event parameters（必填）：** 发送至Google Analytics的事件回传中必须包含的预定义AppsFlyer事件参数。

  <div id="important-2" />

  > 🚧 **重要提示！**
  >
  > 事件定义中必须准确包含表中所列的所有预定义AF事件参数；否则，Google Analytics将拒绝回传。


<div id="the-event-mapping-table" />

#### 事件映射表

下表列出了所有Google Analytics事件及其对应的预定义AppsFlyer参数。请仅将您实际完成映射的事件整理成表格，并发送给开发人员。

| AF推荐名称（可选） | Google Ads事件名称 | 预定义AF事件参数（必填） |
| --- | --- | --- |
| af\_add\_payment\_info | [add\_payment\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_payment_info) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [add\_shipping\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_shipping_info) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_cart | [add\_to\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_cart) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_wishlist | [add\_to\_wishlist](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_wishlist) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_initiated\_checkout | [begin\_checkout](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#begin_checkout) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [campaign\_details](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#campaign_details) | campaign id, campaign name |
| af\_spent\_credits | [earn\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#earn_virtual_currency) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [generate\_lead](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#generate_lead) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>,<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [join\_group](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#join_group) |  |
| af\_level\_achieved | [level\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#level_up) |  |
| af\_login | [login](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#login) |  |
|  | [post\_score](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#post_score) | af\_user\_score |
| af\_purchase | [purchase](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#purchase) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>，<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>，<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>，<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>，<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor>，<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [refund](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#refund) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>，<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>，<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>，<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>，<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor>，<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [remove\_from\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#remove_from_cart) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [screen\_view](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#screen_view) |  |
| af\_search | [search](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#search) |  |
|  | [select\_content](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_content) |  |
|  | [select\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_item) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [select\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_promotion) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [share](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#share) |  |
|  | [sign\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#sign_up) |  |
|  | [spend\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#spend_virtual_currency) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [tutorial\_begin](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_begin) |  |
| af\_tutorial\_completion | [tutorial\_complete](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_complete) |  |
| af\_achievement\_unlocked | [Unlock\_achievement](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#unlock_achievement) | af\_achievement\_id |
|  | [view\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_cart) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_item\_list](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item_list) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_promotion) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_search\_results](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_search_results) |  |
| af\_ad\_view | [ad\_impression](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#ad_impression) | <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>，<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |

<div id="reserved-google-event-names" />

#### Google保留事件名称

以下事件名称是保留的，不能用作自定义事件名称：

* `ad_activeview`
* `ad_click`
* `ad_exposure`
* `ad_query`
* `ad_reward`
* `adunit_exposure`
* `app_clear_data`
* `app_exception`
* `app_install`
* `app_remove`
* `app_store_refund`
* `app_update`
* `app_upgrade`
* `dynamic_link_app_open`
* `dynamic_link_app_update`
* `dynamic_link_first_open`
* `error`
* `firebase_campaign`
* `firebase_in_app_message_action`
* `firebase_in_app_message_dismiss`
* `firebase_in_app_message_impression`
* `first_open`
* `first_visit`
* `in_app_purchase`
* `notification_dismiss`
* `notification_foreground`
* `notification_open`
* `notification_receive`
* `notification_send`
* `os_update`
* `session_start`
* `user_engagement`

</Accordion>

<div id="5-retrieve-app-instance-id-in-appsflyer-sdk" />

<Accordion title="5. 在AppsFlyer SDK中检索应用实例ID">

应用实例ID（app instance ID）用于标识Firebase应用的某一次具体安装。该数值需要由AppsFlyer SDK从Firebase SDK中获取。

请让开发人员实现以下代码逻辑：

1. 从Firebase收集`app_instance_id`字段。
2. 在首次启动前调用`setAdditionalData`，将应用实例ID包含在激活、打开以及应用内事件中。

<div id="important-3" />

> 🚧 **重要提示！**
>
> `setAdditionalData`（Android / Unity / React Native）和 `customData`（iOS）接受 **键值对的映射**。如果您的应用同时发送 `app_instance_id` 和 `ga_session_id`（见 [第 6 步](#h_01HZQ5SESSIONID)），**请将它们一起发送在同一映射中**，以便包含这两个值。如果您在 **单独** `setAdditionalData` 调用中发送它们，后一个将覆盖前一个。

<Tabs>
<Tab title="安卓原生">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).appInstanceId.addOnCompleteListener { task ->
   if (task.isSuccessful) {
       AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.result)
    }
}
```

**java**

```java
FirebaseAnalytics.getInstance(this).getAppInstanceId().addOnCompleteListener(task -> {
       if (task.isSuccessful()) {
           AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.getResult());
       }
  });
```

API reference: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="iOS原生">

**iOS原生**

```swift
let appInstanceId = Analytics.appInstanceID()
    AppsFlyerLib.shared().customData = ["app_instance_id": appInstanceId]
```

**Objective C**

```objectivec
(void) fetchAnalyticsInstanceId {
           NSString *instanceID = [FIRAnalytics appInstanceID];
           [[AppsFlyerLib shared] setAdditionalData:@{@"app_instance_id": instanceID}];
}
```

API reference: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="Unity">

```java
using Firebase.Analytics;
    public class AnalyticsManager : MonoBehaviour
    {
        private async void Start()
        {
           AppsFlyer.initSDK(devKey, appID, this);
           string appInstanceId = await FirebaseAnalytics.GetAnalyticsInstanceIdAsync();
           Dictionary <string, string> customData = new Dictionary<string, string>();
           customData.Add("app_instance_id", appInstanceId);
           AppsFlyer.setAdditionalData(appInstanceId);
           AppsFlyer.startSDK();
        }
}
```

API reference: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="React Native">

API reference: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<div id="h_01HZQ5SESSIONID" />

<Accordion title="6. 在AppsFlyer SDK中检索GA4应用打开ID">

GA4应用打开ID`ga_session_id`用于标识Firebase应用的某一次应用打开。该数值必须由AppsFlyer SDK从Firebase SDK中获取，并通过`setAdditionalData`API发送至GA4。

请让开发人员实现以下代码逻辑：

1. 从Firebase收集`ga_session_id`字段。
2. 在首次启动前调用`setAdditionalData`，将会话ID包含在数据中。
3. 调用API时使用密钥`ga_session_id`。

<div id="important-4" />

> 🚧 **重要提示！**
>
> `setAdditionalData`（Android / Unity / React Native）和 `customData`（iOS）接受 **键值对的映射**。如果您的应用同时发送 `app_instance_id` 和 `ga_session_id`（见 [第 5 步](#5-retrieve-app-instance-id-in-appsflyer-sdk)），**请将它们一起发送在同一映射中**，以便包含这两个值。如果您在 **单独** `setAdditionalData` 调用中发送它们，后一个将覆盖前一个。

<Tabs>
<Tab title="安卓原生">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).sessionId.addOnCompleteListener { task ->
    if (task.isSuccessful) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.result)
    }
}
```

**java**

```java
FirebaseAnalytics.getInstance(this).getSessionId().addOnCompleteListener(task -> {
    if (task.isSuccessful()) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.getResult());
    }
});
```

API reference: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="iOS原生">

**Swift**

```swift
if #available(iOS 14.0, *) {
    Analytics.sessionID { sessionID, error in
        if let sessionID = sessionID {
            AppsFlyerLib.shared().customData = ["ga_session_id": sessionID]
        }
    }
}
```

**Objective-C**

```objectivec
- (void)fetchAnalyticsSessionId {
    if (@available(iOS 14.0, *)) {
        [FIRAnalytics sessionIDWithCompletion:^(NSString * _Nullable sessionID, NSError * _Nullable error) {
            if (sessionID) {
                [[AppsFlyerLib shared] setAdditionalData:@{@"ga_session_id": sessionID}];
            }
        }];
    }
}
```

API reference: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="Unity">

```csharp
using Firebase.Analytics;
using System.Threading.Tasks;
using AppsFlyerSDK;
using UnityEngine;
using System.Collections.Generic;

public class AnalyticsManager : MonoBehaviour
{
    private async void Start()
    {
        AppsFlyer.initSDK("yourDevKey", "yourAppID", this);

        // Get session ID
        string sessionId = await FirebaseAnalytics.GetSessionIdAsync();

        Dictionary<string, string> customData = new Dictionary<string, string>();
        customData.Add("ga_session_id", sessionId);
        AppsFlyer.setAdditionalData(customData);

        AppsFlyer.startSDK();
    }
}
```

API reference: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<div id="6-validate-the-ga4-integration" />

<Accordion title="7. 验证GA4对接">

确保您发送到GA4的事件回传已被Google Analytics记录和读取。广告主可以通过以下两种方式查看数据：

* 使用[GA4探索(Explorations)](https://support.google.com/analytics/answer/7579450?hl=en&ref_topic=12153537,12153943,2986333,&sjid=20462331341270448-EU&visit_id=638532662145815538-1056226594&rd=1#access-analysis&zippy=%2Cin-this-article)：您可以基于所有相关参数探索原始事件数据。**前提条件：** 请在您的GA4属性中启用[BigQuery](https://support.google.com/analytics/answer/9823238)导出功能。
* **事件报告**：广告主可在事件报告中查看回传事件。该报告可能位于一个或多个报告集合下。  
  例如，事件报告可以在[生命周期](https://support.google.com/analytics/answer/12924233?hl=en)或[游戏报告](https://support.google.com/analytics/answer/12925133?hl=en&sjid=5454549956257318969-NC)集合中找到，路径为**互动（Engagement）** > **事件（Events）**。   
  有关事件报告的更多信息，请参见[Google文档](https://support.google.com/analytics/answer/12926615?sjid=5454549956257318969-NC)。[![](https://files.readme.io/01625878b13a46b8a87c34bf465c0ef6494a0f528960d62ce5535b69b29e7d0a-25707728713745.png)](https://files.readme.io/01625878b13a46b8a87c34bf465c0ef6494a0f528960d62ce5535b69b29e7d0a-25707728713745.png)
* **流量获取报告**：帮助您了解网站和应用中访问者的来源。

  在[生命周期](https://support.google.com/analytics/answer/12924233?hl=en)集合下，转到**获客** > **流量获取**。

  有关流量获取报告的更多信息，请参见[Google文档](https://support.google.com/analytics/answer/12923437?hl=en&sjid=5454549956257318969-NC#zippy=%2Chow-do-i-filter-out-traffic-sources-from-the-report)。

  <Image align="center" alt="" src="https://files.readme.io/fa51e22d1a7941666224eb668efcbfc5a3bb8cce42cf373a82f3b1e096d2a9db-25707770926353.png" />

</Accordion>

<div data-zendesk-anchors="01J9BA4J7TPNMPTWK576VG3BP4=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA set-up-google-analytics-ga4-integration=%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 h_01HZXY8R12MQWKNHX2BXA68MR3=%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 h_01J35AP3FF599P0XA8VPWTS5R9=%E8%AE%BE%E7%BD%AEgoogle-analytics-ga4%E5%AF%B9%E6%8E%A5 h_01HZQ4ABBMC8D23K36V5P8T23R=1-select-google-analytics-ga4-in-the-partner-marketplace h_01HZQ4ABBMKEF619ZTDXVYWHEK=2-set-ga4-integration-in-appsflyer h_01J35CWSD6MGAR0Y76EEEHKFH6=%E6%B3%A8%E6%84%8F h_01HZQ4ABBME2A42V738S6K84HX=3-set-in-app-event-postbacks h_01J35DVVAVW9DSVTX0VRSYH5KX=%E6%B3%A8%E6%84%8F-1 h_01HZQ4ABBMQZMCYGMMAE20TRXV=4-send-your-developer-the-postback-event-mapping h_01HZQ4ABBMR9REVXRDC09B25QT=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 h_01HZQ4ABBN6VC1DX3CK39RNEFG=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2 the-event-mapping-table=%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84%E8%A1%A8 h_01HZQ4ABBN0YEVFJXBNS0HTSQ5=%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84%E8%A1%A8 reserved-google-event-names=google%E4%BF%9D%E7%95%99%E4%BA%8B%E4%BB%B6%E5%90%8D%E7%A7%B0 h_01HZQ4ABBN6ZEB7RJQMFS0AB73=google%E4%BF%9D%E7%95%99%E4%BA%8B%E4%BB%B6%E5%90%8D%E7%A7%B0 h_01HZQ4ABBN3D3T8A2Y5N428884=5-retrieve-app-instance-id-in-appsflyer-sdk h_01KH6GJX5RM895G51ZXN8VJDMF=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-4 6-retrieve-ga4-session-id-in-the-appsflyer-sdk=h_01HZQ5SESSIONID h_01KH6HDB7A2FH4ZQY1PRKPQBPM=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-4 h_01HZQ4ABBN4JA16D9RZHERFE63=6-validate-the-ga4-integration" />
