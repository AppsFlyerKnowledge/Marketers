---
title: 酒店预订类应用事件推荐
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
  created_at: '2021-04-29T14:49:54Z'
  edited_at: '2026-10-14T10:12:41Z'
  id: 360019843558
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/360019843558
---
> **概要：** 概览： 通过为您的酒店预订应用程序记录这些建议的应用内事件，评估用户在整个用户路径中的质量。


<span id="-hotel-booking"></span><span id="hotel-booking"></span>航班预订 App 允许旅客轻松预订航班, 同时从最优价格中进行选择。

记录事件可以帮助您确定：

* 哪些广告活动和媒体渠道带来实际预订假期的用户
* 哪些广告活动和媒体渠道带来预订最多的用户和更多的收入

您可以将酒店分数、季节、国家和随行未成年人等偏好数据归因到特定的媒体渠道。

<div id="important" />

> 🚧 **重要提示！**
>
> * 如需详细的开发人员指南，请在**AppsFlyer开发者资源中心**查找<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">。</Anchor>
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

<div id="recommended-structures-for-predefined-events" />

## 预定义事件的推荐结构

以下部分提供P2P借贷垂直营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="complete-registration-af_complete_registration" />

<Accordion title="完成注册（af_complete_registration）">

**作用**

了解有多少用户安装了该应用程序并完成了注册过程，用户偏爱什么注册方式，以及哪些媒体渠道带来了实际注册的用户。

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

<div id="search-af_search" />

<Accordion title="搜索（af_search）">

**作用**

了解用户在寻找什么，哪些搜索结果最相关并促成购买。此外，您还可以查看特定地理位置的用户正在搜索的内容，并跨媒体渠道相应地将其定位。

**触发**

用户执行搜索时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_date\_a | 入住日期 | 2018/07/26 |
| af\_date\_b | 退房日期 | 2018/08/01 |
| af\_destination\_a | 用户位置 | 伦敦 |
| af\_destination\_b | 酒店地点 | Madrid |
| af\_num\_adults | 入住人数 | 2 |
| af\_num\_children | 儿童人数 | 0 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="内容浏览（af_content_view）">

**作用**

此事件可以帮助您确定：

* 搜索结果是否与搜索查询相关
* 用户正在寻找哪些酒店类型
* 季节性趋势
* 热门地点
* 哪些媒体渠道带来用户，然后在广告和促销活动中重新定位这些用户

**触发**

用户查看酒店时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price | 酒店的标价 | 674 |
| af\_content\_id | 酒店的ID |  |
| af\_date\_a | 入住日期 | 2018/07/26 |
| af\_date\_b | 退房日期 | 2018/08/01 |
| af\_destination\_a | 用户位置 | 伦敦 |
| af\_destination\_b | 酒店地点 | Madrid |
| af\_class | 房型 | Deluxe |
| af\_num\_adults | 入住人数 | 2 |
| af\_num\_children | 儿童人数 | 0 |
| af\_hotel\_score | 用户评价中对酒店的评分 | 9.6 |
| af\_preferred\_star\_ratings | 首选酒店星级 | 5 |
| af\_preferred\_neighborhoods | 酒店所在的区域 | Centro |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="添加到种草清单（af_add_to_wishlist）">

**作用**

**触发**

用户添加到他们的愿望列表时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price | 酒店的标价 | 674 |
| af\_content\_id | 酒店的ID |  |
| af\_date\_a | 入住日期 | 2018/07/26 |
| af\_date\_b | 退房日期 | 2018/08/01 |
| af\_destination\_a | 用户位置 | 伦敦 |
| af\_destination\_b | 酒店地点 | Madrid |
| af\_class | 房型 | Deluxe |
| af\_num\_adults | 入住人数 | 2 |
| af\_num\_children | 儿童人数 | 0 |
| af\_hotel\_score | 用户评价中对酒店的评分 | 9.6 |
| af\_preferred\_star\_ratings | 首选酒店星级 | 5 |
| af\_preferred\_neighborhoods | 酒店所在的区域 | Centro |
| purchase\_method | 购买方式 | Credit card |
| af\_coupon\_code | 促销代码或会员积分 | SUM2018 |
| property\_type | 酒店类型 | Hotel |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="发起结帐（af_initiated_checkout）">

**作用**

此事件可以帮助您确定：

* 使用了哪种购买方式，例如信用卡或电子钱包
* 用户是否完成结帐过程

**触发**

