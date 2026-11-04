---
title: Apple Ads（搜索广告）对接设置
metadata:
  keywords:
    - cost
    - Advertisers
    - apple search ads
    - asa
    - apple ads
    - apple search advanced
    - apple search ads campaign group
    - apple keywords
    - apple searchads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-31T09:04:38Z'
  edited_at: '2026-10-14T10:14:53Z'
  id: 213747963
  locale: zh-cn
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/zh-cn/articles/213747963
---
> **概要：** Apple Search Ads（ASA）是AppsFlyer的SRN对接渠道。用户在App Store使用关键词搜索时，ASA能让他们看到您的应用。

<Image alt="apple_search_ads.png" src="https://files.readme.io/20c980a800209d1ba77cec42ccfdb8c0d5659562f2c30b2aaa6ec36cae52ab50-51911955934097.png" width="217px" />

用户在App Store搜索后是否会出现您的广告取决于广告相关性。用户对于广告的反应是广告相关性的一种体现，因此ASA会通过用户对广告的反应来判定最常显示哪些广告。

> 📘 **注意**
>
> * AppsFlyer现已支持Apple Search Ads的点击归因、用户<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销</Anchor>以及通过API获取的<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview">成本数据</Anchor>（需订阅 ROI360）。
> * 自2025年3月27日起，AppsFlyer新增了对Apple Search Ads展示归因的支持。

<div id="set-up-apple-ads-integration" />

## ASA对接设置指南

<div id="get-started" />

<Accordion title="开始">

**前期准备**

* 在您的应用中接入最新版本的AppsFlyer iOS SDK

**请按以下步骤在AppsFlyer后台配置ASA对接：**

您可以在**活跃对接** 页面完成设置，但在添加新合作伙伴前，请先前往<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations">Partner Marketplace</Anchor>。请按照下文说明，在各个选项卡中完成相关的对接配置。

<div id="note-1" />

> 📘 **注意**
>
> 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系相关渠道</Anchor>并在其平台上开设账户。

</Accordion>

<div id="integration" />

<Accordion title="渠道对接选项卡">

Apple Search Ads是一个自归因渠道（即SRN），它是通过 API与AppsFlyer对接的，因此没有回传设置。请根据您的归因目标完成以下各板块的设置。

<table><thead><tr><th>板块 </th><th>说明</th></tr></thead><tbody><tr><td>对接激活</td><td><p><strong>请按以下方式启用或修改该对接：</strong></p><ol><li> <strong>启用方式：</strong> 从AppsFlyer的侧边栏中选择<strong>协作</strong> &gt; <strong>Partner Marketplace</strong>。<br/><strong>修改方式</strong>：从AppsFlyer面板左侧的菜单栏中选择<strong>协作</strong> &gt; <strong>活跃对接</strong>。</li><li>搜索并选择相关渠道。</li><li>点击<strong>设置对接</strong>，界面会跳转到对接设置页。</li><li>进入<strong>渠道对接</strong>选项卡，选择需要对接的应用，并打开<strong>启用该渠道</strong>开关。<br/><strong>请注意：</strong> 在您与该渠道合作期间，请确保该开关总是处于打开<a href="./partner-activation-deactivation" target="_blank">（启用）</a>状态。</li><li>请按照下文说明，在各个选项卡中完成相关的对接配置。</li></ol></td></tr><tr><td>安装点击归因</td><td><p>设置点击回溯窗口，即从点击到激活的最长时间跨度。这样，AppsFlyer就能将在该窗口期内发生的激活归因到ASA。</p><p>可用范围：1–30天<br/><br/>有关回溯窗口的更多信息，请参见<a href="./set-up-lookback-windows" target="_blank">回溯窗口说明</a>。</p></td></tr><tr><td>浏览型激活归因</td><td><p>设置浏览回溯窗口，即从浏览到激活的最长时间跨度。浏览型激活归因回溯窗口滑块仅支持以小时为单位设置（最大：24小时，默认：24小时</p><p>可用范围：1–24小时</p><p>有关回溯窗口的更多信息，请参见<a href="./set-up-lookback-windows" target="_blank">回溯窗口说明</a>。</p></td></tr><tr><td rowspan="2">重装激活 </td><td><p><strong>重装激活归因</strong></p><p>打开<strong>重装激活归因</strong>开关后，AppsFlyer就可以将重装激活归因到ASA。</p><p>重装激活归因回溯窗口沿用激活归因的设置。</p><p>AF会将用户在<a href="./set-up-re-attribution-window" target="_blank">再归因窗口期</a>内完成的重装激活归因到ASA。</p><p>您可以在数据总览面板的再营销视图中查看重装激活数据。</p><p>原始数据中的<strong>Store reinstall</strong>（来自商店的重装激活） 字段为true。 </p><p>目前ASA的再营销不支持再互动。</p></td></tr><tr><td><p><strong>不活跃窗口期</strong></p><p>您可以通过设置用户的<a href="./set-retargeting-inactivity-window" target="_blank">不活跃窗口期</a>（以天为单位）来调整再营销广告的投放范围。 </p></td></tr><tr><td>数据回传</td><td>目前，Apple Ads对接不支持回传。 </td></tr></tbody></table>

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

