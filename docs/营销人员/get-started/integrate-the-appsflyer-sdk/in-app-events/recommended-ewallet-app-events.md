---
title: 电子钱包类应用的事件记录推荐
metadata:
  keywords:
    - Advertisers
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
  created_at: '2021-06-10T11:36:07Z'
  edited_at: '2026-10-14T10:07:23Z'
  id: 4402425586065
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/4402425586065
---
> **概要：** 本文针对电子类钱包应用提供了事件记录推荐，帮助您衡量全链路的用户质量。

## <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="67px" /> eWallet

记录这些事件可以帮助您确定：

> 🚧 **重要提示！**
>
> * 如需详细的开发人员指南，请在**AppsFlyer开发者资源中心**查找<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">。</Anchor>
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

## 预定义事件的推荐结构

以下部分提供游戏业垂直营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="complete-registration-af_complete_registration" />

<Accordion title="完成注册（af_complete_registration）">

**作用**

了解有多少用户安装了该应用程序并完成了注册过程，以及用户喜欢什么注册方式。

**触发**

用户完成注册过程时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_registration\_method | 注册方式的类型 | 电子邮件，Facebook，Google |

</Accordion>

<div id="login-af_login" />

<Accordion title="登录（af_login）">

**作用**

了解注册用户的留存情况

**触发**

用户成功登录时

**事件参数**

可在无需任何其他参数的情况下发送

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="内容浏览（af_content_view）">

**作用**

此事件可以帮助您：

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| 注意事项 |  |  |
| merchant\_name |  | cineplex |

</Accordion>

## 自定义事件的推荐结构

以下部分提供事件结构列表，其中包括自定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

**作用**

充值资金可用于购买应用内提供的任何套餐或任何其他服务。

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| top\_up\_amount |  | 100 |
| top\_up\_method | 付款方式类型 |  |


**作用**

此事件可以帮助您：

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| 注意事项 |  |  |
| quantity | 已支付的金额 | 1 |
|  |  | 50 |


**作用**

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| merchant\_name |  |  |
| payment\_amount | 已支付的金额 | 100 |
| 类别 |  |  |


**作用**

此事件可以帮助您确定：

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| promo\_type |  | 停用 |


**作用**

此事件可以帮助您确定：

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| voucher\_ID |  | 1735103 |
| merchant\_name |  | cineplex |


**作用**

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| merchant\_name |  | cineplex |
| 类型 |  |  |
| Amount |  | USD |
| merchant\_ID |  | 123456 |


**作用**

此事件可以帮助您：

**触发**

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| merchant\_name |  | cineplex |
| merchant\_ID |  | 123456 |

<div data-zendesk-anchors="ewallet=-ewallet h_01HGTAEVWFZXCA7AV0P35W992F=-ewallet h_01HGTAEVWFR4QS6XAT1T28N1R5=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAEVWF8SVYTQMQ12219HX0=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAEVWFBA3CD7ZA40VCER95=complete-registration-af_complete_registration h_01HGTAEVWGDBN8B3P2YHQJ5RYF=login-af_login h_01HGTAEVWGYFYEZBD3ZED7GGFG=content-view-af_content_view recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAEVWG39P9A84P926BG3VE=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84" />
