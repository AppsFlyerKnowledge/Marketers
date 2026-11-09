---
title: AppsFlyer中的Steam对接配置说明
metadata:
  keywords:
    - kahuna
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
  created_at: '2016-09-14T11:26:59Z'
  edited_at: '2026-10-14T10:13:43Z'
  id: 212561966
  locale: zh-cn
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/zh-cn/articles/212561966
---
> **概要：**

<div id="important-note" />

<div id="important" />

> 🚧 **重要提示！**
>
> 部分渠道限制第三方的数据共享。

1.

* 6.14.0及以上版本的SDK

2.

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId = Kahuna.getInstance().getKahunaDeviceId();
customData .put("customData", deviceId);
AppsFlyerLib.setAdditionalData(customData);
```

```objectivec
NSString *kahunaDeviceID = [Kahuna getKahunaDeviceId];
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{@"customData" : kahunaDeviceID}];
```


**<span id="setting-up-kahuna"></span>前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. 1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
      **修改方式**：从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
   2. 搜索并选择相关渠道。
   3. 点击**设置对接**，界面会跳转到对接设置页。
   4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
      **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开 （启用） 状态。

请按照下文说明，在各个选项卡中完成相关的对接配置。

此时您仅可使用配置窗口中的对接选项卡。

如需进一步了合作伙伴配置页面中各选项卡的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">此文档</Anchor>。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

下文说明了对接选项卡中所包含各部分内容。

<div id="activate-partner" />

### 启用渠道

**第一次访问**时，需要打开***激活合作伙伴***开关以开启对接选项卡内的配置参数。只要仍与该合作伙伴合作，这个开关必须为ON。   
有关渠道激活的详细说明请参见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。

<div id="obtaining-the-kahuna-secret-key" />

<div id="general-settings" />

### 通用设置


1.

2.

<Image align="center" alt="" src="https://files.readme.io/4962454c4dd428c69e90d4ebcfa20304dc0ea57c7d58a1368c9a9369ba3e563a-207206166.png" />

3.

<Image align="center" alt="" src="https://files.readme.io/73d24826e6c55636dafbc22766910fea12fbe7a58c49079c800d5056be45352a-207229823.png" />

4.

* 点击**保存**。

<div id="testing-with-sandbox" />

<div id="view-user-attribution-data-in-kahuna" />

<div id="default-postbacks" />

### 默认回传

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

点击**保存**。

* Kahuna Dev\_ID
* Media Source（媒体渠道）
* Country code
* OS Version（操作系统版本）

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


<Image align="center" alt="" src="https://files.readme.io/ebbb7f265e37ead80dd77a9956b9629ce07eeb2fcc9b283ad7b6cc927fe10758-207230483.png" />

<Image align="center" alt="" src="https://files.readme.io/ea6ae8494f600bb8a9b9b0af3e36a976e65d72b64052da3e7399f9a9b0c9458c-207230503.png" />

<Image align="center" alt="" src="https://files.readme.io/3e0a99f178cc1a9ab18886a576b4ba56878fecb6dbd0866926730fb32b65bc59-207230563.png" />


1.

<Image align="center" alt="" src="https://files.readme.io/b69fc390ed7f1303ee8ba6dd1345d2c76b5b4c22b4b0b6ec0957a108d709247b-360002217229.png" />

2.

3.

4.

5.

6.

7.

<Image align="center" alt="" src="https://files.readme.io/8b16b6d84f0244db3510e4376bf5fc51b6a737e13df89da82e951e1bda90711a-207230963.png" width="486px" />

8. 在您的设备上安装应用

9.

<Image align="center" alt="" src="https://files.readme.io/b365a27e7638a6a87e6a5b46a67d329956f6a678b234bd1fd802acaeeceaaeb2-207207606.png" width="629px" />

<div data-zendesk-anchors="h_01H9FKAF22A3FTGC7CSE5K0CY4=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01H9FKAF22W59PMYJRFW8HKBQ7=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01H9FKAF222ES9240V0THQQ5X0=setting-up-kahuna h_01H9FKAF227SZWFTCP9P1B7HEK=integration-tab activate-partner=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01H9FKAF22EFF1F8D2QR1F38PV=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01H9FKAF221EXQYBJGS8GFRF4S=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE obtaining-the-kahuna-secret-key=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01H9FKAF22XMJW7A89MBD0J276=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9FKAF2258JVR3XS6P7TT8H3=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9FKAF22DMF1NNJRY3SJB5XX=attribution-link-tab h_01H9FKAF22KPY1ABFJN63XZ5CM=cost-tab h_01H9FKAF22KRDEFTVBR954JSJT=ad-revenue-tab h_01H9FKAF22HJPHZZM59TQ7RRFM=permissions-tab view-user-attribution-data-in-kahuna=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 testing-with-sandbox=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9FKAF22A5910NXRFDGC1JTG=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9FKAF22KW2J6H2B6F9AMDP9=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0" />