成本对接可提供下列汇总数据：

* 广告系列、广告组、国家/地区和关键词维度的成本数据。详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">广告平台成本对接表</Anchor>，其中详细说明了适用维度、指标和功能。  
  **请注意：** 您需要购买ROI360才能获得成本数据。
* 点击、展示数据以及扩充数据——关键词、广告系列名称以及广告组。

<div id="note-2" />

> 📘 **注意**
>
> * ASA成本对接支持同时使用多个ASA账户。也就是说，如果您使用不同的ASA账户投放同一个应用的广告，AppsFlyer能够接收所有相关账户的数据。
> * ASA的报告API不上报“campaign groups”（广告系列组）的成本数据，因此AppsFlyer后台没有该数据。
> * 如需使用Apple账户登录，您需要有ASA管理员权限（只读或读写权限都可以）。
> * 通过Apple登录时，您之前提供的所有API证书都会停止拉取数据。
> * 通过Apple登录时，ASA campaign group（广告系列组）的授权无法累积。也就是说当您对接新的应用时，针对以往应用选定的campaign group授权会被撤销，需要重新选定。
> * 通过Apple登录时，您不能使用<Anchor target="_blank" href="https://support.apple.com/en-il/guide/apple-business-manager/axmb19317543/web">federated login</Anchor>（联合登录）。

**如需获取成本、点击、展示和扩充数据：**

* 请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">对接指南</Anchor>进行操作。

您可以在成本（及广告收入）对接状态面板或单独的广告平台面板中查看AppsFlyer最近一次拉取成本数据的时间以及<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">成本API状态</Anchor>。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">详情请见广告平台与代理权限设置指南。</Anchor>

</Accordion>

<div id="set-up-agencies-and-apple-ads-marketing-partners" />

## 设置代理和ASA营销伙伴

<div id="principles" />

<Accordion title="原理">

**Apple Search Ads：平台官方合作渠道与代理的区别**

广告商和代理商可以选择与 ASA 营销合作伙伴合作 以报告和优化 ASA 上的活动。

代理商和营销合作伙伴之间的区别已列出 具体请参考下方表格；

<div id="agency-vs-marketing-partner" />

#### 代理商与营销合作伙伴对比表

|  | Agency（代理） | 平台官方合作渠道 |
| --- | --- | --- |
| AppsFlyer是否发送回传 | 否 | 是 |
| 技术 | 广告代投 | 可通过附加值技术方案优化投放 |

<div id="configuring-agencies-and-marketing-partners" />

#### 如何配置代理商和营销合作伙伴

使用以下检查表以确保您完成所有步骤 在配置过程中。详细说明包含在 每种合作伙伴类型的后续部分中。

<div id="configuration-steps-checklist" />

#### 配置操作清单

| 配置方 | 与代理商对接 | 与营销合作伙伴对接 |
| --- | --- | --- |
| 广告主 | <ol><li>在 AppsFlyer 的 ASA 集成标签中， 打开**激活渠道开关**。</li><li>在代理权限中选择代理商， 打开**代理权限**开关。</li></ol> | <ol><li>在 ASA 集成标签中，打开 启用渠道</li><li>在 ASA 仪表板中获取营销合作伙伴的 campaign\_group\_id</li><li>在营销合作伙伴的对接选项卡中执行以下操作：<ol><li>打开**激活渠道开关**。</li><li>设置Campaign Group。</li><li>配置应用内事件回传。</li></ol></li></ol> |
| Agency（代理） | 在 ASA 集成标签中，设置 Apple Search Ads Campaign Group | <ol><li>在 ASA 集成标签中，打开 启用渠道</li><li>在 ASA 仪表板中获取营销合作伙伴的 campaign\_group\_id</li><li>在营销合作伙伴的对接选项卡中执行以下操作：<ol><li>打开**激活渠道开关**。</li><li>设置Campaign Group。</li><li>配置应用内事件回传。</li></ol></li></ol> |

</Accordion>

<div id="marketing-partner-setup" />

<Accordion title="营销合作伙伴的设置方式">

**请按以下方式设置营销合作伙伴：**

1. 请根据实际需要激活**Apple Search Ads对接**：
   1. 在 AppsFlyer 中，转到 **配置** **活动集成合作伙伴** > Apple Search Ads
   2. 打开**激活渠道**开关。
   3. 点击**保存**。
