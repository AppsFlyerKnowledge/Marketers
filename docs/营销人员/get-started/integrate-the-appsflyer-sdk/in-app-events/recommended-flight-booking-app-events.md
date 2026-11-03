---
title: 机票预订类应用内事件推荐
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
  created_at: '2021-04-29T13:07:29Z'
  edited_at: '2026-10-14T10:04:45Z'
  id: 360019670857
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/360019670857
---
> **概要：** 概览：通过为您的航班预订应用程序记录这些建议的应用内事件，评估用户在整个用户路径中的质量。


<span id="flight-booking"></span>航班预订 App 允许旅客轻松预订航班, 同时从最优价格中进行选择。

记录事件可以帮助您：

* 了解热门目的地
* 分析季节性趋势
* 了解用户偏爱的热门航空公司

> 🚧 **重要提示！**
>
> * 如需详细的开发人员指南，请在**AppsFlyer开发者资源中心**查找<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">。</Anchor>
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

## 预定义事件的推荐结构

以下部分提供P2P借贷垂直营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="complete-registration-af_complete_registration" />

<Accordion title="完成注册（af_complete_registration）">

**作用**

了解有多少用户安装了该应用程序并完成了注册过程，用户喜欢什么注册方式。

**触发**

用户完成注册过程时

事件参数

| 字段名称 | 说明 | 示例值 |
| --- | --- | --- |
| af\_registration\_method | 注册方式的类型 | 电子邮件，Facebook |

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

<div id="travel-booking-af_travel_booking" />

<Accordion title="行程预订（af_travel_booking）">

**作用**

预定航班是此 App 最核心的一项功能。此事件可以帮助您确定：

* 热门目的地
* 热门航空公司
* 季节性趋势

**触发**

用户在成功预定航班后进入“感谢页面”时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 航班预订的金额 | 647.99 |
| af\_currency | 货币代码 | SGD |
| af\_price | 价格 | 674 |
| af\_content\_id | 航班报价的ID |  |
| af\_departing\_departure\_date | 出发日期 | 2018-06-21 |
| af\_returning\_departure\_date | 返程日期 | 2018-06-26 |
| af\_destination\_a | 第一个目的地 |  |
| af\_destination\_b | 第二个目的地（如适用） | SYD |
| airline\_code | 航空公司代码 | KLM |
| af\_class | 预定航班的舱位 | economy |
| purchase\_method | 购买方式 | credit card |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="内容浏览（af_content_view）">

**作用**

此事件可以帮助您确定：

* 了解用户觉得最吸引人的航班。
* 搜索结果是否与搜索查询相关

**触发**

用户点击搜索结果时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_departing\_departure\_date | 出发日期 | 2018-06-21 |
| af\_returning\_departure\_date | 返程日期 | 2018-06-26 |
| af\_destination\_a | 第一个目的地 |  |
| af\_destination\_b | 第二个目的地（如适用） | SYD |

</Accordion>

<div id="search-af_search" />

<Accordion title="搜索（af_search）">

**作用**

航班预订应用程序允许用户搜索航班及优惠信息。洞悉用户喜好的其中一种方法就是记录搜索参数。此事件可以帮助您：

* 了解用户正在寻找什么
* 了解哪些目的地最受欢迎
* 查看有多少携带儿童旅行的用户
* 查看用户喜欢或计划在一年中的哪个时间旅行

**触发**

用户填写搜索表单并点击搜索按钮后

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_num\_children | 正在旅行的儿童人数 | 0 |
| af\_destination\_a | 第一个目的地 |  |
| af\_destination\_b | 第二个目的地 (如相关) | SYD |
| af\_departing\_departure\_date | 出发日期 | 2018-06-21 |
| af\_returning\_departure\_date | 返程日期 | 2018-06-26 |
| af\_num\_infants | 正在旅行的婴儿人数 | 0 |
| af\_num\_adults | 正在旅行的 成人人数 | 1 |

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="添加付款信息（af_add_payment_info）">

**作用**

记录预订航班时添加付款信息的成功和失败尝试。

**触发**

用户点击预订航班按钮时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_success | 添加付款方式是否成功 | true |

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
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 预计购买收入 | 1205.99 |
| af\_price | 总购买额 | 4000 |
| af\_content\_id | 商品编号 | 121 |
| af\_content\_type | 商品类别 | 航班 |
| af\_currency | 货币代码 |  |
| af\_quantity | 购物车中的商品数量 | 1 |
| af\_order\_id | 购买后生成的订单ID | X123ABC |
| af\_receipt\_id | 订单ID，需要CRITEO和Google AdWords再营销对接 | X123ABC |

</Accordion>

## 自定义事件的推荐结构

以下部分提供事件结构列表，其中包括自定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="first-purchase-first_purchase" />

<Accordion title="首次购买(first_purchase)">

**作用**

* 新买家需要多长时间完成购买
* 查看首次购买者更喜欢购买哪些航班。
* 首次购买的平均价格和收入

**触发**

用户完成首次购买时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 购买收入 | 1205.99 |
| af\_price | 总购买额 | 4000 |
| af\_content\_id | 商品编号 | 21 |
| af\_content\_type | 商品类别 | 航班 |
| af\_currency | 货币 |  |
| af\_quantity | 购物车中的商品数量 | 1 |
| af\_order\_id | 购买后生成的订单ID | X123ABC |
| af\_receipt\_id | 订单ID，需要CRITEO和Google AdWords再营销对接 | X123ABC |

</Accordion>

<div data-zendesk-anchors="h_01HGTAZRKG0SQ66XK7VN9KVGEY=flight-booking h_01HGTAZRKGGQBBAM4XJHR4B45P=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAZRKHK1427YX16HWRDRPN=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAZRKHACHNSNX9DSZ3ZZ51=complete-registration-af_complete_registration h_01HGTAZRKHTC9TNWNPACRZW31Y=login-af_login h_01HGTAZRKHZGW442XTZF99VGV9=travel-booking-af_travel_booking h_01HGTAZRKHGY0Z83ETZWAFNSWP=content-view-af_content_view h_01HGTAZRKH8JYE8Q6NDPF1PQC7=search-af_search h_01HGTAZRKH78CR2GH0960MS8R0=add-payment-info-af_add_payment_info h_01HGTAZRKHXE8VF78ZE0KF9AF6=purchase-af_purchase recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAZRKH4ZZEK5JGXZ7G5QDJ=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAZRKHG7GE4BKFDRHZC163=first-purchase-first_purchase" />
