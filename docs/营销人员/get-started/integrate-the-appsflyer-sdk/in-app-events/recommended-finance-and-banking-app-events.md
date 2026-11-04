---
title: 金融银行类应用内事件推荐
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
  created_at: '2021-04-27T12:58:44Z'
  edited_at: '2026-10-14T10:11:05Z'
  id: 360019598337
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/360019598337
---
> **概要：** 概览：通过为您的金融和银行应用程序记录这些建议的应用内事件，评估用户在整个用户路径中的质量。


<span id="-finance-and-banking"></span><span id="finance-and-banking"></span>财务和银行应用程序使用户能够执行与财务相关的广泛目标，包括注册新的信用卡或申请贷款。

记录这些事件可以帮助您确定：

* 用户最想要的账户，并为您提供再营销的想法
* 用户希望在信用卡中获得哪些好处
* 用户需要哪些财务援助，以及他们需要多少援助

<div id="important" />

> 🚧 **重要提示！**
>
> * 如需详细的开发人员指南，请在**AppsFlyer开发者资源中心**查找<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">。</Anchor>
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

<div id="recommended-structures-for-predefined-events" />

## 预定义事件的推荐结构

以下部分提供P2P借贷垂直营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="login-af_login" />

<Accordion title="登录（af_login）">

**作用**

了解注册用户的留存情况

**触发**

用户成功登录时

**事件参数**

可在无需任何其他参数的情况下发送

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="完成注册（af_complete_registration）">

**作用**

了解有多少用户安装了该应用程序并完成了注册过程，以及用户喜欢什么注册方式

**触发**

用户完成注册过程时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_registration\_method | 注册方式的类型 | 电子邮件，Facebook |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## 自定义事件的推荐结构

以下部分提供事件结构列表，其中包括自定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="registration-verified-registration_verified" />

<Accordion title="注册已验证(registration_verified)">

**作用**

**触发**

注册通过验证时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| submit\_registration | 验证注册方法类型。 | 电子邮件，Facebook |

</Accordion>

<div id="submit-account-application-submit_account_application" />

<Accordion title="提交账户申请(submit_account_application)">

**作用**

**触发**

用户完成账户申请过程时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| account\_type | 申请的账户类型 | 储蓄 |
| application\_method | 提出申请的地方 | 设定的名称 |
| PII\_type | 申请期间使用的ID类型 | 护照 |

</Accordion>

<div id="open-account-success-open_account_success" />

<Accordion title="开户成功(open_account_success)">

**作用**

**触发**

用户申请被接受并开立账户时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| account\_type | 开立的账户类型 | 储蓄 |
| application\_method | 提出申请的地方 | 设定的名称 |
| PII\_type | 申请期间使用的ID类型 | 身份证 |

</Accordion>

<div id="open-account-rejected-open_account_rejected" />

<Accordion title="开户被拒(open_account_rejected)">

**作用**

**触发**

用户完成注册过程时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| account\_type | 申请的账户类型 | 储蓄 |

</Accordion>

<div data-zendesk-anchors="h_01HGTAXN8PV7TPNRBWD593BR4K=finance-and-banking h_01HGTAXN8Q652HG7412X583KWX=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAXN8QWEWD86FMF6GEZNZD=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAXN8Q3K0EFGXZ41XZH438=login-af_login h_01HGTAXN8Q6KFDPB8XSVT3F9E8=complete-registration-af_complete_registration recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAXN8Q47F6CXXBEVCDPSBA=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAXN8QB911JMER3EV7RGTM=registration-verified-registration_verified h_01HGTAXN8QCYR0BQ3Q3VN0EQ9X=submit-account-application-submit_account_application h_01HGTAXN8QJ4DKQS2FY9KY0AX4=open-account-success-open_account_success h_01HGTAXN8QK1P5QYEN5SNBQ5ED=open-account-rejected-open_account_rejected" />
