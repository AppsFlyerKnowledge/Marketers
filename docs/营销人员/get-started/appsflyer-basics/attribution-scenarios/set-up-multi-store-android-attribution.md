---
title: 安卓第三方应用商店（multi-store）配置指南
metadata:
  keywords:
    - Android
    - Google
    - Google Play
    - Add App
    - amazon
    - Advertisers
    - Agencies
    - baidu
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-12-24T10:48:17Z'
  edited_at: '2026-10-14T10:14:33Z'
  id: 207447023
  locale: zh-cn
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/zh-cn/articles/207447023
---
> **概要：**

## 多个安卓第三方商店归因

AppsFlyer的归因支持多家应用商店的场景。（英文表述中，我们会将第三方安卓应用商店称为out-of-market stores或alternate Android stores）广告主在AppsFlyer后台，可以选择（1）在单一应用面板下查看所有商店的数据，也可以选择（2）一个应用对应一个三方商店，多个应用下分别查看对应商店的数据。

> 📘 **注意**
>
> * AppsFlyer的安卓归因解决方案全面支持各设备ID，包括GAID和<Anchor target="_blank" href="/marketers/zh/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor> 等。

![DashboardType_us-en-new.jpg](https://files.readme.io/10fdd08c4e57f799756f46922b5f8dc45c67f7550f9105e65076652f459c98f7-9545756936593.jpg)

### 查看多个商店数据：单一应用面板 vs. 多个应用面板

* 单一面板
* 多个应用面板也就是说，App上架多少个商店，就可以在AppsFlyer后台添加多少个App。

<table><thead><tr><th> </th><th>单一面板<br/>【推荐】</th><th> 多个应用面板</th></tr></thead><tbody><tr><td><span id="android-package-name"></span>安卓包名</td><td colspan="2">单一应用需要物理包名一致；多个应用面板，物理包名通常需要一致，通过后缀channel区分。 </td></tr><tr><td><span id="channel-name"></span>流量入口名称</td><td>/</td><td><ul><li>通过<span><strong>Android Out-of-Store APK</strong></span>入口添加App，并注意设置channel值。</li><li><span>channel值可用作标识商店，如channel-amazon。</span></li><li>物理包名+channel值的组合，代表您在AppsFlyer后台显示的完整App包名，并对应各自的商店。 </li><li>举例来说， </li><li>如果APK Manifest中设置了channel值，但是AppsFlyer后台并没有配置该channel值的应用，那么该APK的归因数据将上报给原本无channel值的包名。如有上架Google Play, 且包名一致，那么数据就会上报给您Google Play对应的应用面板。 </li></ul></td></tr><tr><td><span id="populating-the-install_app_store-field"></span>上报install_app_store字段</td><td><ul><li>各应用商店/下载渠道的唯一标示</li><li>如仅上架Google Play, 无需使用该字段。 </li><li>支持manifest配置和API方法上报。</li></ul></td><td>不适用</td></tr><tr><td><span id="onelink-template"></span><a href="./create-a-onelink-template#创建onelink模板" target="_blank">OneLink模板</a></td><td> </td><td>不适用 </td></tr><tr><td><span id="measurementattribution-links"></span>归因链接 </td><td><ul><li>归因链接相同。</li><li>确保用户被跳转至正确的商店，请使用<a href="./set-up-multi-store-android-attribution#single-dashboard-attribution-links">＆af_r</a>参数设置重定向URL。(国内媒体如涉及异步监测，即跳转链接带有is_redirect=false参数的，可忽略af_r参数)</li></ul></td><td><ul><li>每个应用/商店对应各自的归因链接。</li><li> </li><li>App ID是物理包名_channel的组合。示例：com.abc.def-def_store <br/>所以，各个App对应的归因链接也是不同的。 </li></ul></td></tr><tr><td><span id="reporting-options-available-having-install_app_store-field"></span>可查看install_app_store的面板和报告</td><td> </td><td>不适用 </td></tr><tr><td><span id="considerations"></span>注意事项</td><td><ul><li>归因准确性 </li><li><span>自然激活：一个面板下显示所有商店/渠道APK包的自然激活</span></li><li> </li></ul></td><td><ul><li>归因准确性</li><li> <span>在AppsFlyer的各个应用面板上分别查看</span>各渠道/商店包的  自然  和非自然  激活和应用内事件。 </li><li><span>如需在一个面板下汇总所有商店数据，可以借助群组报告或自定义面板等工具实现。</span></li><li> </li></ul></td></tr></tbody></table>

## 设置方法

请参考本章节进行设置。具体的操作步骤需要由市场人员和开发人员共同配合完成。

针对 多个应用面板 选项，需要针对每个应用面板/商店重复步骤。

### **开始之前**

* 确定命名规则，方便后续给channel或install\_app\_store赋值。
* 可参考以下表格准备channel和install\_app\_store的命名。
* 表格主要方便开发人员后续准备APK打包。

<table><thead><tr><th>参数</th><th>说明</th><th>单一面板<br/>【推荐】</th><th>多个应用面板</th></tr></thead><tbody><tr><td>安卓包名</td><td>各商店/渠道包包名一致</td><td colspan="2">如果APK包已经上架Google Play，可以直接选择使用该App面板查看多个商店数据。示例： comb.abc.def</td></tr><tr><td>流量入口名称</td><td>各个渠道/商店包的唯一名称 （命名由广告主自定义）</td><td>无需设置 </td><td><p>每个APK包/渠道包对应一个channel名/渠道号。需要通过打包时在manifest配置，同时在添加App时填写完全一致的channel名，此处务必注意技术与运营配合一致。 </p></td></tr><tr><td>install_app_store</td><td>各个渠道/商店包的唯一名称 （命名由广告主自定义）</td><td>每个APK包/渠道包对应一个channel名/渠道号。或者API的方式赋值（如渠道包数量较多，建议直接用API的方式）。</td><td> 无需设置</td></tr></tbody></table>

### 配置流程

| 步骤 | 负责人员 | 单一面板 | 多个应用面板 |
| --- | --- | --- | --- |
| 1 | 开发人员 | [APK打包](/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation) | [APK打包](/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation) |
| 2 | 营销人员 | 如果面板已经有包名相同的Google Play App存在，且团队愿意在一个面板下同时查看Google Play包和第三方应用商店包的数据，则无需操作此处，直接使用原有面板进行配置。如果仍需单独添加新的应用面板，作为集合各APK包数据的单一面板，请参考文档：中国国内安卓市场归因指南 | 在AppsFlyer中添加相关应用。 |
| 3 | 营销人员 | [准备归因链接。](/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links) | 分App(包名+channel名)准备归因链接。 |
| 4 | 市场人员和研发人员互相配合 | [测试](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) | [测试](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) |

## 配置流程

<div id="single-dashboard-apk-preparation" />

<Accordion title="单一应用面板-APK打包">

安卓包名决定了归因数据发往哪个应用面板。在单一应用面板的场景下，所有的商店/渠道包的包名是一致的。 此处无需再使用channel渠道号。 除去一种情况：即您在添加单一面板时，使用了out of store方式，此时仍需上报channel号确保包名一致。

SDK中的AF\_STORE参数对应原始数据和上文中的install\_app\_store，即每个APK包的下载来源。

**集成打包APK：**

1. 创建App build 副本。**请注意**： 注意 ：请勿更改安卓包名。
2. 为不同APK包/商店包/渠道包名赋值：
   * 在AndroidManfest.xml的`<application>`中添加以下代码为channel赋值。为每APK包/商店包/渠道包设置AF\_STORE值。

     ```xml
     <application>
        ...
        <meta-data android:name="AF_STORE" android:value="EnterStoreNameHere"/>
        ...
     </application>
     ```

     **--或者--**
   * API方法调用setOutOfStore API以设置AF\_STORE值。为每个商店设置唯一AF\_STORE值。(注意：如果您使用的国内第三方应用商店较多，建议使用此方法)   

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("EnterStoreNameHere")
     ```

AF\_STORE对应AppsFlyer原始数据中的install\_app\_store字段。目前包含该字段的报告和API包括：

* 数据总览面板
* 群组面板
* <Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">原始数据报告</Anchor> （原始数据报告是AppsFlyer高级功能）

</Accordion>

<div id="single-dashboard-attribution-links" />

<Accordion title="单一应用面板-归因链接">

1. 该配置对应af\_r参数，会直接填充至af\_r中，以确保用户重定向到正确的落地页。使用场景示例:   
   **请注意：** <Anchor target="_blank" href="/marketers/zh/docs/app-settings#outofstore-app-url">详情请见此处说明。</Anchor>
2. 注意配置链接中的`af_r`af\_raf\_r参数，以设定落地页地址。
3. 设置其他需要的<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#归因链接参数">归因链接参数</Anchor>。
4. 媒体渠道可使用**设备ID进行归因**，同时AppsFlyer也支持<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#probabilistic-modeling">概率模型</Anchor>作为后备方案，以应对设备ID缺失的场景。
5. 建议在归因链接中使用一个或多个设备ID参数：
   * `android_id`
   * `advertising_id`
   * `oaid`
6. 复制归因链接，填写至广告平台。

</Accordion>

<div id="dashboard-per-store-apk-preparation" />

<Accordion title="多个应用面板-APK集成打包">

此处完整包名为：物理包名，加后缀“-channel”，因此归因数据会显示在对应的完整包名下。

**为每APK包/商店包/渠道包配置manifest:**

* 在AndroidManfest.xml的`<application>`中添加以下代码为channel赋值。为每APK包/商店包/渠道包配置channel名/渠道号。

  ```xml
  <application>
       ...
       <meta-data android:name="CHANNEL" android:value="EnterStoreNameHere"/>
       ...
  </application>
  ```

  **请注意：注意： 参数区分大小写。 不能使用连字符（-）、下划线（\_）等其他字符。**

</Accordion>

<div id="dashboard-per-store-adding-the-app" />

<Accordion title="多个应用面板-添加应用">

添加应用面板，对应物理包名和后缀“-channel”。举例来说，示例：物理包名com.myapp ，channel名配置为abcstore，，那么AppsFlyer面板显示的完整包名为com.myapp-abcstore 。

**在AppsFlyer后台，为每个商店添加多个面板**：

3. 完整数据：
   * **安卓包名**
   * 流量入口名称 channel名：/strong>APK包/商店包/渠道包的唯一标识符，以区分具有相同物理包名的多个面板。请注意此处填写的channel名需要与manifest配置的channel名称完全一致，大小写敏感。  
     **请注意：** 不能使用连字符（-）、下划线（\_）等其他字符。
   * **App URL**
4. 点击**Next**。

</Accordion>

<div id="testing-both-dashboard-options" />

<Accordion title="测试方法">

#### **非自然安装**

**测试非自然激活的方式如下：**

1. 请使用未安装过测试App的设备或白名单设备<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices">建议将设备添加至白名单</Anchor>。
2. 以 "test"来命名媒体渠道 ("&pid=test").
3. 将设备ID（GAID，OAID，IMEI或Android ID）添加到点击URL。参数写法参考：AppsFlyer归因链接结构和参数

   ```http
   https://app.appsflyer.com/com.greatapp?pid=test
   &af_r=https://www.destinationurl.com&advertising_id=b5a3-78d9b5-0f12345-xxxx
   ```

   4. 通过电子邮件把该归因链接发送给自己，然后点击它。**重定向后, 不要从商店安装**。而是要安装已集成了AppsFlyer归因SDK的测试版应用并打开该应用。

| 单一面板 | 多个应用面板 |
| --- | --- |
| <ol><li>在导出数据页面的原始数据报告里查看您测试的激活数据。</li><li>测试成功后，您会看到一条媒体信息（media source）为test的激活数据。在 **Install App Store**栏，您会看到配置的AF\_STORE数据。</li></ol> | <ol><li>前往与完整包名对应的应用面板下。</li><li>在数据导出的原始数据或数据总览里查看您的激活测试数据。</li><li>您应该会看到来自“test”媒体渠道的一个安装转化。</li></ol> |

#### **Organic installs（自然激活）**

**测试自然激活：**

1. 1. 使用未安装该应用或已列入白名单的 Android 设备。
2. 2. 安装已集成了AppsFlyer归因SDK的测试版应用并打开该应用。
3. 查看数据：

#### 如测试成功，您会看到：

| 单一面板 | 多个应用面板 |
| --- | --- |
| 前往数据总览面板，查看是否有新增自然激活。目前，在使用单一应用方法时，还无法区分自然安装的来源。 | <ol><li>进入已测试商店的应用控制面板上的数据总览页面。</li><li>您应该会看到来自“organic”媒体渠道的一个安装转化。</li></ol> |

</Accordion>

## 其他功能

<div id="driving-users-to-the-amazon-app-store-from-facebook" />

<Accordion title="从Facebook引导用户到Amazon应用商店">

1. 在Facebook应用设置页面下的Android**部分**配置跳转链接。
2. 以应用管理员的身份登录到Facebook，前往<Anchor target="_blank" href="https://developers.facebook.com/apps/">https://developers.facebook.com/apps/</Anchor> 并选择相应应用。
3. 进入设置页面找到您的Android设置，如果您还没有配置Android的话，先添加该平台。
4. 填写所有内容，包括该应用的amazon应用商店URL。   

   [![outofstore_1.png](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)

</Accordion>

* 群组
  * 在一个报表中集合多个面板/应用的数据。
  * 以install\_app\_store 作为分组维度，查看各个应用面板的数据。
* Pull API（用于单一应用方式）
* 自定义控制面板（用于多应用方式）


| 第三方应用商店 | 开始于 | SDK version |
| --- | --- | --- |
|  <span id="huawei-app-store"></span>| 2024年7月31日 | 6.14.0 + |
| <span id="samsung-galaxy-store"></span>三星Galaxy商店 | 2021年12月 | 6.1.1 + |
| <span id="xiaomi-getapps-store"></span>Xiaomi GetApps Store | 2024年9月19日 | 6.9.0 + |


* 使用场景示例:
* 协作方举例来说，


## 问题排查

### 激活归因给默认的应用

如果没有建立默认的Google Play App，则数据无法被记录。

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
|  |  |
| 带来激活的应用商店 |  |
|  |  |
| 广告收入 |  |

<div data-zendesk-anchors="multistore-android-attribution=%E5%A4%9A%E4%B8%AA%E5%AE%89%E5%8D%93%E7%AC%AC%E4%B8%89%E6%96%B9%E5%95%86%E5%BA%97%E5%BD%92%E5%9B%A0 h_01HJ369QB8PDKG7QQRV840KRAY=%E5%A4%9A%E4%B8%AA%E5%AE%89%E5%8D%93%E7%AC%AC%E4%B8%89%E6%96%B9%E5%95%86%E5%BA%97%E5%BD%92%E5%9B%A0 h_01HJ369QB876GZKQCGJZQDXDRF=%E6%B3%A8%E6%84%8F single-dashboard-vs-dashboard-per-store=%E6%9F%A5%E7%9C%8B%E5%A4%9A%E4%B8%AA%E5%95%86%E5%BA%97%E6%95%B0%E6%8D%AE%E5%8D%95%E4%B8%80%E5%BA%94%E7%94%A8%E9%9D%A2%E6%9D%BF-vs-%E5%A4%9A%E4%B8%AA%E5%BA%94%E7%94%A8%E9%9D%A2%E6%9D%BF h_01HJ369QB8SRN61ABBZ51TKFX2=%E6%9F%A5%E7%9C%8B%E5%A4%9A%E4%B8%AA%E5%95%86%E5%BA%97%E6%95%B0%E6%8D%AE%E5%8D%95%E4%B8%80%E5%BA%94%E7%94%A8%E9%9D%A2%E6%9D%BF-vs-%E5%A4%9A%E4%B8%AA%E5%BA%94%E7%94%A8%E9%9D%A2%E6%9D%BF reporting-options-available-having%C2%A0install_app_store-field=reporting-options-available-having-install_app_store-field setup-tasks=%E8%AE%BE%E7%BD%AE%E6%96%B9%E6%B3%95 h_01HJ369QB8NPE8FAHR42D2YN0K=%E8%AE%BE%E7%BD%AE%E6%96%B9%E6%B3%95 before-you-begin=%E5%BC%80%E5%A7%8B%E4%B9%8B%E5%89%8D h_01JD2DEXW74MFE44FM3S0JCK5Q=%E5%BC%80%E5%A7%8B%E4%B9%8B%E5%89%8D tasks=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B h_01JD2DFF2K0APZ98JV1X09ZB33=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B procedures=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B-1 h_01HJ369QB990HH38TRQESQVFWN=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B-1 single-dashboard%E2%80%94apk-preparation=single-dashboard-apk-preparation h_01HJ369QB9V3W9R3EB6SJSNBED=single-dashboard-apk-preparation single-dashboard%E2%80%94attribution-links=single-dashboard-attribution-links h_01HJ369QB9H3J6E892X4V15AYJ=single-dashboard-attribution-links dashboard-per-store%E2%80%94apk-preparation=dashboard-per-store-apk-preparation h_01HJ369QB9SP4DHZM5JB0RKEWG=dashboard-per-store-apk-preparation dashboard-per-store%E2%80%94adding-the-app=dashboard-per-store-adding-the-app h_01HJ369QB9X58DVBTWVWD0GCAV=dashboard-per-store-adding-the-app testing%E2%80%94both-dashboard-options=testing-both-dashboard-options h_01HJ369QB97FN9BJKD9WRW99YG=testing-both-dashboard-options nonorganic-installs=%E9%9D%9E%E8%87%AA%E7%84%B6%E5%AE%89%E8%A3%85 h_01HJ369QB93A3ZZFAF0JAEXFRR=%E9%9D%9E%E8%87%AA%E7%84%B6%E5%AE%89%E8%A3%85 organic-installs=organic-installs%E8%87%AA%E7%84%B6%E6%BF%80%E6%B4%BB h_01HJ369QB9SA05Y8VES8DD1FY4=organic-installs%E8%87%AA%E7%84%B6%E6%BF%80%E6%B4%BB expected-results=%E5%A6%82%E6%B5%8B%E8%AF%95%E6%88%90%E5%8A%9F%E6%82%A8%E4%BC%9A%E7%9C%8B%E5%88%B0 h_01HJ369QBAJADS4SMSDPKK9RHW=%E5%A6%82%E6%B5%8B%E8%AF%95%E6%88%90%E5%8A%9F%E6%82%A8%E4%BC%9A%E7%9C%8B%E5%88%B0 additional-features=%E5%85%B6%E4%BB%96%E5%8A%9F%E8%83%BD h_01HJ369QBAQ49ACSG3VEGSH7D4=%E5%85%B6%E4%BB%96%E5%8A%9F%E8%83%BD h_01HJ369QBA1XVMZD4G019T2S9W=driving-users-to-the-amazon-app-store-from-facebook troubleshooting=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 01JBKV47A5YJXKYHWA7H8NQAAF=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 installs-attributed-to-the-default-app=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0%E7%BB%99%E9%BB%98%E8%AE%A4%E7%9A%84%E5%BA%94%E7%94%A8 h_01HJ369QBANRCTCFKTGK8BTQEC=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0%E7%BB%99%E9%BB%98%E8%AE%A4%E7%9A%84%E5%BA%94%E7%94%A8 traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HJ369QBAJA87QJNTYNWYX82N=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
