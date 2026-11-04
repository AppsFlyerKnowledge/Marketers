---
title: 从其他归因平台迁移到 AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2019-07-01T13:11:37Z'
  edited_at: '2026-11-01T08:56:51Z'
  id: 360001923697
  locale: zh-cn
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001923697
---
> **概览：** 规划从其他归因服务商迁移至 AppsFlyer 的流程。了解如何在迁移期间避免重复扣费、数据重复和数据丢失等问题。

![迁移流程](https://files.readme.io/31d67493ae3ae6912b4da3163ebb731a8d58494c3007ef1d08cb7332226d9e81-360017326677.png)

<div id="about-migrating-to-appsflyer-from-other-vendors" />

## 从其他归因平台迁移到 AppsFlyer

从其他归因平台迁移到 AppsFlyer 时需完成以下事项：

* [SDK 对接](/docs/migration-to-appsflyer-from-other-vendors#sdk-对接)
* [设备迁移](/docs/migration-to-appsflyer-from-other-vendors#设备迁移可选)
* [广告投放迁移](/docs/migration-to-appsflyer-from-other-vendors#广告投放迁移)
* [数据报告设置](/docs/migration-to-appsflyer-from-other-vendors#数据报告设置)

您可以同时开展这些任务。不过，我们建议您：但建议您：

* 先完成以上全部流程，然后再上线带有 AppsFlyer SDK 的新版本应用。
* 着手迁移设备 ID 之前，请先暂停现行广告的投放。

<div id="compare-measurement-between-appsflyer-and-other-mmps" />

### 比较 AppsFlyer 与其他 MMP 衡量方式上的差异

考虑从其他移动归因合作伙伴（MMP）迁移至 AppsFlyer 时，广告主可能希望在相同的媒体渠道和广告系列中，对比两个 MMP 的归因衡量结果。但并非所有媒体渠道都支持同时使用多个 MMP 进行衡量。即使支持，也可能存在一些限制和挑战，需要特别注意，以避免归因结果出现差异。详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/measuring-attribution-with-multiple-mmps">《使用多个 MMP 衡量归因》</Anchor>。

<div id="tasks" />

## 迁移流程

下表列出了各项工作的具体内容。如需查看各项常规任务的详细分解并记录进度，请下载<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQqbJIkE7kD87uSm7MH7zfkPN1VLuBaeotTEHAID2pYFVWM_LuQIA2AE2-8fVnXH-DrbXUQCs2iaiDe/pub?output=xlsx">相应的电子表格</Anchor>。

<div id="scope-of-work" />

#### 工作范围

<table><thead><tr><th>事项</th><th>所需操作</th><th>人员</th><th>预计耗时</th><th>备注说明</th></tr></thead><tbody><tr><td>前期准备</td><td><ol><li> <a href="https://www.appsflyer.com/get-started" target="_blank">创建 AppsFlyer 账户</a>。</li><li> 在 AppsFlyer 中<a href="./adding-an-app-to-appsflyer" target="_blank">添加应用</a>。</li><li>［可选］将默认的 90 天<a href="./set-up-re-attribution-window" target="_blank">再归因窗口</a>调整为符合<span>您对活跃用户的定义</span>。 </li></ol></td><td>投放运营人员/使用 AppsFlyer 面板的用户</td><td>2 小时</td><td> </td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#sdk-对接">SDK 对接</a></td><td><ul><li>将 AppsFlyer SDK 接入您的应用中。</li><li>映射 S2S 或 SDK 应用内事件。</li><li>在应用商店中更新应用版本。</li></ul></td><td>应用开发人员</td><td>1-2 周</td><td><ul><li> <strong>建议：</strong>先在预发布版本的应用中对接 AppsFlyer SDK 并进行测试。</li><li>对于已开发完毕的应用，请务必在完成其他所有步骤后，在应用商店中更新该应用。</li></ul></td></tr><tr><td> <a href="./migration-to-appsflyer-from-other-vendors#设备迁移可选">设备迁移</a>（可选）</td><td>迁移设备 ID 可以避免对现有用户进行重复归因。</td><td>数据工程师</td><td>1-2 周</td><td rowspan="2"><ul><li>更新应用版本后，建议您先暂停在投广告，等到设备 ID 信息迁移完毕后再继续投放。</li><li>建议在过渡期的最后一天重复设备迁移流程，以确保覆盖所有设备。 </li></ul></td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#广告投放迁移">广告投放迁移</a></td><td><ul><li>将您使用的广告平台对接到 AppsFlyer</li><li>迁移现有的广告系列：<ul><li>SRN</li><li>非 SRN 广告平台</li><li>自有媒体</li></ul></li></ul></td><td>营销人员/UA 经理</td><td>1-3 周</td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#数据报告设置">数据报告设置</a></td><td><ul><li>将当前的报告结构按照 AppsFlyer 数据结构进行调整/映射。</li><li>做好准备工作，以便接收 AppsFlyer 数据报告。</li></ul></td><td>数据工程师</td><td>2-4 周</td><td> </td></tr></tbody></table>

<div id="sdk-integration" />

### SDK 对接

<div id="sdk-integration::c763138b" />

<Accordion title="SDK 对接">

应用中对接的 AppsFlyer SDK 是应用与 AppsFlyer 平台之间的连接。从而实现应用激活、应用打开、应用内事件等数据的上报。

**如需对接 AppsFlyer SDK**：

1. 将 AppsFlyer SDK 接入相关应用。  
   在应用中对接 AppsFlyer SDK。  
   参阅 <Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">Android</Anchor> 和 <Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">iOS</Anchor> SDK 对接指南。
2. 使用 AppsFlyer 的事件定义，映射需要记录的应用内事件。  
   您可以通过 <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">SDK</Anchor> 或 <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> 完成此操作。您可以通过 <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">SDK</Anchor> 或 <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> 完成此操作。
3. 移除其它归因平台的 SDK。  
   您可以立即移除其他服务商的 SDK，完全切换至 AppsFlyer；也可以在过渡期间同时运行两个 SDK 数周。下表详细介绍了这两种方案。

| 操作 | 发布新版应用后的情况 | 成效提升 |
| --- | --- | --- |
| 删除其它归因工具的 SDK（推荐） | 只有 AppsFlyer 会记录新安装和更新应用的用户。对于尚未更新应用的用户，原服务商仍会显示其产生的事件。 | <ul><li>快速过渡。</li><li>无重复归因。</li></ul> |
| 在过渡期间保留其它归因工具的 SDK | AppsFlyer 和原服务商都会对新安装进行归因并上报事件。之后再移除原服务商的 SDK。 | <ul><li>可以进行数据验证。可以验证数据，即对比 AppsFlyer 与原服务商的数据。</li><li>可能发生重复归因，导致广告平台重复扣费（见下方示例）。具体请参见下文示例。</li><li>工作量更大。</li></ul> |

4. 完成所有其他迁移任务后，请将对接 AppsFlyer SDK 的新版应用发布到应用商店。此后，新用户将由 AppsFlyer 进行归因。   
   **注意**：
   * 请确保在 App Store、Google Play 和其他第三方商店中上线更新后的应用。
   * 安卓应用可能会有非官方的 APK 下载渠道（请使用您的应用包名进行搜索，检查是否存在这种情况）。 您的 Android 应用可能已被上传至一些非官方 APK 网站，即使您对此并不知情（您可以在网上搜索应用的包名，检查是否存在此类情况）。这些网站通常需要一段时间才能更新至最新版本，因此仍可能为您带来自然量用户，而这些用户安装的可能是尚未对接 AppsFlyer SDK 的旧版本应用。
   * 应用商店中的应用更新可能需要几天才能全部完成。在此期间安装应用的用户，仍可能使用旧版本。

</Accordion>

<div id="device-migrationoptional" />

### 设备迁移——可选

<div id="about-device-migration" />

<Accordion title="设备迁移说明">

设备迁移是指将现有用户的设备 ID（IDFA、IDFV、GAID、CUID）列表上传到 AppsFlyer。请务必先完成这个流程，然后再上线带有 AppsFlyer SDK 的新版本应用。设备迁移是指将现有用户的设备 ID 列表（IDFA、IDFV、GAID、CUID）上传至 AppsFlyer 的过程。

设备迁移可以解决现有应用用户的相关数据问题。这些用户之前已经下载应用，并由原归因服务商进行归因。

<div id="example" />

> 📄 **示例**
>
> * 某个新用户在 Facebook 应用上点击了一则广告，然后在 6 月 15 日激活了您的应用。
> * 6 月 24 日，该用户将应用更新为对接 AppsFlyer SDK 的版本，并打开应用。对于 AppsFlyer 而言，这是一名新用户，需要实时进行归因。
> * AppsFlyer 使用该用户的设备 ID 向 Meta ads 发出查询请求。由于该用户仍处于 Meta 广告平台的 28 天回溯窗口期内，Meta 广告平台会再次将该用户归因至自身。从而导致同一用户的双重计费。

设备迁移完毕后，AppsFlyer 中呈现的数据如下：

* **安装数据：** 与<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window#reinstall">重新安装</Anchor>类似，已迁移的设备没有安装数据记录。 AppsFlyer 中不会呈现已迁移设备的激活。
* **应用内事件和会话数据：** 如果采用[非归因迁移方式](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration)，相关数据会记录并显示为自然量；如果采用[归因迁移方式](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration)，则会归因至相应的媒体渠道和广告系列。
* **再营销：** 再归因和再互动数据会正常显示。
* **活跃数据：** 正常显示。
* **留存和同期群数据：** 已迁移的设备没有安装记录。因此不会关联到任何同期群，也不会显示在留存和同期群报告中。

<div id="note" />

> 📘 **说明**
>
> 如果应用在迁移日期后的 180 天内一直未被打开，系统将删除所有已迁移的设备数据。这种情况下，如果用户在 180 天之后打开了应用，AF 就会记录一个新增激活。

</Accordion>

<div id="how-to-migrate-devices" />

<Accordion title="设备迁移方法">

**请按照以下步骤迁移设备：**

1. 确定需要迁移的用户范围。您可以迁移所有现有用户，但这可能导致 AppsFlyer 无法准确获取再归因数据；也可以只迁移近期安装应用的用户，但这可能导致部分安装时间较早的用户被重复扣费。<strong>我们建议的迁移范围是当前再归因窗口期内的活跃用户。</strong>举例来说，如果相关应用的再归因窗口期为 90 天，则推荐的迁移范围是在过去 90 天内打开过该应用的用户。
2. ［可选］通知营销人员或用户获取（UA）经理，暂停现有广告系列，包括 SRN、非 SRN 广告平台和自有媒体广告系列，直至设备迁移完成。如果决定不暂停广告系列，请在对接 AppsFlyer SDK 的新版应用发布至应用商店后，尽快迁移原服务商中剩余的设备 ID。
3. 根据所选用户范围，按照归因迁移或非归因迁移对应的文件结构准备 CSV 文件。<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">请参阅 CSV 示例</Anchor>
4. 将您准备好的 CSV 文件发给 AppsFlyer 客户成功经理（CSM）。  
   您的 CSM 将负责把设备 ID 迁移至 AppsFlyer。

</Accordion>

<div id="attributed-migration" />

<Accordion title="归因迁移">

对于通过这种方法迁移到 AppsFlyer 的设备，AppsFlyer 会按照之前的归因工具所上报的媒体渠道以及相关广告平台的数据保留政策，记录并呈现其应用内事件和应用打开（sessions）数据，

<div id="note-1" />

<div id="attributed-device-migration-csv-structure" />

#### 用于归因设备迁移的 CSV 文件结构

| 列名称 | 描述 | 是否必须配置 | 实例 |
| --- | --- | --- | --- |
| app\_id | 即 AppsFlyer 面板中显示的 App ID | 收集 | <ul><li>Android：com.great.app1</li><li>iOS：id123456789</li></ul> |
| platform | 设备平台：iOS 或安卓 | 收集 | <ul><li>iOS</li><li>Android</li></ul> |
| device\_id | <ul><li>Android：gaid、android\_id</li><li>iOS：IDFV（可用时建议作为首选）或 IDFA</li><li>不得在多行中重复使用相同的设备 ID 与应用 ID 组合。如果发生重复，系统将采用文件中最后一次出现的记录。</li></ul> | 收集 | <ul><li>**gaid**（小写）：9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**android\_id**（小写）：f35aea8908254891</li><li>**IDFV**（大写）：A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA**（大写）：9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android：<ul><li>advertiserId</li><li>android\_id</li><li>amazon\_aid</li></ul></li><li>iOS：<ul><li>idfa</li><li>idfv</li></ul></li><li>目前不支持 OAID、IMEI 等其他标识符。<br />对于未通过 Google Play 获取的 Android 用户，请使用非归因迁移方式。<br />对于非 Google Play 的安卓用户，请使用非归因迁移。</li></ul>**备注**<br />`android_id` 默认不会由 AppsFlyer SDK 收集。如果使用 `android_id` 作为标识符，请确保在<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">SDK 对接过程中收集该字段</Anchor>。 | 收集 | <ul><li>advertiserId</li><li>android\_id</li><li>idfa</li><li>idfv</li><li>amazon\_aid（小写）：df07c7dc-cea7-4a89-b328-810ff5acb15d</li></ul> |
| install\_time | 应用最初的安装时间，采用 <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor> UTC 格式：  <br />**yyyy-mm-ddTHH:MM:SS.SSS** | No（否） | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>可以是以下任意一种：<ul><li>AppsFlyer 渠道 ID</li><li>自定义媒体渠道（不能使用对接渠道 ID）</li></ul></li><li>渠道 ID 是 AppsFlyer 中的必填项，您可以按以下方式获取其列表：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">启用所有相关的对接渠道。</Anchor></li><li>调用 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">Get active integrations API</Anchor>，获取所有启用中的对接列表。</li><li>将 API 返回的**media\_source\_name** 作为 CSV 文件中的 **media\_source** 值。</li><li>例外情况：<ul><li>Apple Search Ads 使用 **Apple Search Ads**。</li><li>Twitter 使用 **twitter**。</li></ul></li></ul></li><li>注意：参数值区分大小写</li></ul> | 收集 | 非自然：facebook\_int、googleadwords\_int<br /><br />自然：organic |
| integrated\_partner | <ul><li>表示该媒体渠道是否为已对接的合作伙伴。对于自然量或自定义媒体渠道，应根据实际情况填写。</li><li>注意：参数值区分大小写</li></ul> | 收集 | <ul><li>yes</li><li>no（如果是自定义的 media\_source）</li></ul> |
| campaign | 如需获取更为详细的归因信息，请提供原始广告系列名称。<br /><br />格式：字符串 | No（否） |  |
| campaign\_id | 如需获取更详细的归因信息，请提供原始的广告系列 ID。<br /><br />格式：不含空格的字符串 | No（否） |  |

**CSV 文件规则：**

* CSV 文件中可以包含多个应用的用户设备。
* 不得在多行中重复使用相同的设备 ID 与应用 ID 组合。如果出现重复，AppsFlyer 会取用最后一次出现的数据。
* 必须包含所有列标题：app\_id、platform、device\_id、id\_type、install\_time、media\_source、integrated\_partner、campaign、campaign\_id。**注意**：字段顺序很重要，必须保持不变。
* 同一设备可以同时填写 IDFV 和 IDFA，但必须分别放在不同的行中。除 device\_id 外，这些行中的其他字段都必须相同。
* 每行必须包含 9 个字段，每个字段之间以逗号区隔。
* 将非必填字段留空（空值）
* 文件最多可以包含 500 万行。
* 如果您有多个文件，请确保各文件的名称之间没有重复。
* 必须使用 UTF-8 对数据进行编码。
* 【可选】可以使用 ZIP 或 GZIP 来压缩文件。

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=0&single=true&output=csv">查看 CSV 文件范例</Anchor>

</Accordion>

<div id="nonattributed-migration" />

<Accordion title="非归因迁移">

采用此方式迁移至 AppsFlyer 的设备会被记录为自然量用户，但不会显示在相关界面中。这些设备上的应用内事件和应用打开（sessions）也会被记录为自然量，并显示在面板中。

<div id="non-attributed-device-migration-csv-file-structure" />

#### 用于非归因设备迁移的 CSV 文件结构

| 操作 | D. Columns | 使用场景 | 示例 |
| --- | --- | --- | --- |
| 1 | App ID + IDFA/GAID | <ul><li>如果您所有的安卓用户都有 GAID。</li><li>如果您的用户仅使用 iOS</li></ul> | [![device_migration_file_option_1.png](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png)](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png) |
| 2 | App ID + Device ID + Device ID type | <ul><li>如果您的部分安卓用户只有 IMEI 或 Android ID，而没有 GAID（如第三方应用商店、4.4.2 以下的安卓版本）。</li><li>Android ID 必须为十六进制格式。</li></ul>**注意**：<ul><li>ID 类型列必须使用以下准确的字符串：advertiserId（也支持 amazon\_aid）、idfa、idfv、android\_id、imei。</li><li>如果您使用的是 android\_id 或 imei，但后续 AppsFlyer 接收到了规格更高的标识符，就会将其记录为新的转化归因。</li><li>`android_id` 和 `imei` 默认不会由 AppsFlyer SDK 收集。如果使用其中任一标识符，请确保在<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">SDK 对接过程中收集相应字段</Anchor>。</li></ul> | [![device_migration_file_option_2.png](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png)](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png) |

**CSV 文件规则：**

* CSV 文件中可以包含多个应用的用户设备。
* 每行针对每个应用只能包含一个设备 ID。
* 文件中的列标题必须设置为特定的字段并以指定的顺序排列，具体方式有以下两种可选：
  * 选项 1：app\_id、device\_id
  * 选项 2：app\_id、device\_id、id\_type
* App ID 应为小写
* Android 标识符应为小写
* IDFA/IDFV 应为大写
* 最多可包含 2500 万行

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">查看 CSV 文件范例</Anchor>

</Accordion>

<div id="campaign-migration" />

### 广告投放迁移

将在投广告切换到 AppsFlyer 后，就可以开始使用 AppsFlyer 归因，同时避免发生重复付费和归因数据丢失的问题。

**注意**：您也可以分批迁移营销广告系列。如果选择这种方式，可以按媒体渠道（例如广告平台或代理商）、地理区域或广告系列，对需要迁移的内容进行分类。

<div id="srns" />

<Accordion title="SRN">

当 MMP（移动衡量合作伙伴）向 SRN 发出请求，查询具体设备的互动信息时，SRN 会回复认领结果。如果两个 MMP（例如 AppsFlyer 和其他归因服务商）同时向同一个 SRN 查询同一次设备安装，您可能会因此被重复扣费。

**如需迁移 SRN 广告系列**：

* 在 AppsFlyer 中<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#与appsflyer对接的srn">启用并配置相关 SRN</Anchor>。

> 📘 **说明**
>
> * 您可以对同一个 SRN 使用多个 MMP（Meta ads 和 Twitter 除外）。
> * Meta ads 不能对应用内事件去重。

</Accordion>

<div id="nonsrn-ad-networks" />

<Accordion title="非 SRN 广告平台">

广告平台的归因链接会记录用户与广告的互动情况，之后如果用户激活了相关应用，AppsFlyer 就能将该激活归因到对应的广告互动。

**如需迁移非 SRN 广告平台的广告系列**：

1. 在 AppsFlyer 中<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">启用</Anchor>相关广告平台。
2. 为每个广告平台<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">生成 AppsFlyer 归因链接</Anchor>。
3. 将各个广告系列中的现有追踪链接替换为 AppsFlyer 的归因链接。

</Accordion>

<div id="owned-media" />

<Accordion title="自有媒体">

自有媒体是指您在以下场景中使用的归因链接：

* 内容分享
* 网页到应用程序
* 邮件
* 短信
* 社交媒体发布
* 博客
* 社区帖子（Quora 等）
* 等场景

对于这些广告系列，AppsFlyer 使用 <Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink 链接</Anchor>。 OneLink 链接会根据用户的设备类型让用户跳转到对应的应用商店、网址/落地页，或直接调起应用。

**如需将现有自有媒体链接替换为 AppsFlyer OneLink 链接**：

* 请联系您的 CSM，让其协助您根据当前使用的流量入口和工具将自有媒体链接转换成 OneLink 链接。

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

对于 SKAdNetwork（SKAN）归因，只能由一个 SDK 更新转化值。否则，SKAN 数据将失去意义。因此，完成迁移后，请确保只有 AppsFlyer SDK 更新 SKAN 转化值。

<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">了解如何在 AppsFlyer 中设置 SKAN 转化值。</Anchor>

</Accordion>

<div id="data-report-setup" />

### 数据报告设置

<div id="adapt-and-map-report-structures" />

<Accordion title="调整并映射报告结构">

迁移之前，您的系统会根据与当前服务商约定的报告结构、字段和参数，存储归因数据。为了确保 AppsFlyer 能够正确生成报告，您必须将现有报告结构、字段和参数调整并映射为 AppsFlyer 对应的结构、字段和参数。

**调整/映射报告结构的方法如下：**

* 请与您的客户成功经理联系，便于将您的报告数据结构从 Adjust，Branch / Tune 或 Kochava 快速调整/迁移到 AppsFlyer。

</Accordion>

<div id="prepare-report-methods" />

<Accordion title="报告的获取方式">

AppsFlyer 支持通过多种方式获取<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-apis">原始</Anchor>报告数据和<Anchor target="_blank" href="/marketers/zh/docs/analytics-and-aggregate-reporting-apis">汇总</Anchor>报告数据。请全面了解这些方法，然后选择最适合自己的方式系统化地完成数据对接设置。

您可以通过以下方式获取数据：

* 面板
* 导出报告
* Push API
* Pull API
* Data Locker

</Accordion>

<div data-zendesk-anchors="overview=%E4%BB%8E%E5%85%B6%E4%BB%96%E5%BD%92%E5%9B%A0%E5%B9%B3%E5%8F%B0%E8%BF%81%E7%A7%BB%E5%88%B0-appsflyer 01H8EDSTP8N4GZJQ5J609C3DHM=%E4%BB%8E%E5%85%B6%E4%BB%96%E5%BD%92%E5%9B%A0%E5%B9%B3%E5%8F%B0%E8%BF%81%E7%A7%BB%E5%88%B0-appsflyer compare-measurement-between-appsflyer-and-other-mmps=%E6%AF%94%E8%BE%83-appsflyer-%E4%B8%8E%E5%85%B6%E4%BB%96-mmp-%E8%A1%A1%E9%87%8F%E6%96%B9%E5%BC%8F%E4%B8%8A%E7%9A%84%E5%B7%AE%E5%BC%82 h_01HQJ10ZFJR43KBYMD9A07CJ99=%E6%AF%94%E8%BE%83-appsflyer-%E4%B8%8E%E5%85%B6%E4%BB%96-mmp-%E8%A1%A1%E9%87%8F%E6%96%B9%E5%BC%8F%E4%B8%8A%E7%9A%84%E5%B7%AE%E5%BC%82 tasks=%E8%BF%81%E7%A7%BB%E6%B5%81%E7%A8%8B 01H8EDSTP8YGDZBPEY1976JP8C=%E8%BF%81%E7%A7%BB%E6%B5%81%E7%A8%8B scope-of-work=%E5%B7%A5%E4%BD%9C%E8%8C%83%E5%9B%B4 01H8EDSTP8HGCVHYX49GQQEHBB=%E5%B7%A5%E4%BD%9C%E8%8C%83%E5%9B%B4 sdk-integration=sdk-%E5%AF%B9%E6%8E%A5 h_01F0RDXJ4F34DDKRFV5G6WZQX0=sdk-%E5%AF%B9%E6%8E%A5 01H8EDSTP97C85X2E9EKBSVFQJ=sdk-integration::c763138b device-migration%E2%80%94optional=%E8%AE%BE%E5%A4%87%E8%BF%81%E7%A7%BB%E5%8F%AF%E9%80%89 h_01F0RDXVSQ13R9Q2KT7PK1KSCQ=%E8%AE%BE%E5%A4%87%E8%BF%81%E7%A7%BB%E5%8F%AF%E9%80%89 01H8EDSTP9NDF6611MVEMWQSMZ=about-device-migration 01H8EDSTP93QJA4XZB6TDWWH1V=%E7%A4%BA%E4%BE%8B 01JA2CAMW3HCHC4B9FX7517FJ6=%E8%AF%B4%E6%98%8E 01H8EDSTP9M2MDMGZ8QBQGPM6S=how-to-migrate-devices h_01F0RPWKQ4B0T1TXRGPVTYPPFB=attributed-migration attributed-device-migration-csv-structure=%E7%94%A8%E4%BA%8E%E5%BD%92%E5%9B%A0%E8%AE%BE%E5%A4%87%E8%BF%81%E7%A7%BB%E7%9A%84-csv-%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84 01H8EDSTP9HABKEZJXMB84CDDE=%E7%94%A8%E4%BA%8E%E5%BD%92%E5%9B%A0%E8%AE%BE%E5%A4%87%E8%BF%81%E7%A7%BB%E7%9A%84-csv-%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84 h_01KV852C6CGBHSB6EFY122DRQY=%E7%94%A8%E4%BA%8E%E5%BD%92%E5%9B%A0%E8%AE%BE%E5%A4%87%E8%BF%81%E7%A7%BB%E7%9A%84-csv-%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84 h_01F0RPX3SJ391M8SPNNN50DDA8=nonattributed-migration nonattributed-device-migration-csv-file-structure=%E7%94%A8%E4%BA%8E%E9%9D%9E%E5%BD%92%E5%9B%A0%E8%AE%BE%E5%A4%87%E8%BF%81%E7%A7%BB%E7%9A%84-csv-%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84 01H8EDSTP9AFDMQS6BPQJY19ZH=%E7%94%A8%E4%BA%8E%E9%9D%9E%E5%BD%92%E5%9B%A0%E8%AE%BE%E5%A4%87%E8%BF%81%E7%A7%BB%E7%9A%84-csv-%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84 campaign-migration=%E5%B9%BF%E5%91%8A%E6%8A%95%E6%94%BE%E8%BF%81%E7%A7%BB h_01F0RDY9WPSBZVP3B7XN3ZEJKK=%E5%B9%BF%E5%91%8A%E6%8A%95%E6%94%BE%E8%BF%81%E7%A7%BB 01H8EDSTP94KSE1J4J5B7HX96Z=srns 01H8EDSTP9ZGMHSM44BWGF1FJN=%E8%AF%B4%E6%98%8E-1 01H8EDSTP981XVWVM2NE0A45RM=nonsrn-ad-networks 01H8EDSTP9XNJA80Z5XR7WR9QN=owned-media 01H8EDSTP9Q8JAPNXSQWSHSK32=skan data-report-setup=%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E8%AE%BE%E7%BD%AE h_01F0RDYKYHAEZ65GZBZ3MWTB5Z=%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E8%AE%BE%E7%BD%AE 01H8EDSTP91E934EDXTPXW2ARJ=adapt-and-map-report-structures 01H8EDSTPAF8H5ESHDVK42M0RB=prepare-report-methods" />
