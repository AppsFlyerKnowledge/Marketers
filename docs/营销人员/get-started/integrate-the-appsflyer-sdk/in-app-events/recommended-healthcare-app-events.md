---
title: 医疗保健类应用事件推荐
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
  created_at: '2021-05-01T10:41:05Z'
  edited_at: '2026-10-14T10:12:03Z'
  id: 360019888518
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/360019888518
---
> **概要：** 概览： 通过为您的医疗保健应用程序记录这些建议的应用内事件，评估用户在整个用户路径中的质量。


<span id="-healthcare"></span><span id="healthcare"></span>用户可以使用医疗保健类应用执行各种操作，如购买医疗保险、预约挂号、在线问诊等等。在这类应用中，建议您记录登录、注册和其他不涉及个人或医疗信息的常规事件。

<div id="important" />

> 🚧 **重要提示！**
>
> * 如需详细的开发人员指南，请在<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyer开发者资源中心</Anchor>查找。
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

![In_appEvents_UserJourneys_-_Copy_of_Healthcare__1_.png](https://files.readme.io/54174e697c8dfe2d0d388c19fdd5fa0fbf9703c0155b9c250b40b5d0bcf19698-8232949117073.png)

<div id="recommended-structures-for-predefined-events" />

## 预定义事件的推荐结构

以下部分提供医疗保健垂直营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

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

用户完成注册过程时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_registration\_method | 注册方式的类型 | 电子邮件，Facebook |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="添加到购物车（af_add_to_cart）">

**作用**

此事件可以帮助您确定：

* 购买者在一次购买中平均添加多少产品
* 添加两种不同产品之间的时间间隔是多少
* 有多少购买者放弃购物车

**触发**

用户将产品添加到购物车时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_quantity | 订购数值 | 1 |
| af\_price | 产品价格 | 10 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="购买（af_purchase）">

**作用**

此事件可以帮助您：

* 确定用户的LTV以及您通过广告平台和广告代理投放广告活动的ROI
* 确定哪些项目最受用户欢迎
* 横向对比带有购买内容的广告活动，以优化广告活动定向

**触发**

用户在成功购买后进入“感谢页面”时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 购买收入 | 50.55 |
| af\_currency | 货币代码 | USD |
| af\_order\_id | Order ID | 9277 |
| payment\_method\_type | 使用的付款方式 | 信用卡，本地 |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## 自定义事件的推荐结构

以下章节说明了事件的构成，包括自定义事件名称以及推荐使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

**作用**

充值资金可用于购买应用内提供的任何套餐或任何其他服务。 您可以记录用户充值并将其与其他数据进行比较，以了解有关用户的更多信息。

**触发**

用户完成充值时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 充值金额 | 2000.55 |
| top\_up\_id | 充值ID | 397 |
| payment\_method\_type | 使用的付款方式 | 信用卡，本地付款 |

<div data-zendesk-anchors="h_01HGTAFRKKJ22SHB4JHMTGW2TV=healthcare h_01HGTAFRKKPWC1PQTKF227WWBD=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAFRKKRB8EY8KJ9NXM4Z2T=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAFRKK35Q5W5ADQC2KYHR9=login-af_login h_01HGTAFRKK8E52FRVWQXP4Y3VV=complete-registration-af_complete_registration h_01HGTAFRKN6NJPDB053YYYH202=add-to-cart-af_add_to_cart h_01HGTAFRKNJVFECSFGSWG8B7GN=purchase-af_purchase recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAFRKN29RJRW2V2WCH2AXT=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84" />
