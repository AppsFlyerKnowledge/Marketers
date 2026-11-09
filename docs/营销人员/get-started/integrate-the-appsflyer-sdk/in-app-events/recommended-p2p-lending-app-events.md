---
title: P2P贷款类应用事件推荐
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
  created_at: '2021-04-28T09:01:59Z'
  edited_at: '2026-10-14T09:59:28Z'
  id: 360019614017
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/360019614017
---
> **概要：** 概览： 通过为您的点对点（P2P）借贷应用程序记录这些建议的应用内事件，评估用户在整个用户路径中的质量。


<span id="-p2p-lending"></span><span id="p2p-lending"></span>P2P借贷是个人和企业相互借贷的一种方式。我们建议记录的典型事件有个人贷款人和借款人的行为、人们提供的贷款类型，以及贷款接受率和拒绝率。

您从事件记录中收集的数据可以筛选出值得信赖的借款人，并为他们提供更优惠的利率。同样, 您可以看到谁是最活跃的贷款者, 并向他们提供更低的费用。此外，一旦知道哪种类型的贷款最受用户欢迎，您就可以发起针对这些受众的营销广告活动。

<div id="important" />

> 🚧 **重要提示！**
>
> * 如需详细的开发人员指南，请在**AppsFlyer开发者资源中心**查找<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">。</Anchor>
>
> 有关记录应用内事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

<Image align="center" alt="Flowchart_for_recommended_events P2P_lending_app_user_journey" src="https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png" />

<div id="recommended-structures-for-predefined-events" />

## 预定义事件的推荐结构

以下部分提供P2P借贷垂直营销典型事件结构列表。每个结构都包括预定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="complete-registration-af_complete_registration" />

<Accordion title="完成注册（af_complete_registration）">

**作用**

确定有多少用户在注册后实际验证其身份。您可以将这些用户归因到广告活动中，并查看哪些广告活动带来了活跃用户。

**触发**

用户的注册获得批准时

**事件参数**

| 特点 | 说明 | 示例值 |
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

<div id="recommended-structures-for-custom-events" />

## 自定义事件的推荐结构

以下部分提供事件结构列表，其中包括自定义事件名称和建议使用的事件参数。请注意，应用内事件可以包括满足您业务需求的任何事件参数。

<div id="registration-submitted-registration_submitted" />

<Accordion title="已提交的注册(registration_submitted)">

**作用**

由于P2P借贷很容易被滥用，用户必须首先验证自己的身份。他们通过提交注册申请来验证。此事件可以帮助您：

* 确定有多少用户已注册，但从未验证其账户
* 查看注册方法（如电子邮件、Facebook、Google）和验证率的关联程度

**触发**

用户提交注册申请后

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| af\_registration\_method | 注册方式的类型 | 电子邮件，Facebook |

</Accordion>

<div id="fill-loan-form-fill_loan_form_form_name" />

<Accordion title="填写贷款表单(fill_loan_form_&lt;FORM_NAME>)">

**作用**

确定放弃率，并重新定位未完成贷款申请的借款人。

请注意，发送此事件时，请在事件名称中包括表单名称。

**触发**

借款人提交表单时

**事件参数**

可在无需任何其他参数的情况下发送

<div id="note" />

> 📘 **注意**
>
> 强烈建议您将贷款与贷款人联系起来。为此，请确保设置客户的用户ID。<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">设置客户的用户ID</Anchor>可以将贷款人与应用程序用户在AppsFlyer中显示的用户相匹配。通过设置客户的用户ID，您可以确保使用客户的用户ID发送任何事件。

<div id="submit-loan-application-submit_loan_application" />

<Accordion title="提交贷款申请(submit_loan_application)">

**作用**

此事件可以帮助您：

* 确定应用程序中的贷款申请总数
* 了解贷款申请中的最高、最低和平均金额
* 确定人们申请的贷款类型

**触发**

用户成功提交贷款申请时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| loan\_id | 贷款ID | 1735102 |
|  | 申请的金额 | 1000 |
| loan\_type | 贷款期限 | 3 months |

</Accordion>

<div id="loan-form-loan_form" />

<Accordion title="贷款表单(loan_form)">

**作用**

审核借款人提交的贷款申请

**触发**

借款人成功提交贷款申请时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| loan\_id | 贷款ID | 1735102 |
|  | 申请的金额 | 1000 |
| loan\_type | 贷款期限 | 3 months |

</Accordion>

<div id="submit-credit-check-submit_credit_check" />

