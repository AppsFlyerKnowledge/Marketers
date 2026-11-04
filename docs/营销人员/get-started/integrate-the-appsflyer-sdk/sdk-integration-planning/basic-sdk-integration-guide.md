---
title: 基础SDK对接指南
metadata:
  keywords:
    - sdk
    - iOS
    - Android
    - Integration
    - Advertisers
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2013-08-22T16:09:08Z'
  edited_at: '2026-10-14T10:10:10Z'
  id: 207032066
  locale: zh-cn
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/zh-cn/articles/207032066
---
> **概要：** 本文将指导您如何与移动端或CTV端开发人员合作，在安卓或iOS应用中接入并安装SDK。基础的对接工作完成后，您就可以对该应用的激活进行归因，并衡量其应用内事件。

<div id="implementing-the-dev-key-in-your-app" />

## **在相关应用中添加dev key**

这是AppsFlyer对您的帐户进行唯一性标识的方式。dev key是对接SDK时的必填字段，因为SDK需要通过dev key才能安全地发送/拉取属于您账户的数据。您的开发人员需要在相关应用中安装并对接SDK，然后嵌入dev key。

<div id="retrieve-the-dev-key" />

#### 获取dev key

在开发人员安装并接入SDK之前，您必须先获取dev key，

1. 从AppsFlyer后台的侧边栏中选择**配置** > **应用配置**。
2. 复制dev key，并发送给您的移动端开发人员。[![](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)

<div id="provide-the-dev-key-to-your-developer" />

#### 将dev key提供给您的开发人员

将dev key、应用程序 ID 和 AppsFlyer API v2 token提供给您的移动开发人员，并附上说明：

* 请使用<Anchor target="_blank" href="https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration">SDK对接向导</Anchor>（SDK Integration Wizard）完成自动化SDK安装与对接。
* 您也可以按照分步骤指南手动<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">安装</Anchor>并<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-integration">对接SDK</Anchor>。

<div id="where-to-start-the-sdk" />

## **SDK初始化节点**

规划AppsFlyer SDK对接时，首先需要明确SDK在应用打开流程中的初始化节点。

主流的做法是让SDK在应用打开后尽快开始发送数据，**这能确保SDK捕捉到激活以及首个session中所有的应用内事件。**

但是为了确保GDPR和CCPA等隐私保护条例的合规性，广告主可能需要让SDK先等待用户同意共享信息，然后才向AppsFlyer发送数据。

<Tabs>
<Tab title="安卓原生">

<div id="starting-the-sdk-in-android-native" />

### 在安卓端原生环境中启动SDK

<div id="select-in-what-class-to-start-the-sdk" />

#### 选择启动SDK的类（Class）

您可以选择在全局`Application`类或在`Activity`类中启动SDK：

* **如果在全局**`Application`**类中启动SDK：** 一般情况下，推荐在全局`Application`类/子类中启动SDK，因为`Application`类会在应用界面打开之前加载并初始化。这可以确保SDK在任何场景中都能启动，包括深度链接。
* **在**`Activity`**类中启动SDK（延迟启动）**：适用于需要用户授权共享数据的场景。这是因为请求用户授权需要用到`Activity`类中的用户界面（UI）。

<div id="android-developer-instructions" />

#### 安卓端开发人员相关说明

* 开发人员需要了解以下问题的最终决定：
  * SDK在哪个类中启动：`Application`还是`Activity`？
  * 使用哪一种Opt-in/Opt-out场景？
* 请将以下参考文档的链接发送给您的开发人员：
  * [如何实现SDK的延迟启动](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-the-android-sdk)

</Tab>

<Tab title="iOS原生">

<div id="starting-the-sdk-in-ios" />

<div id="starting-the-sdk-in-ios-native" />

### 在iOS端原生环境中启动SDK

<div id="delay-the-sdk-start-in-ios" />

#### 在iOS中延迟SDK的启动

规划SDK的启动方式时，您必须决定是否要延迟`start`的调用，等待用户授权。

AppsFlyer的SDK提供`waitForATTUserAuthorization`方法，用于**配置SDK在向AppsFlyer服务器发送数据前等待用户授权的时长**。

如需进一步了解该方法的数据流及其与iOS ATT框架的交互方式，请参考[应用追踪透明度](/docs/basic-sdk-integration-guide#waitforattuserauthorization功能简介)

<div id="ios-developer-instructions" />

#### iOS端开发人员相关说明

请与您的开发人员共享以下信息：

* 在向AppsFlyer发送数据之前等待几秒？
* 开发者文档链接：
  * 开发人员[iOS SDK启动](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#starting-the-ios-sdk)指南及参考信息。
  * [应用追踪透明度（ATT）支持配置指南](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support)中说明了`waitForATTUserAuthorization`方法的数据流及其与iOS ATT框架交互的方式
  * 开发人员的[应用追踪透明度（ATT）支持启用指南](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support)以及`waitForATTUserAuthorization`参考信息

</Tab>

<Tab title="Unity">

<div id="starting-the-sdk-in-Unity" />

<div id="starting-the-sdk-in-unity" />

### 在Unity中启动SDK

请将这篇<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#manual-integration">开发者文档</Anchor>发送给您的开发人员，其中说明了SDK的启动方式。

</Tab>

<Tab title="React Native">

<div id="starting-the-sdk-in-react" />

<div id="starting-the-sdk-in-react-native" />

### 在React Native中启动SDK

请将这篇<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#startsdk">开发者文档</Anchor>发送给您的开发人员，其中说明了SDK的启动方式。

</Tab>
</Tabs>

<div id="select-your-privacy-preserving-strategy" />

## 选择您的隐私保护策略

选择您**保护用户隐私的方式**。可选方案包括在应用激活时停用SDK、禁止第三方共享数据、对用户数据进行匿名化处理或禁用某些标识符。

如需进一步了解保护用户隐私的SDK配置，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-privacy-preserving-sdk-methods">此文档</Anchor>。

<div id="attribution" />

## **归因**

SDK会收集<Anchor target="_blank" href="/marketers/zh/docs/about-device-identifiers">标识符</Anchor>（identifier），用于归因。 为确保激活能够得到准确的记录和归因，请按照以下指南进行操作。

**所有平台**

<div id="unique-identifier-for-installs" />

<Accordion title="激活的唯一标识符">

用户每次安装一个应用后，AF都会为其匹配一个专属的AppsFlyer ID。这个环节无需市场人员进行任何操作。

您可以使用该标识符来完成下列事项：

* 发送<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S应用内事件</Anchor>。
* 将AppsFlyer ID与您后台的用户记录进行匹配。
* 下载<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">应用内事件原始数据报告</Anchor>并使用**appsflyer\_id**来分析用户行为和链路。

</Accordion>

<div id="integrate-unique-identifiers-from-your-bi-system-with-appsflyer" />

<Accordion title="将BI系统中的唯一标识符接入AppsFlyer系统">

在AppsFlyer SDK中设置CUID（客户用户ID）后，您就可以对BI系统中的专属ID、AppsFlyer ID和其他ID进行交叉对照。您可以在AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">原始数据</Anchor>报告中查看CUID，还能在回传API中使用该ID与您的内部ID进行交叉索引。

如需进一步了解CUID，请参阅<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">此文档</Anchor>。

</Accordion>

**仅适用于安卓**

以下章节解释了对来自Google Play或第三方应用商店的流量进行归因时需要考虑到哪些因素。

<div id="attribute-apps-published-on-google-play" />

<Accordion title="对来自Google Play的流量进行归因">

#### GOOGLE PLAY INSTALL REFERRER

[Google Play Install Referrer API](https://developer.android.com/google/play/installreferrer)改善了<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#归因方法">归因</Anchor>准确率，保护广告主免受假量侵害，而且能以安全的方式让广告主从Google Play获取安装来源数据（如应用首次激活时的版本信息）。

建议您将[Google Play Install Referrer API部署指南](https://developer.android.com/google/play/installreferrer/library)发送给开发人员。

#### GAID

从SDK V4.8.0开始，AppsFlyer会自动收集这个设备标识符。

</Accordion>

<div id="attribute-apps-in-thirdparty-app-stores" />

<Accordion title="对第三方应用商店中的应用进行归因">

您可以通过AppsFlyer<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution">对来自第三方应用商店的激活进行归因</Anchor>，这些商店包括亚马逊、Opera,、GetJar、百度和华为。 这样，您就可以在没有Google Play商店的市场中推广您的应用，并触达更多用户。

AppsFlyer支持第三方应用商店的归因，具体如下：

* **IMEI或Android ID：** SDK不会自动收集IMEI或Android ID。如果您需要收集这些标识符（如<Anchor target="_blank" href="/marketers/zh/docs/measure-attribution-in-the-chinese-domestic-market#中国国内安卓市场归因指南">在中国国内市场推广应用</Anchor>时），可以让开发人员通过以下任意一种方式来实现这一功能：
  * 手动收集： 手通过 `setImeiData`或`setAndroidIdData` API（详见下方窗口中列出的参考函数信息），让应用将IMEI或Android ID发送给SDK，然后SDK再将数据发送到AppsFlyer服务器。

    <Tabs>
    <Tab title="安卓端原生">

    安卓SDK参考信息：

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>

    <Tab title="Unity">

    Unity SDK参考信息：

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>
    </Tabs>

  * 启用设备ID收集：使用setCollectIMEI和setCollectAndroidID强制SDK收集IMEI或Android ID（详见下方窗口中列出的参考函数信息）。

    <Tabs>
    <Tab title="安卓端原生">

    安卓SDK参考信息：

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>

    <Tab title="UnityReact Native">

    Unity SDK参考信息：

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>
    </Tabs>

* **OAID：** 您可通过该ID对来自第三方安卓应用商店的激活进行归因。详情请见<Anchor target="_blank" href="/marketers/zh/docs/android-oaid-implementation-in-the-sdk">OAID使用指南</Anchor>。
* **Install referrer（激活来源标识）：** AF的SDK支持从Samsung Gallery和华为应用市场拉取referrer数据。

</Accordion>

**仅适用于iOS**

以下几个章节中包含了适用于iOS 14+设备的重要信息。

<div id="configure-app-tracking-transparency-att-support" />

<Accordion title="适用于ATT框架的配置">

**背景介绍**

从iOS 14.5开始，IDFA的收集需要得到用户的授权。也就是说IDFA的读取权限是由[**App Tracking Transparency**](https://developer.apple.com/documentation/apptrackingtransparency)（应用追踪透明度，简称ATT）框架所控制的。在iOS 14+设备上，SDK需要通过ATT框架来获取设备IDFA的读取权限。有关ATT的简介请参阅<Anchor target="_blank" href="/marketers/zh/docs/about-att-and-skan#att-principles">ATT原则</Anchor>。

<Tabs>
<Tab title="iOS端原生">

详见开发者资源中心（Dev Hub）中的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support">ATT部署指南</Anchor>。

</Tab>

<Tab title="Unity">

详见开发者资源中心（Dev Hub）中的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager">ATT部署指南</Anchor>。

</Tab>
</Tabs>

若使用IDFA进行归因，一定要在应用**首次启动时发送IDFA。** 为此，AppsFlyer SDK专门提供了`waitForATTUserAuthorization`方法以确保相关数据的发送。

<div id="waitforattuserauthorization-overview" />

#### waitForATTUserAuthorization功能简介

<div id="important" />

> 🚧 **重要提示！**
>
> 如果您不打算触发ATT弹窗，请不要调用`waitForATTUserAuthorization`。

您可以通过`waitForATTUserAuthorization`来设定让SDK延迟多久再将数据发送给AppsFlyer服务器，并在此期间等待ATT授权状态。

[![](https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png)](https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png)

当终端用户打开应用时，ATT状态为**notDetermined**。 在`waitForATTUserAuthorization`响应超时期间，SDK会将激活和后续的应用内事件组成队列保存在缓存中，这与离线事件的记录方式相似。

* 如果用户在ATT弹窗中选择了**同意**（IDFA收集）：
  * SDK将IDFA添加到缓存的事件中。
  * SDK启动，发送带有IDFA的缓存事件（无需等到timeout结束）
* 如果用户在ATT弹窗中选择**拒绝授权**：SDK启动后发送不带有IDFA的缓存事件（无需等到计时器走完）
* 如果计时器走完后ATT状态仍然是 ：SDK启动后发送不带有IDFA的缓存事件。

**注意事项**

* 对于iOS 14+设备，如果在没有设置`waitForATTUserAuthorization`的情况下调用[`requestTrackingAuthorization`](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/3547037-requesttrackingauthorization)，则应用打开和其他事件的回传中不会带有IDFA。
* 如果用户在timeout期间将应用切换至后台：
  * timeout计时器暂停，直到该应用重新返回到前台运行。
  * 事件被保存在缓存中。
* 如果用户在timeout期间关闭应用，系统自动退出：
  * 计时器在下次应用启动时重新开始计时。
  * 缓存的事件会丢失。

</Accordion>

<div id="customize-att-consent-dialog" />

<Accordion title="定制ATT授权弹窗的文案">

您可以在ATT弹窗中使用定制的文案。清晰地说明收集设备ID的意义能够提升用户的同意率。

编写弹窗文案时请注意以下事项：

* 以最清晰有效的方式向用户解释您的应用为什么要请求授权。
* 告诉用户他们的数据会以何种方式被使用。 [详情请见用户隐私和数据使用。](https://developer.apple.com/app-store/user-privacy-and-data-use/)

弹窗文案完成后，请将执行指南与文案一并发送给开发人员。

<Tabs>
<Tab title="iOS端原生">

详见开发者资源中心（Dev Hub）中的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#customizing-the-att-consent-dialog">ATT授权弹窗定制指南</Anchor>。

</Tab>

<Tab title="Unity">

详见开发者资源中心（Dev Hub）中的[ATT授权弹窗定制指南](https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager)。

</Tab>
</Tabs>

<div id="support-for-skan-attribution" />

<Accordion title="适用于SKAN归因的配置">

<div id="note" />

> 📘 **注意**
>
> 要全面支持SKAN归因，您需要先升级到iOS SDK V6.2.3以上版本。

SKAN是iOS中用来验证非自然激活的一种方式，其中的应用激活验证流程涉及到流量方应用（source app）和广告主应用（advertised app）。

在广告平台上投放的广告会展示在流量方应用中。广告展示的配置并不在AppsFlyer SDK可控制的范围内。如需进行相关配置，请按照[Apple的相关说明](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app)进行操作。

对于广告主应用（即配有AppsFlyer SDK的应用），AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">SKAN解决方案</Anchor>会通过SKAN来实现归因回传，同时在确保用户隐私的前提下对数据进行收集、转换和汇总。用户首次启动应用时，AppsFlyer平台会基于广告主侧所设定的配置来指导SDK如何设置SKAN转化值。

请按以下步骤启用SKAN解决方案：

* 首先，市场人员需要在AppsFlyer后台配置SKAN衡量方案。 开发人员无需进行任何操作。
* AppsFlyer SDK 会自动调用必要的SKAN API。
* 通过AppsFlyer进行SKAN归因时，请务必关闭其他SDK中的SKAN调用。
* 开发人员和市场人员都无需在App Store中再完成其他操作或注册流程。

如需关闭SKAN归因，请让您的开发人员在SDK中将其禁用。

<Tabs>
<Tab title="iOS端原生">

如需禁用SKAN归因，请使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableskadnetwork">`disableSKAdNetwork`</Anchor>。

</Tab>

<Tab title="UnityReact Native">

如需禁用SKAN归因，请使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#disableskadnetwork">`disableSKAdNetwork`</Anchor>。

</Tab>
</Tabs>

</Accordion>

</Accordion>

<div id="recording-in-app-events" />

## **记录应用内事件**

应用内事件（简称IAE）能让您深入了解用户在应用中的行为。记录应用内事件能帮助您衡量ROI（投资回报率）和LTV（生命周期价值）等一系列KPI，因此建议您认真仔细地去定义需要记录的事件。

确定了您想要衡量的应用内事件后，请将这些事件名称、事件参数以及以下链接一并发送给您的开发人员：

* [SDK 安装向导](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration)，包含专门针对应用内事件的对接流程
* <Anchor target="_blank" href="http://dev.appsflyer.com/hc/docs/in-app-events-sdk">帮助开发者在SDK中实现事件追踪的分步指南</Anchor>

要了解如何定义应用内事件并将其发送给开发人员，请参阅我们的<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件指南</Anchor>。

**所有平台**

<div id="record-revenue" />

<Accordion title="记录收入">

您可以通过任何应用内事件发送收入数据。如需记录收入数据，请务必使用**af\_revenue**参数，只有这个参数才在原始数据和面板报告中统计实际收入。 详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#revenue-events">此文档</Anchor>。

<Tabs>
<Tab title="安卓原生">

开发人员的收入事件设定指南请见[此文档](https://dev.appsflyer.com/hc/docs/in-app-events-android#logging-revenue)。

</Tab>

<Tab title="iOS nativeUnity">

开发人员的收入事件设定指南请见[此文档](https://dev.appsflyer.com/hc/docs/in-app-events-ios#logging-revenue)。

</Tab>
</Tabs>

</Accordion>

<div id="validate-inapp-purchases" />

<Accordion title="验证应用内购">

AppsFlyer的SDK可通过服务器验证机制对应用内购进行验证。应用内购验证功能会自动将应用内购事件上报给AppsFlyer，如果广告主侧再发送这些事件就会造成重复上报。

</Accordion>

<div id="industry-verticals" />

<Accordion title="行业垂类">

请参考<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#recommended-events-by-business-vertical">按垂类梳理的应用内事件推荐</Anchor>，其中包括旅游、游戏、电商等各种垂类。

</Accordion>

<div id="deep-linking-with-onelink" />

## **OneLink™深度链接**

OneLink是AppsFlyer专为跨平台归因、**跳转和深度链接**而设计的解决方案。

**所有平台**

<div id="device-detection-and-redirection" />

<Accordion title="设备识别和跳转">

若用户还未安装应用，OneLink能够识别设备类型并跳转到正确的终点（如Google Play、苹果应用商店、三方应用商店、网页等）。具体的跳转取决于您的OneLink模板设置。 <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">详情请见此处说明。</Anchor>

</Accordion>

<div id="deep-linking" />

<Accordion title="深度链接">

如果用户已经安装了您的应用，OneLink就会打开该应用。此外，您还可以通过深度链接让用户跳转到应用中某个具体的页面。您的开发人员可以通过以下方式实现Unified Deep Linking（UDL）：

* [SDK安装向导](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration)，包含专门针对深度链接的实现流程
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">实现Unified Deep Linking的分步指南</Anchor>

**请注意**：

* 若需使用UDL，请确保安装SDK V6.1或以上版本。
* 如果您已经在用OneLink进行深度链接，那么您可能是通过[历史API的方式](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking)实现的，而非UDL。

请参见<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">深度链接和延迟深度链接</Anchor>的设置指南。

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="延迟深度链接">

如果用户尚未安装相关应用，OneLink能够识别设备类型并跳转到对应的终点，不管是Google Play、Apple App Store,、第三方应用商店还是落地页。延迟深度链接可以在用户打开应用时将其引导至应用中某个特定的页面。

您的开发人员可以过以下方式实现延迟深度链接。

* [SDK安装向导](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration)，包含专门针对深度链接的实现流程
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">实现延迟深度链接的分步指南</Anchor>

**请注意**：

* 若需使用UDL，请确保安装SDK V6.1或以上版本。
* 如果您已经在用OneLink进行延迟深度链接，那么您可能是通过[历史API的方式](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking)实现的，而非UDL。

请参见<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">深度链接和延迟深度链接</Anchor>的设置指南。

</Accordion>

<div id="accessing-attribution-and-deep-linking-data" />

## **拉取归因和深度链接数据**

下表罗列了归因和深度链接数据的各种拉取方式：

| 方法 | 相关人员 | 返回结果 | 拉取方式 | 归因数据 | 深度链接数据 | 可用性 |
| --- | --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/push-api-streaming-raw-data">**Push API**</Anchor> | • 市场人员 • 后端开发 | 一般为几分钟 | 后台 | Y | N | 高阶付费 |
| <Anchor target="_blank" href="/marketers/zh/docs/pull-api-raw-data">**Pull API**</Anchor> | • 市场人员 • 后端开发 | • 定期（非实时）。• 您可自行设定原始数据报告的下载时间。 | 后台 | Y | Y | 原始数据报告为高阶付费功能 |
| <Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">**Data Locker**</Anchor> | • 市场人员 • 后端开发 | 报告每小时更新，可在更新后的1-3小时内拉取到。 | 可从下列云端存储方案中任选一种：• AppsFlyer的AWS存储桶 • 您自有的AWS或GCS存储桶 | Y | Y | 高阶付费 |
| <Anchor target="_blank" href="/marketers/zh/docs/conversion-data-payloads-and-scenarios#速览">**Get conversion data (GCD)**</Anchor> | • 市场人员 • 移动端开发人员请参考<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">开发者专用文档</Anchor> | 最多5秒 | SDK | Y | Y | 所有账户 |
| <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">**Unified Deep Linking (UDL)**</Anchor> | • 市场人员 • 移动端开发人员请参考<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">开发者专用文档</Anchor> | 最多1秒 | SDK | N | Y | 所有账户 |

对于iOS 14.5+中未授权ATT的用户，请注意以下几点：

* 在付费媒体或自有媒体中使用UDL时，仍可获取深度链接数据。
* 在付费媒体中使用GCD时，数据受限且不包含归因和深度链接的具体数据。

<div id="tip" />

> 👍 **提示**
>
> 建议您按以下方式拉取数据：
>
> * 使用Push API拉取归因数据，将其发送到您的服务器上做进一步处理。使用这种方式时，API会等待归因结果，然后再回传数据，因此准确性较高，而且几乎是实时的。GCD虽然能实时返回数据，但由于系统至少需要5秒钟才能判断最终的归因结果，因此有时会出现不准确的现象。
> * 使用Pull API定期（如每天）拉取数据作为对实时归因数据的补充，同时也能弥补数据传输中可能发生的错误。

<div id="testing-your-sdk-integration" />

## **测试SDK对接**

SDK对接配置完成后，您就可以到AppsFlyer面板，进入SDK对接测试页面，测试自然和非自然激活、应用内事件和深度链接， 以确保激活和应用内事件能得到正确的记录和归因。

请参阅<Anchor target="_blank" href="/marketers/zh/docs/testing-the-sdk-integration-for-marketers">SDK对接测试</Anchor>说明，了解测试场景和相关指南。

**请注意：** 进行归因测试时，您需要先为您的<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices">测试设备加白</Anchor>（安卓或iOS），才能让AF后台将每次激活都记录为新增激活。测试设备加白后，重复激活应用不会被AF判定为重装激活。

<div id="note-1" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC和主机平台简介</Anchor>

<div data-zendesk-anchors="retrieving-the-dev-key=%E5%9C%A8%E7%9B%B8%E5%85%B3%E5%BA%94%E7%94%A8%E4%B8%AD%E6%B7%BB%E5%8A%A0dev-key h_01HAWCK9K4QBRE74JAS8Q7MEXW=%E5%9C%A8%E7%9B%B8%E5%85%B3%E5%BA%94%E7%94%A8%E4%B8%AD%E6%B7%BB%E5%8A%A0dev-key retrieve-the-dev-key=%E8%8E%B7%E5%8F%96dev-key h_01HHHKTARNPQTBXQ6CQGEHMJRG=%E8%8E%B7%E5%8F%96dev-key embed-the-dev-key=%E5%B0%86dev-key%E6%8F%90%E4%BE%9B%E7%BB%99%E6%82%A8%E7%9A%84%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98 h_01HHHKXMBGV6EM0CCW842RQQZ6=%E5%B0%86dev-key%E6%8F%90%E4%BE%9B%E7%BB%99%E6%82%A8%E7%9A%84%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98 where-to-start-the-sdk=sdk%E5%88%9D%E5%A7%8B%E5%8C%96%E8%8A%82%E7%82%B9 h_01HAWCK9K4MBS0F0HE6QE1W1AN=sdk%E5%88%9D%E5%A7%8B%E5%8C%96%E8%8A%82%E7%82%B9 starting-the-sdk-in-android=%E5%9C%A8%E5%AE%89%E5%8D%93%E7%AB%AF%E5%8E%9F%E7%94%9F%E7%8E%AF%E5%A2%83%E4%B8%AD%E5%90%AF%E5%8A%A8sdk h_01HAWCK9K45HCJEDRW761WHKES=%E5%9C%A8%E5%AE%89%E5%8D%93%E7%AB%AF%E5%8E%9F%E7%94%9F%E7%8E%AF%E5%A2%83%E4%B8%AD%E5%90%AF%E5%8A%A8sdk select-in-what-class-to-start-the-sdk=%E9%80%89%E6%8B%A9%E5%90%AF%E5%8A%A8sdk%E7%9A%84%E7%B1%BBclass h_01HAWCK9K428SDFBFCCSZ15X9J=%E9%80%89%E6%8B%A9%E5%90%AF%E5%8A%A8sdk%E7%9A%84%E7%B1%BBclass android-developer-instructions=%E5%AE%89%E5%8D%93%E7%AB%AF%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E7%9B%B8%E5%85%B3%E8%AF%B4%E6%98%8E h_01HAWCK9K4XR1HZHP7Y15Q2Q4N=%E5%AE%89%E5%8D%93%E7%AB%AF%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E7%9B%B8%E5%85%B3%E8%AF%B4%E6%98%8E h_01HAWCK9K4693729EX1WYFR6XT=starting-the-sdk-in-ios h_01HAWCK9K4QSBP874RX2ZRA7EB=delay-the-sdk-start-in-ios h_01HAWCK9K4VHDFB9CYHC144BZN=ios-developer-instructions select-the-optoutin-scenario::ae4c6e25=%E9%80%89%E6%8B%A9%E6%82%A8%E7%9A%84%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4%E7%AD%96%E7%95%A5 h_01HAWCK9K4EXBA2F0BPVBXFAMG=%E9%80%89%E6%8B%A9%E6%82%A8%E7%9A%84%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4%E7%AD%96%E7%95%A5 attribution=%E5%BD%92%E5%9B%A0 h_01HAWCK9K41T5GGWDB3ABYGRHW=%E5%BD%92%E5%9B%A0 h_01HAWCK9K4HY8NZC0VM3NBF4H9=unique-identifier-for-installs h_01HAWCK9K44GRVGBB1P3FWBX4A=integrate-unique-identifiers-from-your-bi-system-with-appsflyer h_01HAWCK9K4SE4YWTQYF3R1WH2Z=attribute-apps-published-on-google-play h_01HAWCK9K4V91MPQHXDZBD0HKR=google-play-install-referrer h_01HAWCK9K4YD8CYQDB2YRA8W1F=gaid h_01HAWCK9K4EFCGWJ45K8VRAFFM=attribute-apps-in-thirdparty-app-stores h_01HAWCK9K5VKBZS5MSF27WNG1G=configure-app-tracking-transparency-att-support waitforattuserauthorization-overview=waitforattuserauthorization%E5%8A%9F%E8%83%BD%E7%AE%80%E4%BB%8B h_01HAWCK9K5JHDWS8KTBTTGSS9G=waitforattuserauthorization%E5%8A%9F%E8%83%BD%E7%AE%80%E4%BB%8B h_01HAWCK9K5X4Z9DWRT1VDSFEPH=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HAWCK9K5FY2H211JFQQDSXHK=customize-att-consent-dialog h_01HAWCK9K5HV3SBY82A28ZD4KN=support-for-skan-attribution h_01HAWCK9K5HS9Y836X33YMV21C=%E6%B3%A8%E6%84%8F recording-inapp-events=%E8%AE%B0%E5%BD%95%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HAWCK9K5ZZYQR8KPCWANZEA5=%E8%AE%B0%E5%BD%95%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HAWCK9K50T438WCG0PKP5M3G=record-revenue h_01HAWCK9K5Z0N6DP38VCB3K3B2=validate-inapp-purchases h_01HAWCK9K5A3W2XKCM7XRNGKQK=industry-verticals deep-linking-with-onelink=onelink%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01HAWCK9K5PK9RE7WZQVCY97KC=onelink%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01HAWCK9K593KCJ9QQQV0E0E71=device-detection-and-redirection h_01HAWCK9K5SNBFHNFXYBBC20HN=deep-linking h_01HAWCK9K5YJSB78Z4RJSAP1KM=deferred-deep-linking accessing-attribution-and-deep-linking-data=%E6%8B%89%E5%8F%96%E5%BD%92%E5%9B%A0%E5%92%8C%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E6%95%B0%E6%8D%AE h_01HAWCK9K5ACPZ2WKBTVR3VVTD=%E6%8B%89%E5%8F%96%E5%BD%92%E5%9B%A0%E5%92%8C%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E6%95%B0%E6%8D%AE h_01HAWCK9K6N405V344RDEGC0QJ=%E6%8F%90%E7%A4%BA testing-your-sdk-integration=%E6%B5%8B%E8%AF%95sdk%E5%AF%B9%E6%8E%A5 h_01HAWCK9K6JQ33T32RYKYH20P1=%E6%B5%8B%E8%AF%95sdk%E5%AF%B9%E6%8E%A5 h_01H9FHRVKE88CXGH8G7E26ZXT2=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
