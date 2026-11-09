---
title: 使用OneLink API创建批量投放链接
metadata:
  keywords:
    - api
    - Premium
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Premium
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2018-06-27T12:00:29Z'
  edited_at: '2026-10-14T10:07:41Z'
  id: 360001250345
  locale: zh-cn
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001250345
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** OneLink API可以生成大量个性化链接，用于大规模广告投放，帮助您提高自有媒体的利用率，有效吸引终端用户。该解决方案需要市场人员和开发人员共同实施。

<div id="referral-and-advocate-sharing" />

<div id="offline-and-qrbased-engagement" />

<div id="crmpowered-channels-sms-email-whatsapp" />

<div id="crossplatform-journeys-ctv-desktop-webtoapp" />

<div id="traits-and-limitations" />

<div id="use-cases" />

<div id="dashboard" />

<div id="get-started" />

<div id="example" />

<div id="about-onelink-api" />

## OneLink API

OneLink API是一个高阶功能，可用于：

* 自动<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">创建</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">获取</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">更新</Anchor>和<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">删除</Anchor>带有自定义参数的OneLink短链。  
  这里的参数包括以下两种：
  * 与归因有关的参数，用于衡量并监测营销成效，如媒体渠道、广告系列和广告组等参数。**请注意**：必须配置媒体渠道（pid）参数。
  * 个性化参数，用于配置个性化的用户体验。您可以使用这些参数，引导用户点击相关链接后直接进入应用内为其定制的内容，如特定的产品页面、优惠券码或促销活动。
* 可将网页和应用内容直接分享给移动端用户，从而提升移动端的用户互动和激活。
* 快速生成大量的OneLink自定义归因链接。  
  **请注意**：如需了解推荐链接的详细信息，请参考<Anchor target="_blank" href="/marketers/zh/docs/user-invite-attribution">用户邀请归因</Anchor>说明。

> 📄 **示例**
>
> 一个名为Feed Me的生鲜配送服务平台希望通过短信向现有用户发送个性化链接，引导他们下载其应用并在应用中购买香蕉。Feed Me通过OneLink REST API根据用户所在的国家/地区配置了自定义OneLink链接，其中包含用户所在国家/地区、用户身份和香蕉折扣的详细信息。

OneLink API的调用频次上限取决于您的账户类型。您可以在OneLink API面板中查看您已经使用的次数以及剩余额度。

如需提高API调用频次上限，请联系您的CSM。

### 设置

**请按以下方式设置OneLink API：**

1. <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">创建一个OneLink模板</Anchor>。
2. 复制OneLink模板ID。  
   <Image align="center" alt="" src="https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg" />
3. 复制<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens#token类型">OneLink API token</Anchor>。为了保障数据安全，必须由管理员用户来提取这个API key，因为账户下的其他用户没有API key的访问权限。
4. 将OneLink ID和OneLink API token发送给开发人员。
5. 请开发人员按照<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelink_rest_api">开发者资源中心中的指南进行操作</Anchor> 。

### 面板

OneLink API面板会显示日度、月度和季度的API使用情况。

**OneLink API面板的查看方式如下**：

从AppsFlyer后台的侧边栏中选择**互动** > **OneLink API**。

### 特点与局限性

| 特点 | 说明 |
| --- | --- |
| API调用频次限制 | <ul><li>使用OneLink API创建、编辑或删除OneLink链接的频次上限为每个账户每月（以UTC时间为准）750万次。</li><li>超过该限额后的所有请求AF皆不会响应，也不会创建相应的链接；调用API后会返回错误状态码429，报错消息为“Monthly quota exceeded”（超过月度限额）。</li><li>如需了解限额使用情况以及剩余额度，请在OneLink API面板中查看。</li></ul> |
| 频次限制 | <ul><li>账户层级的API请求频次为每秒500次（每分钟3万次）。</li><li>超过每秒500个请求（每分钟3万次）的限额后，AF就不会响应任何请求，也不会创建相应的链接；调用API后会返回错误状态码429，报错消息为“Monthly quota exceeded”（超过月度限额）。</li></ul> |
| 链接可见性 | <ul><li>通过该API创建的链接不会出现在AppsFlyer面板的OneLink自定义链接列表中。</li><li>推荐方式：将通过API创建的链接保存到本地图表，便于后续查看使用。</li></ul> |
| TTL | <ul><li>通过OneLink API的OneLink短链默认有效期（TTL）为31天。每次有用户点击该链接时，有效期就会自动延长31天。若有用户在TTL过期后点击链接，该链接仍可根据您设定的OneLink基础配置进行跳转，但无法再进行归因。<ul><li>OneLink短链会在TTL过期后的48小时内完成删除。</li></ul></li><li>TTL的上限为31天。即使您设置了超过31天的TTL值，这个值仍会自动还原到默认的31天。</li><li>如需更改默认TTL，可以添加参数`ttl={value}`，指定TTL的天数、小时数或分钟数。比如`ttl=7d`、`ttl=12h`或`ttl=10m`。</li><li>您可以通过发送<Anchor target="_blank" href="https://dev.appsflyer.com/reference/onelink_rest_api#update-onelink-attribution-link">更新请求</Anchor>来设定TTL。发送更新请求后，AF会将现有链接的TTL重置为请求主体（request body）中指定的值。<ul><li>也就是说发送该请求后，TTL会被替换为您指定的值。举例来说，假设目前您现有链接的TTL值为29d，这时您发送了一个TTL值为2d的更新请求，那么这些链接的TTL值就会变成TTL=2d（而非31d）。</li><li>发送更新请求可以延长归因链接的效期。举例来说，假设您目前的链接TTL为20d，且距该链接上线已有5天，这时您发送一个TTL为31d的更新请求，那么该链接的TTL会从更新发生的时间开始重新计算这31天。</li></ul></li><li>如果您不想让TTL自动延期，请在链接中添加`renew_ttl=false`参数。该参数的值为布尔值，即true（默认值）或false。</li><li>`renew_ttl`参数不会出现在实际链接中。</li></ul> |
| 特殊字符 | 使用API创建链接时，若使用以下字符，须对其编码： ;、*、!、@、#、?、$、^、:、&、~、\`、=、+、'、>、 &lt;、/<br />若未编码，这些字符会变成空格，相关功能可能无法正常使用，导致跳转失败。<br /><br />**请注意：** 用户点击链接后，下列3个参数仍会保持编码后的状态，不会被解码：<ul><li>\`af_dp\`</li><li>\`deep_link_value\`</li><li>\`deep_link_sub1\`</li></ul> |
| 有效信息 | 有效信息（payload）中的查询参数字符串不能超过2048个字符。 |
| URL ID | 您可以更改URL ID（即短链ID），以凸显您的推广内容，如：[https://myapp.onelink.me/abc123/apples](https://myapp.onelink.me/abc123/apples)。URL ID不能超过50个字符，可以同时包含字母和数字。默认长度为8个字符。<br /><br />请注意：<ul><li>您仅可更改当前未被使用的URL ID。</li><li>如果相关的URL ID已经在使用中，则调用API后无法创建链接，并返回错误响应码（400）。发生这种情况时，您需要与您的开发人员共同决定后续如何配置。</li><li>即使调用失败，仍会从您的月度API限额中扣除相应的次数。</li></ul> |