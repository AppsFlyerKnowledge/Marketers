---
title: 电商类应用内事件推荐
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
  created_at: '2021-04-19T06:32:18Z'
  edited_at: '2026-10-14T10:06:17Z'
  id: 360019347957
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/360019347957
---
> **概览：** 通过为您的电子商务应用程序记录这些建议的应用内事件，评估用户在整个用户路径中的质量。

## <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="67px" /> eCommerce

电商类应用允许购买者在网上轻松的搜索并购买商品。我们建议记录的典型事件有搜索、购买、添加到购物车和添加到愿望列表。

记录事件可以帮助您确定：

* 最受欢迎的类别
* 买家正在寻找什么
* 有多少买家完成了付费
* 有多少买家是回头客，有多少一次性买家

> 🚧 **重要提示！**
>
> * 请阅读面向营销人员的<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#设置应用内事件">操作指南</Anchor>，以了解如何设置应用内事件。
> * 为简化设置过程，请使用我们的<Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce">应用内事件生成器</Anchor>。该工具涵盖本文中介绍的所有常见应用内事件，您可以根据业务需求进行调整。完成后，请将文件分享给开发人员。
> * 对于本文中推荐的每个事件，我们都提供了<Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce&view=code">iOS、Android 和 Unity 开发者可用的代码示例</Anchor>。
> * 如需详细的开发人员指南，请在<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">**AppsFlyer开发者资源中心**</Anchor>**查找。**
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

[![Flowchart_for_recommended_events e-Commerce_app_user_journey](https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png)](https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png)

## 预定义事件的推荐结构

以下部分提供电商领域营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="complete-registration-af_complete_registration" />

<Accordion title="完成注册（af_complete_registration）">

**作用**

了解有多少用户安装了该应用程序并完成了注册过程，以及用户喜欢什么注册方式。

**触发**

用户完成注册过程时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_registration\_method | 注册方式的类型 | 电子邮件，Meta广告 |

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

了解用户在寻找什么，哪些搜索结果最相关并促成购买。

**触发**

以下内容之一：

* 当用户点击搜索按钮时
* 当用户进入搜索结果页面时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_search\_string | 搜索词 | Red dress, running shoes |
| af\_content\_list | 内容ID列表 | 001, 092 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="内容浏览（af_content_view）">

**作用**

确定特定产品的浏览率。此事件可以帮助您：

* 将产品浏览量与产品销售相关联
* 根据产品浏览量了解哪些类别最受欢迎
* 查看买家的币种与他们查看的产品之间的相关性

**触发**

用户查看特定的产品详细信息页面时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price | 产品价格 | 2000 |
| af\_content | 国际商品条码（EAN）或其他产品或内容标识符。<br /><br />**Meta广告动态广告的必要参数** | ABC123 |
| af\_content\_id | Product ID<br /><br />**Meta广告动态广告的必要参数** | 102 |
| af\_content\_type | 商品类别<br /><br />**Meta广告动态广告的必要参数**  <br />  <br />**请注意：** 将`af_content_type`映射到Meta的`fb_content_type`时，唯一支持的值是`product`或`product_group`。 | Shoes |
| af\_currency | 产品详细信息页面中的币种 | THB, USD |

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="列表浏览（af_list_view）">

**作用**

记录买家查看最多的列表（例如，新添加的产品、相关产品或推荐产品）。

**触发**

用户查看特定列表时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_content\_type | 商品类别<br /><br />**Meta广告动态广告的必要参数**  <br />  <br />**请注意：** 将`af_content_type`映射到Meta的`fb_content_type`时，唯一支持的值是`product`或`product_group`。 | Related, recommended, new arrivals |
| af\_content\_list | 类别中的内容ID列表 | 001, 092 |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="添加到愿望列表（af_add_to_wishlist）">

**作用**

记录买家将哪些产品和类别添加到他们的愿望列表。当你知道哪些产品经常被添加到愿望清单中时, 你可以在促销或折扣中提供这些产品, 并鼓励买家购买。您还可以根据用户添加到他们的愿望列表中的产品向他们进行重定向营销。

**触发**

当用户将商品添加到愿望列表时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price | 产品价格 | 600 |
| af\_content\_id | Product ID | 300 |
| af\_content\_type | 商品类别<br /><br />**Meta广告动态广告的必要参数**  <br />  <br />**请注意：** 将`af_content_type`映射到Meta的`fb_content_type`时，唯一支持的值是`product`或`product_group`。 | Shoes, electronics |
| af\_currency | 产品详细信息页面上显示的币种 | GBP |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="添加到购物车（af_add_to_cart）">

**作用**

记录当用户将产品添加到购物车时。此事件可以帮助您确定：

* 购买者在一次购买中平均添加多少产品
* 添加两种不同产品之间的时间间隔是多少
* 有多少购买者放弃购物车

**触发**

用户将产品添加到购物车时

**事件参数**

| 字段名称 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price | 产品价格 | 350, 1000 |
| af\_content | 国际商品条码（EAN）或其他产品或内容标识符。<br /><br />**Meta广告动态广告的必要参数** | ABC123 |
| af\_content\_id | Product ID<br /><br />**Meta广告动态广告的必要参数** | 001, 092 |
| af\_content\_type | 商品类别<br /><br />**Meta广告动态广告的必要参数**  <br />  <br />**请注意：** 将`af_content_type`映射到Meta的`fb_content_type`时，唯一支持的值是`product`或`product_group`。 | Shirt, shoes |
| af\_currency | 产品币种 | THB, USD |
| af\_quantity | 同一产品的多少个商品被添加到购物车 | 2, 5 |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="发起结帐（af_initiated_checkout）">

