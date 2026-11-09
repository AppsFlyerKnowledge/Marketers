---
title: Amazon Ads广告系列配置
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2023-01-04T10:14:20Z'
  edited_at: '2026-10-14T10:12:38Z'
  id: 11904659502737
  locale: zh-cn
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/zh-cn/articles/11904659502737
---
> **概要：** Amazon Ads（amazondsp\_int）是AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">SRN</Anchor>对接渠道之一。广告主可以通过AppsFlyer，将电视、平板和移动设备上的转化与来自Amazon Ads的点击或展示进行匹配。

<Image align="center" alt="mceclip0.png" src="https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png" />

<div id="activate-partner" />

## 启用渠道

**前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式**：从AppsFlyer面板左侧的菜单栏中选择**协作** > **活跃对接**。
2. 搜索并选择Amazon Ads对接。  
   **重要提示：** 请确保您选择的是amazondsp\_int，而不是amazon\_int（旧版对接）。
3. 点击**设置对接**，然后界面会跳转到**活跃对接**设置页面。
4. 在**渠道对接**选项卡中，打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开（即<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">启用</Anchor>）状态。
5. 参考下文说明，根据您的具体需求在相关选项卡中完成各项配置。

<div id="complete-the-setup-in-amazon-ads" />

## 在Amazon Ads中进行设置

请在Amazon Ads中完成以下步骤：

1. 请确保您已在Amazon Ads中完成应用注册。请参见Amazon Ads文档中的<Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">注册应用</Anchor>。
2. 创建Amazon Ads广告系列时，请将需要衡量的转化与该广告系列关联。请参见 Amazon Ads 文档中的 <Anchor target="_blank" href="https://advertising.amazon.com/help/GMQBB4PRFK8C33AE">将转化事件关联到广告系列</Anchor>。

<div id="setting-up-amazon-ads" />

## Amazon Ads的对接配置

Amazon Ads的对接支持点击和展示归因。配置窗口包括以下选项卡：渠道对接、归因链接、成本、广告收入和授权。在Amazon Ads对接中，可用的选项卡为“渠道对接”和“权限”。

<div id="note" />

> 📘 **注意**
>
> 该对接支持Android、iOS和Fire应用，并支持通过SKAN衡量iOS应用。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

**渠道对接**选项卡中包括以下几个部分。

<div id="activate-partner-1" />

#### 启用渠道

