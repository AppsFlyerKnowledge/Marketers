---
title: 百度搜索归因配置--Baidu Search Ads Configuration
deprecated: false
hidden: false
metadata:
  keywords:
    - baidu
    - 百度
    - OCPC
    - baidu search
    - 百度搜索
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2018-11-28T10:15:51Z'
  edited_at: '2023-07-31T06:37:48Z'
  id: 360000620817
  locale: zh-cn
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000620817
---
> 【概要】：本文讲解了如何针对百度搜索启用AppsFlyer的归因与衡量功能，以便您在AppsFlyer面板上查看百度搜索广告的归因数据。

#### 请注意:

#### 1.完成百度搜索广告平台的正常归因，请务必保证应用收集IDFA／OAID，了解更多信息，请查看<Anchor target="_blank" href="/marketers/vi/docs/sdk-integration-overview">安卓</Anchor>/<Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide">iOS</Anchor>对应的SDK整合指南。

#### 2.在百度搜索使用CPC或者OCPC出价模式，都可以按照本篇配置文档来操作。如果使用CPC出价方式，在百度后台保持OCPC处于第一阶段，不将模型自动优化功能生效即可。

### 1. 进入媒体平台配置页面

进入您想要推广的产品相应页面, 从左边导航栏点击”媒体平台配置”。

![___1.png](https://files.readme.io/424b62c668e7da9d673bdc441abfe654266d118f329a310178d61dfb7ab15b08-360001161517.png)

### 2. 搜索选择针对百度搜索OCPC（baidusearch\_int)的归因配置页面

进入媒体平台配置页面后, 在搜索框输入baidusearch\_int

![___2.png](https://files.readme.io/fca2eea05fe6ace32fe2f6edf8b704d7461e69d2560638b2336422a6a373b5df-360001161537.png)

### 3. 打开百度搜索OCPC配置页面, ”渠道对接”模块点击“激活”按钮，归因的应用激活信息会默认发送给媒体。

![mceclip0.png](https://files.readme.io/da69c64626656863dd89ab6a305f13e01c7e7161b98c9f1e97571d347ae2d5f1-360003338578.png)

### 4. 在“归因链接”模块取出预配置好的点击归因链接。

![mceclip1.png](https://files.readme.io/a3b8d791e9547f7fd8e6e16eb0777d17def70e1c4001649718fdebe790edc086-360003248497.png)

形如：

[https://app.appsflyer.com/id554782625?af\_siteid=`{{USER_ID}}&c={{PLAN_ID}}&af_adset={{UNIT_ID}}&af_ad={{IDEA_ID}}&pid=baidusearch_int&af_click_lookback=7d&muid={{IMEI}}&idfa={{IDFA}}&android_id={{ANDROID_ID}}&os={{OS}}&af_ip={{IP}}&af_ua={{UA}}&ts={{TS}}&clickid={{CLICK_ID}}&callback_url={{CALLBACK_URL}}&sign={{SIGN}}&redirect=false&callType=v3&md5_imei={{IMEI_MD5}}&android_id={{ANDROID_ID}}`&af\_lang=%e4%b8%ad%e6%96%87](https://app.appsflyer.com/id554782625?af_siteid=%7B%7BUSER_ID%7D%7D&c=%7B%7BPLAN_ID%7D%7D&af_adset=%7B%7BUNIT_ID%7D%7D&af_ad=%7B%7BIDEA_ID%7D%7D&pid=baidusearch_int&af_click_lookback=7d&muid=%7B%7BIMEI%7D%7D&idfa=%7B%7BIDFA%7D%7D&android_id=%7B%7BANDROID_ID%7D%7D&os=%7B%7BOS%7D%7D&af_ip=%7B%7BIP%7D%7D&af_ua=%7B%7BUA%7D%7D&ts=%7B%7BTS%7D%7D&clickid=%7B%7BCLICK_ID%7D%7D&callback_url=%7B%7BCALLBACK_URL%7D%7D&sign=%7B%7BSIGN%7D%7D&redirect=false&callType=v3&md5_imei=%7B%7BIMEI_MD5%7D%7D&android_id=%7B%7BANDROID_ID%7D%7D&af_lang=%e4%b8%ad%e6%96%87)

预配置的AppsFlyer归因链接里的参数与百度搜索广告后台对应的参数结构和含义：

| AF平台对应名称 | AF追踪链接里的参数 | 百度搜索API监测参数 | 百度搜索平台对应名称 |
| --- | --- | --- | --- |
| 广告系列 | c | `{{PLAN_ID}}` | 广告计划ID |
| 广告组 | af\_adset | `{{UNIT_ID}}` | 广告单元ID |
| Ad | af\_ad | `{{IDEA_ID}}` | 广告创意ID |
| Site ID | af\_siteid | `{{USER_ID}}` | 广告账户ID |
| Keywords | af\_keywords | `{{WORDID}}` | 关键词ID |

#### **注意**：

1. 当前在百度搜索OCPC监测接口的通配符中，仅对加白客户开放关键词ID信息。您可以向您在百度搜索的联系人提供百度搜索广告账户的UID申请开通使用关键词参数。

2. 如何在百度后台确认关键词字段和关键词ID的对应关系：百度投放后台-数据报告-关键词数据-下载

3. 目前在AF后台，不能直接在数据概览（Overview）页面直接按关键词维度删选查看数据，可以在留存报告、数据导出-原始数据的功能里查看af\_keywords对应的值。如果需要在AF后台的数据概览页面直接看到关键词ID，可以把参数`{{WORDID}}以横杠“-”或者下划线“_"的方式加到c, af_adset,或者af_ad 等可以在数据概览页面直接显示的参数后面，举例把链接中已有的&c={{PLAN_ID}} 改为&c={{PLAN_ID}} _{{WORDID}}` 进行使用。

### 5.使用AppsFlyer的点击归因链接，请根据此<Anchor target="_blank" href="https://dev2.baidu.com/content?sceneType=0&pageId=101214&nodeId=662&subhead=">文档</Anchor>在百度搜索后台建立转化跟踪。