---
title: 打车类应用事件推荐
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
  created_at: '2021-04-29T08:42:34Z'
  edited_at: '2026-10-14T10:05:22Z'
  id: 360019651957
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/360019651957
---
> **概要：** 概览：通过为您的网约车应用程序记录这些建议的应用内事件，评估用户在整个用户路径中的质量。


<span id="ridehailing"></span>共享出行最近变得非常流行, 尤其是在大多居民没有私家车的城市地区。

记录事件可以帮助您确定：

* 乘客和司机如何互动
* 更多使用您共享出行服务的国家。
* 有关价格、行程和乘车距离的指标

> 🚧 **重要提示！**
>
> * 如需详细的开发人员指南，请在**AppsFlyer开发者资源中心**查找<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">。</Anchor>
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

[![Flowchart_for_recommended_events_ride_hailing_app_user_journey](https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png)](https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png)

## 预定义事件的推荐结构

以下部分提供P2P借贷垂直营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="complete-registration-af_complete_registration" />

<Accordion title="完成注册（af_complete_registration）">

**作用**

此事件可以帮助您：

* 了解用户喜欢哪种注册方式
* 了解下载并安装应用程序后实际注册的用户数量
* 查看不同国家的注册趋势，用来确定哪些国家的用户更有可能使用您的应用。

**触发**

用户完成注册过程时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_registration\_method | 用户注册的平台或方式 | Facebook |
| country\_code | 国家/地区代码（电话代码） | 66 |

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

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="添加付款信息（af_add_payment_info）">

**作用**

您可以：

* 了解用户添加其付款信息需要多长时间
* 哪种付款方式最受欢迎，例如信用卡或电子钱包
* 设置广告活动并与最常用付款方式的供应商合作

**触发**

用户成功将付款信息添加到其账户时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_success | 付款方式是否成功 | true |
| credit\_card\_type | 信用卡类型 (可选) | Visa，Mastercard |
| payment\_method\_type | 付款方式类型 |  |

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="积分消费（af_spent_credits）">

**作用**

该参数记录乘客每次乘车所获取的积分。乘客可以用积分换取优惠券和折扣。

此事件可以帮助您：

* 查看有多少乘客用积分换取优惠券
* 查看乘客更喜欢哪类优惠券和折扣

**触发**

乘客消费积分时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_content | 优惠券或折扣的类型 | 单张电影票 |
| credits\_used | 使用多少积分 | 1000 |
| credits\_remaining | 账户剩余积分 | 2090 |
| invoice\_id | 为消费积分创建的发票ID | KO215123SD |

</Accordion>

## 自定义事件的推荐结构

以下部分提供事件结构列表，其中包括自定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="ride-booking-requested-ride_booking_requested" />

<Accordion title="已请求乘车预约(ride_booking_requested)">

**作用**

此事件可以帮助您：

* 了解热门目的地
* 了解趋势，人们乘车往返于何处
* 查看行程的平均距离
* 查看大多数用户来自哪些城市、地区和国家

此外, 记录此事件和其他三个和预订相关的事件可以帮助您记录成功的交易。例如, 您可以查看预订行程的数量, 以及有多少行程最终被完成或取消。

**触发**

乘客提出了乘车预订请求时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price | 行程的价格 | 22.4 |
| af\_currency | 货币 | SGD |
| af\_destination\_a | 出发点 | Plaza Singapura |
| af\_destination\_b | 到达点 | Marina Bay Sands |
| distance | 两个目的地之间的距离 | 5.2 |
| af\_content\_type | 交通方式类型 | Taxi |
| payment\_method\_type | 付款方式类型 |  |
| af\_city | 预订乘车的城市 | Singapore |
| af\_region | 预订乘车的地区 | SFA |
| af\_country | 预订乘车的国家 | Singapore |
| order\_id | Order ID | 135790 |

</Accordion>

<div id="ride-booking-confirmed-ride_booking_confirmed" />

<Accordion title="已确认的乘车预订(ride_booking_confirmed)">

**作用**

此事件可以帮助您：

* 了解哪些是最活跃的司机
* 查看司机最常去的目的地
* 查看每名司机的行程均价和总价

此外, 记录此事件与其他三个预订相关事件可以帮助您更好地了解司机的行为。您可以看到哪些司机确认的行程预订请求最多, 哪些司机选择短途或长途行程等。

#### **触发**