2. **从Apple Search Ads后台** 获取 与 Apple Search Ads 活动组 ID 参数相关的 平台官方合作渠道使用以下屏幕截图作为指南 以定位 ID。  ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
3. **在AppsFlyer后台配置ASA营销合作伙伴：**
   1. 从AppsFlyer后台的侧边栏中选择 协作： 活跃对接
   2. 搜索要配置的**Apple Search Ads*营销合作伙伴。***  
       界面会显示营销合作伙伴列表。
   3. 选择要配置的营销合作伙伴。
   4. 打开**激活渠道**开关。
   5. 输入合作伙伴名称 **Apple Search Ads 活动组 ID** 是您 在之前的步骤中检索到的。请仅输入数字。 只要
   6. 点击**保存**。
4. 【可选】配置应用内事件回传：
   1. 打开**应用内事件回传**开关。
   2. 点击 **添加事件** 以添加 SDK 事件 到列表中。
   3. 请配置以下参数：
      1. **AppsFlyer事件**：名称 事件，接收自 AppsFlyer，来自 集成在您的应用中的 SDK，或来自服务器 到服务器事件。**提示：** 如果您 如果列表中没有显示您想要查看的事件， 确保在具有的设备上激活事件 非有机安装并重新检查。
      2. **回传内容：** 选择其中一个 具体方法如下：没有值和没有收入，值 和没有收入，或值和收入。
5. 点击**保存对接**。

</Accordion>

<div id="agency-setup" />

<Accordion title="代理商的设置方式">

广告主允许代理机构代表他们运行活动，使用 Apple Search Ads。广告主和代理机构都执行设置操作 在 AppsFlyer 中，如本节所述。

**前期准备**

在 AppsFlyer 上配置代理机构之前，代理机构和 广告主必须在 ASA 平台上采取以下步骤：

* **代理：**
  1. 在代理账号中创建单独的Campaign Group。
  2. 邀请广告主作为活动组经理或 通过链接账户角色连接他们的应用商店 连接账户
* **广告主：** 在收到邀请后， 链接账户，广告主必须将活动组链接到 其 App Store Connect 账户。

请参阅 ASA 文档中的 <Anchor target="_blank" href="https://searchads.apple.com/help/get-started/0012-link-app-store-connect-accounts">如何将客户的 App Store Connect 账户链接到代理账户。</Anchor>

**Apple Search Ads Campaign Group**

* 代理活动和广告主活动必须是单独的 Apple 搜索广告 ID 活动组。
* 请勿在Campaign Group名称中使用特殊则符或空格。
* 当您使用 Apple 登录时，ASA 活动组的授权 不是累积的。这意味着当您集成一个新应用时， 之前选择的活动组的授权将被撤销，除非再次选择。 您需要选择有限访问 和每个相关的活动 组（与您想要为广告主连接的应用相关）。 转到 集成 标签，打开

<div id="advertiser-actions" />

#### **广告主需要完成的操作**

**前期准备**：

<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#代理权限">为代理开放权限</Anchor>。

**请按以下步骤启用ASA归因：**

1. 从AppsFlyer后台的侧边栏中选择 协作： 活跃对接
2. 选择**Apple Search Ads**。
3. [可选] 如果您想归因于在重新归因窗口期间重新安装应用的用户，请打开 启用渠道
4. 从侧边菜单中，选择 协作 > 当一个代理与 Apple 搜索广告营销合作伙伴合作时， 重装激活归因
5. 点击**保存**。

<div id="note-3" />

<div id="agency-actions" />

#### **代理需要完成的操作**

1. **从Apple Search Ads后台**随单赠送 campaign\_group\_id使用以下屏幕截图作为指南 以定位 ID。请仅复制数字部分。 ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
2. 在AppsFlyer选择相关应用。
3. 该代理必须在两个中配置相同的活动组 ID 活跃对接
4. 选择**Apple Search Ads**。
5. 输入**Apple Search Ads Campaign ID**参数。 请注意：请仅输入数字，切勿输入其他字符。
6. 点击**保存**。

> 📘 **注意**
>
> Apple 搜索广告配置页面和营销合作伙伴 之间。 配置页面。

<div id="note-4" />

<div id="cost-clicks-and-impressions-data" />

### 成本、点击和展示数据

如果您启用成本 API，AppsFlyer 将接收成本, 点击， 以及通过 API 从 ASA 接收的展示数据。 请参阅 <Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">广告网络成本集成表</Anchor> 以获取 其中列出了所有的适配维度、指标和 **请注意**： 您需要购买ROI360才能获得成本数据。 没有 ROI360，仅 接收点击和展示数据。

**Cost API的启用方式如下**：

* 请完成<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">对接指南中的操作</Anchor>。 确保在提示您登录 Apple Search Ads 时 在 **选择权限** 中选择其中一个 具体方法如下：
  * **Account Read and Write（账户读写权限）**
  * **Account Read Only（账户只读权限）**  
     **请注意**：如果您选择有限访问和 特定的广告系列组，您可能会遇到数据错误。