**作用**

了解买家在结账过程中的行为。此事件可以帮助您确定：

* 与购买事件中的平均价格相比较买家结帐时的平均价格
* 用户是否在继续结帐后添加或删除产品

**触发**

当用户准备结账但并没有完成结账时

**事件参数**

| 字段名称 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price | 购物车中的总价 | 4000 |
| af\_content\_id | 购物车中产品的 ID | 221, 124 |
| af\_content\_type | 商品类别<br /><br />**Meta广告动态广告的必要参数**  <br />  <br />**请注意：** 将`af_content_type`映射到Meta的`fb_content_type`时，唯一支持的值是`product`或`product_group`。 | Shirt, pants |
| af\_currency | 结帐时的货币 | THB |
| af\_quantity | 购物车中的商品总数 | 2, 5 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="购买（af_purchase）">

**作用**

了解您应用程序中的购买趋势。此事件可以帮助您：

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
| af\_content | 国际商品条码（EAN）或其他产品或内容标识符。<br /><br />**Meta广告的必要参数** **动态广告** | ABC123 |
| af\_content\_id | 商品编号<br /><br />**Meta广告动态广告的必要参数** | 121, 262 |
| af\_content\_type | 商品类别<br /><br />**Meta广告动态广告的必要参数**  <br />  <br />**请注意：** 将`af_content_type`映射到Meta的`fb_content_type`时，唯一支持的值是`product`或`product_group`。 | Shoes, pants |
| af\_currency | 货币代码 | AUD |
| af\_quantity | 购物车中的商品数量 | 2, 5 |
| af\_order\_id | 购买后生成的订单ID | X123ABC |
| af\_receipt\_id | Order ID<br /><br />**用于验证购买行为的 CRITEO 和 Google Ads 所需参数** | X123ABC |

</Accordion>

## 自定义事件的推荐结构

以下部分提供事件结构列表，其中包括自定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="first-purchase-first_purchase" />

<Accordion title="首次购买(first_purchase)">

**作用**

与[购买](/docs/recommended-ecommerce-app-events#purchase-af_purchase)事件相同。此外，此事件可以帮助您确定：

* 新买家需要多长时间完成购买
* 新买家更喜欢购买哪些产品
* 首次购买的平均价格和收入

**触发**

用户完成首次购买时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 购买收入 | 1205.99 |
| af\_price | 总购买额 | 4000 |
| af\_content | 国际商品条码（EAN）或其他产品或内容标识符。<br /><br />**Meta广告动态广告的必要参数** | ABC123 |
| af\_content\_id | 商品编号<br /><br />**Meta广告动态广告的必要参数** | 121, 262 |
| af\_content\_type | 商品类别<br /><br />**Meta广告动态广告的必要参数**  <br />  <br />**请注意：** 将`af_content_type`映射到Meta的`fb_content_type`时，唯一支持的值是`product`或`product_group`。 | Shoes, pants |
| af\_currency | 币种 | AUD |
| af\_quantity | 购物车中的商品数量 | 2, 5 |
| af\_order\_id | 购买后生成的订单ID | X123ABC |
| af\_receipt\_id | Order ID<br /><br />**对接CRITEO和Google AdWords再营销功能所需的参数** | X123ABC |

</Accordion>

<div id="remove-from-cart-remove_from_cart" />

<Accordion title="从购物车中移除(remove_from_cart)">

**作用**

记录此事件可以帮助您：

* 确定买家从购物车中移除了哪些商品
* 确定买家从购物车中移除商品的产品类别
* 比较从[添加到购物车](/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart)事件获取的数据，以深入分析那些没有最终结账的产品

**触发**

用户从购物车中移除商品时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_content\_id | 商品或产品 ID | 521 |
| af\_content\_type | 商品类别<br /><br />**Meta广告动态广告的必要参数**  <br />  <br />**请注意：** 将`af_content_type`映射到Meta的`fb_content_type`时，唯一支持的值是`product`或`product_group`。 | Shoes |

</Accordion>

<div data-zendesk-anchors="ecommerce=-ecommerce h_01HGTAWG2166CZYKJE9166G12J=-ecommerce h_01HGTAWG21Z0C9SR2G54W68G8Q=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAWG2115VB3A8J2WG3DJKK=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAWG21EQ0FE40WGFJRDJY5=complete-registration-af_complete_registration h_01HGTAWG22HFZ24V2BDCH3RFN8=login-af_login h_01HGTAWG22B5Z9AXENDATKR67T=search-af_search h_01HGTAWG22PSKS80ZQNAC0K24M=content-view-af_content_view h_01HGTAWG2219SVQ86PT1K3TVV9=list-view-af_list_view h_01HGTAWG22EQMVWXJCXC2KQDX8=add-to-wishlist-af_add_to_wishlist h_01HGTAWG23T81SPFJEA6BY5F2W=add-to-cart-af_add_to_cart h_01HGTAWG23FPKQ6RHJ9VYET63Y=initiated-checkout-af_initiated_checkout h_01HGTAWG2385E9Q0FXZXEW38YK=purchase-af_purchase recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAWG235EXE17EJ5DWQYERM=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAWG23NTG0Q70B9A3685AD=first-purchase-first_purchase h_01HGTAWG239TQ51Z7FQW4FC1TZ=remove-from-cart-remove_from_cart" />
