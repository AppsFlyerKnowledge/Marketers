---
title: 受众人群的用户标识符共享规则
metadata:
  keywords:
    - IDFA
    - Audiences
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-12-23T15:39:55Z'
  edited_at: '2026-10-14T10:14:15Z'
  id: 360016791118
  locale: zh-cn
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/zh-cn/articles/360016791118
---
> **概要：** 您可以通过**账户级别**的用户标识符共享规则调控您与渠道共享的受众数据。

## 背景

<Anchor target="_blank" href="/marketers/zh/docs/audiences-partner-connections">您在受众共享面板中设定人群包后，AppsFlyer就会将该人群包中用户的标识符发送到您选定的</Anchor>推广渠道。这样，渠道就能仅向这些用户投放您的广告。

为了遵守iOS 14.5和其他用户隐私政策规定的要求，AppsFlyer的受众共享工具（Audiences）中与渠道共享的标识符完全由广告主决定。

* 账户层级
* 渠道连接层级

本文解释了用户标识符共享规则在账户级别的管理流程。如需进一步了解渠道连接层级的标识符共享规则管理方式，请参考受众共享产品指南中的<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#manage-connections">管理连接</Anchor>部分。

## 用户标识符

本节说明了可与渠道共享的标识符。

<div id="shared-identifiers" />

<Accordion title="共享标识符">

默认情况下，AppsFlyer的受众共享工具（Audiences）会与渠道共享下列标识符：

* **iOS：** IDFA（在iOS 14.5及以上版本的设备中，需要用户同意共享IDFA后才能取得该信息）
* **Android**GAID

部分推广渠道同时支持以下标识符：

* 电子邮件（哈希加密）
* 电话号码（哈希加密）
* OAID和IMEI（这两种标识符仅适用于Google Play以外的第三方安卓应用商店）

此外，还有一些适用于广告主侧内部流程的标识符（如CRM或数据分析）：

* CUID
* IDFV（仅适用于 iOS）

如需进一步了解相关信息（包括在AppsFlyer中使用特定标识符时需要符合的要求），请参见下文的标识符说明表。

</Accordion>

<div id="identifiers-table" />

<Accordion title="标识符说明表">

<table><thead><tr><th>标识符</th><th>操作系统</th><th>是否默认共享	</th><th>使用要求/<br/>注意事项<br/><br/> </th></tr></thead><tbody><tr><td>IDFA</td><td>iOS</td><td>参见脚注<br/>（右）</td><td>默认情况下，仅共享<a href="./audiences-user-identifier-policy#ios">ATT授权状态为已授权或未确定</a>的用户的IDFA </td></tr><tr><td>GAID</td><td>安卓</td><td>是</td><td>无</td></tr><tr><td>OAID</td><td>安卓<br/>（非Google play）</td><td>否</td><td> <a href="./android-oaid-implementation-in-the-sdk" target="_blank">必须</a>在AppsFlyer SDK中<a href="./android-oaid-implementation-in-the-sdk" target="_blank">配置</a> </td></tr><tr><td>IMEI</td><td>安卓<br/>（非Google play）</td><td>否</td><td> <a href="./android-oaid-implementation-in-the-sdk" target="_blank">必须</a>在AppsFlyer SDK中<a href="./android-oaid-implementation-in-the-sdk" target="_blank">配置</a> </td></tr><tr><td>CUID</td><td>iOS<br/>安卓</td><td>否</td><td><ul><li>由广告主生成并通过AppsFlyer API或SDK<a href="./customer-user-id-field-cuid" target="_blank">上报到AppsFlyer</a> </li><li>不共享到推广渠道，但可用于您的内部流程</li><li>需遵守<a href="https://support.appsflyer.com/hc/article_attachments/360017900558">其他的标识符使用条款</a> </li></ul></td></tr><tr><td>IDFV</td><td>iOS</td><td>否</td><td><ul><li>不共享到推广渠道，但可用于您的内部流程</li><li>需遵守<a href="https://support.appsflyer.com/hc/article_attachments/360017900558">其他的标识符使用条款</a> </li></ul></td></tr><tr><td>电子邮件（哈希加密）</td><td>iOS<br/>安卓</td><td>N</td><td rowspan="2"><ul><li> <a href="./audiences-configure-additional-identifiers-for-partner-audience-creation" target="_blank">必须</a>通过AppsFlyer SDK或S2S-mobile API配置</li><li>必须使用SHA256哈希加密</li><li>需遵守<a href="https://support.appsflyer.com/hc/article_attachments/360017900558">其他的标识符使用条款</a> </li></ul></td></tr><tr><td>电话号码（哈希加密）</td><td>iOS<br/>安卓</td><td>否</td></tr></tbody></table>

