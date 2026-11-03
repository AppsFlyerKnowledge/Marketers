---
title: （参见数据净室——数据连接使用指南）。
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2023-03-20T13:18:17Z'
  edited_at: '2026-10-14T10:05:31Z'
  id: 13886278812817
  locale: zh-cn
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/zh-cn/articles/13886278812817
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：**

## 速览


1. [![dcr_manage_connections_button.png](https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png)](https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png)

1. * <span id="creating-inbound-connections"></span>如果您的账户中没有设置连接，界面会打开创建**新数据连接**的对话框。


<Image alt="dcr_create_inbound_connection.png" src="https://files.readme.io/b30606026761528f4a0d3efcc1a3207e8b9c99ca8202f76b2d698a86efaa21ee-13913809617297.png" width="457px" />

<div id="bigquery-inbound" />

<Accordion title="BigQuery">

* <Image alt="BQ_project_ID.png" src="https://files.readme.io/de295dfc0224ff90f041b1aeaf2996828ec1920a715ba668b46a2f50489fd15b-13910856739857.png" width="457px" />

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

![ui-snowsight-account-identifier.png](https://files.readme.io/9995c3fd523548de93bafc7c575203e7d38be3b6be2a5e876d7a0a8495ca04c9-24698313004433.png)

</Accordion>


<span id="creating-outbound-connections"></span>DCR会通过<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>向您选定的云服务平台发送DCR报告。

> 📘 **注意**
>
> 请注意：接收DCR报告不需要Data Locker的付费功能。如果您需要通过Data Locker接收其他的AppsFlyer报告，请联系您的CSM或发送邮件至[hello@appsflyer.com](mailto:hello@appsflyer.com)咨询详情。


[![dcr_dl_new_connection_dialog.png](https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png)](https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png)

<div id="bigquery-outbound" />

<Accordion title="BigQuery">

2. * <Image alt="BQ_project_ID_dataset_name.png" src="https://files.readme.io/c784b0369c51a6e123279fdc5b2fa1fba255ae371d436e9247cb5e4685387983-13928683779089.png" width="457px" />

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

**请注意：** 请注意：以下流程必须由Snowflake账户管理员（**Accountadmin**）完成。

2. * **重要提示！**  

     <Image alt="snowflake_account_locator.png" src="https://files.readme.io/23495b3209129f48ed1ca3442a1e96fac791d46df6f87050ac036893a050e427-13930022354961.png" width="536px" />

2. 将您的角色切换为**Accountadmin**。
3. 在左侧边栏中选择Private Sharing。

</Accordion>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01HKA1AS2QGDTPW85WA07K35M0=%E9%80%9F%E8%A7%88 h_01HKA1AS2QRRBJAYNKSWWZXE3N=creating-inbound-connections complete-the-connection-inbound=%E9%80%9F%E8%A7%88 h_01HKA1AS2Q06F07RDD8W384RE2=%E9%80%9F%E8%A7%88 h_01HKA1AS2QXP5H2HBJ911F3TPZ=bigquery-inbound h_01HKA1AS2QCPC6515FZ45E8Q67=snowflake-inbound h_01HKA1AS2QAV9DJWZQ2703TS0Z=creating-outbound-connections h_01HKA1AS2Q76NP9FY7S4H0QP4D=%E6%B3%A8%E6%84%8F complete-the-connection-outbound=%E6%B3%A8%E6%84%8F h_01HKA1AS2RKTWNY2ZR7VYAJC90=%E6%B3%A8%E6%84%8F h_01HKA1AS2R7RFWKM2W89QSEH3V=%E6%B3%A8%E6%84%8F h_01HKA1AS2RJXZPCBKE7ST0SA63=bigquery-outbound h_01HKA1AS2R7TV495V39N35CWAR=snowflake-outbound" />
