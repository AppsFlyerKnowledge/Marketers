---
title: 通知
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
  created_at: '2025-03-24T10:10:37Z'
  edited_at: '2026-10-14T10:02:08Z'
  id: 33732395637905
  locale: zh-cn
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/zh-cn/articles/33732395637905
---
> **概要：** 通过AppsFlyer平台管理账户重要通知。

您可以选择接收AppsFlyer通知的方式，以便在发生特定事件及时收到通知。在**通知偏好设置**中，选择开启或关闭相应的通知类型。

<div id="accessing-and-configuring-notification-preferences" />

## 访问并配置通知偏好设置

<div id="to-access-notifications" />

### 查看通知

* 从页面顶部导航栏打开账户菜单（点击右上角的邮箱地址，打开下拉菜单）> **通知**。
* 平台内的铃声图标 > **点击设置图标。**

<div id="configuring-notifications" />

### 配置通知

如需选择接收某项通知，请在可用通知列表中将其开启。

如需停止接收，请将其关闭。

注意：有些通知只能通过电子邮件发送。您可以在仅通过电子邮件发送通知的选项卡中进行[设置。](/docs/notifications#仅通过邮件发送通知)

<div id="what-notifications-can-i-receive" />

## 我可以接收哪些通知？

您可以接收以下类型的通知：

* 账号和套餐管理
* 计费或交易问题
* 隐私警报
* 关键信息和配置
* 协作功能

请注意：有些通知只能通过电子邮件发送。如需了解更多信息请点击[此处](/docs/notifications#email-notification)。

若要选择接收某项特定通知，必须满足以下条件：

* <strong>该通知在贵公司AppsFlyer账户中处于可用状态。</strong>如果该通知在公司账户中不可用，则不会显示相应的开关。
  * 例如，如果公司未购买AppsFlyer的Push API功能，则不会显示与此功能相关的通知开关。
* <strong>可用选项取决于您的用户权限。</strong>如某项通知关联的功能或模块超出您的权限范围，开关将处于禁用状态，无法开启或关闭。
  * 例如，如果您没有添加或编辑对接渠道的权限，与对接渠道配置相关的通知开关将处于禁用状态。

<div id="when-will-i-receive-notifications" />

## 我会在何时收到通知？

如果您已选择接收某项通知，当该通知的触发事件发生时，您将收到相关通知。但**仅当**该事件与您有权限访问的**应用和媒体渠道**相关时，您才会收到通知。

<div id="example" />

<Accordion title="示例">

请参考以下使用场景：

* 贵公司在AppsFlyer中有3个应用：App A、App B和App C。
* 每个应用都与两个媒体渠道（对接渠道）进行了对接：Google Ads 和 TikTok。
* 假设您的AppsFlyer用户账户拥有以下权限：
  * 添加/编辑对接渠道
  * 访问App C的数据
  * 访问Google Ads的数据
* 你已选择接收关于对接渠道配置变更的通知。

那么将出现以下情况：

* 当App A和App B的对接渠道配置变更时，您**不会**收到通知。
* 当App C中TikTok的配置变更时，您也**不会**收到通知。
* 当App C中Google Ads的配置变更，您**将收到**通知。

</Accordion>

<div id="where-will-i-receive-notifications" />

## 我可以在哪里接收通知？

您可以通过[铃声](/docs/notifications#bell-notification)图标、[电子邮件](/docs/notifications#email-notification)或[Slack](/docs/notifications#slack-notification)对接接收通知。

<div id="bell-notification" />

<Accordion title="铃声图标">

您可以账户菜单（右上角电子邮箱下拉菜单）左侧找到铃声图标。

点击齿轮图标进入[通知偏好设置](/docs/notifications#访问并配置通知偏好设置)。

</Accordion>

<div id="email-notification" />

<Accordion title="邮件通知">

您可以通过与AppsFlyer账户关联的邮箱接收邮件通知。

有些通知只能通过电子邮件发送。您可以在**仅通过电子邮件发送的通知**选项卡中进行设置。

<div id="note" />

> 📘 **注意**
>
> AppsFlyer的所有邮件通知均由[notifications@appsflyer.com](mailto:notifications@appsflyer.com)发出。

<div id="email-only-notifications" />

#### 仅通过邮件发送通知

下表显示了**仅通过电子邮件**发送的通知及其触发事件：

| 通知类型 | 触发事件 |
| --- | --- |
| 对接渠道配置变更 | <ul><li>激活新的对接渠道</li><li>停用现有对接渠道</li><li>现有对接渠道设置变更</li></ul> |
| Push API调用失败 | 在连续12小时内，某个应用有5%或以上的Push API消息发送失败。 |
| 受众共享连接失败 | 受众共享连接失败，需要您的注意。 |
| 广告收入对接中止 | 某项广告收入对接处于警告状态超过30天，已被停用 |
| 无法接收广告收入数据 | 某项广告收入对接未接收到任何数据 |
| 对接渠道成本配置变更 | 团队成员更改了成本对接设置。 |
| SKAN连接失败 | Google Ads或Meta SKAN与AppsFlyer对接时出现问题，需要您的注意。您可能需要删除当前对接，并重新登录。 |

</Accordion>

<div id="slack-notification" />

<Accordion title="Slack通知">

**设置Slack通知**

要设置Slack通知，首先需完成Slack对接：

1. 在通知偏好设置页面，点击页面右上角的**对接**按钮。
2. 在Slack通知连接器旁，点击**连接**。
3. 查看并批准权限请求。
   1. **如果您是Slack管理员**。
      1. 在Slack中点击相应的Slack工作区以完成授权。  
         <Image align="center" alt="" src="https://a.slack-edge.com/8e8e4/helpcenter/img/workspace-picker@2x.jpg" width="263px" />
         注意：确保您连接了正确的Slack工作区。
      2. 前往**工具与设置** -> **管理应用**
      3. 在**管理面板**中，选择**请求** 。
      4. 在**待批准**标签页下，点击AppsFlyer应用请求旁边的三个点。
      5. 点击**批准**，并在弹出的窗口中确认。
      6. 返回**AppsFlyer对接页面**，点击**允许**按钮完成对接。
   2. **如果您不是Slack管理员**。  
      1. 请向您的Slack管理员请求权限，以便将Slack与AppsFlyer对接。
      2. 以上所有步骤**必须**由Slack管理员完成。在此期间：
      3. Slack connector将显示为待处理状态。
      4. 待管理员批准连接后，您可以点击**连接**按钮开始对接流程，状态将从“待处理”变为“已连接”。

</Accordion>

<div data-zendesk-anchors="accessing-email-notifications=%E8%AE%BF%E9%97%AE%E5%B9%B6%E9%85%8D%E7%BD%AE%E9%80%9A%E7%9F%A5%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE h_01HKA254W4XDVNP816N46N59ZV=%E8%AE%BF%E9%97%AE%E5%B9%B6%E9%85%8D%E7%BD%AE%E9%80%9A%E7%9F%A5%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE to-access-notifications=%E6%9F%A5%E7%9C%8B%E9%80%9A%E7%9F%A5 h_01JQ66J4YSCSX7ZGG81XHGJ3MM=%E6%9F%A5%E7%9C%8B%E9%80%9A%E7%9F%A5 configuring-notifications=%E9%85%8D%E7%BD%AE%E9%80%9A%E7%9F%A5 h_01HKA254W497H0SKTZ33CVSA4P=%E9%85%8D%E7%BD%AE%E9%80%9A%E7%9F%A5 what-notifications-can-i-receive=%E6%88%91%E5%8F%AF%E4%BB%A5%E6%8E%A5%E6%94%B6%E5%93%AA%E4%BA%9B%E9%80%9A%E7%9F%A5 h_01HKA254W47XRG1D3HZ6VBZ2BH=%E6%88%91%E5%8F%AF%E4%BB%A5%E6%8E%A5%E6%94%B6%E5%93%AA%E4%BA%9B%E9%80%9A%E7%9F%A5 when-will-i-receive-notifications=%E6%88%91%E4%BC%9A%E5%9C%A8%E4%BD%95%E6%97%B6%E6%94%B6%E5%88%B0%E9%80%9A%E7%9F%A5 h_01JQ66BX52MV5WQ7RXH6SY3QHK=%E6%88%91%E4%BC%9A%E5%9C%A8%E4%BD%95%E6%97%B6%E6%94%B6%E5%88%B0%E9%80%9A%E7%9F%A5 h_01JQ6EYTZ13FHYERT48K3J25SV=example where-will-i-receive-notifications=%E6%88%91%E5%8F%AF%E4%BB%A5%E5%9C%A8%E5%93%AA%E9%87%8C%E6%8E%A5%E6%94%B6%E9%80%9A%E7%9F%A5 h_01HKA254W4Z95M335V7KWAJA6N=%E6%88%91%E5%8F%AF%E4%BB%A5%E5%9C%A8%E5%93%AA%E9%87%8C%E6%8E%A5%E6%94%B6%E9%80%9A%E7%9F%A5 h_01JQ667RAW19658DVMZNFXNAJK=bell-notification h_01JQ667RAWCAVYBZD3J0T8XH2G=email-notification h_01JJGTDQFM1WE9G3XWSN9S7Z02=%E6%B3%A8%E6%84%8F emailonly-notifications=%E4%BB%85%E9%80%9A%E8%BF%87%E9%82%AE%E4%BB%B6%E5%8F%91%E9%80%81%E9%80%9A%E7%9F%A5 h_01JQ6EQR8JRBZ2ECJ7SHHWDWFC=%E4%BB%85%E9%80%9A%E8%BF%87%E9%82%AE%E4%BB%B6%E5%8F%91%E9%80%81%E9%80%9A%E7%9F%A5 h_01JQ667RAW48YQ64VXW899EW3X=slack-notification" />
