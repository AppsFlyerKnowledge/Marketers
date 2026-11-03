---
title: Amplitude与AppsFlyer的集成
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Amplitude
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
  created_at: '2016-08-02T05:18:03Z'
  edited_at: '2026-10-14T10:13:59Z'
  id: 211200306
  locale: zh-cn
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/zh-cn/articles/211200306
---
> **概要：** 将AppsFlyer与Amplitude集成，以共享用户归因数据和事件分析，从而更好地洞察用户参与度、留存率和收入。根据您的用例和分析需求，在**两个集成版本——V1或V2**之间进行选择。

## 关于集成

Amplitude是AppsFlyer的集成合作伙伴，是一个产品分析平台，供产品、增长和营销团队使用，以了解用户在移动和网络上的行为。该集成允许AppsFlyer在安装后将关键事件数据发送到Amplitude，从而实现全面的用户级分析。

有两个Amplitude集成版本：

* **Amplitude V1:**  
  此版本使用Amplitude的归因API。AppsFlyer在集成完成后发送收集的安装数据。Amplitude使用广告ID作为标识符，如果在72小时内没有记录匹配的用户事件，则会丢弃数据。<Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/attribution">详情请见此处说明。</Anchor>
* **Amplitude V2 :**  
  此版本使用Amplitude的HTTP V2 API。完成对接后，AppsFlyer 可向其同步激活事件与应用内事件数据。系统会优先使用 user\_id 和 device\_id 进行用户匹配，若匹配失败，则会记录为新用户。<Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/http-v2">详情请见此处说明。</Anchor>

<span id="h_01JSE81SX1FR182N1CZJ5CQP5N"></span>**<span id="integration-methods"></span>集成版本:**

| 版本 | 使用的API | 使用的标识符 | 事件覆盖 |
| --- | --- | --- | --- |
| **V1** | Attribution API | 广告ID（AdID） | 仅激活 |
| **V2** | HTTP V2 API | `user_id`, `device_id`（回退逻辑） | 安装和应用内事件 |

> 🚧 **重要提示！**
>
> * 选择 Amplitude V1 或 V2 集成。**请勿同时使用**。同时使用两个版本可能会导致重复事件发送到 Amplitude。
> * 某些媒体来源限制与第三方共享数据。即使已配置，受限事件的回传也不会发送给此合作伙伴。

## 前期准备

**前期准备：**

* 如果您还没有帐户，请联系 Amplitude 创建一个。
* 决定您将设置 Amplitude **V1** 还是 **V2** 集成。
* 确保您避免从 Amplitude SDK 和 AppsFlyer 同时发送相同的事件，以防止重复。
* 请查看 Amplitude V2 集成的额外前提条件。

### Amplitude V2 集成的额外前提条件

V2 集成需要设置：

