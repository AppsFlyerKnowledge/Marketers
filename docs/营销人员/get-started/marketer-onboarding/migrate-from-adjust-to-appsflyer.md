---
title: 从 Adjust 迁移至 AppsFlyer
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2024-12-02T10:01:48Z'
  edited_at: '2026-10-22T08:49:16Z'
  id: 30563700129297
  locale: zh-cn
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/zh-cn/articles/30563700129297
---
> **内容概要：** 规划从 Adjust 迁移至 AppsFlyer 的流程。了解如何在迁移期间避免重复收费、数据重复和数据丢失。

<Image alt="" src="https://files.readme.io/cc012894dd05255c0b7fa448b1c95d925d556ddb43dc461086bb71e9279da90d-30633481029137.png" width="1765px" />

## 迁移至 AppsFlyer 概述

迁移至 AppsFlyer，您将获得全面、可靠的归因与营销分析平台，实现顺畅的迁移过渡。 AppsFlyer 提供安全、公正的解决方案，以及一整套先进工具，帮助品牌应对行业变化。凭借遍布全球的客户支持团队，以及对产品持续优化的专注，AppsFlyer 致力于为企业提供所需的工具和洞察，助力业务增长并灵活应对变化。

#### 对比 AppsFlyer 与 Adjust 的衡量结果

在规划迁移时，您可能希望针对相同的媒体渠道和广告活动，对比 AppsFlyer 与 Adjust 的归因衡量结果。但并非所有媒体渠道都支持同时使用多个移动归因平台（MMP）进行衡量。即使支持，也可能存在一些限制和挑战，以避免归因结果出现差异。详情请参阅 <Anchor target="_blank" href="/marketers/zh/docs/measuring-attribution-with-multiple-mmps">使用多个 MMP 进行归因衡量</Anchor>。

## 迁移任务