</Accordion>

## 设置账户层级的用户标识符共享规则

用户标识符共享规则仅可由AppsFlyer账户的管理员设置。

**如需设置或更改您的标识符共享规则，请按以下步骤操作：**

1. 从AppsFlyer后台的侧边栏中选择**互动** > **受众共享**。
2. 点击页面右上角的设置图标（小齿轮）。
3. **在用户标识符共享规则窗口中，选择符合贵司隐私政策的设置。**
   * [如果您选择共享IDFA、GAID、OAID和IMEI以外的标识符，必须先查看并接受 其他标识符的使用条款。](https://support.appsflyer.com/hc/article_attachments/360017900558)
   * 如果您选择禁止通过现有渠道连接共享标识符，界面会弹出确认请求窗口，让您选择是否确定要停止上传这些标识符。
4. 点击**保存**。

您对IDFA共享规则所做的变更自Apple发布iOS 14.5起生效。您对所有其他用户标识符共享规则所做的变更自下次渠道上传起生效。

## 隐私监管政策

本节介绍了影响用户标识符共享的隐私监管政策。

<div id="ios" />

<Accordion title="iOS">

从iOS 14.5开始，Apple要求每个应用都为用户提供广告跟踪的授权选项，即让用户选择允许/不允许共享其IDFA设备标识符，用于广告投放（即App Tracking Transparency，应用广告跟踪透明度，简称ATT）。用户是否看到并回应ATT授权弹窗决定了该用户的<Anchor target="_blank" href="/marketers/zh/docs/att-implications-ios-14-and-deprecation-of-lat">ATT授权状态</Anchor>。

在iOS中，用于标识符共享的受众共享规则取决于用户最近的ATT授权状态。具体的共享规则如下：

| 用户共享规则 | 对应的标识符共享规则 |
| --- | --- |
| 永不上传 | 不向渠道上传该标识符 |
| 仅在ATT授权状态为“authorized”（已授权）时上传 | 如果用户最近的ATT授权状态为**authorized**或**af\_authorized**，则上传该标识符 |
| ATT授权状态为“authorized”（已授权）或“not determined”（未明确）时上传 | 如果用户最近的ATT授权状态为\*\*authorized\*\*、\*\*af\_authorized\*\*、 \*\*not\_determined\*\*或\*\*af\_unavailable，则上传该标识符  <br />  <br />*自Apple发布iOS 14.5起，对于IDFA共享的默认选项\*\** |
| 始终上传 | 无论ATT授权状态如何，都上传该标识符。请确保您选择的共享规则符合您的应用使用条款。  <br />  <br />*该选项对IDFA不可用* |

**请注意：** 在新用户看到并回应ATT授权弹窗之前，受众共享产品总是将其授权状态视为not determined（未明确）。

如需进一步了解ATT授权状态的定义，请参考

* <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">Apple对ATT授权状态的定义</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/att-implications-ios-14-and-deprecation-of-lat#att-values">AppsFlyer对ATT授权状态的定义</Anchor>（af\_authorized、af\_unavailable）

此外，对于欧洲经济区（EEA）的用户，您还需要遵守Google针对《[数字市场法案](/docs/audiences-user-identifier-policy#eu-digital-markets-act)》（DMA）的应对政策。

</Accordion>

<div id="android" />

<Accordion title="安卓">

对于欧洲经济区（EEA）的安卓用户，您需要遵守Google针对《[数字市场法案](/docs/audiences-user-identifier-policy#eu-digital-markets-act)》（DMA）的应对政策。

</Accordion>

<div id="eu-digital-markets-act" />

<Accordion title="欧盟的数字市场法案">

为了符合欧盟《数字市场法案》（DMA）的要求，Google从2024年3月6日起推行应对政策，对其欧盟用户意见征求政策进行了更新。作为Google的应用归因合作伙伴，AppsFlyer也在做必要调整，以支持Google的政策规定，同时确保广告主能充分发掘Google Ads作为营销渠道的价值。<Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">详情请见此处说明。</Anchor>

**该政策会对受众共享产生以下影响：**

* **新的AppsFlyer SDK**  
  最新版本的AppsFlyer SDK会针对<Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">欧洲经济区（EEA）</Anchor>的用户从应用侧收集用户授权信息，以便与Google共享相关用户的数据。对于您在AppsFlyer中创建的人群包（如自定义人群包或推荐人群包），AppsFlyer SDK会将收集到的用户授权信息会自动发送到AF受众共享，然后再共享给Google。如需自动完成此流程，请更新到最新版本的SDK。
* **连接到Google的人群包**
  * **用户同意授权** - 对于同意与Google共享信息的EEA用户，AppsFlyer会将其设备信息发送到Google。
  * **用户拒绝授权** - 对于拒绝与Google共享信息的EEA用户，AppsFlyer不会将其设备信息发送到Google。
  * **授权状态未知** - 对于既未同意也未拒绝授权的EEA用户，AppsFlyer会将其设备信息标记为“Unspecified”（未指明）发送到Google。Google很可能不会将这些用户收归到其平台的人群包中。  

    详情请见Google提供的<Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">FAQ</Anchor>文档。
* **现存人群包**  
  2024年3月6日之前的Google侧现存人群包不受上述政策影响，相关用户仍会保留在对应的人群包中。仅新建人群包或在现存人群包中新添加的EEA用户设备在上传到Google时需要带有用户授权信息。
* **上传的人群包大小**  
  AF预估的人群包大小和实际上传的数量可能会有差异，具体取决于同意或拒绝授权的用户数量。
* #### **导入人群包**

  * **导入标准人群包** - AppsFlyer会在其中添加由SDK收集到的用户授权数据，并移除拒绝授权或未指明授权状态的用户设备，然后再将人群包发送到Google。
  * **按原样导入的人群包** - 通过<Anchor target="_blank" href="/marketers/zh/docs/audiences-import-audience-segments-from-internal-systems#import-a-csv-file">CSV文件上传</Anchor>或<Anchor target="_blank" href="/marketers/zh/docs/audiences-import-audience-segments-from-internal-systems#use-the-import-audience-api">API</Anchor>按原样导入人群包时，需要另外添加以下两个授权信息字段：

| AppsFlyer字段（1） | Google字段（2） | 值 | 字段用途 |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true/false | 用于说明该用户是否允许Google将其数据用于个性化广告 |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true/false | 用于说明该用户是否同意将其数据发送到Google |

如果以上授权信息字段中没有填充字段值，相关用户就会被标记为“Unspecified”，发送到Google。

> 📘 **注意**
>
> Google对于《数字市场法案》（DMA）的应对政策同时对安卓和iOS平台生效。

</Accordion>

<div data-zendesk-anchors="background=%E8%83%8C%E6%99%AF h_01HKA2FS9VBCSV8FP8FH79H4R0=%E8%83%8C%E6%99%AF user-identifiers=%E7%94%A8%E6%88%B7%E6%A0%87%E8%AF%86%E7%AC%A6 h_01HKA2FS9VSVJD54R14GC7G0P4=%E7%94%A8%E6%88%B7%E6%A0%87%E8%AF%86%E7%AC%A6 h_01HNZH99Z8NA9607VHSYH5XVW0=shared-identifiers h_01HKA2FS9V1KBK9BJAJ63FP6CV=identifiers-table setting-accountlevel-user-identifier-policy=%E8%AE%BE%E7%BD%AE%E8%B4%A6%E6%88%B7%E5%B1%82%E7%BA%A7%E7%9A%84%E7%94%A8%E6%88%B7%E6%A0%87%E8%AF%86%E7%AC%A6%E5%85%B1%E4%BA%AB%E8%A7%84%E5%88%99 h_01HKA2FS9WNGGRP3NX5NKV15SK=%E8%AE%BE%E7%BD%AE%E8%B4%A6%E6%88%B7%E5%B1%82%E7%BA%A7%E7%9A%84%E7%94%A8%E6%88%B7%E6%A0%87%E8%AF%86%E7%AC%A6%E5%85%B1%E4%BA%AB%E8%A7%84%E5%88%99 user-identifier-policy-options=%E9%9A%90%E7%A7%81%E7%9B%91%E7%AE%A1%E6%94%BF%E7%AD%96 h_01HKA2FS9W5NSKKRK2VCZARG15=%E9%9A%90%E7%A7%81%E7%9B%91%E7%AE%A1%E6%94%BF%E7%AD%96 h_01HNZJ1ET6F87AHHVQK17QHZDD=ios h_01HNZJ1ET67JQQCPYSM3H6Y9VW=android h_01HNZN8MWETDCMGWKJ0MMM8JK4=eu-digital-markets-act importing-audiences=%E5%AF%BC%E5%85%A5%E4%BA%BA%E7%BE%A4%E5%8C%85 h_01HPGV1GYT8DW0GYWTC031TNVH=%E5%AF%BC%E5%85%A5%E4%BA%BA%E7%BE%A4%E5%8C%85 h_01HNZEAJT00KKEBDPR7FD0TJNR=%E6%B3%A8%E6%84%8F" />
