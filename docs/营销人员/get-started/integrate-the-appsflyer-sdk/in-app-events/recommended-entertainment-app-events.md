---
title: 娱乐类应用事件推荐
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
  created_at: '2021-04-25T10:44:33Z'
  edited_at: '2026-10-14T10:11:21Z'
  id: 360019699898
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/360019699898
---
> **概要：** 概览：通过为您的娱乐应用程序记录这些建议的应用内事件，评估用户在整个用户路径中的质量。


<span id="-entertainment"></span><span id="entertainment"></span>随着用户对点播内容的需求不断增长，娱乐应用市场的竞争变得异常激烈。我们建议记录的典型事件有用户订阅、流媒体内容以及下载和保存内容。

记录事件可以帮助您确定：

* 用户消费的内容
* 根据用户需求内容的广告活动绩效
* 用户互动与使用情况

这些事件也与在以下智能电视上运行的娱乐应用程序有关：

* 安卓智能电视
* 苹果电视 (tvOS)
* Amazon Fire TV

<div id="important" />

> 🚧 **重要提示！**
>
> * 如需详细的开发人员指南，请在**AppsFlyer开发者资源中心**查找<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">。</Anchor>
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

<div id="recommended-structures-for-predefined-events" />

## 预定义事件的推荐结构

以下部分提供娱乐业垂直营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="complete-registration-af_complete_registration" />

<Accordion title="完成注册（af_complete_registration）">

**作用**

了解有多少用户安装了该应用程序并完成了注册过程，以及用户喜欢什么注册方式。

**触发**

用户完成注册过程时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_registration\_method | 用户选择注册的方式 | Facebook, Google, email |

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

<div id="start-trial-af_start_trial" />

<Accordion title="开始试用（af_start_trial）">

**作用**

许多流媒体服务为用户提供一个探索高级功能的试用期。此事件可以帮助您：

* 查看有多少用户选择试用
* 试用是否是促销活动的一部分或与合作伙伴合作的一部分
* 哪些促销活动促使用户激活试用期

**触发**

用户选择加入并激活试用期时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| trial\_method | 激活试用的方式 | 免费通过新手机，免费通过运营商、促销活动、优惠券代码 |
| trial\_method\_identifier | 试用方式的标识符 | 运营商名称，例如**Vodafone**<br /><br />优惠券代码，例如**TRA123** |

<div id="note" />

> 📘 **注意**
>
> 如果您要让这个事件对应到Meta ads的StartTrial（开始试用）事件，并关联收入，请把参数设为af\_price，而不是af\_revenue。

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="订阅（af_subscribe）">

**作用**

订阅是流媒体服务的核心。此事件可以帮助您：

* 查看哪些广告活动带来了订阅用户
* 比较试用中的用户数量与订阅用户数量
* 确定订阅产生的收入，并将其归因到广告活动和媒体渠道

**触发**

* 用户成功订阅时
* 续订订阅时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| new\_subscription | 订阅是新定还是续订 | 真/假 |
| af\_coupon\_code | 优惠券代码，如果订阅期间使用了优惠券代码 | 3MonthsSubscription |
| coupon\_code\_value | 优惠券的优惠差额 | 10% |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 与订阅相关联的收入 | 5.95 |
| af\_currency | 订阅付款的币种 | USD |
| subscription\_method | 订阅中使用的付款方式 | credit card, e-wallet, PayPal |
| expiration\_date | 订阅的到期日期 | 2018/07/18 |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## 自定义事件的推荐结构

以下部分提供事件结构列表，其中包括自定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="media-play-media_play" />

<Accordion title="媒体播放(media_play)">

**作用**

记录用户播放您提供媒体的事件。这样的媒体可以是，例如，视频、音乐、电视节目或广播节目。

记录此事件可以帮助您确定：

* 按类型和内容分类的媒体消费
* 最受欢迎的流媒体内容的语言
* 流媒体内容的最短、最长和平均持续时间

**触发**

在流媒体内容的预定义数量（例如2分钟）之后。

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_content\_type | 流媒体内容的类型 | tv show, music |
| af\_content\_id | 流媒体内容的ID |  |
| af\_content | 内容的标题，例如歌曲名称或电视节目的标题和集目 | Title of content |
| media\_duration |  | 5 |
| language | 内容的语言 |  |

</Accordion>

<div id="media-minutes-media_minutes" />

<Accordion title="媒体分钟(media_minutes)">

**作用**

媒体分钟是指用户消耗的给定内容项的数量。这是仅次于收入指标，在流媒体行业内最重要的一个指标，因为它可以让您估计用户使用该服务的情况。它还能让您了解该服务的整体使用率和哪些内容最受欢迎。此事件可以帮助您：

* 查看哪些用户广泛使用您的服务
* 了解哪些媒体类型和内容类型受到欢迎

**触发**

以下内容之一：

* 当用户完成一个流媒体项目时
* 当用户退出一个流媒体项目时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| minutes\_consumed |  | 3 |
| af\_content\_type | 流媒体内容的类型 | tv show, music |
| af\_content\_id | 流媒体内容的ID |  |
| af\_content | 内容的标题，例如歌曲名称或电视节目的标题和集目 | Title of content |
| media\_duration |  | 5 |
| language | 内容的语言 |  |

</Accordion>

<div id="media-downloaded-media_downloaded" />

<Accordion title="媒体已下载(media_downloaded)">

**作用**

您可以查看哪些内容用户喜欢在线播放而哪些媒体内容用户更倾向下载。

**触发**

用户开始下载媒体时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_content\_type | 内容类型 | tv show, music |
| af\_content\_id | 内容ID |  |
| af\_content | 内容的标题，例如歌曲名称或电视节目的标题和集目 | Title of content |
| media\_duration |  | 5 |
| language | 内容的语言 |  |

</Accordion>

<div id="media-saved-media_saved" />

<Accordion title="媒体已保存(media_saved)">

**作用**

帮助您凸显用户喜好

**触发**

每当媒体被保存在用户的设备上时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_content\_type | 内容类型 | tv show, music |
| af\_content\_id | 内容ID |  |
| af\_content | 内容的标题，例如歌曲名称或电视节目的标题和集目 | Title of content |
| media\_duration |  | 5 |
| language | 内容的语言 |  |

</Accordion>

<div data-zendesk-anchors="h_01HGTAX1B0KT8Q6PRE41JCPJ60=entertainment h_01HGTAX1B0K2RKYGPFFARM0E1B=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAX1B05C7G67RJPSG3YF66=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAX1B0CN19DY7PAR27YATD=complete-registration-af_complete_registration h_01HGTAX1B0MG1MTD7QXBCK6JHN=login-af_login h_01HGTAX1B0GTJ6ZWRNW5SEJVE9=start-trial-af_start_trial h_01HGTAX1B1XW0RAV8WPP0HF8HD=%E6%B3%A8%E6%84%8F h_01HGTAX1B1AHHGW6SMXST1KXQE=subscription-af_subscribe recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAX1B1ATFH70K2BJZ7XW13=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAX1B1WRQ39H27KPRFZH9W=media-play-media_play h_01HGTAX1B15Z24J8JKKAQH2Z2S=media-minutes-media_minutes h_01HGTAX1B1JPY44SYM59K0M9H2=media-downloaded-media_downloaded h_01HGTAX1B1FXF1DRC91VYRCGMP=media-saved-media_saved" />