<Accordion title="提交信用检查(submit_credit_check)">

**作用**

检查借款人的财务记录（例如，过去的信用、付款习惯和贷款类型）以评估风险级别。

**触发**

贷款人收到贷款请求后

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| loan\_id | 贷款ID | 1735102 |
|  | 申请的金额 | 1000 |
| loan\_type | 贷款期限 | 3 months |

</Accordion>

<div id="loan-accepted-loan_accepted" />

<Accordion title="已接受的贷款(loan_accepted)">

**作用**

了解贷款和其他指标的趋势。此事件可以帮助您确定：

* 什么类型的贷款得到接受
* 批准的贷款中申请的金额

**触发**

接受贷款时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| loan\_id | 贷款ID | 1735102 |
|  | 申请的金额 | 1000 |
| loan\_type | 贷款期限 | 3 months |

</Accordion>

<div id="loan-rejected-loan_rejected" />

<Accordion title="贷款被拒绝(loan_rejected)">

**作用**

您可以查看贷款的金额跟周期与拒贷率的相关性。您还可以对这些贷款被拒的用户进行重定向营销，向他们推荐额度更小的贷款项目。

**触发**

贷款人拒绝贷款时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| loan\_id | 贷款ID | 1735102 |

</Accordion>

<div id="payment-payment" />

<Accordion title="支付(payment)">

**作用**

良好借款人是那些履行其贷款义务的借款人。您可以将借款人归因到渠道推广活动, 以便了解哪些渠道活带来了值得信赖的借款人。追踪该事件能够帮您收集有关付款的最低、最大和平均金额的数据。

**触发**

借款人偿还贷款时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| loan\_id | 贷款ID | 1735102 |
| payment\_amount | 已支付的金额 | 100 |
| payment\_id | 支付ID | AE12SF |

</Accordion>

<div id="payment-completed-payment_completed" />

<Accordion title="已完成的支付(payment_completed)">

**作用**

您可以对此类借款人进行重定向营销，并为他们提供更低的利息费和其它促销优惠。

**触发**

贷款全额还清时

**事件参数**

| 字段名称 | 说明 | 示例值 |
| --- | --- | --- |
| loan\_id | 贷款ID | 1735102 |

</Accordion>

<div id="payment-received-payment_received" />

<Accordion title="已收到支付(payment_received)">

**作用**

验证借款人是否按照贷款协议的条款完成了贷款支付。

**触发**

借款人偿还贷款时

**事件参数**

| 特点 | 说明 | 示例值 |
| --- | --- | --- |
| loan\_id | 贷款ID | 1735102 |
| payment\_amount | 已支付的金额 | 100 |
| payment\_id | 支付ID | AE12SF |

</Accordion>

</Accordion>

<div data-zendesk-anchors="h_01HGTAY6DHKXCTP52P2EPHXN5H=p2p-lending h_01HGTAY6DHDDG3MVCXEM705MTK=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA recommended-structures-for-predefined-events=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAY6DH1V6S5NKJEFCVW1PF=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAY6DHHGW3M6NQ0K3J6HTC=complete-registration-af_complete_registration h_01HGTAY6DHZTKJR94T8B6WEYZ6=login-af_login recommended-structures-for-custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAY6DH00660DSP5RX3PA9C=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%8E%A8%E8%8D%90%E7%BB%93%E6%9E%84 h_01HGTAY6DHETK285KPGW54YV5Z=registration-submitted-registration_submitted h_01HGTAY6DHCQKWMG4YRZDHBMZT=fill-loan-form-fill_loan_form_form_name h_01HGTAY6DHHNJ9EKV3FQ6BKKBF=%E6%B3%A8%E6%84%8F h_01HGTAY6DH4D6NV1NHV5717CDH=submit-loan-application-submit_loan_application h_01HGTAY6DHVWFEFJYB4TGK1B9W=loan-form-loan_form h_01HGTAY6DH7V1JSPCDHDTFR4YA=submit-credit-check-submit_credit_check h_01HGTAY6DH22HRQQJ5NQ2T71QM=loan-accepted-loan_accepted h_01HGTAY6DHTMJ22KQSXHNBJ8B3=loan-rejected-loan_rejected h_01HGTAY6DHD8A2H61XKFPXW589=payment-payment h_01HGTAY6DJWJDQBW52RPG7W7P4=payment-completed-payment_completed h_01HGTAY6DJE0K3VC0YNVWAXT29=payment-received-payment_received" />
