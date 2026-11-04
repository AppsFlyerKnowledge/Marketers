---
title: 测试设备加白
metadata:
  keywords:
    - whitelisting
    - Testing
    - device
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-03-10T08:19:35Z'
  edited_at: '2026-10-14T10:13:16Z'
  id: 207031996
  locale: zh-cn
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/zh-cn/articles/207031996
---
> **概要：** 进行归因测试时，您需要先为您的测试设备加白，才能让AF后台将每次激活都记录为新增激活。测试设备加白后，重复激活应用不会被AF判定为重装激活。

<div id="why-register-a-test-device" />

## 测试设备加白的目的

开展归因测试时，再归因窗口期会限制激活归因的次数，每90天内仅记录一次激活。因此，如果您使用同一设备反复测试激活归因，就记录不到任何内容。这种情况下，您就需要将您的测试设备加白。加白后的测试设备反复完成激活时，这些激活不会被判定为重装激活。

<div id="methods-for-registering-a-test-device" />

## 测试设备加白方式

为测试设备加白时，您需要选择设备操作系统（安卓、iOS或Windows）并添加设备标识符。

您可以使用以下任一方式对设备加白：

* [下载并安装名为“My Device ID by AppsFlyer”的应用:](#register-a-device-using-the-appsflyer-device-id-app-admin-only)您在测试设备上安装该应用后，设备就会自动加白，并向您的AppsFlyer账户发送设备ID信息。该设备会被自动列入**测试设备**页面。

  <div id="note" />

  > 📘 **注意**
  >
  > 在iOS 14及以上版本的测试设备中，只有您的应用中使用了 AppTrackingTransparency（ATT）功能，并且您想要测试授权用户的归因，才能使用此加白方法。如果您的测试场景不符合这些条件，请使用手动方式完成设备加白。

* [手动添加测试设备：](#register-a-device-manually) 您账户下的任何用户都可以直接在**测试设备**页面中添加相关设备的标识符，从而完成设备加白。

注意事项：

* 已加白的测试设备可用于相关账户下的所有应用。
* 广告平台如需添加设备需要让广告主完成相关操作；代理则可以自行添加测试设备。

<div id="supported-device-identifiers" />

<Accordion title="适用的设备标识符">

适用的设备标识符包括以下几种：

* **安卓：** AID（GAID或OAID）、IMEI、Android ID

  <div id="note-1" />

  > 📘 **注意**
  >
  > 为测试设备加白时，建议仅在相关应用收集并使用IMEI或Android ID的情况下添加这些设备标识符。

* **iOS：** IDFA、IDFV
* **Windows Phone：** Windows advertising ID

</Accordion>

<div id="managing-test-device-registration" />

## 管理测试设备加白

<div id="register-a-device-using-the-appsflyer-device-id-app-admin-only" />

<Accordion title="通过AppsFlyer的设备ID应用为测试设备加白">

**请通过以下方式下载AppsFlyer的设备ID应用：**

1. 扫描以下二维码（Google Play Store）或点击二维码下方的链接，下载并安装该应用：

   <div id="android" />

   <Accordion title="安卓">

   [<Image alt="" src="https://files.readme.io/a3fd43836c7f489ab37a2d03263e9e873f1ec700c4f6a9c10771775b38295333-51911871701649.png" width="233px" />](https://files.readme.io/a3fd43836c7f489ab37a2d03263e9e873f1ec700c4f6a9c10771775b38295333-51911871701649.png)

   **链接：** [Google Play](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid&hl=en)和[第三方商店](https://apkpure.com/my-device-id-by-appsflyer/com.appsflyer.android.deviceid)

   </Accordion>

   <div id="ios" />

   <Accordion title="iOS">

   [<Image alt="" src="https://files.readme.io/bdd0aaaf73063815527e0b44784db783e88a99dd7430ec48dad90bb67cebc696-51911871705489.png" width="233px" />](https://files.readme.io/bdd0aaaf73063815527e0b44784db783e88a99dd7430ec48dad90bb67cebc696-51911871705489.png)

   </Accordion>

   <div id="windows" />

   <Accordion title="Windows">

   p [<Image alt="" src="https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png" width="233px" />](https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png)

   </Accordion>

2. 如果您想要收集iOS 14.5+设备的IDFA，请在界面弹出ATT授权弹窗时点击**允许**。[![](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)
3. 在安卓/iOS/Windows界面中点击**Register**，为测试设备加白：

   <div id="android::db8cc168" />

   <Accordion title="安卓">

   [![](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)

   </Accordion>

   <div id="ios::80f176b3" />

   <Accordion title="iOS">

   [![](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)

   </Accordion>

   <div id="windows::6c6af14b" />

   <Accordion title="Windows">

   [![](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)

   </Accordion>

4. 输入您的AppsFlyer登录凭证。设备加白完毕。
5. 点击**Share details**，与AF账户共享设备ID信息。

</Accordion>

<div id="register-a-device-manually" />

<Accordion title="测试设备手动加白">

相关账户下的用户可以手动为测试设备加白：

1. 从AppsFlyer后台的侧边栏中选择**配置** > **测试设备**。
2. 选择**测试设备**。
3. 点击 **+添加设备**。

   [![](https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png)](https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png)
4. 请填写以下字段：
   * **名称（仅限英文字母）：** 输入一个具有唯一性的设备名称，用于识别该设备。
   * **操作系统：** 选择设备的操作系统。
   * **设备ID类型：** 选择一种设备标识符。
   * **设备ID：** 根据设备的操作系统输入相对应的设备ID：

     <div id="ios::41efa11e" />

     <Accordion title="iOS">

     IDFA或IDFV的获取方式如下：

     * **IDFA：** 如需获取IDFA，请在您的测试设备上安装AppsFlyer的设备ID应用。具体操作：见上文“通过AppsFlyer设备ID应用[添加设备](#register-a-device-manually)（仅限账户管理员）”部分。
     * **IDFV：** 如需获取IDFV，请让您的开发人员在您的测试设备上安装IDFV测试工具应用。安装并激活该工具应用后，界面会显示该设备的IDFV。**请注意：** 开发人员必须先在X-Code中完成前期准备后方可安装该测试工具。

     如需了解IDFA或IDFV的使用场景，请参见[为iOS测试设备加白](#为ios测试设备加白)部分。

     </Accordion>

     <div id="android::7db075c7" />

     <Accordion title="安卓">

     您可以使用AppsFlyer的设备ID应用，或在设备中键入以下代码，以获取设备标识符：

     | 标识符 | 拉取方式 | Google Play | Other（其他） |
     | --- | --- | --- | --- |
     | AID（GAID或OAID） | 使用[AppsFlyer的设备ID应用](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid) | 是否必须配置 |  |
     | IMEI | *#06#* | 不适用 | 请确保开发人员使用了<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">setCollectImei</Anchor>来收集该ID。 |
     | Android ID | *#*#8255#*#*  (可能不适用于较新的设备) | 不适用 | 请确保开发人员使用了<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">setCollectAndroidID</Anchor>来收集该ID。 |

     </Accordion>

5. 点击**Save**保存。 该设备会出现在已加白设备的列表中。 **请注意**：虽然该设备会立即出现在已加白设备的列表中，但可能需要等待几分钟才能正式录入系统并正常使用。

<div id="note-2" />

> 📘 **注意**
>
> 在某些情况下（比如要在同一个设备上同时收集IDFA和IDFV），您可能需要为一个测试设备添加多个标识符。
>
> **请按以下步骤添加其他标识符：**
>
> 1. 点击 **添加设备**。
> 2. 使用同一个测试设备名称，添加第2个标识符。
> 3. 点击**Save**保存。

</Accordion>

<div id="unregister-a-device" />

<Accordion title="注销测试设备">

每个账户下最多可加白200个设备。

**请按以下步骤从列表中删除设备：**

1. 进入AF后台，点击右上角的邮箱地址。
2. 选择**测试设备**。
3. 点击删除图标，即可注销设备。

</Accordion>

<div id="registering-an-ios-test-device" />

## 为iOS测试设备加白

以下流程图展示了iOS测试设备加白时会出现的几种路径。

[![](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)

为iOS测试设备加白时，请从以下几种方式中选择一种：

<div id="register-your-testing-device-with-idfa" />

<Accordion title="使用IDFA为测试设备加白">

<div id="when-to-use-idfa-for-test-device-registration" />

#### **何种情况下需要使用IDFA为测试设备加白？**

如果您的应用中使用了AppTransparency Tracking（即ATT弹窗），而且您想要测试授权用户的归因，可以使用IDFA为测试设备加白。在测试过程中首次打开相关应用时，请确保在ATT弹窗中点击**允许**。

<div id="how-to-register-your-test-device-with-an-idfa" />

#### **如何使用IDFA为测试设备加白？**

如需使用IDFA，请通过AppsFlyer的设备ID应用为测试设备加白。

</Accordion>

<div id="register-your-testing-device-with-idfv" />

<Accordion title="使用IDFV为测试设备加白">

<div id="when-to-use-idfv-for-test-device-registration" />

#### **何种情况下需要使用IDFV为测试设备加白？**

当IDFA无法访问时，IDFV是唯一的可选方案。在以下场景中，您**必须使用IDFV**：

* 相关应用中**使用了ATT弹窗**，但您想要测试不授权用户的归因。在测试过程中首次打开相关应用时，请确保在ATT弹窗中点击**要求App不跟踪**。
* 相关应用中**没有添加ATT弹窗**。

<div id="how-to-register-your-device-with-idfv" />

#### **使用IDFV为测试设备加白的方法**

1. 使用IDFV为测试设备加白之前，必须先让您的开发人员在测试设备上安装IDFV测试工具应用。您可以让开发人员参考<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-the-idfv-test-tool-app">此文档</Anchor>，查看相关说明。
2. IDFV测试工具应用安装完毕后，请将其打开，并复制界面中显示的IDFV。
3. 使用该IDFV[手动为测试设备加白](#register-a-device-manually)。

<div id="note-3" />

> 📘 **注意**
>
> **为何要安装IDFV测试工具应用？**
>
> * IDFV测试工具的用途是提取测试设备的IDFV，帮助您完成加白流程。
> * 如果测试设备中没有安装您开发者账户下的其他应用，则您每次重装并激活相关应用时，iOS系统都会为该设备生成一个新的IDFV。一般情况下，测试过程中需要完成多次重装激活，而每次重装激活都会触发iOS重置测试设备的IDFV。**这时，该测试工具可以假装成同厂商的应用，防止iOS在每次发生重装激活时重新生成IDFV。**

</Accordion>

<div id="dont-register-a-testing-device" />

<Accordion title="使用未加白的设备进行测试">

建议您仅在无法通过IDFA或IDFV为测试设备加白时，才使用这一方法。在这种情况下，AF会使用概率模型进行归因。测试设备上的每一次激活都会被记录为新增激活。如果出现以下任一情况，该方法可以帮助您记录测试过程中在同一个设备上完成的重复激活：

* AppsFlyer iOS SDK版本为v6.8.0或更低。
* 相关应用禁用了重装激活识别（不建议已上架的应用使用该设置）。
* 如果测试归因链接中包含`is_retargeting="true"`，则相关激活会被记录为再归因，且会呈现在再营销面板和再营销原始数据报告中。
* 仅适用于iOS：测试时为了避免Protect360将点击标记为假量，请在您的测试归因链接中添加查询参数`pid="ios_testing"`。

</Accordion>

<div data-zendesk-anchors="why-register-a-testing-device=%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD%E7%9A%84%E7%9B%AE%E7%9A%84 01H7W9EA7RQDB69QS339XFHAFZ=%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD%E7%9A%84%E7%9B%AE%E7%9A%84 methods-for-registering-a-testing-device=%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD%E6%96%B9%E5%BC%8F 01H7W9EA7RRRJBFSXW3KY53R9K=%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD%E6%96%B9%E5%BC%8F 01H7W9EA7RTTQ1FHZZ6GBGV0WP=%E6%B3%A8%E6%84%8F 01H7W9EA7RWWNACKSEETMCP90W=supported-device-identifiers 01H7W9EA7R9A8KCNRD0BTPPQTH=%E6%B3%A8%E6%84%8F-1 managing-testingdevice-registration=%E7%AE%A1%E7%90%86%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD 01H7W9EA7R7SJVVQCST3WA6YBM=%E7%AE%A1%E7%90%86%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD h_01H6V7FQFF10E4C82ZQ97PEEZA=register-a-device-using-the-appsflyer-device-id-app-admin-only 01JHJKN5Z3562N4W2H543XPC7E=android 01JHJKN5Z54T180C7G462C26Z4=ios 01JHJKN5Z51FABEGCFVTK0MPYR=windows 01JHJKTNRHHSZSC44WDWA9J2PD=android::db8cc168 01JHJKTNRJJBBA6WAC44PD33V7=ios::80f176b3 01JHJKTNRK9DY99SZ759ZGRP23=windows::6c6af14b h_01H6V7GM8KKXF8VS5ZRA4NV592=register-a-device-manually 01JHJKDZK8084GMZ9QAZPHVBHQ=ios::41efa11e 01JHJKDZK9MTNXANVEHCM18EBM=android::7db075c7 01H7W9EA7R190M9DH7GPY1VJ77=%E6%B3%A8%E6%84%8F-2 01H7W9EA7R0KGH3YXZ9SMAFESZ=unregister-a-device registering-an-ios-testing-device=%E4%B8%BAios%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD h_01H6S2AKDH181MBDFGPBP1BQPV=%E4%B8%BAios%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD 01H7W9EA7SPA47GR1X0S9WZKDH=register-your-testing-device-with-idfa when-to-use-idfa-for-testing-device-registration=%E4%BD%95%E7%A7%8D%E6%83%85%E5%86%B5%E4%B8%8B%E9%9C%80%E8%A6%81%E4%BD%BF%E7%94%A8idfa%E4%B8%BA%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD 01H7W9EA7SRD5V5134H2BRZ2AF=%E4%BD%95%E7%A7%8D%E6%83%85%E5%86%B5%E4%B8%8B%E9%9C%80%E8%A6%81%E4%BD%BF%E7%94%A8idfa%E4%B8%BA%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD how-to-register-your-testing-device-with-an-idfa=%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8idfa%E4%B8%BA%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD 01H7W9EA7SBBCAP3Y24FFCCGJW=%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8idfa%E4%B8%BA%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD 01H7W9EA7SNZ3ER02MBV8VJGH3=register-your-testing-device-with-idfv when-to-use-idfv-for-testing-device-registration=%E4%BD%95%E7%A7%8D%E6%83%85%E5%86%B5%E4%B8%8B%E9%9C%80%E8%A6%81%E4%BD%BF%E7%94%A8idfv%E4%B8%BA%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD 01H7W9EA7S3103TSHSH4XHTP1R=%E4%BD%95%E7%A7%8D%E6%83%85%E5%86%B5%E4%B8%8B%E9%9C%80%E8%A6%81%E4%BD%BF%E7%94%A8idfv%E4%B8%BA%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD how-to-register-your-device-with-idfv=%E4%BD%BF%E7%94%A8idfv%E4%B8%BA%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD%E7%9A%84%E6%96%B9%E6%B3%95 01H7W9EA7SGTDQCRVJKKRH0EVT=%E4%BD%BF%E7%94%A8idfv%E4%B8%BA%E6%B5%8B%E8%AF%95%E8%AE%BE%E5%A4%87%E5%8A%A0%E7%99%BD%E7%9A%84%E6%96%B9%E6%B3%95 01H7W9EA7SHVSDPJN8P2WBSFN1=%E6%B3%A8%E6%84%8F-3 01H7W9EA7S3KJ89AN9ZBMHFGRR=dont-register-a-testing-device" />
