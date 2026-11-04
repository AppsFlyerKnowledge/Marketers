---
title: 体育博彩类应用内事件推荐
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-11T13:24:45Z'
  edited_at: '2026-10-14T10:08:15Z'
  id: 4410672219025
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410672219025
---
> **概要：** 本文针对电子类钱包应用提供了事件记录推荐，帮助您衡量全链路的用户质量。


<span id="-sports-betting"></span><span id="sports-betting"></span>记录事件可以帮助您确定：

* 用户进行互动的程度如何

<div id="important" />

> 🚧 **重要提示！**
>
> * 如需详细的开发人员指南，请在**AppsFlyer开发者资源中心**查找<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">。</Anchor>
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

[![In_appEvents_UserJourneys_-_Sports_betting__5_.png](https://files.readme.io/7a47ba917ebc5a6e661efb23b078675c16ce43c59c41f9c6fd6fd89d37c242bf-4424606611473.png)](https://files.readme.io/7a47ba917ebc5a6e661efb23b078675c16ce43c59c41f9c6fd6fd89d37c242bf-4424606611473.png)

<div id="recommended-structures-for-predefined-events" />

## 预定义事件的推荐结构

以下部分提供P2P借贷垂直营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="login-af_login" />

<Accordion title="登录（af_login）">

**作用**

了解注册用户的留存情况

**触发**

每当用户成功登录时

**事件参数**

可在无需任何其他参数的情况下发送

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="完成注册（af_complete_registration）">

**作用**

了解有多少用户安装了该应用程序并完成了注册过程，以及用户喜欢什么注册方式。

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_registration\_method | 注册方式的类型 | 电子邮件，Facebook |

</Accordion>

<div id="account-credited-account_credited" />

<div id="account-deducted-account_deducted" />

<div id="cancels-bet-canceled_bet" />

<div id="bonus-bet-bonus_bet" />

<div id="withdrawal-withdrawal" />

<div id="placed-bet-placed_bet" />

<div id="deposit-deposit" />

<div id="first-time-deposit-first_time_deposit" />

<div id="recommended-structures-for-custom-events" />

## 自定义事件的推荐结构

请注意，应用内事件可以包括满足您业务需求的任何事件参数。

**作用**

记录此事件可以帮助您确定：

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> |  | 200 |
| af\_currency |  |  |


**作用**

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> |  | 200 |
| af\_currency |  |  |


**作用**

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price |  | 100 |
| af\_currency |  |  |
| event\_number |  | 123789 |
| event\_date |  | 13122021 |
| event\_time |  | 17:30 |
| transaction\_id |  | 221 |


**作用**

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> |  | -100 |
| af\_currency |  |  |


**作用**

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price |  | 100 |
| af\_currency |  |  |
| event\_number |  | 123789 |
| event\_date |  | 13122021 |
| event\_time |  | 17:30 |
| bonus\_id |  | 221 |


**作用**

此事件可以帮助您：

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price |  | 100 |
| af\_currency |  |  |
| event\_number |  | 123789 |
| event\_date |  | 13122021 |
| event\_time |  | 17:30 |


**作用**

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price |  | 100 |
| af\_currency |  |  |
| account\_number |  | 15780 |
| event\_number |  | 123789 |
| event\_date |  | 13122021 |
| event\_time |  | 17:30 |


**作用**

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price |  | 100 |
| af\_currency |  |  |
| account\_number |  | 15780 |
| event\_number |  | 123789 |
| event\_date |  | 13122021 |
| event\_time |  | 17:30 |

<div data-zendesk-anchors="h_01HGTAE0AT9KD9RKX7XPR7A4AT=sports-betting h_01HGTAE0ATTMEART2R1BD1ZDSB=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAE0ATYW0RDDZZD5EAR7BZ=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAE0ATMBJVKS14SGWGK0DG=login-af_login h_01HGTAE0ATHZWSM0R9A6R9BV96=complete-registration-af_complete_registration recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAE0ATJQDWWBB8D836QRJ5=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84" />