在配置对接之前，必须先[打开](/docs/amazon-ads-campaign-configuration#启用渠道)**启用该渠道**开关。详情请见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation#渠道对接的启用方式">渠道对接的启用和停用说明</Anchor>。

<div id="general-settings" />

#### 通用设置

**Amazon advertiser ID**

该密钥由Amazon为相关广告主生成，具有唯一性。Amazon advertiser ID是对接设置流程中的必填字段，也是对Amazon Ads进行归因的必要条件。请按以下方式查找Amazon advertiser ID：

* **自助使用该平台的广告主：** 请进入Amazon Ads数据上报面板中，在“Advertiser”选项卡的“Amazon DSP Campaign Manager”部分，找到您的“Advertiser Name”，其下方就是您的Advertiser ID。
* **有专员服务的广告主：** 请让您的Amazon客户经理为您提供该advertiser ID。
* 如果您为同一应用使用多个Amazon广告账号（拥有多个Amazon广告主ID），请按以下方式配置对接：
  1. 在Amazon Ads中选择一个广告账号，并将其设为**源账号**。将其他所有广告账号设为**目标账号**。
  2. 联系Amazon客户团队，由其在后台完成相关配置。
  3. 在AppsFlyer中，输入与源账号关联的Amazon广告主ID。完成后，系统会将该对接配置应用于所有相关的目标账号。

**Amazon应用ID**

* **安卓应用：** 即相关包名，如：`com.example.app`。
* **Fire TV或Fire平板设备中的应用：** 相关产品的ASIN（Amazon Standard Item Number，亚马逊商品的标准识别号）
* **iOS应用：** 没有 "`id`" 的应用商店应用ID（示例：`12345678`）。
* <Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution#查看多个商店数据单一应用面板-vs-多个应用面板">**单面板应用**</Anchor>（针对AppsFlyer中的同一个应用，在同一个面板中同时结合Google Play和Amazon商店两方的数据）：请输入Android软件包名称作为应用ID。  
  **注意：** 请确保在相关Amazon Ads账号中将该应用<Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">注册</Anchor>为安卓应用。

<div id="install-attribution" />

#### 激活归因

设置点击型和浏览型的激活归因（即首次应用打开）窗口期。请注意，仅在相关回溯窗口内发生的激活才会被归因到Amazon Ads。

**请注意：** 该对接不支持重装激活（即相关设备上除了初次激活以外的任何其他激活）的归因。

1. 设置**点击型激活回溯窗口**，可用的时长范围为1-24小时或1-14天。  
   **请注意：** Amazon Ads建议您将点击型回溯窗口设置为14天，与其归因窗口保持一致，避免出现数据差异。
2. 【可选】打开**浏览型激活归因**，并设置**浏览型激活归因窗口**，可用的时长范围为1-24小时。   
   **请注意：** Amazon Ads建议您将浏览型回溯窗口设置为14天，与其归因窗口保持一致，避免出现数据差异。

<div id="re-engagement-attribution" />

#### 再互动归因

打开**再互动归因**的开关，设置不同的归因窗口期，将现有用户的再互动行为归因到相关的广告浏览、点击或其他***广告交互***形式。请注意，仅在相关回溯窗口内发生的再互动才会被归因到Amazon Ads。

1. 【可选】打开**再互动归因**的开关，并设置回溯窗口：
   * 设置**点击型再互动回溯窗口**，可用的时长范围为1-23小时或1-14天。
2. 【可选】打开**浏览型再互动归因**的开关，并设置回溯窗口：
   * 设置**浏览型再互动回溯窗口**，可用的时长范围为1-23小时或1-14天。
3. 设置**再互动窗口**，可用的时长范围为1-23小时、1-90天或用户的**整个生命周期**。

<div id="ignore-active-users-for-retargeting" />

#### 再营销广告中忽略活跃用户

打开这个开关并设置其窗口期后，AppsFlyer就会<Anchor target="_blank" href="/marketers/zh/docs/set-retargeting-inactivity-window#不活跃时长">忽略在此期间打开相关应用的用户所完成的再互动和再归因</Anchor>。也就是说，这些用户在该窗口期内的行为不会被记录到AppsFlyer中。

<div id="note-1" />

> 📘 **注意**
>
> 在此期间处于**沉睡**状态的用户所完成的再互动和再归因**会得到记录**。

1. 打开**在再营销广告中忽略活跃用户**的开关。
2. 设置**不活跃窗口**，可用的时长范围为1-30天。  
   **请注意：** Amazon Ads建议您将不活跃窗口设置为7天，与其平台侧设置保持一致，避免出现数据差异。

<div id="in-app-event-postbacks" />

#### 应用内事件回传

将回传中的应用内事件映射到Amazon Ads平台中的对应事件：

**请按以下步骤配置应用内事件回传：**

1. 打开**应用内事件回传**开关。
2. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。下表列出了必须配置的字段：

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。<br />**提示**：如果下拉菜单中没有您要查看的事件：<ul><li>请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。</li><li>在**AppsFlyer事件**中输入该事件的名称，然后点击**创建自定义事件**。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">自定义事件映射</Anchor>。</li></ul> |
| **渠道映射事件** | Amazon Ads为每个事件定义的专属名称或ID。从预定义的渠道事件列表中选择与相关应用事件（即AppsFlyer事件）对应的事件。<br /><br />**请注意：**<ul><li>如果您需要的应用内事件没有直接对应的渠道映射事件，请选择“其他”。</li><li>启用再互动衡量后，建议不要映射`af_app_opened`事件，或仅将其映射到`OTHER`。这样可以避免发送该事件时出现重复。</li></ul> |
| **事件来源** | 选择事件回传的范围：<ul><li>**仅该合作渠道**：仅回传归因到该渠道的事件。</li><li>**所有媒体渠道，包括自然流量**：回传所有带量渠道的事件，以及自然量。</li></ul> |
| **回传内容** | <ul><li>**不发送值与收入（默认）**：仅发送事件本身，不带任何事件值。</li><li>**发送值与收入**：发送所有事件参数，**包括**收入（若有）。</li><li>**仅发送值**：发送**除**收入以外的所有参数。</li></ul> |

   <div id="note-2" />

   > 📘 **注意**
   >
   > 如果您通过S2S将应用内事件发送给AppsFlyer，Amazon建议在请求中包含IP地址。这样，AppsFlyer可以将事件发生地对应的国家/地区代码发送给Amazon，从而帮助Amazon进行DMA法规分类。这也有助于Amazon更充分地优化您的应用内事件。

3. 【可选】点击**添加条件**<Image alt="onditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />图标，<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">设置事件的回传条件</Anchor>。
4. 点击**保存对接**。
5. 【可选】您可以在保存对接后留在配置页面，将其他应用也对接到该渠道：
   1. 点击页面左上角渠道名称下方的应用名称，打开应用列表。
   2. 在下拉菜单中选择一个其他应用。
   3. 为选定应用完成[对接流程](#integration-tab)。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

在Amazon Ads的对接中，归因链接不可用。我们会结合Amazon Ads的广告交互数据与AppsFlyer的数据，并根据您在[渠道对接](#integration-tab)选项卡中设置的点击和浏览回溯窗口得出归因结果。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本、点击和展示选项卡">

Amazon Ads的对接不支持成本、点击和展示数据。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

Amazon Ads的对接不支持广告收入数据。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

您可以在这个板块中选择需要向Amazon Ads开放的数据和操作权限。

<div id="note-3" />

> 📘 **注意**
>
> * 请注意，即使您<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">停用</Anchor>了这个对接，但只要其权限开关处于打开状态，相关权限就仍向Amazon Ads开放。
> * 进一步了解与<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">授权</Anchor>相关的信息。

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/setting-up-amazon-fire-tv-ad-attribution">Amazon Fire TV广告归因设置指南</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/attribution-discrepancies-between-amazon-ads-and-appsflyer">AppsFlyer与Amazon Ads之间的归因差异</Anchor>

<div id="deferred-deep-linking" />

## 延迟深度链接

* Amazon Ads不支持深度链接。
* 延迟深度链接——AppsFlyer提供的两种延迟深度链接方案都不适用于Amazon Ads，具体如下：
  * [UDL](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl)（Unified Deep Link）——不支持SRN
  * [GCD](https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking) （Get Conversion Data）——犹豫Amazon Ads的归因数据[受限](/docs/amazon-ads-campaign-configuration#原始数据限制)，因此不适用于Amazon Ads。

<div id="raw-data-restrictions" />

## 原始数据限制

来自Amazon Ads的原始数据<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions#媒体渠道数据限制">在AppsFlyer平台中的呈现会受到限制</Anchor>。在原始数据中，该平台的媒体渠道名称会显示为“restricted”（受限），且广告系列信息为null。原始数据报告中不包含来自Amazon ads的点击和展示。

<div id="ctv-to-mobile-attribution" />

## CTV到移动端归因

Amazon可能会将移动应用安装归因到CTV（联网电视）广告系列，例如Amazon Prime Video广告系列。如果用户观看CTV广告时，已在移动设备上的Amazon应用中登录账号，Amazon便可能完成此类归因。

**请注意：** 报告中**不会明确标识**广告系列是否属于CTV广告系列。为方便识别和衡量，建议在适用情况下在广告系列名称中添加`CTV`。

<div id="support-amazon-eu-consent-policy" />

## 支持Amazon欧盟用户同意政策

为配合<Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">《数字市场法案》（DMA）</Anchor>的实施，Amazon Ads正在更新欧盟用户同意政策。作为Amazon的应用归因合作伙伴，AppsFlyer也将根据此次政策调整进行相应更新，帮助广告主充分发挥Amazon广告的投放效果。更新后的政策将于2026年6月30日生效。

<div id="note-4" />

> 📘 **注意**
>
> 更新后的欧盟同意政策仅适用于来自欧盟、英国或瑞士（CH）用户的数据（包括安装、重新互动及应用内事件）。

为满足相关要求，请采用与Google DMA用户同意信息<Anchor target="_blank" href="/marketers/zh/docs/support-google-eu-consent-policy">相同的方式，将DMA用户同意信息发送给AppsFlyer。</Anchor>

<div id="dma-consent-methods" />

### DMA用户同意信息传递方式

AppsFlyer目前支持以下两种DMA用户同意信息传递方式：

| 方法 | 说明 |
| --- | --- |
| **手动** | 亚马逊要求的唯一必填字段为`ad_user_data_enabled`。 |
| <Anchor target="_blank" href="https://iabeurope.eu/transparency-consent-framework/">**TCF**</Anchor> **(透明度与同意框架)** | 如果您使用同意管理平台（CMP），请确保将亚马逊广告供应商ID（**793**）添加到供应商白名单列表中。 |

<div id="note-5" />

> 📘 **注意**
>
> Amazon也支持通过<Anchor target="_blank" href="https://iabtechlab.com/gpp/">Global Privacy Platform（GPP）</Anchor>传递用户同意信号，但AppsFlyer目前尚不支持这种方式。

<div id="see-also-1" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance">通过AppsFlyer SDK发送DMA用户同意信息</Anchor>
> * `consent_data`<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-overview">通过AppsFlyer S2S发送DMA用户同意信息</Anchor>（搜索 ）

<div id="traits-and-limitations" />

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 代理 | Amazon Ads的对接目前不支持代理，因此仅可通过广告主账号管理该对接。 |
| 展示、点击和成本 | 该对接尚不支持展示、点击和成本数据。 |
| 深度链接 | [该对接不支持深度链接](#延迟深度链接)。 |
| 重装激活和再归因 | 该对接不支持重装激活和再归因。 |
| 预装归因 | 该对接不支持预装监测，但您可通过旧版对接amazon\_int进行预装归因。 |
| 回传限制 | 在Android设备上，如果`advertiserIdEnabled`字段的值为false，即使能够获取广告主ID，AppsFlyer也不会将安装或再互动数据发送给Amazon。 |

<div data-zendesk-anchors="activate-partner=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 01H88VAJH3B5ESK12D3ATMMVZ8=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 complete-the-setup-in-amazon-ads=%E5%9C%A8amazon-ads%E4%B8%AD%E8%BF%9B%E8%A1%8C%E8%AE%BE%E7%BD%AE h_01KMG57HR62CC9TX495SG3WSRD=%E5%9C%A8amazon-ads%E4%B8%AD%E8%BF%9B%E8%A1%8C%E8%AE%BE%E7%BD%AE setting-up-amazon-dsp-integration=amazon-ads%E7%9A%84%E5%AF%B9%E6%8E%A5%E9%85%8D%E7%BD%AE 01H88VAJH3VENKYVRQY5RXN63P=amazon-ads%E7%9A%84%E5%AF%B9%E6%8E%A5%E9%85%8D%E7%BD%AE 01H88VAJH3BYZSXQGGZZJQ9N0C=%E6%B3%A8%E6%84%8F 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93-1 01H88VAJH34GP7FK1KTJGRDPM7=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93-1 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE 01H88VAJH3F2FJK5YP3M2V7RWD=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE install-attribution=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 01H88VAJH3SSG6ZNV7XQ46W5CX=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 reengagement-attribution=%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 h_01J4RC3GR8B04RNFSD61QK45C0=%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 ignore-active-users-for-retargeting=%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E4%B8%AD%E5%BF%BD%E7%95%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7 h_01HNWSTJZPFQVQ5C8M0JA1J0T5=%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E4%B8%AD%E5%BF%BD%E7%95%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7 h_01HMXNJVHK9C3FT8E04RE0TH99=%E6%B3%A8%E6%84%8F-1 inapp-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H88VAJH3AS37MVF75GANWX4B=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01JEXXHXMEC5M7N1BDSGS3ZZ51=%E6%B3%A8%E6%84%8F-2 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%E6%B3%A8%E6%84%8F-3 h_01HDNZ59NQEDFC3D8JYGENR1NR=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3 deferred-deep-linking=%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 01J9G5FQGB0219RGWVW06BQPG7=%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 raw-data-restrictions=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E9%99%90%E5%88%B6 01JBY7HD39BA9ZNR2N2TYYPBW3=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E9%99%90%E5%88%B6 ctvtomobile-attribution=ctv%E5%88%B0%E7%A7%BB%E5%8A%A8%E7%AB%AF%E5%BD%92%E5%9B%A0 h_01JZG6S5TB1888XG9560MKEBF3=ctv%E5%88%B0%E7%A7%BB%E5%8A%A8%E7%AB%AF%E5%BD%92%E5%9B%A0 support-amazon-eu-consent-policy=%E6%94%AF%E6%8C%81amazon%E6%AC%A7%E7%9B%9F%E7%94%A8%E6%88%B7%E5%90%8C%E6%84%8F%E6%94%BF%E7%AD%96 h_01KP0DJ73P9FRX51SR3RS4YWVP=%E6%94%AF%E6%8C%81amazon%E6%AC%A7%E7%9B%9F%E7%94%A8%E6%88%B7%E5%90%8C%E6%84%8F%E6%94%BF%E7%AD%96 h_01KP0DJ73PDB7FM1RG0VV99707=%E6%B3%A8%E6%84%8F-4 dma-consent-methods=dma%E7%94%A8%E6%88%B7%E5%90%8C%E6%84%8F%E4%BF%A1%E6%81%AF%E4%BC%A0%E9%80%92%E6%96%B9%E5%BC%8F h_01KP0DJ73PG0JMWG3WAWCKXE1S=dma%E7%94%A8%E6%88%B7%E5%90%8C%E6%84%8F%E4%BF%A1%E6%81%AF%E4%BC%A0%E9%80%92%E6%96%B9%E5%BC%8F h_01KP0DJ73PNPYT0TRWF089VE9R=%E6%B3%A8%E6%84%8F-5 h_01KP0DJ73PC4ABGRPRDAR7BW5B=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3-1 traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