[![](https://files.readme.io/7deffffc032dce24c30b5b73ae09c083a227ac6f4ec13be224bb7f7fb5b7042f-30642410251793.png)](https://files.readme.io/7deffffc032dce24c30b5b73ae09c083a227ac6f4ec13be224bb7f7fb5b7042f-30642410251793.png)下表列出了迁移所需的主要步骤。如需查看各项常规任务的详细说明并记录进度，请下载 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQqbJIkE7kD87uSm7MH7zfkPN1VLuBaeotTEHAID2pYFVWM_LuQIA2AE2-8fVnXH-DrbXUQCs2iaiDe/pub?output=xlsx">此 Excel 表格</Anchor>。

这些任务可以并行开展，也就是说，营销人员、开发人员和数据工程师大多可以同时执行各自负责的任务。请注意，我们建议您：

* 在发布集成了 AppsFlyer SDK 的新版 App 之前，完成所有迁移任务。
* 在迁移设备 ID 之前，暂停现有的营销活动。

<table><thead><tr><th>步骤</th><th>负责人</th><th>预计耗时</th><th>备注</th></tr></thead><tbody><tr><td>1. 创建 AppsFlyer 账户</td><td>营销人员 / AppsFlyer 面板用户</td><td>2 小时</td><td> </td></tr><tr><td>2. 在 AppsFlyer 中添加 App</td><td>营销人员 / AppsFlyer 面板用户</td><td>2 小时</td><td> </td></tr><tr><td>3. 对接 SDK</td><td>App 开发人员</td><td>1 天，另加 1 周进行测试和迭代</td><td><ul><li> <strong>建议</strong>：先在预发布版本的 App 中集成 AppsFlyer SDK 并进行测试。</li><li>完成所有其他任务后，再将更新后的 App 发布至应用商店。</li></ul></td></tr><tr><td>4. 迁移设备（可选）</td><td>数据工程师</td><td>1–2 周</td><td rowspan="2"><ul><li>建议考虑在迁移前暂停现有广告活动，并在 App 更新版本发布后重新启动。 </li><li>建议在最终迁移日期再次执行设备迁移，以确保数据覆盖完整。 </li></ul></td></tr><tr><td>5. 迁移营销活动</td><td>营销人员 / 用户获取（UA）经理</td><td>每个媒体渠道 1–3 天</td></tr><tr><td>6. 设置数据报告</td><td>数据工程师</td><td>3–6 周</td><td> </td></tr></tbody></table>

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="步骤 1. 创建 AppsFlyer 账户">

**创建 AppsFlyer 账户：**

1. <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">创建 AppsFlyer 账户</Anchor>。
2. <Anchor target="_blank" href="/marketers/zh/docs/user-management">添加账户用户，并为其分配相应权限</Anchor>。

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="步骤 2. 添加您的 App">

**在 AppsFlyer 中添加您的 App：**

1. 在 AppsFlyer 中<Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer">添加您的 App</Anchor>。
2. [可选] 将默认的 90 天<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口期</Anchor>调整为符合您对活跃用户定义的时长。
3. 在 AppsFlyer 的 App 接入向导中，准备并向您的开发人员发送一封邮件，说明完成 SDK 对接及应用内事件映射所需执行的操作。

</Accordion>

<div id="step-3-integrate-the-sdk" />

<Accordion title="步骤 3. 对接 SDK">

对接到 App 中的 AppsFlyer SDK，是 App 与 AppsFlyer 平台之间的桥梁。用于上报 App 安装、打开以及应用内事件等数据。

**对接 AppsFlyer SDK：**

1. 接收营销人员发来的邮件，其中包含完成 SDK 对接及应用内事件映射所需的说明和任务。
2. 按照邮件中的说明，使用 <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?sourceos=android&utm_source=kb&utm_medium=sdk-int-wizard-orvw">AppsFlyer SDK 对接向导</Anchor>将 AppsFlyer SDK 对接到 App 中。
   * 该向导会引导开发人员从安装 SDK 到完成对接测试的全过程。同时也会指导开发人员定义应用内事件，并测试事件是否成功发送至 AppsFlyer。<Anchor target="_blank" href="/marketers/zh/docs/for-ios-and-android-the-sdk-integration-wizard">进一步了解 SDK 对接向导</Anchor>
   * 另请参阅 <Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">Android</Anchor> 和 <Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">iOS</Anchor> SDK 对接的详细开发者指南。
   * 使用 AppsFlyer 的方案，映射您希望记录的应用内事件。  
     此操作可以通过 <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">SDK</Anchor> 或 <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> 完成。
3. 移除 Adjust SDK。  
   您可以立即移除并完全切换至 AppsFlyer，也可以在一段时间内同时保留两个 SDK。下表列出了这两种方案的差异。

| 方案 | 更新版本发布后  <br />的情况 | 影响 |
| --- | --- | --- |
| 移除 Adjust SDK（推荐） | 仅由 AppsFlyer 记录新增安装和已更新用户的数据。  <br />在用户更新 App 之前，Adjust 仍会显示这些用户产生的事件。 | <ul><li>快速过渡。</li><li>不会出现重复归因。</li></ul> |
| 过渡期内保留 Adjust SDK | AppsFlyer 与 Adjust 会同时对新增安装进行归因并上报事件。待后续再移除 Adjust SDK。 | <ul><li>可以进行数据验证。也就是说，您可以借此对比 AppsFlyer 与 Adjust 的数据。</li><li>重复归因可能导致广告平台产生重复计费。具体请参见下文示例。</li><li>工作量更大。</li></ul> |

4. 完成本文中的所有其他迁移任务后，将集成了 AppsFlyer SDK 的版本发布至市场。此后，新用户将由 AppsFlyer 进行归因。   
   **注意**：
   * 请确保在 iOS、Google Play 以及其他相关的安卓第三方应用商店中都更新该 App。
   * 您的安卓 App 可能存在于非官方的 APK 网站中，即便您并不知情（可以通过搜索 App 的包名来确认）。 这类网站更新到最新版本需要一定时间，因此可能会带来安装了不含 AppsFlyer SDK 的旧版本的自然用户。
   * 应用商店中的版本更新推送可能需要几天时间才能完全完成。在此期间安装 App 的用户可能仍会获取到旧版本。

</Accordion>

<div id="step-4-migrate-devices-optional" />

<Accordion title="步骤 4. 迁移设备 —— 可选">

设备迁移是指将现有用户的设备 ID 列表（IDFA、IDFV、GAID）上传至 AppsFlyer 的过程。（如果您没有所需的全部设备 ID，可以联系您的客户成功经理（CSM），让其指导您使用 CUID 完成迁移流程。）请务必在发布包含 AppsFlyer SDK 的新版本 App 之前完成此流程。迁移设备时有两种方式可选：[归因迁移](/docs/migrate-from-adjust-to-appsflyer#attributed-migration)或[非归因迁移](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration)。

设备迁移可以解决与已下载 App 并由 Adjust 完成归因的现有用户相关的数据问题。例如 SRN 重复计费问题：如果某用户最初由 Adjust 归因到某个自归因网络（SRN），且该用户仍处于回溯窗口期内，那么在切换到 AppsFlyer 后，该 SRN 可能会再次认领这名用户，从而造成重复计费。

> 📄 **示例**
>
> * 某新用户在 Facebook 应用上点击了一则广告，并于 6 月 15 日安装了您的 App。
> * 6 月 24 日，该用户将 App 更新至集成了 AppsFlyer SDK 的版本并打开。对 AppsFlyer 而言，这是一名新用户，需要进行实时归因。
> * AppsFlyer 使用该用户的设备 ID 向 Meta ads 发起查询。由于该用户仍处于 Meta ads 28 天的回溯窗口期内，Meta ads 会对该用户进行自归因。这会导致 App 所有者针对同一用户产生重复计费。

完成设备迁移后，相关数据将按以下方式体现在 AppsFlyer 中：

* **安装** **数据：** 与<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window#reinstall">重新安装</Anchor>类似，已迁移的设备没有安装数据。 AppsFlyer 中不会显示已迁移设备的安装记录。
* **应用内事件和打开（session）数据：** 如果使用[非归因设备迁移方式](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration)，将被记录并显示为自然量；如果使用[归因迁移方式](/docs/migrate-from-adjust-to-appsflyer#attributed-migration)，则会归因到对应的媒体渠道和广告活动。
* **再营销：** 再归因和再互动数据将正常显示。
* **活跃数据：** 正常显示。
* **留存和群组数据：** 已迁移的设备没有安装记录。因此，这些设备不会关联到任何群组，也不会出现在群组和留存报告中。

> 📘 **注意**
>
> 如果 App 在迁移日期起的 180 天内未被打开，所有已迁移的设备数据都会被删除。因此，如果用户在 180 天后才打开 App，系统将记录为一次新增安装。

**迁移设备：**

1. 确定需要迁移的用户群体。您可以迁移所有现有用户（但这可能导致无法从 AppsFlyer 获得准确的再归因数据），也可以只迁移近期安装 App 的用户（但这可能导致对部分安装时间较早的用户产生重复计费）。  
   <strong>我们建议迁移在当前再归因窗口期内活跃的用户。</strong>例如，如果您的 App 再归因窗口期为 90 天，建议迁移过去 90 天内至少打开过一次 App 的用户。
2. [可选] 通知营销人员 / UA 经理，在设备迁移完成之前，暂停现有的营销活动（包括 SRN、非 SRN 广告平台、自有媒体等渠道的活动）。  
   如果您决定不暂停广告活动，请在集成了 AppsFlyer SDK 的新版本 App 发布至应用商店后，尽快迁移来自其他厂商的剩余设备 ID。
3. 根据所选的用户群体，使用[归因](/docs/migrate-from-adjust-to-appsflyer#attributed-migration)或[非归因](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration)迁移结构准备一份 CSV 文件。<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">查看 CSV 示例</Anchor>
4. 将 CSV 文件发送给您的 AppsFlyer 客户成功经理（CSM）。  
   您的 CSM 会将这些设备 ID 迁移至 AppsFlyer。

</Accordion>

<div id="step-5-migrate-campaigns" />

<Accordion title="步骤 5. 迁移营销活动">

将现有的营销活动切换至 AppsFlyer，以启用 AppsFlyer 归因，并避免重复计费和归因数据丢失。

**注意**：您可以选择一次仅迁移少量营销活动。在这种情况下，您可以按媒体渠道（例如广告平台或代理商）、地区或广告系列对要迁移的内容进行分组。

以下各部分将说明针对不同类型的媒体渠道（SRN、非 SRN 广告平台、自有媒体和 SKAN）启用 AppsFlyer 衡量所需的操作。

#### SRN

当移动衡量合作伙伴（MMP）就特定设备的互动情况发起查询时，SRN 会做出回复。如果 AppsFlyer 与 Adjust 就同一设备的同一次安装，向同一个 SRN 发起查询，可能会导致重复计费。

**迁移 SRN 渠道的营销活动：**

* 在 AppsFlyer 中激活并配置相关的 <Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#与appsflyer对接的srn">SRN</Anchor>。

> 📘 **注意**
>
> * SRN 可以同时对接多个 MMP（Meta ads 和 Twitter 除外）。
> * Meta ads 无法对应用内事件进行去重。

#### 非 SRN 广告平台

广告平台的归因链接会记录用户的互动情况，之后用于对转化为实际安装的互动进行归因。

**迁移非 SRN 广告平台渠道的营销活动：**

1. 在 AppsFlyer 中<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">启用</Anchor>相关的广告平台。
2. 为每个广告平台<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">生成 AppsFlyer 归因链接</Anchor>。
3. 将各广告系列中的现有链接替换为 AppsFlyer 归因链接。

#### 自有媒体

自有媒体是指您在以下渠道中使用的归因链接：

* 内容分享
* 网页到 App
* 邮件
* 短信
* 社交媒体发文
* 博客
* 网络社区（如 Quora 等）
* 以及更多……

针对这些渠道，AppsFlyer 使用 <Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink 链接</Anchor>。 OneLink 链接会根据用户的设备类型，将用户引导至相应的应用商店、直接调起 App，或跳转至网页 URL / 落地页。

**将 Adjust 链接转换为 AppsFlyer OneLink 链接：**

* 请联系您的 CSM，根据您目前使用的渠道和工具，协助您将自有媒体链接转换为 OneLink 链接。

#### SKAN

对于 SKAdNetwork（SKAN）归因，只能由一个 SDK 更新转化值。否则，SKAN 数据将失去意义。因此，请确保迁移完成后，只有 AppsFlyer SDK 更新 SKAN 转化值。

<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">了解如何在 AppsFlyer 中设置 SKAN 转化值。</Anchor>

</Accordion>

<div id="step-6-set-up-data-reporting" />

<Accordion title="步骤 6. 设置数据报告">

您可以通过多种方式从 AppsFlyer 获取<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-apis">原始</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/analytics-and-aggregate-reporting-apis">汇总</Anchor>报告数据。请熟悉这些方式，并设置与您相关的方式。

报告方式包括：

* 面板
* 导出报告
* Push API
* Pull API
* Data Locker

在迁移之前，您的系统会按照您在 Adjust 中设置好的报告结构、字段和参数，存储来自 Adjust 的归因数据。为了让 AppsFlyer 正确上报数据，您必须将现有的报告结构调整并映射为 AppsFlyer 的报告结构、字段和参数。

**调整/映射报告结构：**

* 请联系您的 AppsFlyer 客户成功经理（CSM），协助您快速将报告数据结构从 Adjust 调整/迁移至 AppsFlyer。

</Accordion>

## 补充信息

<div id="attributed-migration" />

<Accordion title="归因迁移">

通过此方式迁移至 AppsFlyer 的设备，其应用内事件和打开（session）数据将按照此前归因工具所上报的媒体渠道，以及相关广告平台的数据保留政策进行记录和展示。

#### 归因设备迁移 CSV 文件结构

| 列  <br />名称 | 说明 | 是否必填 | 示例 |
| --- | --- | --- | --- |
| app\_id | 即 AppsFlyer 面板中显示的 App ID | 是 | <ul><li>Android：com.great.app1</li><li>iOS：id123456789</li></ul> |
| platform | 设备平台：ios 或 android | 是 | <ul><li>ios</li><li>android</li></ul> |
| device\_id | <ul><li>Android：gaid 或 android\_id</li><li>iOS：IDFV（如可用，建议优先使用）或 IDFA</li><li>请勿在多行中重复使用相同的设备 ID 与 App ID 组合。如果出现重复，系统将使用文件中最后一次出现的数据。</li></ul> | 是 | <ul><li>**gaid**（小写）：9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**android\_id**（小写）：f35aea8908254891</li><li>**IDFV**（大写）：A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA**（大写）：9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android：advertiserId（也支持 amazon\_aid）、android\_id</li><li>iOS：idfa 或 idfv</li><li>目前尚不支持其他标识符，例如 OAID、IMEI。<br />对于非来自 Google Play 的安卓用户，请使用非归因迁移方式。</li></ul> | 是 | <ul><li>advertiserId</li><li>android\_id</li><li>idfa</li><li>idfv</li></ul> |
| install\_time | 原始 App 安装时间，采用 <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor> UTC 格式：  <br />**yyyy-mm-ddTHH:MM:SS.SSS** | 否 | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>可以是以下任意一种：<ul><li>AppsFlyer 渠道 ID</li><li>自定义媒体渠道（不能是渠道 ID）。</li></ul></li><li>如需获取 AppsFlyer 要求格式的渠道 ID 列表：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">启用所有相关的已对接渠道。</Anchor></li><li>运行 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">获取活跃对接渠道 API</Anchor>，获取所有活跃对接渠道的列表。</li><li>使用 API 返回的 **media\_source\_name** 作为 CSV 中 **media\_source** 字段的值。</li><li>例外情况：<ul><li>对于 Apple Search Ads，请使用 **Apple Search Ads**。</li><li>对于 Twitter，请使用 **twitter**。</li></ul></li></ul></li><li>格式：区分大小写</li></ul> | 是 | 非自然量：facebook\_int、googleadwords\_int<br /><br />自然量：organic |
| integrated\_partner | <ul><li>表示该媒体渠道是否为已对接的渠道。即是否为自然量或自定义媒体渠道。</li><li>格式：区分大小写</li></ul> | 是 | <ul><li>yes</li><li>no（如果 media\_source 为自定义值）</li></ul> |
| campaign | 如需获取更精细的归因详情，请提供原始广告系列名称。<br /><br />格式：字符串 | 否 |  |
| campaign\_id | 如需获取更精细的归因详情，请提供原始广告系列 ID。<br /><br />格式：字符串，不允许包含空格 | 否 |  |

**CSV 文件规则：**

* CSV 文件中可以包含多个 App 的用户设备。
* 请勿在多行中重复使用相同的设备 ID 与 App ID 组合。如果出现重复，系统将使用文件中最后一次出现的数据。
* 必须包含以下所有列标题：app\_id、platform、device\_id、id\_type、install\_time、media\_source、integrated\_partner、campaign、campaign\_id。**注意**：字段的顺序非常重要，必须保持不变。
* 您可以为同一设备同时添加 IDFV 和 IDFA，但二者必须分别位于不同的行中。这些行中除 device\_id 外，其他所有字段的值都应保持一致。
* 每行必须恰好包含 9 个以逗号分隔的字段。
* 非必填字段请留空。
* 文件最多可包含 500 万行。
* 如果有多个文件，请为每个文件设置唯一的名称。
* 请使用 UTF-8 对数据进行编码。
* [可选] 可以使用 ZIP 或 GZIP 压缩文件。

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=0&single=true&output=csv">查看 CSV 示例</Anchor>

</Accordion>

<div id="nonattributed-migration" />

<Accordion title="非归因迁移">

通过此方式迁移至 AppsFlyer 的设备，会被记录为自然用户（但不会显示）。这些设备的应用内事件和打开（session）数据，也会被记录并显示为自然量。

#### 非归因设备迁移 CSV 文件结构

| 方案 | 列 | 适用场景 | 示例 |
| --- | --- | --- | --- |
| 1 | App ID + IDFA/GAID/IDFV | <ul><li>如果您所有的安卓用户都拥有 GAID 标识符。</li><li>仅限 iOS 用户</li></ul> | [![device_migration_file_option_1.png](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png)](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png) |
| 2 | App ID + Device ID + Device ID type | <ul><li>如果您部分安卓用户只有 IMEI 或 Android ID，而没有 GAID（例如第三方应用商店渠道，或安卓版本低于 4.4.2）。</li><li>Android ID 必须为十六进制格式。</li></ul>**注意**：<ul><li>**ID type** 列请使用准确的字符串：advertiserId（也支持 amazon\_aid）、idfa、idfv、android\_id、imei。</li><li>如果您使用 android\_id 或 imei，而 AppsFlyer 之后又获取到了更优的标识符，则可能会记录一次新的归因。</li></ul> | [![device_migration_file_option_2.png](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png)](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png) |

**CSV 文件规则：**

* CSV 文件中可以包含多个 App 的用户设备。
* 每行针对每个 App 只能包含一个设备 ID。
* 根据您所选的文件结构方案，文件列必须按以下顺序设置：
  * 方案 1：app\_id、device\_id
  * 方案 2：app\_id、device\_id、id\_type
* App ID 请使用小写。
* 安卓标识符请使用小写。
* IDFA/IDFV 请使用大写。
* 最多允许 2500 万行。

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">查看 CSV 示例</Anchor>

</Accordion>

<div data-zendesk-anchors="overview=%E8%BF%81%E7%A7%BB%E8%87%B3-appsflyer-%E6%A6%82%E8%BF%B0 01H8EDSTP8N4GZJQ5J609C3DHM=%E8%BF%81%E7%A7%BB%E8%87%B3-appsflyer-%E6%A6%82%E8%BF%B0 compare-measurement-between-appsflyer-and-adjust=%E5%AF%B9%E6%AF%94-appsflyer-%E4%B8%8E-adjust-%E7%9A%84%E8%A1%A1%E9%87%8F%E7%BB%93%E6%9E%9C h_01HQJ10ZFJR43KBYMD9A07CJ99=%E5%AF%B9%E6%AF%94-appsflyer-%E4%B8%8E-adjust-%E7%9A%84%E8%A1%A1%E9%87%8F%E7%BB%93%E6%9E%9C tasks=%E8%BF%81%E7%A7%BB%E4%BB%BB%E5%8A%A1 01H8EDSTP8YGDZBPEY1976JP8C=%E8%BF%81%E7%A7%BB%E4%BB%BB%E5%8A%A1 01JE3EC4C847ZEK769Y9G237KG=step-1-create-an-appsflyer-account 01JE3EC4C9V83D0V46EJK49JZ2=step-2-add-your-app 01JE3EC4CAKY4FQBPPZSJFP5V5=step-3-integrate-the-sdk step-4-migrate-devices%E2%80%94optional=step-4-migrate-devices-optional 01JE3EC4CPT4KAER27C8C0DHH7=step-4-migrate-devices-optional 01H8EDSTP93QJA4XZB6TDWWH1V=%E7%A4%BA%E4%BE%8B 01JA2CAMW3HCHC4B9FX7517FJ6=%E6%B3%A8%E6%84%8F 01JE3EJ5DVXF1VT28ZCGR7SMF3=step-5-migrate-campaigns srns=srn 01JE3EXVNRMA2MFVPSJZ2RMR09=srn 01H8EDSTP9ZGMHSM44BWGF1FJN=%E6%B3%A8%E6%84%8F-1 nonsrn-ad-networks=%E9%9D%9E-srn-%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0 01JE3EXVNTWK4ZJS55WXHFKSMX=%E9%9D%9E-srn-%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0 owned-media=%E8%87%AA%E6%9C%89%E5%AA%92%E4%BD%93 01JE3EXVNTS4FVXN370G1CR8Z9=%E8%87%AA%E6%9C%89%E5%AA%92%E4%BD%93 01JE3EXVP4TSMGSZD4B460RSQA=skan 01JE3F6VXDG9MDCVWN81RSHXVG=step-6-set-up-data-reporting additional-information=%E8%A1%A5%E5%85%85%E4%BF%A1%E6%81%AF 01JE3E5VHV2WCFWABC9FYQW3VG=%E8%A1%A5%E5%85%85%E4%BF%A1%E6%81%AF 01JE3FG6K95QT60C36R88WGDG4=attributed-migration attributed-device-migration-csv-structure=%E5%BD%92%E5%9B%A0%E8%AE%BE%E5%A4%87%E8%BF%81%E7%A7%BB-csv-%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84 01H8EDSTP9HABKEZJXMB84CDDE=%E5%BD%92%E5%9B%A0%E8%AE%BE%E5%A4%87%E8%BF%81%E7%A7%BB-csv-%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84 01JE3FG6MKNJMTHSR5B2ZMQP1K=nonattributed-migration nonattributed-device-migration-csv-file-structure=%E9%9D%9E%E5%BD%92%E5%9B%A0%E8%AE%BE%E5%A4%87%E8%BF%81%E7%A7%BB-csv-%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84 01H8EDSTP9AFDMQS6BPQJY19ZH=%E9%9D%9E%E5%BD%92%E5%9B%A0%E8%AE%BE%E5%A4%87%E8%BF%81%E7%A7%BB-csv-%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84" />
