---
title: 使用AppsFlyer SDK获取转化数据——概述
metadata:
  keywords:
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
  created_at: '2021-11-09T10:06:52Z'
  edited_at: '2026-10-14T10:15:19Z'
  id: 4410481069969
  locale: zh-cn
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410481069969
---
> **概要：** 本文介绍了如何利用转化数据识别各种转化场景、打造定制化用户体验等等。

您可以使用转化数据完成以下工作：

* 引导用户进入应用内的具体页面
* 向用户展示定制化内容

由于数据准确性和延时之间存在此消彼长的关系，因此同一个设备ID的转化数据可能会因API而异。

<div id="get-conversion-data" />

## 获取转化数据

AppsFlyer SDK会通过以下API返回转化数据：

* * `onConversionDataSuccess`：用户获取 (UA) 和再归因转化  
    * 用于安卓：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerconversionlistener#onconversiondatasuccess">onConversion</Anchor> DataSuccess
    * iOS：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * Unity：loadConversionData
  * `onAppOpenAttribution`：用于再互动转化

<div data-zendesk-anchors="get-conversion-data=%E8%8E%B7%E5%8F%96%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE h_01HTZ6M409RPZAQM66R0H5HA16=%E8%8E%B7%E5%8F%96%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE" />
