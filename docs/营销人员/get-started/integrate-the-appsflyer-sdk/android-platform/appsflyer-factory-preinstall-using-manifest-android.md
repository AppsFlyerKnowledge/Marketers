---
title: 基于Manifest的AppsFlyer出厂预装归因（安卓）
metadata:
  keywords:
    - Android
    - Pre-Install
    - Attribution
    - Metrics
    - Advertisers
    - Agencies
    - af_pre_install_name
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
    - Agencies
  created_at: '2014-10-13T11:14:04Z'
  edited_at: '2026-10-14T10:14:43Z'
  id: 207032166
  locale: zh-cn
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/zh-cn/articles/207032166
---
> **概要：** 概要：对于预装到设备出厂设置中的应用，AppsFlyer可以将其激活归因到相应的设备厂商。**请注意**：注意：另请参见其它预装归因原理。

<Image align="center" alt="pre-install-intro-breakdown.png" src="https://files.readme.io/bf586f87419027778cae169e8c19b7f188326173417550fe3a747db8c7dab72d-51165335908369.png" />

<div id="introduction" />

## 简介

<div id="what-is-a-pre-install-campaign" />

### 什么是预装推广？

应用所有者（广告主）可以通过预装推广在不投放线上广告的情况下触达大量潜在用户。

在预装推广场景中，广告主会让设备生产商**将相关应用作为出厂设置安装在设备中**。

预装推广也包括与第三方渠道合作，让其代表广告主通过设备生产商实现预装。

<div id="important" />

> 🚧 **重要提示！**
>
> 用户首次启动应用时，AppsFlyer会记录一次激活。因此，AppsFlyer中呈现的预装数量是指激活应用的用户数量，而不是预装了该应用的设备数量。

<div id="benefits-of-recording-installs-from-pre-install-campaigns" />

### 记录预装推广带来的激活有何意义

对预装推广进行归因后，您就可以了解：

* 打开了相关预装应用的用户数量
* 各设备生产商带来的用户数量
* 用户LTV，并以此来判断带来高价值用户的生产商

<div id="how-can-i-measure-pre-install-campaigns" />

### 如何衡量预装推广？

