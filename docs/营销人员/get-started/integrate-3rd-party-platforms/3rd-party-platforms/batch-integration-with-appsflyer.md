---
title: AppsFlyer中的Steam对接配置说明
metadata:
  keywords:
    - Advertisers
    - Batch
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-01-28T10:06:24Z'
  edited_at: '2026-10-14T10:05:23Z'
  id: 360000833437
  locale: zh-cn
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000833437
---
> **概要：**

> 🚧 **重要提示！**
>
> 部分渠道限制第三方的数据共享。


<div id="setting-customer-user-id" />

<div id="integrating-batch-and-appsflyer" />

### 获取客户用户ID

<Tabs>
<Tab title="Android">

<div id="batch" />

#### 批次

```java
Batch.User.editor()
    .setIdentifier("user@example.com")
    .save();
```

#### AppsFlyer

```java
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>

<Tab title="iOS">

<Tabs>
<Tab title="Objective-C">

#### 批次

```objectivec
BatchUserDataEditor *editor = [BatchUser editor];
[editor setIdentifier:@"user@example.com"];
[editor save];
```

#### AppsFlyer

```objectivec
[AppsFlyerTracker sharedTracker].customerUserID = @"user@example.com";
```

</Tab>

<Tab title="Swift">

#### 批次

```swift
let editor = BatchUser.editor()
editor.setIdentifier("user@example.com")
editor.save()
```

#### AppsFlyer

```swift
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>
</Tabs>

</Tab>
</Tabs>


**<span id="setting-up-batch"></span><span id="setting-up-batch-in-appsflyer-dashboard"></span>前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系相关渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作**> **Partner Marketplace**。  
   **修改方式**：从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**。界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开 <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">（启用）</Anchor> 状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

<div id="activate-partner" />

### 渠道激活

**第一次访问**时，需要打开**激活合作伙伴**开关以开启对接选项卡内的配置参数。只要仍与该合作伙伴合作，这个开关必须为ON。   
有关渠道激活的详细说明请参见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。

<div id="general-settings" />

### 常规设置

![batch-general-settings-keys.png](https://files.readme.io/fb165253ec81c0ad4ee9569ef928dc63fb476efe6da8fc7c9120d6619b3124c1-360001692717.png)

<div id="viewing-appsflyer-data-in-the-batch-dashboard" />

<div id="default-postbacks" />

### 默认回传

![batch-default-postbacks.png](https://files.readme.io/e3e84f990d7f05c94fb69195a7e57caeffcd1ca35a5fb0148fc6a81ab9816673-360001778958.png)

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


[![Userbase.png](https://files.readme.io/b0277dc43b81630d5b260273b208a5ab9b62e13c7caca08e8b631d73c8de3b2a-small-360001694717.png)](https://files.readme.io/b0277dc43b81630d5b260273b208a5ab9b62e13c7caca08e8b631d73c8de3b2a-small-360001694717.png)

<div data-zendesk-anchors="h_01H9FK389FZGSK6XPYE73MYEDH=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA integrating-batch-and-appsflyer=%E8%8E%B7%E5%8F%96%E5%AE%A2%E6%88%B7%E7%94%A8%E6%88%B7id setting-customer-user-id=%E8%8E%B7%E5%8F%96%E5%AE%A2%E6%88%B7%E7%94%A8%E6%88%B7id h_01H9FK389GXG3CDFPNM5ASKJ3N=%E8%8E%B7%E5%8F%96%E5%AE%A2%E6%88%B7%E7%94%A8%E6%88%B7id h_01H9FK389MPKFN8J74BX1E3MGG=%E8%8E%B7%E5%8F%96%E5%AE%A2%E6%88%B7%E7%94%A8%E6%88%B7id batch=%E6%89%B9%E6%AC%A1 h_01H9FK389MK1HM1460VAT6X82Y=%E6%89%B9%E6%AC%A1 h_01H9FK389MPGNEX8B3923KYDB3=appsflyer batch::28a946d0=%E6%89%B9%E6%AC%A1 h_01H9FK389MC4K8PNVPAGC00TBW=%E6%89%B9%E6%AC%A1 appsflyer::3f0aa95b=appsflyer h_01H9FK389M7V83A66M6T9EV8QT=appsflyer batch::24c5c955=%E6%89%B9%E6%AC%A1 h_01H9FK389MRV4ARHMHXPAXVXQ9=%E6%89%B9%E6%AC%A1 appsflyer::deb78dd1=appsflyer h_01H9FK389MT6PD8FW21SYHBPCV=appsflyer h_01H9FK389MCSR5YDSF4RKFDSDZ=setting-up-batch-in-appsflyer-dashboard h_01H9FK389MG9459909JZBDN77E=integration-tab activate-partner=%E6%B8%A0%E9%81%93%E6%BF%80%E6%B4%BB h_01H9FK389M19AVM63DEX5JTTQK=%E6%B8%A0%E9%81%93%E6%BF%80%E6%B4%BB general-settings=%E5%B8%B8%E8%A7%84%E8%AE%BE%E7%BD%AE h_01H9FK389MN82EKHVGMM9Z6H58=%E5%B8%B8%E8%A7%84%E8%AE%BE%E7%BD%AE default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9FK389MXA3DS403VXRRK5NX=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9FK389MERP4XBF19T28E6DN=attribution-link-tab h_01H9FK389M3E05PVMNA83TBFJZ=cost-tab h_01H9FK389M06FEQ4RZJ04HTH33=ad-revenue-tab h_01H9FK389MB31S8BR8WX178GHX=permissions-tab viewing-appsflyer-data-in-the-batch-dashboard=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9FK389M8BNRFECN0WG23BCD=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0" />