* [Amplitude 设备 ID](/docs/amplitude-integration-with-appsflyer#amplitude-设备-id)
* [Customer user ID](/docs/amplitude-integration-with-appsflyer#customer-user-id)
* [Amplitude 会话 ID](/docs/amplitude-integration-with-appsflyer#amplitude-会话-id)

#### Amplitude 设备 ID

要启用用户级归因，您必须将 Amplitude 设备 ID 传递到 AppsFlyer SDK。此值会随每个回传发送。

<Tabs>
<Tab title="Android">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeDeviceId", amplitude.getDeviceId())
```

语言Java Kotlin

**文档：** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata">Android SDK 参考</Anchor>，<Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/android/android-kotlin-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Objective-C)">

```objc
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeDeviceId": [[Amplitude instance] getDeviceId]}];
```

语言Objective-C

**文档：** [iOS SDK 参考](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)，<Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeDeviceId": Amplitude.instance().getDeviceId()]
```

语言Swift

**文档：** [iOS SDK 参考](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)，<Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();  
customData.Add("AmplitudeDeviceId", Amplitude.getInstance().getDeviceId());  
AppsFlyer.setAdditionalData(customData);
```

语言C#

**文档:** [Unity SDK 参考](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="React Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()},  
(res) => {  
//...  
}  
);
```

语言JavaScript

**文档:** [React Native SDK 参考](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()});
```

语言JavaScript

**文档:** 不适用

</Tab>

<Tab title="Flutter">

```dart
var data = {"AmplitudeDeviceId": amplitude.getDeviceId()};  
appsFlyerSdk.setAdditionalData(data);
```

语言Dart

**文档:** [Flutter SDK 参考](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

#### Customer user ID

用于设置客户用户ID（CUID）。这是一个通常在用户注册期间由应用所有者生成和设置的唯一标识符。  
由应用所有者在用户注册期间设置。<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid?utm_source=chatgpt.com">详情请见此处说明。</Anchor>

#### Amplitude 会话 ID

设置 Amplitude 会话 ID 并将其传递给 AppsFlyer（可选）。<Anchor target="_blank" href="https://amplitude.com/docs/data/sources/instrument-track-sessions">详情请见此处说明。</Anchor>

<Tabs>
<Tab title="Android">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeSessionId", amplitude.getSessionId())
```

语言Java Kotlin

**文档:** [安卓SDK对接参考文档](https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Objective-C)">

```objc
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeSessionId": [[Amplitude instance] getSessionId]}];
```

语言Objective-C

**文档:** [iOS SDK 参考](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeSessionId": Amplitude.instance().getSessionId()]
```

语言Swift

**文档:** [iOS SDK 参考](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();  
customData.Add("AmplitudeSessionId", Amplitude.getInstance().getSessionId());  
AppsFlyer.setAdditionalData(customData);
```

语言C#

**文档:** [Unity SDK 参考](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="React Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()},  
(res) => {  
//...  
}  
);
```

语言JavaScript

**文档:** [React Native SDK 参考](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()});
```

语言JavaScript

**文档:** 不适用

</Tab>

<Tab title="Flutter">

```dart
var data = {"AmplitudeSessionId": amplitude.getSessionId()};  
appsFlyerSdk.setAdditionalData(data);
```

语言Dart

**文档:** [Flutter SDK 参考](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

## 如需设置对接：

**如需设置对接：**

1. 在 AppsFlyer 中，转到 **协作** >**合作伙伴市场**。
2. 要设置 Amplitude V1 集成，请选择 **Amplitude V1**（技术合作伙伴）。  
     
   <Image alt="选择 Amplitude V1 doctored.png" src="https://files.readme.io/71721bb1a48dda061ce2a099522edf9baed39ef2d67edad8ac14277b42cd2d70-36713632837777.png" width="511px" />  
     
     
   要设置 Amplitude V2 集成，请选择 **Amplitude V2** （技术合作伙伴）。   
     
   <Image alt="选择 Amplitude V2.png" src="https://files.readme.io/4bbf57727a2b6e16e5205505b459a78f8642f02d1bb1c4e8f72e26b3bd9e1bd3-36713631187857.png" width="503px" />
3. 选择 Amplitude 版本后，单击 **设置集成**。  
     
   点击![](https://files.readme.io/c13fef10fb4cf0ea12f44d56f8c3b64936376ce181a1d12c9f096ad6103c29a6-36713632857617.png)设置对接，
4. （此开关在**渠道对接**选项卡中）。
   * 选择您的应用。
   * 打开 **激活合作伙伴** 切换。  
       
     <Image alt="激活合作伙伴模糊.png" src="https://files.readme.io/5e0e7ae537cd89b2c561c8561de9ebc160f6d6eb0fedc5c7ba0c761ddb73632a-36713631194641.png" width="521px" />
5. 在其余选项卡中完成配置:

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

下文说明了对接选项卡中所包含各部分内容。

### 启用渠道

请在首次访问该页面时打开**启用该渠道**开关，然后就可以设置对接了。在您与该渠道合作期间，请确保该开关总是处于打开状态。  
详情请见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">渠道启用说明</Anchor>。

### 通用设置

#### 高级数据共享（Advanced data sharing）

要与 Amplitude 分享额外的安装信息，请开启 **高级数据共享**。开启后，Amplitude 将接收以下与安装相关的数据（不包括应用内事件），并映射到列出的 Amplitude 属性：

| Amplitude 属性 | AppsFlyer Data Point |
| --- | --- |
| sub\_publisher | af\_siteid |
| network\_name | pid |
| adgroup\_name | af\_adset |
| creative\_name | af\_ad\_id |
| installed\_at | install\_timestamp |
| search\_term | af\_keywords |
| channel | af\_channel |
| user\_id | af\_customer\_user\_id |
| af\_sub1 | af\_sub1 |
| af\_sub2 | af\_sub2 |
| af\_sub3 | af\_sub3 |
| af\_sub4 | af\_sub4 |
| af\_sub5 | af\_sub5 |
| app\_version | app\_version |

#### Amplitude EU Data Center

当 **Amplitude 欧盟数据中心** 关闭时，安装回调将发送到美国数据中心。  
要将安装回调发送到 Amplitude 的欧盟数据中心，请开启 Amplitude 欧盟数据中心。

#### API Key

Amplitude 通过唯一的 API 密钥与 AppsFlyer 连接。如果您还没有，必须从 Amplitude 获取它以继续集成，或按照以下步骤操作。

<span id="obtaining-the-api-key-from-amplitude"></span>**从 Amplitude 获取 API 密钥**

**注意**：只有在 Amplitude 上拥有管理员或经理角色的用户才能访问 API 密钥。

1. 登录到您的 Amplitude 账户。
2. 在页面右上角，点击设置图标 > **组织设置**。  
   <Image alt="" src="https://files.readme.io/214df773c045239924b65a4a1e6b0a1957f6b7ea09e225af80d83ffa0a469c26-16258070772625.png" width="240px" />Amplitude
3. 点击 **项目** 并选择要将数据发送到 AppsFlyer 的项目。   
   ![](https://files.readme.io/eaf158e4505f47f8da0fdae4f97be773ab32910352b50cab5ca5d4de3e8782ac-16335170399505.png) Amplitude
4. 在 **项目** 标签中，复制您的 API 密钥。  
   <Image alt="" src="https://files.readme.io/cf65648a9a8c122febe2b36fd4bd0b9f7f436cac49cfeec7f41870f614a16c6c-16258070773649.png" width="648px" />Amplitude
5. 继续在 AppsFlyer 仪表板中配置 Amplitude。

### 默认回传

AppsFlyer 可以在用户安装后自动向 Amplitude 发送回调。使用此部分定义每个事件的回调发送用户的来源。了解更多关于 <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#default-postbacks">默认回调</Anchor> 的信息。

### 应用内事件设置

* 输入 API 密钥。
* 当 **Amplitude 数据中心** 关闭时，应用内事件回调将发送到美国数据中心。  
  **要将应用内事件回调发送到 Amplitude 的欧盟数据中心，请开启 Amplitude 数据中心。**

一旦您保存了配置，AppsFlyer 将以下数据发送到 Amplitude：

* 设备 ID (IDFV/Google 广告 ID)
* Media Source（媒体渠道）
* Campaign name

向 iOS 设备发送 IDFA 需遵循 <Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">用户的 ATT 同意和高级隐私设置</Anchor>。

### 应用内事件回传

<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">配置发送应用内事件回调</Anchor> 到 Amplitude。

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

Amplitude 不提供权限。

</Accordion>

## 在 Amplitude 控制台查看归因数据

从 AppsFlyer 发送到 Amplitude 的归因数据在您的仪表板中显示为以 **[AppsFlyer]** 为前缀的事件和属性：

![amplitude-properties.png](https://files.readme.io/bf52831ea6060172ce251136f47962ffb7f1ec9ffce13b9e35c614c4178e77f1-360009623597.png)

> 🚧 **重要提示！**
>
> 在某些情况下，Amplitude 将来自 AppsFlyer 的数据显示为 "已阻止"。如果您在 Amplitude 中看不到 AppsFlyer 数据，请检查它是否被定义为阻止事件。![amplitude-blocked-data.png](https://support.appsflyer.com/hc/article_attachments/51911907937553)

## 将 Amplitude 事件发送到 AppsFlyer

该集成还允许通过服务器到服务器 API 将您的 Amplitude 事件发送到 AppsFlyer。请参阅 <Anchor target="_blank" href="https://www.docs.developers.amplitude.com/data/destinations/appsflyer/">Amplitude 文档</Anchor> 了解如何操作。

<div data-zendesk-anchors="about-the-integration=%E5%85%B3%E4%BA%8E%E9%9B%86%E6%88%90 h_01JSE81SX1B1RH978Y08W1XXX8=%E5%85%B3%E4%BA%8E%E9%9B%86%E6%88%90 h_01JSEAMM69J9CD7E32M4NKXRR6=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA set-up-the-integration=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01JSE958V510B9P6VEQTXC55S7=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 additional-prerequisites-for-the-v2-integration=amplitude-v2-%E9%9B%86%E6%88%90%E7%9A%84%E9%A2%9D%E5%A4%96%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01JSKEMMEB00PERVQWPYNF5V2E=amplitude-v2-%E9%9B%86%E6%88%90%E7%9A%84%E9%A2%9D%E5%A4%96%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 amplitude-device-id=amplitude-%E8%AE%BE%E5%A4%87-id h_01JSKFH7KPSE5P0CRPVJ3FJ2WN=amplitude-%E8%AE%BE%E5%A4%87-id h_01JSKFK4BFH3PP98XAZ0W8GG11=customer-user-id amplitude-session-id=amplitude-%E4%BC%9A%E8%AF%9D-id h_01JSKFQXPPJVCW68C4H9B4EJ76=amplitude-%E4%BC%9A%E8%AF%9D-id set-up-the-integration::45aa5acf=%E5%A6%82%E9%9C%80%E8%AE%BE%E7%BD%AE%E5%AF%B9%E6%8E%A5 h_01JSKFQAZ8Q76KF1JJKZTAPVBQ=%E5%A6%82%E9%9C%80%E8%AE%BE%E7%BD%AE%E5%AF%B9%E6%8E%A5 h_01HNSS4TXFFTZGZRZ6ZTAWNN6N=integration-tab activate-partner=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 01H8KPA9JKDRA680Y0WPZ172EM=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE 01H8KPA9JKF4VCA4S22SYT40WT=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE advanced-data-sharing=%E9%AB%98%E7%BA%A7%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%ABadvanced-data-sharing 01H8KPA9JKJ2XN1AEPV74QVJYZ=%E9%AB%98%E7%BA%A7%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%ABadvanced-data-sharing amplitude-data-center=amplitude-eu-data-center 01H8KPA9JKP0T0FDND97VA23EY=amplitude-eu-data-center 01H8KPA9JKDYDPDGRXZSH2BAV8=api-key 01H8KPA9JK510YKV47816DT7E7=obtaining-the-api-key-from-amplitude default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 01H8KRBGYQ973CT3H8GHZ8R0BH=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-event-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE 01H8KPA9JKM4S79160BEYN3B6V=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE inapp-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H8KSQ76XE9Z191P1RMANF6EQ=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H8KPA9JK4D6XX55Q55TBF4QN=attribution-link-tab 01H8KPA9JKK04NNDZA0XTSSWM5=cost-tab 01H8KPA9JK6X04T661D6YBHTVC=ad-revenue-tab 01H8KPA9JKG1VQJJBNFM6Q985X=permissions-tab viewing-attribution-data-in-the-amplitude-console=%E5%9C%A8-amplitude-%E6%8E%A7%E5%88%B6%E5%8F%B0%E6%9F%A5%E7%9C%8B%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE 01H8KPA9JK75TA0H8T4P65BMSE=%E5%9C%A8-amplitude-%E6%8E%A7%E5%88%B6%E5%8F%B0%E6%9F%A5%E7%9C%8B%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE 01H8KPA9JK2B4MR26GJZEZJSVT=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 sending-amplitude-events-to-appsflyer=%E5%B0%86-amplitude-%E4%BA%8B%E4%BB%B6%E5%8F%91%E9%80%81%E5%88%B0-appsflyer h_01HPYFZDX1WWDWJEBZ4DK706B4=%E5%B0%86-amplitude-%E4%BA%8B%E4%BB%B6%E5%8F%91%E9%80%81%E5%88%B0-appsflyer" />