预装推广的衡量方式共有四种。详情请见本文的[设置](/docs/appsflyer-factory-preinstall-using-manifest-android#设置方式)部分。

<div id="viewing-pre-install-data" />

### 查看预装数据

与其他激活一样，预装激活在AppsFlyer面板中会呈现在获得归因的渠道下。但是，这些激活的广告系列名称总是显示为**Pre-install** 。

<div id="note" />

> 📘 **注意**
>
> 您可以使用[SDK API方法](/docs/appsflyer-factory-preinstall-using-manifest-android#sdk-api-method)为预装激活配置不同的广告系列名称。

<div id="note-1" />

> 📘 **注意**
>
> 从2022年5月24日：
>
> * 在原始数据报告中，预装推广的Match\_type（匹配类型）显示为`preload_conf`preload\_confpreload\_conf。
> * AppsFlyer会在面板中展示促成预装的广告平台以及促成应用首次打开的广告平台。详情请见<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#preload-campaigns">预装推广</Anchor>。

<div id="setup" />

## 设置方式

下表列出了衡量预装推广的各种方式，您可以根据实际需求选用其中任意一种。

| 方法名称 | 是否需要多个APK | 能否确保预装归因 | 是否需要渠道或厂商侧操作 |
| --- | --- | --- | --- |
| 系统属性（System Properties） | 否 | 是 | 是 |
| SDK API | 是 | 否 | 否 |
| 在Manifest文件中指名（Name in Manifest File） | 是 | 否 | 否 |
| 路径（Path Way） | 否 | 否 | 是 |

<div id="system-properties-method-recommended" />

<Accordion title="系统属性（推荐）">

适配要求：必须使用`V4.0+`V4.0+V4.0+版本的SDK。

该方法是所有方法中最稳定可靠的，但需注意：预装完成后，所有应用激活（包括新增激活和重装激活）都会被归因到预装渠道。

系统属性（System Properties）方法需要应用开发人员和设备生产商双方都完成相应的操作。

<div id="developer" />

#### 开发人员

您需要向设备生产商或媒体渠道APK。该方法只需要用到默认APK，无需提供其他单独的APK。

并在该文件添加以下键值对：

`=`

使用场景示例:

`com.appsflyer.sampleapp=huawei`

**请使用以下方式指定其他预装参数：**

在**pre\_install.appsflyer**文件中以JSON格式传递其他参数。使用场景示例:

```json
com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
```

<div id="important-1" />

> 🚧 **重要提示！**
>
> 使用此方案时，请务必注意以下事项：
>
> * 在原始数据中，Channel（流量入口）显示为“Pre-install”
> * 如果JSON配置中没有`pid`pidpid参数，则原始数据中的媒体渠道（Media Source）显示为“None”
> * 如果JSON配置中没有`c`cc参数，则广告系列名称显示为“Pre-install”
> * 如果JSON格式有误，则参数中的字符串会作为媒体渠道名称显示。

pre\_install.appsflyer配置完毕后，请将其连同APK一起发送给媒体渠道或设备生产商。

<div id="manufacturer" />

#### 设备生产商

设备生产商需要将***pre\_install.appsflyer***放置在其指定的文件路径中，并将**pre\_install.appsflyer**的文件权限设置为744。

然后，设备生产商需要在该系统属性文件中添加一个键值对，以指向***pre\_install.appsflyer***。

<div id="note-2" />

> 📘 **注意**
>
> 这一环节以及预装配置测试都需要用到Root权限。详情请见本文的[测试](/docs/appsflyer-factory-preinstall-using-manifest-android#测试预装配置)部分。

**在安卓系统属性中添加键值对**

```bash
adb shell su
setprop ro.appsflyer.preinstall.path /data/pre_install.appsflyer
```

另一种方法是从安卓文件系统中提取system-properties-file，并返回编辑完毕后的文件。

```bash
adb root
adb remount
adb pull /system/build.prop
echo ro.appsflyer.preinstall.path=/data/pre_install.appsflyer >> build.prop
adb push build.prop /system/build.prop
adb shell chmod 744 /system/build.prop
adb reboot
```

<div id="advantages" />

#### 优势

无需分媒体渠道或厂商单独维护APK。对于在Google Play上架的应用，无需在其代码中添加路径。厂商可以使用自定义路径，并能在不同设备上预装多个应用，且这些应用之间不存在依赖关系。

此方法可确保将激活归因到预装广告系列和媒体渠道。即使用户在打开应用前先进行了更新，或在点击广告后才激活应用，AppsFlyer仍会将预装激活归因到预装渠道或厂商。

<div id="disadvantages" />

#### 缺点

部分工作转移到了渠道和厂商侧，因此开发人员需要确保渠道或厂商完成必要操作。此外，该方法可能会增加开发人员的测试难度。

</Accordion>

<div id="sdk-api-method" />

<Accordion title="SDK API">

SDK API方法可以在本机层面指定预装激活的归因厂商或渠道名称。

如需使用SDK API，请在AFApplication类中添加以下方法，在SDK初始化之前调用：

`setPreinstallAttribution(String mediaSource, String campaign, String siteId)`

<div id="when-working-with-a-media-source" />

#### 与媒体渠道合作时

```java
AppsFlyerLib.getInstance().setPreinstallAttribution("MEDIA_SOURCE_NAME", "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

<div id="when-working-with-a-manufacturer" />

#### 与厂商合作时

```java
AppsFlyerLib.getInstance().setPreinstallAttribution(android.os.Build.MANUFACTURER, "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

<div id="note-3" />

> 📘 **注意**
>
> * 媒体渠道是必须配置的参数。
> * 使用此属性获取厂商名称时，同一厂商的不同设备可能会以不同的格式呈现该名称。请确保该属性中包含您预期的厂商名称。

<div id="advantages-1" />

#### 优势

您可以使用SDK API以程序化的方式拉取厂商名称信息。无论您与哪个厂商合作，SDK方法都可以直接从设备中读取该厂商的名称。也就是说，即使您与多个厂商合作，也只需要维护一个APK。

您可以将各个厂商或媒体渠道划分为不同的广告系列，而不是全都设置为“Pre-install”广告系列。

<div id="disadvantages-1" />

#### 缺点

如果您直接与厂商合作，就必须维护两个版本的APK，一个用于厂商预装，另一个用于Google Play上架。这两个场景都需要用到多个APK。

如果您通过多个渠道与厂商合作，还需要针对每个渠道维护单独的APK。

预装应用的激活在部分情况下不会被归因到预装媒体渠道：

* 用户使用新设备直接通过Google Play更新预装应用，然后才完成该应用的首次打开，这时AF会将该激活记录为自然量。
* 用户在新设备上点击广告后通过Google Play更新预装应用，这时AF会将该激活归因到展示广告的媒体渠道。

<div id="tip" />

> 👍 **提示**
>
> 您可以在应用中添加逻辑，使得预装应用的激活在上述场景中也会被记录为预装激活。您需要确保Google Play Store中的APK和厂商预装的APK中都包含该逻辑。
>
> **举例来说，**
>
> * 已知某个厂商在某个型号的设备中预装了广告主的应用，且这些设备具有相同的移动运营商。
> * 用户首次启动应用后，您可以在其激活中核对上述信息。如果该激活中的信息与此一致，就将其记录为预装激活。由于Google Play Store的APK中也存在该逻辑，因此即使用户在启动应用之前对其进行了更新，其激活也会记录为预装激活。

</Accordion>

<div id="name-in-manifest-file-method" />

<Accordion title="在Manifest文件中指名">

使用这个方法时，您需要在相关应用的Manifest文件中添加元数据标签，并针对每个合作渠道或厂商分别完成该操作。

如需使用该方法，请在关闭应用程序标签之前添加以下元数据标签：

```html Markup
...
    <meta-data android:name="AF_PRE_INSTALL_NAME" android:value="market_name"/>
  </application>
</manifest>
```

应用首次启动时，AppsFlyer SDK在manifest文件中检测到这个元数据标签，并根据该标签对激活进行归因。

<div id="advantages-2" />

#### 优势

这是一种是较为简便的预装归因方案，只需要在Manifest中添加一个标签便可完成。此外，该方法也不涉及任何渠道或厂商侧的操作。

<div id="disadvantages-2" />

#### 缺点

由于元数据标签指定了媒体渠道或厂商名称，因此您需要针对每个媒体渠道分别维护一组APK。

预装应用的激活在部分情况下不会被归因到预装媒体渠道：

* 用户使用新设备直接通过Google Play更新预装应用，然后才完成该应用的首次打开，这时AF会将该激活记录为自然量。
* 用户在新设备上点击广告后通过Google Play安装相关应用，这时AF会将该激活归因到投放广告的媒体渠道。

</Accordion>

<div id="pathway-method" />

<Accordion title="路径">

<div id="note-4" />

> 📘 **注意**
>
> 该方法适用于4.5.0及以上版本的SDK。

此方法同时涉及开发侧和厂商侧的操作。

<div id="developer-1" />

#### 开发人员

使用此方法时，您可以指定一个文件路径，该文件中含有预装渠道或厂商的名称。您需要完成三个步骤：

1. 创建一个包含键值对的文件，并将该文件命名为***pre\_install.appsflyer***。  

   <div id="passing-additional-pre-install-parameters" />

   #### 传递其他预装参数

   您可以使用JSON在文件中指定其他预安装参数。例如，您可以在**pre\_install.appsflyer**文件中添加以下键值对：

   ```json
   com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
   ```

   <div id="important-2" />

   > 🚧 **重要提示！**
   >
   > 使用此方案时，请务必注意以下事项：
   >
   > 1. af\_channel显示为"Pre-install"
   > 2. 如果JSON中没有pid，则媒体渠道显示为“无”。
   > 3. 如果JSON配置中没有c参数，则广告系列名称显示为“Pre-install”
   > 4. 如果JSON格式有误，则参数中的字符串会作为媒体渠道名称显示。


   pre\_install.appsflyer配置完毕后，请将其连同APK一起发送给媒体渠道或设备生产商。
2. 与渠道或厂商讨论该文件的存放路径并达成一致。建议将路径设置为“ /data/local/tmp/pre\_install.appsflyer”。
3. 在manifest文件中配置商定的路径。请在关闭应用程序标签之前添加以下代码段：  

   ```html Markup
   <meta-data android:name="AF_PRE_INSTALL_PATH" 
         android:value="/data/local/temp/pre_install.appsflyer" />
   ```

<div id="manufacturer-1" />

#### 设备生产商

厂商需要将文件放在约定的路径中，并将pre\_install.appsflyer的文件权限设置为744。

应用启动后，SDK会读取到manifest文件中指定的路径，并根据该路径找到相应的文件，然后根据其中指定的媒体渠道对激活进行归因。

<div id="advantages-3" />

#### 优势

AppsFlyer会按两个默认路径查找**pre\_install.appsflyer**文件：

```bash
/data/local/tmp/pre_install.appsflyer
OR 
/etc/pre_install.appsflyer
```

部分厂商会选择将文件放在非默认路径中。这时，您可以在manifest文件中指定相应的非默认路径。

<div id="important-3" />

> 🚧 **重要提示！**
>
> 如需使用非默认路径，必须接入4.8及以上版本的SDK。
>
> 虽然我们支持非默认路径，但更建议您使用[系统属性](/docs/appsflyer-factory-preinstall-using-manifest-android#system-properties-method-recommended)方法。

<div id="disadvantages-3" />

#### 缺点

您需要为不同的媒体渠道或厂商维护单独的***pre\_install.appsflyer***文件。

厂商可能希望将***pre\_install.appsflyer***文件放在非默认路径中。在这种情况下，您需要为每个非默认路径维护单独的APK。

如果使用**非默认路径**，则无法保证预装应用的激活能被归因到预装媒体渠道：

* 用户使用新设备直接通过Google Play更新预装应用，然后才完成该应用的首次打开，这时AF会将该激活记录为自然量。
* 用户在新设备上点击广告后通过Google Play安装相关应用，这时AF会将该激活归因到投放广告的媒体渠道。

</Accordion>

<div id="testing-pre-install-configuration" />

## 测试预装配置

本节说明了预装配置的测试和验证方法。

<div id="important-4" />

> 🚧 **重要提示！**
>
> 测试前请先确保您的测试<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices">设备已加白</Anchor>。
> 另外，请在AFApplication类中将调试日志（Debug Log）设置为true。
>
> ```java
> AppsFlyerLib.getInstance().setDebugLog(true);
> ```

<div id="verifying-the-configuration-in-the-app" />

<Accordion title="验证应用中的配置">

<div id="tip-1" />

> 👍 **提示**
>
> 为避免缓存问题并获得最佳结果，建议您在构建项目之前先对其进行清理。进入Android Studio，点击上下文菜单（Context Menu）中的***Build*** ，然后选择***Clean Project*** 。

在Android Studio中构建应用程序，然后将其安装到测试设备上。应用程序启动后，在Android Studio中打开Logcat，然后按“AppsFlyer”筛选，您会看到被归因的激活及其详细信息。如下图所示：

<Image align="center" alt="pre_install_logcat.png" src="https://files.readme.io/cecab55ddad6e2a1fe3bdba1257670312a8cd230434ab6a899661a5cd8879b33-51165335909265.png" />

<Image align="center" alt="pre_install_logcat_2.png" src="https://files.readme.io/716eda668aec4d74e82ac774a42f8be329bb6bca9d7ad83ecb13e8f04b330ec7-51165335912337.png" />

</Accordion>

<div id="verifying-the-configuration-in-the-appsflyer-dashboard" />

<Accordion title="在AppsFlyer面板中验证配置">

如果配置成功，则面板中会出现归因到相关厂商或渠道的非自然激活，且该激活会列在“Pre-install”（预装）广告系列下。

进入您的AppsFlyer帐户，打开要测试应用的面板，然后按照以下步骤操作：

1. 在数据总览面板中按媒体渠道筛选数据，并选择相应的渠道：  

   <Image align="center" alt="choose_media_source.png" src="https://files.readme.io/2343bbe2faea37d804232ef711062dbd933c981d928addfc2759e5f85bcc92f6-51165335913361.png" />
2. <Image align="center" alt="" src="https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png" />
   在该报告中，您可以看到媒体渠道和广告系列信息。如下图截屏所示，媒体渠道为“My Media Source”，广告系列为Pre-install：  

    <Image align="center" alt="" src="https://files.readme.io/0634afa35fbc6bb24f310f9efd6d1af7b9d376b711ffe87a72eccf157cf92d5a-51165335913489.png" />
3. 针对各个预装推广合作厂商和渠道分别完成上述流程。

</Accordion>

<div id="special-cases" />

## 特殊场景

<div id="multiple-preinstall-apps-on-the-same-device" />

<Accordion title="同一台设备上的多个预装应用">

如果您在同一设备上预装了多个应用，则可以使用以下任一方法来和衡量归因：

* 在Manifest文件中指名——在每个应用的Manifest.xml中都指定媒体渠道或厂商。
* SDK API——在每个应用的SDK API方法中都指定预装渠道或厂商。
* 对于system properties或path way方法-可以在***pre\_install.appsflyer***文件中指定应用程序及其对应的媒体渠道。每个应用程序信息应在文件中添加新的一行。使用场景示例:

  ```bash
  com.appsflyer.tester=market_name
  com.newapp.newapp=market_name
  com.game.king=market_name
  ```

</Accordion>

<div id="sending-install-postbacks" />

<Accordion title="发送激活回传">

如果您的合作渠道或厂商是<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#your-integrated-partners">AppsFlyer的对接渠道</Anchor>，就可以向其发送激活回传。

如需发送激活回传，请确保其媒体渠道名称与AppsFlyer配置的媒体渠道pid一致。

比如您与market\_name合作，其pid为market\_name\_int。您可以在<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#点击型归因">对接渠道的归因链接</Anchor>中查看该pid。

</Accordion>

<div id="agencies" />

<Accordion title="代理">

当前，代理商无法获得预安装归因。

如果预装数据中包含af\_prt（用于表达代理名称的参数），则用户激活预装应用后：

* 该用户会被归因到代理所使用的媒体渠道（pid=）。
* 广告主可以访问完整的用户级别数据。
* 用户不会归因给代理商。
* 代理商无法访问用户级别数据。

</Accordion>

<div data-zendesk-anchors="introduction=%E7%AE%80%E4%BB%8B h_01J421581P06FTM7B3XG2GYB2P=%E7%AE%80%E4%BB%8B what-is-a-preinstall-campaign=%E4%BB%80%E4%B9%88%E6%98%AF%E9%A2%84%E8%A3%85%E6%8E%A8%E5%B9%BF h_01J421581P6GYK60D5JQ9PK93N=%E4%BB%80%E4%B9%88%E6%98%AF%E9%A2%84%E8%A3%85%E6%8E%A8%E5%B9%BF h_01J421581PBQQ5AS3S4JPX52CF=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA benefits-of-recording-installs-from-preinstall-campaigns=%E8%AE%B0%E5%BD%95%E9%A2%84%E8%A3%85%E6%8E%A8%E5%B9%BF%E5%B8%A6%E6%9D%A5%E7%9A%84%E6%BF%80%E6%B4%BB%E6%9C%89%E4%BD%95%E6%84%8F%E4%B9%89 h_01J421581P5MS4X9BHSJ3TTWBF=%E8%AE%B0%E5%BD%95%E9%A2%84%E8%A3%85%E6%8E%A8%E5%B9%BF%E5%B8%A6%E6%9D%A5%E7%9A%84%E6%BF%80%E6%B4%BB%E6%9C%89%E4%BD%95%E6%84%8F%E4%B9%89 how-can-i-measure-preinstall-campaigns=%E5%A6%82%E4%BD%95%E8%A1%A1%E9%87%8F%E9%A2%84%E8%A3%85%E6%8E%A8%E5%B9%BF h_01J421581PEZZW2R244ZX9HX0R=%E5%A6%82%E4%BD%95%E8%A1%A1%E9%87%8F%E9%A2%84%E8%A3%85%E6%8E%A8%E5%B9%BF viewing-preinstall-data=%E6%9F%A5%E7%9C%8B%E9%A2%84%E8%A3%85%E6%95%B0%E6%8D%AE h_01J421581PS1CEPK3NN7AZ0ZDE=%E6%9F%A5%E7%9C%8B%E9%A2%84%E8%A3%85%E6%95%B0%E6%8D%AE h_01J421581PDE1CEXRS6BYTDV35=%E6%B3%A8%E6%84%8F h_01J421581PKQTX47GC62K4AB9A=%E6%B3%A8%E6%84%8F-1 setup=%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01J421581P28NEVB44R3XTPY75=%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01J421581QNSQ7W3VYFDVZ1423=system-properties-method-recommended developer=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98 h_01J421581Q8ZAPZS12PEG4VW3N=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98 h_01J421581QYRNXCP16GY8CJTKT=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 manufacturer=%E8%AE%BE%E5%A4%87%E7%94%9F%E4%BA%A7%E5%95%86 h_01J421581QF6Y6MY28N5MR5BTM=%E8%AE%BE%E5%A4%87%E7%94%9F%E4%BA%A7%E5%95%86 h_01J421581QBFMVT3KPCPPFRX42=%E6%B3%A8%E6%84%8F-2 advantages=%E4%BC%98%E5%8A%BF h_01J421581QEPAC0WZK93HH3QYP=%E4%BC%98%E5%8A%BF disadvantages=%E7%BC%BA%E7%82%B9 h_01J421581QCG3HARVZVECMHQ1K=%E7%BC%BA%E7%82%B9 h_01J421581QQ3VJSSQ06DKZQ0BQ=sdk-api-method when-working-with-a-media-source=%E4%B8%8E%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E5%90%88%E4%BD%9C%E6%97%B6 h_01J421581Q6F1AD0SYXEEJB8FB=%E4%B8%8E%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E5%90%88%E4%BD%9C%E6%97%B6 when-working-with-a-manufacturer=%E4%B8%8E%E5%8E%82%E5%95%86%E5%90%88%E4%BD%9C%E6%97%B6 h_01J421581Q3YSNH7KXQXET7FD4=%E4%B8%8E%E5%8E%82%E5%95%86%E5%90%88%E4%BD%9C%E6%97%B6 h_01J421581QRYRWY2WJKCBHQBFG=%E6%B3%A8%E6%84%8F-3 advantages::d999b734=%E4%BC%98%E5%8A%BF-1 h_01J421581QWHP73CA7P13WAQ7Q=%E4%BC%98%E5%8A%BF-1 disadvantages::92772f7d=%E7%BC%BA%E7%82%B9-1 h_01J421581QRRFBJWZB5Z6M08BE=%E7%BC%BA%E7%82%B9-1 h_01J421581QF11R7ZXAXRP2YQYR=%E6%8F%90%E7%A4%BA h_01J421581QJ2J54HJFTXF3G5S0=name-in-manifest-file-method advantages::3f0b06fb=%E4%BC%98%E5%8A%BF-2 h_01J421581Q8WFYYFQJ45KPWZWP=%E4%BC%98%E5%8A%BF-2 disadvantages::919cb3e3=%E7%BC%BA%E7%82%B9-2 h_01J421581QYC02EKB5P0FN5G3F=%E7%BC%BA%E7%82%B9-2 h_01J421581QNFT2E2P3A6MR3BB5=pathway-method h_01J421581QF43JW6A0B48SK9AE=%E6%B3%A8%E6%84%8F-4 developer::7c51f631=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98-1 h_01J421581QB4TH9DMA2ANHG7RD=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98-1 passing-additional-preinstall-parameters=%E4%BC%A0%E9%80%92%E5%85%B6%E4%BB%96%E9%A2%84%E8%A3%85%E5%8F%82%E6%95%B0 h_01J421581Q45AEN4GEM5ZKPYRN=%E4%BC%A0%E9%80%92%E5%85%B6%E4%BB%96%E9%A2%84%E8%A3%85%E5%8F%82%E6%95%B0 h_01J421581Q3MMTKPP3E8SZD13F=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2 manufacturer::56d9649d=%E8%AE%BE%E5%A4%87%E7%94%9F%E4%BA%A7%E5%95%86-1 h_01J421581Q16AVHRCTHME67VHQ=%E8%AE%BE%E5%A4%87%E7%94%9F%E4%BA%A7%E5%95%86-1 advantages::1fb76031=%E4%BC%98%E5%8A%BF-3 h_01J421581QTRY13FVNQRMG0H2B=%E4%BC%98%E5%8A%BF-3 h_01J421581Q0P5VQJHQ9X3VRW8N=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-3 disadvantages::c9cae863=%E7%BC%BA%E7%82%B9-3 h_01J421581QSNNCHPC2VSF48FT3=%E7%BC%BA%E7%82%B9-3 testing-preinstall-configuration=%E6%B5%8B%E8%AF%95%E9%A2%84%E8%A3%85%E9%85%8D%E7%BD%AE h_01J421581QYHRHF119J4YBZD23=%E6%B5%8B%E8%AF%95%E9%A2%84%E8%A3%85%E9%85%8D%E7%BD%AE h_01J421581QW0XKZ635A194W80J=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-4 h_01J421581QPXQDFX5G11B7GSNA=verifying-the-configuration-in-the-app h_01J421581QSZPZVZ6GGQST5FWS=%E6%8F%90%E7%A4%BA-1 h_01J421581Q7PGHJ2HBX1ZDNJS6=verifying-the-configuration-in-the-appsflyer-dashboard special-cases=%E7%89%B9%E6%AE%8A%E5%9C%BA%E6%99%AF h_01J421581Q624TH08PX24B1P3X=%E7%89%B9%E6%AE%8A%E5%9C%BA%E6%99%AF h_01J421581QQHB8624SS6FSSA6D=multiple-preinstall-apps-on-the-same-device h_01J421581Q86AB5GTM91ARYJ23=sending-install-postbacks h_01J421581RD2WQ6SPES729GJEP=agencies" />
