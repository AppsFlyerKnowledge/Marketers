---
title: 在线教育类应用内事件推荐
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
  created_at: '2021-04-28T12:35:57Z'
  edited_at: '2026-10-14T10:02:29Z'
  id: 360019794378
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/360019794378
---
> **概要：** 概览：通过为您的在线教育应用程序记录这些建议的应用内事件，评估用户在整个用户路径中的质量。


<span id="-online-education"></span><span id="online-education"></span>在线教育应用程序使用户可以远程学习。

记录事件可以帮助您确定：

* 用户最想要什么课程，并为您提供定向思路
* 可以重新定向哪些用户，并提醒他们需要额外的教程才能完成课程
* 哪些课程和证书的需求量最大

<div id="important" />

> 🚧 **重要提示！**
>
> * 如需详细的开发人员指南，请在**AppsFlyer开发者资源中心**查找<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">。</Anchor>
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

[![Flowchart_for_recommended_events_online_education_app_user_journey](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)

<div id="recommended-structures-for-predefined-events" />

## 预定义事件的推荐结构

以下部分提供娱乐业垂直营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

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
| af\_registration\_method | 注册方式的类型 | email, facebook |

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="完成新手教学（af_tutorial_completion）">

**作用**

记录此事件可以帮助您确定：

* 用户可能会遇到哪些问题
* 哪些教程绩效不佳并加以改进
* 将整个用户行为与收入等特征相关联

**触发**

* 用户完成教程时
* 用户开始教程但未完成就退出时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_success | 用户是否完成了该教程 | yes |
| af\_tutorial\_id | 教程ID | 3 |
| af\_content | 该教程名称 | 代数 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="购买（af_purchase）">

**作用**

记录用户在应用内进行的购买可以帮助您：

* 确定用户的LTV以及您通过广告平台和广告代理投放广告活动的ROI
* 确定哪些项目最受用户欢迎
* 横向对比带有购买内容的广告活动，以优化广告活动定向

**触发**

用户在成功购买后进入“感谢页面”时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 预计购买收入 | 250.99 |
| af\_currency | 货币代码 | USD |
| af\_content\_id | 相关商品的ID | 21 |
| order\_id | Order ID | 9277 |
| af\_receipt\_id | 收据ID | 9277 |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## 自定义事件的推荐结构

以下部分提供事件结构列表，其中包括自定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="complete-exercise-complete_excercise" />

<Accordion title="完成练习(complete_excercise)">

**作用**

**触发**

用户完成练习时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| course\_name | 课程名称 | 代数 |
| exercise\_name | 练习名称 | 2 |

</Accordion>

<div id="course-completed-course_completed" />

<Accordion title="课程已完成(course_completed)">

**作用**

**触发**

用户完成课程时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| course\_name | 课程名称 | 代数 |
| course\_completed | 课程是否已完成 | yes |

</Accordion>

<div id="certificate-issued-certificate_issued" />

<Accordion title="颁发的证书(certificate_issued)">

**作用**

**触发**

向用户颁发证书时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| course\_name | 课程名称 | 代数 |
| certificate\_received | 证书是否已颁发 | yes |

</Accordion>

<div data-zendesk-anchors="h_01HGTAYQ9V4Z5YEWTNCZPVMVMF=online-education h_01HGTAYQ9VJ6GS1XVQPG198C8Z=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAYQ9VS0DYFSFNEPDCDVTG=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAYQ9VX44FA5HHBT6DGA2R=login-af_login h_01HGTAYQ9VR78MHTJZFVFCKCV4=complete-registration-af_complete_registration h_01HGTAYQ9VE8ZBF1DJ2AAA1HFF=tutorial-completion-af_tutorial_completion h_01HGTAYQ9VSXMR0J1T0KN6WK2G=purchase-af_purchase recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAYQ9V93HET4AZ7XGE0E3V=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAYQ9VBZZJ5TC1W2S0MK3P=complete-exercise-complete_excercise h_01HGTAYQ9WQJBBEYKDJ8DP9E31=course-completed-course_completed h_01HGTAYQ9WVXX20FNDZWHGDNZ2=certificate-issued-certificate_issued" />
