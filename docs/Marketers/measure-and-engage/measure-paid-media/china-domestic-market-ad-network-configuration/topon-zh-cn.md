---
title: TopOn变现配置指南
deprecated: false
hidden: false
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2021-01-06T08:32:42Z'
  edited_at: '2022-10-27T07:37:11Z'
  id: 360016804657
  locale: zh-cn
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/zh-cn/articles/360016804657
---
> 【概要】：TopOn是与AppsFlyer对接的广告变现平台，可为广告主提供广告变现增收解决方案。

1. ### 点击 AppsFlyer 后台左侧菜单栏“合作伙伴配置”入口，并在搜索栏键入”Toponad”：

   ![WechatIMG118.png](https://files.readme.io/a6c01dcfb087743eb4056a42580b04872462b228338c6f3c667d029c28201f5d-360015765698.png)
2. ### 打开 Toponad 对接页面下的“广告收入”栏，并且完成以下配置：

   a. 打开 “Get ad revenue data” 按钮。

   b. 选择拉取数据的颗粒度。如需用户层级数据，请勾选 “user level integration”

   c. 输入对应的 Publisher Key和 Network App id；如果您还未生成 Publisher Key和 Network App id，请联系 TopOn 获取。

   ![WechatIMG120.png](https://files.readme.io/b6d56d350adf6c39571047d256d67488b26d0de1b3bb8b7d3e1e0ca557ae9b08-360015765718.png)
3. ### 点击 “Test connection” 测试接口链接状态

   a. 如链接成功，点击右下角“save”保存配置即可。  
   b. 如链接失败，可以查看API的状态反馈，如果显示“无效凭证”则需检查填写的  token信息是否有误，更改之后再尝试点击“Test connection” ，或者联系您的客户成功经理进行咨询。

### 完成以上操作后即可将 TopOn 广告聚合变现数据通过 Reporting API 的方式拉取至 AppsFlyer后台，以查看ROI数据。