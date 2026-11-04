---
title: 游戏类应用事件推荐
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2021-04-06T14:46:54Z'
  edited_at: '2026-10-14T10:04:15Z'
  id: 360018941117
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/360018941117
---
> **概要：** 概览：通过为您的游戏类应用程序记录这些建议的应用内事件，评估用户在整个用户路径中的质量。


<span id="-gaming"></span><span id="gaming"></span>游戏类应用程序包括街机游戏、策略游戏、教育游戏和博彩游戏。我们建议记录的典型事件有应用内购买、在社交媒体上的分享和对友人的邀请。此外，您还可以包括诸如升级和完成游戏中教程之类的事件。

记录事件可以帮助您确定：

* 用户购买最多的项目是什么
* 用户进行互动的程度如何
* 有多少用户在社交媒体上发布分享信息
* 有多少用户邀请朋友安装此应用程序

这些事件也与在以下平台上运行的游戏类应用程序相关：

* 安卓智能电视
* 苹果电视 (tvOS)
* Amazon Fire TV
* Xbox
* Windows移动设备

<div id="important" />

> 🚧 **重要提示！**
>
> * 如需详细的开发人员指南，请在**AppsFlyer开发者资源中心**查找<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">。</Anchor>
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

<div id="recommended-structures-for-predefined-events" />

## 预定义事件的推荐结构

以下部分提供游戏业垂直营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

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

<div id="purchase-af_purchase" />

<Accordion title="购买（af_purchase）">

**作用**

许多游戏类应用程序允许用户购买物品，例如钱币、宝石或武器。记录这些购买可以帮助您：

* 确定用户的LTV以及您通过广告平台和广告代理投放广告活动的ROI
* 确定哪些项目最受用户欢迎
* 横向对比带有购买内容的广告活动，以优化广告活动定向

**触发**

用户在成功购买后进入“感谢页面”时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 预计购买收入 | 199.99 |
| af\_currency | 货币代码 |  |
| af\_quantity | 购买的物品数量 | 2 |
| af\_content\_id | 商品编号 | 21 |
| af\_order\_id | Order ID | 9277 |
| af\_receipt\_id | 收据ID | 9277 |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="通关级别(af_level_achieved)">

**作用**

用户的主要目标之一是在游戏中提升等级。升级通常会在游戏中解锁新的功能和阶段, 鼓励用户继续玩。记录达到的级别可以帮助您：

* 确定哪些广告活动带来最活跃的用户
* 查看哪种类型的用户最活跃、互动最多
* 将整个用户行为与收入等特征相关联

**触发**

用户进入关卡完成页面时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_level | 用户达到的等级 | 3 |
| af\_score | 与用户成绩相关的分数 | 500 |

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="完成新手教学（af_tutorial_completion）">

**作用**

教程为您的用户提供如何使用该应用程序的指南。记录此事件可以帮助您确定：

* 用户可能会遇到哪些问题
* 哪些教程绩效不佳

**触发**

* 用户完成教程时
* 用户开始教程但未完成就退出时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_success | 用户是否已完成教程 | true |
| af\_tutorial\_id | 教程ID | 3 |
| af\_content | 教程名称 | 启用流程 |

</Accordion>

<div id="share-af_share" />

<Accordion title="分享（af_share）">

**作用**

用户喜欢在社交媒体上分享自己在游戏中的成就。分享能够增强品牌效应，也会促使更多用户下载并安装您的 App。了解有关<Anchor target="_blank" href="/marketers/zh/docs/user-invite-attribution">记录分享和邀请</Anchor>的更多信息。

**触发**

用户在社交媒体上成功发布共享信息时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_description | 在社交媒体上分享的原因，例如，新高分或升级 | 新高分，升级，游戏获胜 |
| platform | 用于发布共享信息的平台 | Facebook，Whatsapp，电子邮件 |

</Accordion>

<div id="invite-af_invite" />

<Accordion title="邀请（af_invite）">

**作用**

了解用户向哪些社交媒体网站发出邀请，以及有多少用户邀请他们的朋友下载并安装此应用程序。

**触发**

用户成功邀请朋友下载并安装此应用程序时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_description | 邀请的背景情况 | Try this app |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## 自定义事件的推荐结构

请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="bonus-claimed-bonus_claimed" />

<Accordion title="已领取奖赏(bonus_claimed)">

**作用**

查看有多少用户领取了奖赏，并将领取的奖赏与用户行为和互动程度相关联。

**触发**

当用户领取奖赏并被更新到他们的账户时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| bonus\_type | 用户领取的奖赏类型 | 钱币 |

</Accordion>

<div data-zendesk-anchors="h_01HGTAVT1XSEY0TS9T2R1H1KXV=gaming h_01HGTAVT1XTXYHV1MTFR20BR6J=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAVT1X4QQS6GREKC0N0VK6=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAVT1XAAPGHBTXE6DT9927=login-af_login h_01HGTAVT1X4V41YCXBEXTV0KFR=complete-registration-af_complete_registration h_01HGTAVT1X64710WYNZHTHD7R5=purchase-af_purchase h_01HGTAVT1X24N9J3BMDHV3S54M=level-achieved-af_level_achieved h_01HGTAVT1X5RN4A1MAE0BFB3B4=tutorial-completion-af_tutorial_completion h_01HGTAVT1X952BV07KGZHK68P6=share-af_share h_01HGTAVT1X7KSTYXZGAKEPCXZM=invite-af_invite recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAVT1YXGTF0E5YQX1C3CJN=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAVT1YNH0YAFYX4PR7D6DH=bonus-claimed-bonus_claimed" />