司机接受预订时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price | 行程的价格 | 22.4 |
| af\_currency | 货币 | SGD |
| af\_destination\_a | 出发点 | Plaza Singapura |
| af\_destination\_b | 到达点 | Marina Bay Sands |
| distance | 两个目的地之间的距离 | 5.2 |
| af\_content\_type | 交通方式类型 | Taxi |
| driver\_id |  | 1706 |
| payment\_method\_type | 付款方式类型 |  |
| af\_city | 预订乘车的城市 | Singapore |
| af\_region | 预订乘车的地区 | SFA |
| af\_country | 预订乘车的国家 | Singapore |
| af\_order\_id | Order ID | 135790 |

</Accordion>

<div id="ride-booking-canceled-ride_booking_canceled" />

<Accordion title="已取消的乘车预订(ride_booking_canceled)">

**作用**

此事件可以帮助您：

* 记录经常取消的司机或乘客
* 了解有多少行程被取消
* 将取消率与价格、目的地、距离和城市等归因相关联
* 了解取消行程的原因

**触发**

取消预订时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price | 行程的价格 | 22.4 |
| af\_currency | 货币 | SGD |
| af\_destination\_a | 出发点 | Plaza Singapura |
| af\_destination\_b | 到达点 | Marina Bay Sands |
| distance | 两个目的地之间的距离 | 5.2 |
| af\_content\_type | 交通方式类型 | Taxi |
| driver\_id |  | 1706 |
| cancelation\_reason | 行程取消的原因 | price is too high, driver didn't show up, passenger didn't show up |
| payment\_method\_type | 付款方式类型 |  |
| af\_city | 预订乘车的城市 | Singapore |
| af\_region | 预订乘车的地区 | SFA |
| af\_country | 预订乘车的国家 | Singapore |
| order\_id | Order ID | 135790 |
| canceled\_by | 行程是被乘客还是司机取消的 | Passenger |

</Accordion>

<div id="ride-booking-completed-ride_booking_completed" />

<Accordion title="已完成的乘车预订(ride_booking_completed)">

**作用**

此事件可以帮助您：

* 了解乘客支出和司机收入
* 将已完成的乘车次数与目的地、距离、支付类型和司机ID等归因相关联
* 查看司机和乘客的平均距离和总距离
* 比较已完成的行程和被取消的行程
* 记录司机的得分

**触发**

行程结束时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_price | 行程的价格 | 22.4 |
| af\_currency | 货币 | SGD |
| af\_destination\_a | 出发点 | Plaza Singapura |
| af\_destination\_b | 到达点 | Marina Bay Sands |
| distance | 两个目的地之间的距离 | 5.2 |
| af\_content\_type | 交通方式类型 | Taxi |
| driver\_id |  | 1706 |
| payment\_method\_type | 付款方式类型 |  |
| af\_city | 预订乘车的城市 | Singapore |
| af\_region | 预订乘车的地区 | SFA |
| af\_country | 预订乘车的国家 | Singapore |
| order\_id | Order ID | 135790 |
| credits\_earned | 乘客完成一次乘车所获取的积分 | 248 |

</Accordion>

<div data-zendesk-anchors="h_01HGTAZ7J64RZE35JP8XPKMTPZ=ridehailing h_01HGTAZ7J6N36EH492QDXCQYB1=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAZ7J6FJ8R9VXKK0F1A1E1=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAZ7J6FQQKV7JB0Z9MG8CD=complete-registration-af_complete_registration h_01HGTAZ7J6YM8DJ96E7Q4M4Y8Q=login-af_login h_01HGTAZ7J67MNJ8T9B9W4NJ5Y9=add-payment-info-af_add_payment_info h_01HGTAZ7J6Z3EX03JTPZFHJJF6=spent-credits-af_spent_credits recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAZ7J6Z6NE8D5A10CRJJH4=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAZ7J6WCY2BQJPSNSTJRQ0=ride-booking-requested-ride_booking_requested h_01HGTAZ7J78J1X3VAYMH8Q3ZBA=ride-booking-confirmed-ride_booking_confirmed trigger=%E8%A7%A6%E5%8F%91 h_01HGTAZ7J7C4R7A7KT2S95835J=%E8%A7%A6%E5%8F%91 h_01HGTAZ7J797KA791H1621F9TE=ride-booking-canceled-ride_booking_canceled h_01HGTAZ7J789CJ8P6X8B0V7A64=ride-booking-completed-ride_booking_completed" />