<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">您可以在成本（和广告收入）对接状态面板或ASA的对接面板中查看Cost API的状态</Anchor> 以及上一次AppsFlyer拉取到 匹配成本数据 单个广告网络仪表板。

> 📘 **注意**
>
> Apple Search Ads 成本数据在 SKAN 仪表板或 SKAN Pull API 中不可用，因为 SKAN 回传不包括广告系列级别的数据。 但是，成本数据在 SSOT 报告中可用，这些报告将 SKAN 安装数据与通过我们的经典 Apple Search Ads 集成检索的成本信息结合在一起。

</Accordion>

<div id="disable-agencies-and-marketing-partners" />

<Accordion title="如何停用代理和营销合作伙伴">

**如需停止记录由代理和营销合作伙伴带来的ASA激活归因，请完成以下操作：**

1. 从AppsFlyer后台的侧边栏中选择 协作： 活跃对接
2. 根据实际情况选择相关的代理或营销合作伙伴。
3. 删除以下内容的 **Apple Search Ads 广告系列组 ID 字段。**
4. 点击**保存对接**。

</Accordion>

<div id="before-september-1-2026" />

<div id="after-september-1-2026" />

<div id="additional-information" />

## 其他相关信息

<div id="asa-attribution" />

<Accordion title="ASA归因">

Apple Search Ads是独立于SKAdNetwork运作的，且无论用户的ATT授权状态如何，ASA都能对其进行确定性归因。也就是说，对于归因到ASA的用户，AF的<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">LTV归因模型</Anchor>能为您提供完整的一系列功能和衡量数据。

ASA的归因不依赖IDFA，而是通过来自设备的token完成（确定性归因），且在不同的ATT授权情况下有所不同：

| **ATT授权** | **可用的点击/展示时间** | **点击/展示回溯窗口** | **说明** |
| --- | --- | --- | --- |
| 是 | 是 | 由广告主设置 | 使用AppsFlyer末次点击归因原则 |
| 否 | 否 | 点击：30天  <br />（由ASA设置）  <br />展示次数24小时 | 未提供点击或展示时间。确定性匹配优先 |

</Accordion>

<div id="discrepancies" />

<Accordion title="数据差异">

由于AppsFlyer和Apple Search Ads使用的归因逻辑不同，因此两个平台之间会有数据差异。<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#归因">Apple Search Ads</Anchor>作为一个SRN，会通过API上报新增激活。

**Apple Search Ads通过API将数据上报给AppsFlyer。**

* 广告系列是按国家/地区汇总的。
* 如果某个广告系列的展示次数少于100次，则不会上报其展示、点击或分国家/地区成本数据。
* 在AppsFlyer中按照Geo进行分组时，不会显示数据不可用的Geo，并且不可用的数据总数将显示在N/A下。

<div id="retargeting-related-discrepancies" />

### 再营销相关的数据差异

除了衡量拉新广告以外，AppsFlyer还提供再营销归因机制，可让广告主衡量并分析再营销投放。

下图说明了投放ASA再营销广告时产生数据差异的原因（与再营销控件的设置无关）。

**再营销启用时**

