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
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-11-28T10:02:33Z'
  edited_at: '2023-07-31T06:44:09Z'
  id: 360000611338
  locale: zh-cn
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000611338
---
> 【概要】：本文讲解了如何针对美图启用AppsFlyer的归因与衡量功能，以便您在AppsFlyer面板上查看美图广告的归因数据。

### 请注意: 完成美图广告平台的正常归因，请务必保证应用收集IDFA／OAID，了解更多信息，请查看<Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">安卓</Anchor>/<Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide">iOS</Anchor>对应的SDK整合指南。

### 步骤：

#### 1. 在AppsFlyer后台取得归因链接

进入您想要推广的产品相应页面, 从左边导航栏点击”Integrated Partners”进入渠道配置页面。

<Image align="center" alt="___1.png" src="https://files.readme.io/3c2660a155494dce2c9e3e4233f2a98a337495a9954afe5933384e550d17f97d-360001152838.png" />

进入 Integrated Partners 页面后, 在相应搜索框输入 meituchina\_int，进一步点击搜索按钮。

<Image align="center" alt="___2.png" src="https://files.readme.io/ad218d3343fc2c01d2499934d8a1c8a3f8d51a3c5f01e98b8a14be1a314210e8-360001161377.png" />

进入Meitu China的配置页面，在“渠道对接-整体配置”版面，点击打开“激活”按钮。

在归因链接版面，可直接取出预配置好的点击归因链接，填写到美图广告后台

<Image align="center" alt="mceclip1.png" src="https://files.readme.io/c6d051fadb62598f191ce5d9b52a5535f2b0b69b03e56f03b9b746fdba34ad79-360003338638.png" />

#### 2. 登录美图广告平台账户进行应用广告归因配置

    a.设置广告组，选择推广目标为“APP下载(iOS/Android)”，

    下载链接输入APPstore的链接，链接类似[https://apps.apple.com/cn/app/xxxxx/idxxxxxxxxxx](https://apps.apple.com/cn/app/mei-yan-xiang-ji/id592331499) 或者Android 应用下载链接

<Image align="center" alt="meitu_1.png" src="https://files.readme.io/d4ab96ac25c682f27d2c52315e815499e0dcf495573b2c15bebbf355b3f35e13-360005581238.png" />

  b. 在新建广告中进行设置，完成投放目标，投放时段，地域，年龄，性别等定向设定。

<Image align="center" alt="meitu_2.png" src="https://files.readme.io/644e5359f5ce3ade166b02b923c141f33807865a84f63b344459e09ad8f4f876-360005581258.png" />

c. 在APP（iOS/Android）下载地址中，将appsflyer监测链接放在“点击监测”中。

<Image align="center" alt="meitu_3.png" src="https://files.readme.io/e8fb740a74fc46fb5a0f72fa87843d1401dab40cfa1254842d3995d9271f275d-360005581278.png" />

d. 上传素材，通过审核后进行投放。

#### 3. 如何向美图平台回传应用内事件

在渠道对接模块，打开应用内事件回调按钮，在左侧的事件名称选择您在AppsFlyer埋点的应用内事件，在右侧按美图的要求填写与左侧对应的渠道方事件标志。

美图平台接收应用内事件的标志：

| 事件类型 | 美图事件标志 |
| --- | --- |
| 注册 | 1 |
| 付费 | 2 |
| 关键事件 | 3 |

<Image align="center" alt="meitu_4.png" src="https://files.readme.io/73ae920889ed8f725ed1491b724c681caec82d7faf558130cc6283571042609c-360005496957.png" />

4. 如何通过美图后台查看转化数据

   a. 在广告界面，选择“自定义表头”，勾选“激活数”。

   ![meitu_5.png](https://files.readme.io/dd728b4b06c2892d4488a88b96b6f32283910ca51f06d75cb5985b9d5f899cee-360005581318.png)

   b. 可查询各个广告计划对应的投放金额，激活数等信息。

  ![meitu_6.png](https://files.readme.io/8f09134d12e0e3b404b1cd7b87c3febadf3cf998bae9fa1a29564ad64cb00444-360005496977.png)