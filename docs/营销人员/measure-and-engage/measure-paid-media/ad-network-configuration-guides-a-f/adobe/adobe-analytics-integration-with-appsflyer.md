---
title: 将Adobe Analytics与AppsFlyer对接
metadata:
  keywords:
    - Adobe Analytics
    - Integration
    - Advertisers
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
  created_at: '2017-07-05T07:20:10Z'
  edited_at: '2026-10-14T10:05:54Z'
  id: 115003326706
  locale: zh-cn
  section: Adobe
  section_id: 6551419728657
  url: https://support.appsflyer.com/hc/zh-cn/articles/115003326706
---
> **概要：** [Adobe Analytics](http://www.adobe.com/marketing-cloud/web-analytics.html)（原Omniture）是一套可以与第三方渠道对接的预测和实时分析工具。该工具套件包括Marketing Reports and Analytics（也称 SiteCatalyst）、Ad Hoc Analysis（Adobe Discover）以及Insight等应用程序，能通过将用户交互转化为洞察，帮助企业全面了解业务运营情况。

<div id="overview" />

## 概览

此对接可实现Adobe与AppsFlyer之间的双向数据传输。为确保对接成功，您需要在应用中部署相应代码，且需同时满足AppsFlyer和Adobe的对接要求，以获取完整功能。

<div id="setting-up-adobe-analytics-integration" />

## 设置Adobe Analytics对接

如您使用Adobe Analytics的报告套件分析整体广告效果和创建人群包，那么您可以通过AppsFlyer与Adobe Analytics的对接将归因数据从AppsFlyer自动传输到Adobe。

<div id="prerequisites" />

### 前期准备：

* 根据<Anchor target="_blank" href="https://developer.adobe.com/client-sdks/documentation/">Adobe Experience Platform移动SDK文档</Anchor>进行设置
* <Anchor target="_blank" href="https://marketing.adobe.com/resources/help/en_US/mcvid/">Marketing Cloud Visitor ID</Anchor>或Experience cloud ID service
* 每个Report Suite中需预留三个eVar，仅用于本次对接

<div id="step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer" />

### 第1步：与AppsFlyer共享Adobe Experience Cloud ID（ECID、Marketing Cloud ID或Visitor ID）。

提取并共享Adobe Experience Cloud ID：

1. <Anchor target="_blank" href="https://developer.adobe.com/client-sdks/documentation/mobile-core/identity/api-reference/#getexperiencecloudid">更新应用，并在Adobe SDK初始化完成后，通过Adobe提供的方法提取Marketing Cloud Visitor ID</Anchor>。
2. 使用AppsFlyer SDK中的以下任一方法，将该ID共享给AppsFlyer：

<div id="setadditionaldata" />

<Accordion title="setAdditionalData">

<Tabs>
<Tab title="安卓">

详见[setAdditionalData方法](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata)说明。

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
customData .put("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyerLib.setAdditionalData(customData);
```

</Tab>

<Tab title="iOS">

详见[setAdditionalData方法](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata)说明。

Objective C

```objectivec
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{
  @"marketingCloudID" : "ADOBE_VISITOR_ID"
}];
```

Swift

```swift
let CustomDataMap: [AnyHashable: Any] = [
  "marketingCloudID" : "ADOBE_VISITOR_ID"
]
AppsFlyerTracker.shared().customData = CustomDataMap
```

</Tab>

<Tab title="Unity">

详见[setAdditionalData方法](https://dev.appsflyer.com/hc/docs/api#setadditionaldata)说明。

```csharp
Dictionary<string, string> CustomDataMap = new Dictionary<string, string>();
CustomDataMap.Add("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyer.setAdditionalData(CustomDataMap);
```

</Tab>
</Tabs>

</Accordion>

<div id="setcustomeruserid" />

<Accordion title="设置Customer User ID">

<Tabs>
<Tab title="Android">

详见<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">setCustomerUserId</Anchor><Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">方法</Anchor>说明。

```java
AppsFlyerLib.getInstance().setCustomerUserId("ADOBE_VISITOR_ID");
```

</Tab>

<Tab title="iOS">

详见<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">setCustomerUserId方法</Anchor>说明。

Objective C

```objectivec
NSString *customerUserID = [AppsFlyerLib shared].customerUserID;
```

Swift

```swift
let customerUserID = AppsFlyerLib.shared().customerUserIDp
```

</Tab>
</Tabs>

</Accordion>

<div id="step-2-configure-adobe-analytics-in-appsflyer" />

### 第2步：在AppsFlyer中配置Adobe Analytics

**前期准备：** 在设置对接之前，请确保已将[Adobe Marketing Cloud Visitor ID成功发送至AppsFlyer SDK](/docs/adobe-analytics-integration-with-appsflyer#第1步与appsflyer共享adobe-experience-cloud-idecidmarketing-cloud-id或visitor-id)。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作**> **Partner Marketplace**。  
   **修改方式**：从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索并选择**Adobe Analytics**。
3. 点击**设置对接**。界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关始终处于打开 <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">（启用）</Anchor> 状态。
5. 打开**Adobe Analytics SDK**中的配置文件（**ADBMobileConfig.XML**），复制**Report\_Suite\_ID**（蓝框标记）和**Adobe\_Analytic\_server\_URL**（绿框标记），并将以上信息分别粘贴至AppsFlyer Adobe Analytics对接设置页面的相应字段。  

   ![](https://files.readme.io/fb46a40178b88dc8f8fb0f9bcce5aa289fc27c2dbf52d1e67783c7b764729f0f-360001063605.png)
6. 点击**保存对接**。

保存后，AppsFlyer将在每次自然或非自然激活发生时，向Adobe Analytics发送以下数据：

* Adobe ID (MCVID)
* Report Suite ID与Server URL
* 用户设备ID
* 媒体渠道
* 广告活动名称

<div id="note" />

> 📘 **注意事项**
>
> 根据Meta Ads和X Ads的服务条款，AppsFlyer不得与第三方共享用户层级数据。也就是说，Meta Ads和X Ads的激活数据将被视为自然流量。

<div id="step-3-map-data-to-evars-in-adobe-analytics" />

### 第3步：将数据映射到Adobe Analytics中的eVars

由于Adobe Analytics Data Connectors已停用，您需要借助处理规则（Processing Rules）将上下文变量（Context Data Variables）映射到eVar中。

详见[处理规则](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html?lang=en)使用说明。

AppsFlyer上下文数据变量的映射方式如下：

* MobileAdCampaign(Context Data)
* MobileAdNetwork(Context Data)
* MobileAdProvider(Context Data)

如果您在通过处理规则映射 AppsFlyer 上下文数据变量时遇到问题，请联系您的 Adobe 客户经理以获取进一步支持。

<div id="step-4-optional-set-up-your-marketing-channel" />

### 步骤 4 [可选]：设置您的营销渠道

请参阅<Anchor target="_blank" href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-channels.html">Adobe Analytics文档</Anchor>，了解如何在其平台上设置您的营销渠道。在配置识别规则时，请选择以下字段：

1. "由Adobe Web Beacon设置的转化变量值"：选择**AppsFlyer**和**Exists**。
2. "将渠道标识为"：选择**Mobile App Attribution**。
3. "将渠道的值设置为"：选择**AppsFlyer Campaign**。

<div id="domain-and-security-details" />

## 域名和安全性说明

以下是域名及安全性配置相关的重要信息：

1. 您可以在应用程序配置文件下的服务器变量中找到ANALYTIC\_SERVER\_DOMAIN。您可以选择任何域名进行归因分析。一般建议使用Adobe Analytics推荐的标准域名，例如sc.omtrdc.net，该值可在**ADBMobile.config**文件的analytics.server设置中找到。
2. URL协议（HTTP/HTTPS）取决于ANALYTIC\_SERVER\_DOMAIN是否为安全连接。请务必使用正确的协议。要确定设置是否安全，请检查**ADBMobile.config**文件中的analytics (SSL)设置是否为**true**。若为true，请使用HTTPS；若为false，请使用HTTP。
3. REPORT SUITE ID可在应用配置文件中的rsids变量中找到。您可以自行为Report Suite命名。
4. ts=`{timestamp}`：仅在配置文件中的**offlineEnabled**设置为true时使用。若**offlineEnabled**为false，或您的Report Suite未启用**时间戳**，请从URL中移除此参数。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01HA4ZWDM1MEW2VDFXYMAJ2QE2=%E6%A6%82%E8%A7%88 setting-up-adobe-analytics-integration=%E8%AE%BE%E7%BD%AEadobe-analytics%E5%AF%B9%E6%8E%A5 h_01HA4ZWDM11RJ6GRJ7W8QMFACT=%E8%AE%BE%E7%BD%AEadobe-analytics%E5%AF%B9%E6%8E%A5 prerequisite=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01HA4ZWDM1YK58Q56Y0S8PC1E2=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer=%E7%AC%AC1%E6%AD%A5%E4%B8%8Eappsflyer%E5%85%B1%E4%BA%ABadobe-experience-cloud-idecidmarketing-cloud-id%E6%88%96visitor-id h_01HA4ZWDM1J65D32PVXY0ZD9YV=%E7%AC%AC1%E6%AD%A5%E4%B8%8Eappsflyer%E5%85%B1%E4%BA%ABadobe-experience-cloud-idecidmarketing-cloud-id%E6%88%96visitor-id h_01HA4ZWDM1RDRDGZ3X7WC0ACV1=setadditionaldata h_01HA4ZWDM1CAXZH7ZNJ0Z37EE1=setcustomeruserid step-2-configure-adobe-analytics-in-appsflyer=%E7%AC%AC2%E6%AD%A5%E5%9C%A8appsflyer%E4%B8%AD%E9%85%8D%E7%BD%AEadobe-analytics h_01HA4ZWDM26AVEQKC4CXF18D22=%E7%AC%AC2%E6%AD%A5%E5%9C%A8appsflyer%E4%B8%AD%E9%85%8D%E7%BD%AEadobe-analytics h_01HA4ZWDM23A6BFXDV2JH4NR2J=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 step-3-map-data-to-evars-in-adobe-analytics=%E7%AC%AC3%E6%AD%A5%E5%B0%86%E6%95%B0%E6%8D%AE%E6%98%A0%E5%B0%84%E5%88%B0adobe-analytics%E4%B8%AD%E7%9A%84evars h_01HA4ZWDM27S52KY36GS1QPKJ5=%E7%AC%AC3%E6%AD%A5%E5%B0%86%E6%95%B0%E6%8D%AE%E6%98%A0%E5%B0%84%E5%88%B0adobe-analytics%E4%B8%AD%E7%9A%84evars step-4-%5Boptional%5D-set-up-your-marketing-channel=%E6%AD%A5%E9%AA%A4-4-%E5%8F%AF%E9%80%89%E8%AE%BE%E7%BD%AE%E6%82%A8%E7%9A%84%E8%90%A5%E9%94%80%E6%B8%A0%E9%81%93 h_01HA4ZX6FG6RM5JNDKQP6GVAD1=%E6%AD%A5%E9%AA%A4-4-%E5%8F%AF%E9%80%89%E8%AE%BE%E7%BD%AE%E6%82%A8%E7%9A%84%E8%90%A5%E9%94%80%E6%B8%A0%E9%81%93 domain-and-security-details=%E5%9F%9F%E5%90%8D%E5%92%8C%E5%AE%89%E5%85%A8%E6%80%A7%E8%AF%B4%E6%98%8E h_01HA4ZWDM2NNFVPP1XYWKPS89A=%E5%9F%9F%E5%90%8D%E5%92%8C%E5%AE%89%E5%85%A8%E6%80%A7%E8%AF%B4%E6%98%8E" />