[![ASA R Enabled2.jpg](https://files.readme.io/0d26cc4844aa97adb793a266cb2a51961a1345e71a24eec305fcc16539d86027-31197524086801.jpg)](https://files.readme.io/0d26cc4844aa97adb793a266cb2a51961a1345e71a24eec305fcc16539d86027-31197524086801.jpg)

**再营销停用时**

[![ASA_R_Disabled.png](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)

<div id="20260901" />

<div id="h_01M0YZYCC5S0E3HA296KAA0SDZ" />

<div id="missing-conversion-payload-for-gender-and-age-targeted-users" />

<div id="preregistration-click-and-impression-lookback-window-discrepancy" />

<div id="see-also" />

<div id="before-september-1-2026-1" />

<div id="after-september-1-2026-1" />

<div id="additional-reasons-for-discrepancies" />

### 其他可能产生数据差异的原因

下表列出了数据差异的主要原因

| 数据差异 | Apple Search Ads | AppsFlyer |
| --- | --- | --- |
| <span id="differences-related-to-appsflyer-sdk-versions"></span>与AppsFlyer SDK版本有关的差异 | 转化衡量与AppsFlyer SDK的版本无关 | AdsServices需要V6.1.3+的SDK才能正确归因。 |
| <span id="limit-ad-tracking-lat-and-att"></span>LAT（限制广告跟踪）和ATT | 总是统计转化。<br /><br />如果您的广告有年龄和性别限制，则投放时会屏蔽掉启用LAT的用户。<br /><br />18岁以下的Apple用户默认启用LAT。 | LAT用户的转化会归因到自然量。<br /><br />如果已接入AdServices且用户安装了iOS14.3+，则可对拒绝授权的用户进行正确归因。 |
| <span id="counting-users"></span>统计用户数 | 根据下载统计用户数 | 根据首次应用启动统计用户数 |
| <span id="reinstall-a-user-after-installing-the-app-deletes-it-clicks-on-a-search-ad-then-installs-the-app-again"></span>重装激活：用户下载某应用后将其卸载，然后在点击某则搜索广告后重新下载该应用 | 计为一次转化（激活） | <ul><li>如果有IDFA：AppsFlyer可识别出重装激活，但出于UA的目的不统计这类激活。请注意：再营销开启时，重装激活会记录为再营销激活（即再归因）。</li><li>如果没有IDFA：AppsFlyer可以通过IDFV来区分新增激活和重装激活。<ol><li>如果用户设备上安装了同一个广告主的其他应用，AppsFlyer会给ASA记录一次再归因。</li><li>如果没有其他应用，则AppsFlyer会给ASA记录一次新增激活。</li></ol></li></ul> |
| <span id="click-lookback-window"></span>点击回溯窗口 | 30天固定窗口期 | 对于没有点击时间的AdServices响应，点击回溯窗口是固定的（30天）。 |
| <span id="impression-lookback-window"></span>展示回溯窗口 | 固定 24 小时窗口 | 对于没有展示时间的 AdServices 响应，展示回溯窗口固定为 24 小时窗口。 |
| <span id="winning-click"></span>获得归因的点击 | 只要用户与广告互动且下载了应用，就总是归因给ASA | 比照多个广告平台的数据，按末次点击原则归因 |
| <span id="install-time"></span>激活时间 | 应用下载时间 | 应用首次打开时间 |
| <span id="time-zone"></span>时区 | 应用商店的本地时区 | UTC或AppsFlyer后台应用配置中的指定时区 |
| <span id="conversion-data"></span>转化数据 | ASA带来的新增激活更新到AppsFlyer后台可能会有5秒钟的延时 | 在5秒之内完成归因，归因完成时转化数据API立即响应。如果未接收到任何数据，则表示该次响应为自然转化 |
| <span id="cost-data"></span>成本数据 | 上报所有关键词的成本数据 | 群组面板或群组API中不上报包含大写字母的成本数据 |
| <span id="geo-locations"></span>地理位置 | Apple Search Ads允许广告主根据国家和地区来进行定向投放，Apple Search Ads支持数量有限的 [**国家**](https://searchads.Apple.com/storefronts/) 。 | AppsFlyer根据IP地址来识别用户的准确地理位置，因此可上报Apple Search Ads中不可用的地理位置信息。<br /><br />请注意：用户从自己所处国家的应用商店下载并激活应用时，AppsFlyer上报的地理位置数据与ASA一致。 |

</Accordion>

<div id="tips" />

<Accordion title="提示">

您在投放ASA广告时可以收集到有价值的营销数据，帮助您提升iOS应用在所有媒体渠道上的拉新效果。

下表所列的建议可提升ASA广告的数据收集效果：

| 提示 | 说明 |
| --- | --- |
| <span id="get-keyword-data"></span>获取关键词数据 | Apple Search Ads与AppsFlyer共享关键词数据。您可以通过原始数据和数据分析工具（数据透视表、留存和群组）查看关键词数据。<br /><br />**请注意：**<ul><li>关键词数据可能会延迟8-12小时，且有些情况下仅包含关键词ID，没有关键词内容。</li><li>如需获取关键词数据，请务必确保您的“成本”开关已打开。关键词数据通过[成本对接](/docs/apple-ads-integration-setup#cost-tab)提供，无需购买ROI360即可获取。</li></ul>如果AppsFlyer后台出现关键词数据缺失，可能是有以下原因造成的：<ul><li>**套餐类型：**  关键词数据由Apple Search Ads与具有Apple Search Ads [高级](https://searchads.Apple.com/advanced/) 套餐的广告客户共享。</li><li>**广告系列类型：** 您可以在Apple搜索广告中配置不同的广告系列关键词匹配类型。根据匹配类型，Apple Search Ads共享以下关键词：<ul><li>**完全匹配**（Exact match）：用户在发起搜索时实际使用的关键词</li><li>**广泛匹配**（Broad match）：Apple在执行搜索时使用的关键词。这些字词与用户实际使用的关键词近似。</li><li>**搜索匹配**（Search match）：Apple**不会**将这些关键词共享给广告主。</li></ul></li></ul>**仅exact match或broad match**搜索广告可上报完整的关键词数据。 |
| <span id="compare-the-quality-of-users-based-on-keyword-data"></span>根据关键词数据比较用户质量 | 关键词也有优劣之分，即使有些关键词的成本相同，但吸引到的用户质量不同。您可以使用留存或<Anchor target="_blank" href="/marketers/zh/docs/pivot-table-user-metrics">数据透视</Anchor>表来找出ROI表现最佳的关键词。 |
| <span id="analyze-keyword-cost"></span>分析关键词成本 | 当ASA关键词广告配置为[exact match（精准匹配）或broad match（广泛匹配）](/docs/apple-ads-integration-setup#get-keyword-data)时，AF后台可提供汇总的关键词成本数据。关键词成本数据具有以下特征：<ul><li>2019年10月13日以后的历史数据可用。</li><li>维度：<ul><li>日期</li><li>广告系列</li><li>广告组</li></ul></li><li>数据分析工具：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/cohort-and-retention-dashboard">群组</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/pivot-table-user-metrics">数据透视表</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor></li></ul></li></ul>**局限性**<ul><li>仅可使用上述维度来对成本数据进行筛选和分组。也就是说，您无法使用地理位置等维度对成本数据进行筛选或分组。</li></ul>**<span id="cohort-example"></span>群组示例**<br />以下示例展示了可用于查看成本和ROI信息的群组设置。<br /><br />**群组设置**<br /><br />[<Image alt="CohortRequest.png" src="https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png" width="327px" />](https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png)<br /><br />**得到的群组数据表**<br /><br />下表展示了总体成本和群组ROI<br /><br />[<Image alt="CohortTable.png" src="https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png" width="429px" />](https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png)<br /><br />**<span id="pivot-example"></span>数据透视表示例**<br /><br />**数据透视表设置**<br /><br />[<Image alt="Pivot_define.png" src="https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png" width="413px" />](https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png)<br /><br />**得到的数据透视表**<br /><br />[<Image alt="Pivot.png" src="https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png" width="439px" />](https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png) |
| <span id="find-the-best-performing-creative-set"></span>找出效果最好的广告组 | ![creative_sets.png](https://files.readme.io/ef8e38d67121283742dcbd1faef11d94a8ea1c612dc258611e72cbf826d7ef8f-31197524112785.png)<br /><br />建议您测试潜在用户对不同素材组反应，并根据转化率选出效果最好的素材组。此外，您也可以根据用户互动的程度来判断素材组质量的优劣。<br /><br />您可以通过这种方式提升ASA乃至iOS上所有潜在用户的转化，因为这些用户都会通过App Store接触到您的应用。对于ASA带来的激活，AppsFlyer会在<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">原始数据</Anchor>的**Ad ID**参数中显示广告组ID，这样您就能对比不同广告组的投放效果了。 |
| <span id="target-redownloaders"></span>定向投放到重新下载的用户 | 将ASA广告定向投放到过去已经使用过您产品的用户，可能会获得最佳的投放效果。<br /><br />如果一个用户卸载了您的应用，之后因为您的ASA再营销广告而又重新下载、安装、激活了该应用，ASA会将其记录为一次Re-Download（重新下载）。如果该次重装激活发生在<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口期</Anchor>内，那么AppsFlyer将其记录为再归因。如在窗口期外，则记录为新增激活。<br /><br />![ASACGroupID.png](https://files.readme.io/ebdc380f2abc3e9a3b134cd258d90ae32f75b3ee4d9eadde39adbc728daae523-31197514645265.png) |

</Accordion>

<div id="asa-change-log" />

<Accordion title="ASA对接变更日志">

| 生效日期 | 更新/变更 |
| --- | --- |
| <span id="20230207"></span>2023-02-07 | 无论您使用哪一种套餐，`Campaign name`（广告系列名称）、`Adset name`（广告组名称）和`Keywords`（关键词）这三个扩充的归因参数仅在成本对接启用时可用。  <br />**也就是说，如果您想要在面板和原始数据报告中看到广告系列名称、广告组名称或关键词，必须在相关渠道对接页面的成本选项卡中打开成本对接的开关。** |
| <span id="20220216"></span>2022-02-16 | 在ASA对接配置页面启用Cost API后，即可通过Cost API拉取关键词成本数据。请注意：无论广告主订购了何种套餐，都可使用该API。 |
| <span id="20210407"></span>2021-04-07 | Apple Search Ads对接：Apple Search Ads是独立于SKAdNetwork运作的，能对用户进行确定性归因。也就是说，对于归因到ASA的用户，AF的<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">LTV归因模型</Anchor>能为您提供完整的一系列功能和衡量数据。 |
| <span id="20210307"></span>2021-03-07 | Apple Search Ads推出Campaign Management API V4.0。该API用于成本及其他投放相关数据，对归因没有影响。我们正在逐步采用这个新API的过程中，广告主侧无需进行任何操作。 |
| <span id="20210215"></span>2021-02-15 | 此后若启用ASA [Cost API](/docs/apple-ads-integration-setup#cost-tab)，可填充广告系列名称和广告组名称字段。无论广告主订购了何种套餐，都可使用该API。 |

ASA的对接更新及变更

</Accordion>

<div id="availability-of-apple-search-ads-campaign-parameters" />

<Accordion title="Apple Search Ads的广告参数可用性">

下表列出了原始数据报告和面板中的归因参数可用性。

| 原始数据报告参数 | 可用性 |
| --- | --- |
| Campaign name（广告系列名称） | 必须在ASA对接配置页面中启用[Cost](/docs/apple-ads-integration-setup#cost-tab) API后才能看到该参数。无论广告主订购了何种套餐，都可使用该API。 |
| Campaign ID | 总是可用 |
| Adset name（广告组名称） | 必须在ASA对接配置页面中启用[Cost](/docs/apple-ads-integration-setup#cost-tab) API后才能看到该参数。无论广告主订购了何种套餐，都可使用该API。 |
| 广告组ID | 总是可用 |
| Ad | 目前不可用 |
| 广告ID | 该参数仅在同时符合以下两个条件时可用：<ul><li>用户的操作系统为iOS 15.2及以上</li><li>相关广告使用了<Anchor target="_blank" href="https://developer.apple.com/app-store/product-page/">Custom Product Pages</Anchor>（自定义产品页），且其广告系列投放在以下任一广告位：<ul><li>`Today tab`</li><li>`Search results`</li></ul></li></ul> |
| Keywords | 必须在ASA对接配置页面中启用[Cost](/docs/apple-ads-integration-setup#cost-tab) API后才能看到该参数。无论广告主订购了何种套餐，都可使用该API。 |
| Keyword ID | 该参数可通过原始数据报告获取。如果您使用Data Locker、Push API和数据导出页，需要在其中手动选择该字段。对于Pull API，则需在`调用`时在`&additional_fields`参数中添加<Anchor target="_blank" href="/marketers/zh/docs/pull-api-raw-data#additional-fields">keyword\_id</Anchor>。 |
| Keyword Match Type（关键词匹配类型） | 目前不可用 |

</Accordion>

<div id="impact-of-aggregated-advanced-privacy" />

<Accordion title="汇总层级高级隐私保护（AAP）的影响">

从iOS 14开始，IDFA的可用性由[ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/)（即ATT）控制。而对于来自ASA的激活，其用户层级归因数据由ASA控制。因此，对于来自ASA的激活，其用户层级数据的可用性不受<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">AAP</Anchor>（汇总层级的高级隐私保护）的影响。

| **ATT授权状态** | **可用的点击/展示时间** | **点击/展示回溯窗口** | **说明** | **可用数据** | **IDFA是否可用** |
| --- | --- | --- | --- | --- | --- |
| 同意授权 | 是 | 由广告主设置 | 使用AppsFlyer末次点击归因原则 | *用户级别归因数据 | 是 |
| 拒绝授权 | 否 | 点击：30天  <br />（由ASA设置）<br /><br />展示：24小时 | 确定性匹配优先 | 用户级别的归因数据，不带点击/展示时间。 | 否 |

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">汇总层级的高级隐私保护（AAP）框架</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">回溯窗口详解</Anchor>

<div data-zendesk-anchors="h_01J3WQNHJZSW1MX8SWXTNX8JKD=%E6%B3%A8%E6%84%8F set-up-asa-integration=asa%E5%AF%B9%E6%8E%A5%E8%AE%BE%E7%BD%AE%E6%8C%87%E5%8D%97 h_01HDPCGMP2CY4B37VM3AT2P114=asa%E5%AF%B9%E6%8E%A5%E8%AE%BE%E7%BD%AE%E6%8C%87%E5%8D%97 h_01HDPCGMP35S325269JETX1EJW=get-started h_01HDPCGMP383Y223E1YXF60C8S=%E6%B3%A8%E6%84%8F-1 h_01HDPCGMP3JC93JWHM2SM8EVZA=integration h_01JP51C2KK0B7PQAT6NB8ANK3B=cost-tab h_01HDPCGMP3XGYXVZZJ8SGDK3G2=%E6%B3%A8%E6%84%8F-2 h_01HDPCGMP3KXMKSHN0GFD6MAFG=permissions-tab set-up-agencies-and-asa-marketing-partners=%E8%AE%BE%E7%BD%AE%E4%BB%A3%E7%90%86%E5%92%8Casa%E8%90%A5%E9%94%80%E4%BC%99%E4%BC%B4 h_01HDPCGMP3D96BG496G7H97YWP=%E8%AE%BE%E7%BD%AE%E4%BB%A3%E7%90%86%E5%92%8Casa%E8%90%A5%E9%94%80%E4%BC%99%E4%BC%B4 h_01HDPCGMP3EBHM0CQXKP05SG9F=principles agency-vs-marketing-partner=%E4%BB%A3%E7%90%86%E5%95%86%E4%B8%8E%E8%90%A5%E9%94%80%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4%E5%AF%B9%E6%AF%94%E8%A1%A8 h_01HDPCGMP3YGJEA942DF2YC9P1=%E4%BB%A3%E7%90%86%E5%95%86%E4%B8%8E%E8%90%A5%E9%94%80%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4%E5%AF%B9%E6%AF%94%E8%A1%A8 configuring-agencies-and-marketing-partners=%E5%A6%82%E4%BD%95%E9%85%8D%E7%BD%AE%E4%BB%A3%E7%90%86%E5%95%86%E5%92%8C%E8%90%A5%E9%94%80%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4 h_01HDPCGMP3NQQ76SC32SEC8TS4=%E5%A6%82%E4%BD%95%E9%85%8D%E7%BD%AE%E4%BB%A3%E7%90%86%E5%95%86%E5%92%8C%E8%90%A5%E9%94%80%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4 configuration-steps-checklist=%E9%85%8D%E7%BD%AE%E6%93%8D%E4%BD%9C%E6%B8%85%E5%8D%95 h_01HDPCGMP39HE117X4MP25M77W=%E9%85%8D%E7%BD%AE%E6%93%8D%E4%BD%9C%E6%B8%85%E5%8D%95 h_01HDPCGMP3BT4YJWJ2G8X76NSE=marketing-partner-setup h_01HDPCGMP3X6B4RYF289WY49P7=agency-setup advertiser-actions=%E5%B9%BF%E5%91%8A%E4%B8%BB%E9%9C%80%E8%A6%81%E5%AE%8C%E6%88%90%E7%9A%84%E6%93%8D%E4%BD%9C h_01HDPCGMP3S3PHHH3F6KZE3SEV=%E5%B9%BF%E5%91%8A%E4%B8%BB%E9%9C%80%E8%A6%81%E5%AE%8C%E6%88%90%E7%9A%84%E6%93%8D%E4%BD%9C agency-actions=%E4%BB%A3%E7%90%86%E9%9C%80%E8%A6%81%E5%AE%8C%E6%88%90%E7%9A%84%E6%93%8D%E4%BD%9C h_01HDPCGMP3MK61YRMCQA2KA5X2=%E4%BB%A3%E7%90%86%E9%9C%80%E8%A6%81%E5%AE%8C%E6%88%90%E7%9A%84%E6%93%8D%E4%BD%9C h_01HDPCGMP3E7PZB8FDG4XN79JA=%E6%B3%A8%E6%84%8F-3 cost-clicks-and-impressions-data=%E6%88%90%E6%9C%AC%E7%82%B9%E5%87%BB%E5%92%8C%E5%B1%95%E7%A4%BA%E6%95%B0%E6%8D%AE h_01HDPCGMP3AVYYK2X03RF057FN=%E6%88%90%E6%9C%AC%E7%82%B9%E5%87%BB%E5%92%8C%E5%B1%95%E7%A4%BA%E6%95%B0%E6%8D%AE h_01JYM0FHV098KXW5RAWW3N916W=%E6%B3%A8%E6%84%8F-4 h_01HDPCGMP3113BYD1GPJM7XBQH=disable-agencies-and-marketing-partners additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HDPCGMP3BXVASH2YJ9G8AS2C=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HDPCGMP31QFVN1SWBCABJ65K=asa-attribution h_01HDPCGMP4DCKH898AEWAY6N01=discrepancies retargeting-related-discrepancies=%E5%86%8D%E8%90%A5%E9%94%80%E7%9B%B8%E5%85%B3%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 h_01HDPCGMP4Z9M3QR6QGRR7A8BM=%E5%86%8D%E8%90%A5%E9%94%80%E7%9B%B8%E5%85%B3%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 additional-reasons-for-discrepancies=%E5%85%B6%E4%BB%96%E5%8F%AF%E8%83%BD%E4%BA%A7%E7%94%9F%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82%E7%9A%84%E5%8E%9F%E5%9B%A0 h_01HDPCGMP4QJ3HYEP7EAYMHRQQ=%E5%85%B6%E4%BB%96%E5%8F%AF%E8%83%BD%E4%BA%A7%E7%94%9F%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82%E7%9A%84%E5%8E%9F%E5%9B%A0 h_01HDPCGMP4A8NAD8SYD191YJYR=tips h_01HDPCGMP4HNS84AVWH7J8H7YA=%E5%85%B6%E4%BB%96%E5%8F%AF%E8%83%BD%E4%BA%A7%E7%94%9F%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82%E7%9A%84%E5%8E%9F%E5%9B%A0 h_01HDPCGMP4MF9FBP4WDRHVZ4BR=cohort-example h_01HDPCGMP4EFMZ4FHZ8WBWW9R2=pivot-example h_01HDPCGMP4XKB75F6R7DDWDHPB=asa-change-log h_01HDPCGMP40MW37BFT8A096PNG=availability-of-apple-search-ads-campaign-parameters h_01HDPCGMP48M04SDA4FGYW6XNQ=impact-of-aggregated-advanced-privacy h_01HDPD3C1T4ZXXZ2RE0GSXPZP3=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
