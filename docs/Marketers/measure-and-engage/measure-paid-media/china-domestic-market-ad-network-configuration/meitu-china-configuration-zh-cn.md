---
title: 美图（中国）广告归因配置--Meitu China Configuration
deprecated: false
hidden: false
metadata:
  keywords:
    - 美图
    - meitu
    - meitu china
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2018-11-28T10:02:33Z'
  edited_at: '2023-07-31T06:44:09Z'
  id: 360000611338
  locale: zh-cn
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000611338
---
【概要】：本文讲解了如何针对美图启用AppsFlyer的归因与衡量功能，以便您在AppsFlyer面板上查看美图广告的归因数据。

### 请注意: 完成美图广告平台的正常归因，请务必保证应用收集IDFA／OAID，了解更多信息，请查看[安卓](/docs/sdk-integration-overview%E5%AF%B9%E6%8E%A5-Android)/[iOS](/docs/basic-sdk-integration-guide%E5%AF%B9%E6%8E%A5-iOS)对应的SDK整合指南。

### 步骤：

#### 1. 在AppsFlyer后台取得归因链接

进入您想要推广的产品相应页面, 从左边导航栏点击”Integrated Partners”进入渠道配置页面。

![___1.png](https://support.appsflyer.com/hc/article_attachments/360001152838)

进入 Integrated Partners 页面后, 在相应搜索框输入 meituchina\_int，进一步点击搜索按钮。

![___2.png](https://support.appsflyer.com/hc/article_attachments/360001161377)

进入Meitu China的配置页面，在“渠道对接-整体配置”版面，点击打开“激活”按钮。

在归因链接版面，可直接取出预配置好的点击归因链接，填写到美图广告后台

![mceclip1.png](https://support.appsflyer.com/hc/article_attachments/360003338638)

#### 2. 登录美图广告平台账户进行应用广告归因配置

    a.设置广告组，选择推广目标为“APP下载(iOS/Android)”，

    下载链接输入APPstore的链接，链接类似[https://apps.apple.com/cn/app/xxxxx/idxxxxxxxxxx](https://apps.apple.com/cn/app/mei-yan-xiang-ji/id592331499) 或者Android 应用下载链接

![meitu_1.png](https://support.appsflyer.com/hc/article_attachments/360005581238)

  b. 在新建广告中进行设置，完成投放目标，投放时段，地域，年龄，性别等定向设定。

![meitu_2.png](https://support.appsflyer.com/hc/article_attachments/360005581258)

c. 在APP（iOS/Android）下载地址中，将appsflyer监测链接放在“点击监测”中。

![meitu_3.png](https://support.appsflyer.com/hc/article_attachments/360005581278)

d. 上传素材，通过审核后进行投放。

#### 3. 如何向美图平台回传应用内事件

在渠道对接模块，打开应用内事件回调按钮，在左侧的事件名称选择您在AppsFlyer埋点的应用内事件，在右侧按美图的要求填写与左侧对应的渠道方事件标志。

美图平台接收应用内事件的标志：

| 事件类型 | 美图事件标志 |
| --- | --- |
| 注册 | 1 |
| 付费 | 2 |
| 关键事件 | 3 |

![meitu_4.png](https://support.appsflyer.com/hc/article_attachments/360005496957)

4. 如何通过美图后台查看转化数据

   a. 在广告界面，选择“自定义表头”，勾选“激活数”。

   ![meitu_5.png](https://support.appsflyer.com/hc/article_attachments/360005581318)

   b. 可查询各个广告计划对应的投放金额，激活数等信息。

  ![meitu_6.png](https://support.appsflyer.com/hc/article_attachments/360005496977)