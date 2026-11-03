---
title: AppsFlyer中的Steam对接配置说明
metadata:
  keywords:
    - Swrve
    - Adobe Analytics
    - 3rd Party
    - SDK
    - Integration
    - integrated partner
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:46:00Z'
  edited_at: '2026-10-14T10:14:36Z'
  id: 207040656
  locale: zh-cn
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/zh-cn/articles/207040656
---
> **概要：**

* 电子邮件

> 🚧 **重要提示！**
>
> 部分渠道限制第三方的数据共享。


第4步：

```java
AppsFlyerLib.setCustomerUserId(SwrveSDK.getUserId());
```

```objectivec
NSString* swrve_user_id = [[Swrve sharedInstanceWithAppID:appId apiKey:apiKey] userID];
[[AppsFlyerTracker sharedTracker].customerUserID = swrve_user_id];
```

```swift
Appsflyer.setCustomerUserID(SwrveComponent.Instance.SDK.UserId);
```

第4步：


**<span id="setting-up-swrve"></span>前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式**：从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**，界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开 （启用） 状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

此时您仅可使用配置窗口中的对接选项卡。

如需进一步了合作伙伴配置页面中各选项卡的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">此文档</Anchor>。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

下文说明了对接选项卡中所包含各部分内容。

### 启用渠道

**第一次访问**时，需要打开***激活合作伙伴***开关以开启对接选项卡内的配置参数。只要仍与该合作伙伴合作，这个开关必须为ON。   
有关渠道激活的详细说明请参见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。

### 通用设置

![Swrve_msc_new_3.png](https://files.readme.io/feb1d5f846629d1909727b70b66e4b36138704ebbe4518e2dc03652b9fe5c57a-360001902065.png)

### 默认回传

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

点击**保存**。

* api\_key
* Media Source（媒体渠道）
* Campaign Name

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

Snapchat不支持归因链接。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

该合作伙伴不支持成本数据对接。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

该渠道不支持广告收入对接。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

</Accordion>


[![](https://files.readme.io/6a3e4cf709f58b20f2932ab47e6fa9289653504d85a0b6eec2580718e2a4dc7c-49839257162769.png)](https://files.readme.io/6a3e4cf709f58b20f2932ab47e6fa9289653504d85a0b6eec2580718e2a4dc7c-49839257162769.png)

[![](https://files.readme.io/561403abefae9e98e24934c96dd25b1ee34ae24cf30695354c4930404e0a7f19-49839257163537.png)](https://files.readme.io/561403abefae9e98e24934c96dd25b1ee34ae24cf30695354c4930404e0a7f19-49839257163537.png)

<div data-zendesk-anchors="h_01H9HWK5DM87JTDVFND0KB965G=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA integrating-swrve-and-appsflyer=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01H9HWK5DM1K9P5XXC6S7ENAGV=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01H9HWK5DMS8HAK25BF5EXZT51=setting-up-swrve h_01H9HWK5DN9D0DS46X72EDAW54=integration-tab activate-partner=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01H9HWK5DN375XJVHQCZ8Y3K13=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01H9HWK5DN0XK2E0HXS61GRECE=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9HWK5DNH6SYY8T9NX09MRYS=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9HWK5DNZVQDZ0Q1Z9WSKRSR=attribution-link-tab h_01H9HWK5DNPG89HSB0107TKHED=cost-tab h_01H9HWK5DNARD4K0MPHPXKBPXZ=ad-revenue-tab h_01H9HWK5DNFKAT0J98JWVRPQ1G=permissions-tab swrve-reporting-with-appsflyer-data=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9HWK5DN3QB9V593EV566GAQ=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0" />