用户添加信用卡信息或连接电子钱包时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price | 酒店的标价 | 674 |
| af\_content\_id | 酒店的ID |  |
| af\_date\_a | 入住日期 | 2018/07/26 |
| af\_date\_b | 退房日期 | 2018/08/01 |
| af\_destination\_a | 用户位置 | 伦敦 |
| af\_destination\_b | 酒店地点 | Madrid |
| af\_class | 房型 | Deluxe |
| af\_num\_adults | 入住人数 | 2 |
| af\_num\_children | 儿童人数 | 0 |
| af\_hotel\_score | 用户评价中对酒店的评分 | 9.6 |
| af\_preferred\_star\_ratings | 首选酒店星级 | 5 |
| af\_preferred\_neighborhoods | 酒店所在的区域 | Centro |
| purchase\_method | 购买方式 | Credit card |
| af\_coupon\_code | 促销代码或会员积分 | SUM2018 |
| property\_type | 酒店类型 | Hotel |

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
| af\_content\_type | 商品类别 | Hotel |
| af\_currency | 货币代码 |  |
| af\_quantity | 购物车中的商品数量 | 1 |
| af\_order\_id | 购买后生成的订单ID | X123ABC |
| af\_receipt\_id | 订单ID， 需要CRITEO和Google Ad Words再营销对接 | X123ABC |

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="行程预订（af_travel_booking）">

**作用**

此事件可以帮助您：

* 记录预订带来的收入。
* 确定携带儿童预订酒店的用户数量
* 确定热门酒店

**触发**

用户在预订酒店后到达“感谢页面”时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 预定产生的收入 | 647.95 |
| af\_currency | 货币代码 | GBP |
| af\_price | 酒店的标价 | 674 |
| af\_content\_id | 酒店的ID |  |
| af\_date\_a | 2018/07/26 | 入住日期 |
| af\_date\_b | 退房日期 | 2018/08/01 |
| af\_destination\_a | 用户位置 | 伦敦 |
| af\_destination\_b | 酒店地点 | Madrid |
| af\_class | 房型 | Deluxe |
| af\_num\_adults | 入住人数 | 2 |
| af\_num\_children | 儿童人数 | 0 |
| af\_hotel\_score | 用户评价中对酒店的评分 | 9.6 |
| af\_preferred\_star\_ratings | 首选酒店星级 | 5 |
| af\_preferred\_neighborhoods | 酒店所在的区域 | Centro |
| purchase\_method | 购买方式 | Credit card |
| af\_coupon\_code | 促销代码或会员积分 | SUM2018 |
| property\_type | 酒店类型 | Hotel |
|  |  | true |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## 自定义事件的推荐结构

以下部分提供事件结构列表，其中包括自定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="first-purchase-first_purchase" />

<Accordion title="首次购买(first_purchase)">

**作用**

* 新买家需要多长时间完成购买
* 新买家更喜欢购买哪些产品
* 首次购买的平均价格和收入

**触发**

用户完成首次购买时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 购买收入 | 1205.95 |
| af\_price | 总购买额 | 4000 |
| af\_content\_id | 商品编号 | 21 |
| af\_content\_type | 商品类别 | Hotel |
| af\_currency | 货币 |  |
| af\_quantity | 购物车中的商品数量 | 1 |
| af\_order\_id | 购买后生成的订单ID | X123ABC |
| af\_receipt\_id | 订单ID，需要CRITEO和Google AdWords再营销对接 | X123ABC |

</Accordion>

<div data-zendesk-anchors="h_01HGTB0APWWTRER6GAWJ7TJ05S=hotel-booking h_01HGTB0APWQDX7VN96GM7520ZH=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTB0APW933179Q90HFASW1V=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTB0APWRKRGCJ5TFKTPHH33=complete-registration-af_complete_registration h_01HGTB0APW1XY5R69CJ8PSQV6C=login-af_login h_01HGTB0APW5YF2DASC0HYDPTA9=search-af_search h_01HGTB0APXTQWBS4EXJ8D724G0=content-view-af_content_view h_01HGTB0APXS95QGK17RE8B3Y1E=add-to-wishlist-af_add_to_wishlist h_01HGTB0APX1XX2W3YX85W75F6B=initiated-checkout-af_initiated_checkout h_01HGTB0APXGPW16FRY3C7VSMDM=purchase-af_purchase h_01HGTB0APXJFHMPGYC63ZTV4R9=travel-booking-af_travel_booking recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTB0APXP6WVM1AVEMEY6KVS=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTB0APX4ND0NGVTK9FA38QR=first-purchase-first_purchase" />
