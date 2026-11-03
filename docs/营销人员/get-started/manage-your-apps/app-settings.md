---
title: 应用设置
metadata:
  keywords:
    - App Settings
    - Advertisers
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Platform essentials
    - Agencies
    - pm-guy-riesenberg
  created_at: '2016-08-16T07:50:37Z'
  edited_at: '2026-10-30T12:29:25Z'
  id: 211719806
  locale: zh-cn
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/zh-cn/articles/211719806
---
> **At a glance:** 了解应用设置如何影响各媒体渠道的应用归因和数据分析。

## 应用设置

**权限：**

* 管理员（或拥有相应权限的其他用户）可以**修改**应用设置。
* 所有有权访问相应应用的账户用户均可**查看**该应用的设置。

**查看或修改应用设置：**

1. 在 AppsFlyer 侧边栏中，依次选择 **设置** > **应用设置。**
2. 在「应用设置」页面查看相关配置，并根据需要进行修改。
3. 点击**保存设置**。

> 📘 **注意**
>
> 您也可以一次性修改多个应用的部分设置，无需逐一操作。对于支持批量修改的设置，请查找设置项旁边的**应用于其他应用**按钮。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。

### 常规应用设置

<Table>
  <thead>
    <tr>
      <th>
        设置项
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="sdk-authentication-dev-key"></span>
        SDK 身份验证：开发密钥
      </td>
      <td>
        * 开发密钥用于验证由应用或通过服务器到服务器（S2S）方式发送至 AppsFlyer 的事件。
        * 该密钥在账户级别唯一，账户内的所有应用共用同一个密钥。
        * 有权访问相应应用的账户用户均可在「应用设置」页面查看该密钥。
        * **可选：** 在特定情况下，可以为单个应用分配独立密钥。如需了解详情，请联系您的客户成功经理（CSM）。
      </td>
    </tr>
    <tr>
      <td><span id="aggregated-advanced-privacy-ios-apps"></span>
        汇总高级隐私保护（仅适用于 iOS 应用）
      </td>
      <td>
        开启后，广告主无法获取用户级归因数据。与合作伙伴共享的回传数据和事件数据将以汇总、匿名的形式提供（了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">汇总高级隐私保护</Anchor>机制）。

        关闭后，所有合作伙伴均可获取汇总形式的用户级归因数据，您还可以针对每个合作伙伴单独配置数据共享方式。

        您也可以一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。
      </td>
    </tr>
    <tr>
      <td><span id="analytics-define-loyal-user-trigger"></span>
        分析：忠实用户判定条件
      </td>
      <td>
        * 用于设置将用户判定为忠实用户的触发条件。添加应用时，系统默认将用户打开应用 3 次作为判定条件。
        * 完成应用内事件归因后，您也可以选择某个应用内事件作为触发事件。
          * **默认设置：** 用户打开应用 3 次。
          * 忠实用户数据可用于衡量用户质量。建议结合<Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide#faq">Protect360</Anchor> 防范作弊行为。
          * 修改此设置会影响历史数据，系统将重新计算历史忠实用户数据。
        * 您也可以一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。
      </td>
    </tr>
    <tr>
      <td><span id="minimum-time-between-sessions"></span>
        会话之间的最短间隔
      </td>
      <td>
        您也可以一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。
      </td>
    </tr>
    <tr>
      <td><span id="app-store-country"></span>
        应用商店国家/地区
      </td>
      <td>
        用于指定应用所在的应用商店国家或地区。此设置会影响以下行为。

        * **1. 将应用状态从待发布更改为已上线**：
          * <Anchor target="_blank" href="/marketers/zh/docs/why-is-my-app-still-pending">应用上线时</Anchor>，AppsFlyer 会根据此处设置的国家或地区检查相应的应用商店，并获取应用图标等信息。
          * 如果在指定的应用商店中找不到该应用，AppsFlyer 就无法将其状态从待发布更改为已上线。
        * **2. 归因链接的跳转行为**：跳转目的地取决于用户类型及访问场景，具体如下表所示。

        | 用户类型 | 跳转场景及规则 |
        | --- | --- |
        | <span id="mobile"></span>移动端用户 | 用户通常会在其他移动应用中点击归因链接。点击后，操作系统会决定将用户跳转至哪个国家或地区的应用商店：<br /><br />* **Android：** 根据用户的 IP 地址或所在位置确定跳转的应用商店。<br />* **iOS：** 跳转至设备上当前登录的 iTunes 账户所对应的应用商店。 |
        | <span id="mobile-and-web"></span>移动端和网页端用户 | 用户在**网站**（包括移动端网站和桌面端网站）上点击归因链接时，系统会先将其跳转至「应用商店国家/地区」设置中指定的商店。<br /><br />用户尝试安装应用时，操作系统会按照上文所述的移动端跳转规则，将其引导至相应国家或地区的应用商店。 |
        | <span id="ipad-ios-13"></span>iOS 13 及更高版本的 iPad | 从 iOS 13 开始，<Anchor target="_blank" href="https://www.apple.com/ipados/features/">iPad 会以桌面版形式显示网站</Anchor>。因此，此处无需区分用户使用的是移动端还是网页端。用户点击归因链接后，会先跳转至桌面版网站，之后按照网页端用户的跳转规则处理。 |
      </td>
    </tr>
    <tr>
      <td><span id="localization-time-zone"></span>
        本地化：时区
      </td>
      <td>
        应用的默认时区为 UTC。<Anchor target="_blank" href="/marketers/zh/docs/changing-app-time-zone-settings">了解详情，请参阅更改应用时区设置。</Anchor>

        即将支持一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。
      </td>
    </tr>
    <tr>
      <td><span id="localization-currency"></span>
        本地化：货币
      </td>
      <td>
        * 用于设置应用专属货币，以下指标均使用此货币：
          * 成本
          * 应用内事件收入
          * 广告收入
        * 默认货币为美元（USD）。
          * 只有尚无收入或成本数据的应用才能更改货币设置。
          * 添加新应用时，需要指定应用货币。
        * 即将支持一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。

        #### 应用货币对报表工具的影响

        | 报表工具 | 可用货币选项 |
        | --- | --- |
        | <span id="dashboards"></span>面板 | 应用专属货币 |
        | <span id="export-data-page"></span>数据导出页面 | 应用专属货币 |
        | <span id="push-api"></span>Push API | 可同时使用应用专属货币和美元（USD） |
        | <span id="pull-api"></span>Pull API | 汇总数据：应用专属货币<br /><br />原始数据：可选择美元（USD）或应用专属货币 |
        | <span id="master-api"></span>Master API | 可选择美元（USD）或应用专属货币 |
        | <span id="data-locker"></span>Data Locker | 仅支持美元（USD） |
      </td>
    </tr>
  </tbody>
</Table>

### 归因设置

> 📘 **注意**
>
> 下表中的设置适用于移动应用（iOS 和 Android）。部分设置可能不适用于 Web 应用，或在 Web 应用中的工作方式有所不同。

| 设置项 | 说明 |
| --- | --- |
| <span id="reattribution-window"></span>再归因窗口 | <Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口</Anchor>是指从首次安装之日起的一段时间，在此期间，用户重新安装应用不会被归因为新的安装。<ul><li>**默认时长：** 3 个月</li><li>可选范围：1 至 24 个月</li></ul>即将支持一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。 |
| <span id="viewthrough-attribution-via-probabilistic-modeling"></span>启用基于概率模型的展示归因 | <ul><li>如果尚未启用，请开启基于概率模型的展示归因功能。</li><li>启用后，还必须在相应广告平台的集成设置页面中开启展示归因。</li><li>即将支持一次性修改多个应用的此项设置。批量修改前，必须已启用指纹识别。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。</li></ul> |
| <span id="reengagement-attribution"></span>再互动归因 | 相关说明请参阅<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销指南</Anchor>。<br /><br />**启用再互动归因：**<ul><li>在 AppsFlyer 侧边栏中，依次选择**设置** > **应用设置**，开启**再互动归因**。</li></ul>除应用级设置外，您还必须<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide#retargeting-settings">针对各个合作伙伴单独配置相关设置</Anchor>。<br /><br /><Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide#排除窗口期">**再互动转化之间的最短间隔**</Anchor> 设置可用于防止现有的再互动窗口在设定时长结束前提前关闭。<br /><br />您也可以一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。批量修改时，系统会在设置生效前要求您确认；单独修改某个应用时，不会出现此确认步骤。 |
| <span id="minimum-time-between-reengagement-conversions"></span>再互动转化之间的最短间隔 | 用于防止现有的再互动窗口在设定时长结束前提前关闭。相关说明请参阅<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide#排除窗口期">再营销归因指南</Anchor>。<br /><br />您也可以一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。 |
| <span id="organic-search-seo-mobile-app-attribution"></span>SEO（自然搜索）和 AEO 移动应用再互动归因 | 相关说明请参阅<Anchor target="_blank" href="/marketers/zh/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">自然搜索归因</Anchor>。<br /><br />**启用 SEO/AEO 归因：**<ul><li>在 AppsFlyer 侧边栏中，依次选择**设置** > **应用设置**，开启**SEO（自然搜索）和 AEO 移动应用再互动归因**。</li></ul>您也可以一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。 |
| <span id="uninstall-measurement"></span>卸载衡量 | <Anchor target="_blank" href="/marketers/zh/docs/measure-uninstalls">卸载衡量</Anchor>与「卸载衡量」开启期间发生的安装相关联。<br /><br />此设置仅适用于 iOS 和 Android 应用。<br /><br />**启用卸载衡量：**<ol><li>按操作系统分别完成以下配置：<ul><li>**iOS：** 实现了iOS 卸载归因功能的应用，需要在此处上传 P12 证书。</li><li>**Android：** 应用需要在此处配置 Firebase/GCM 服务器密钥，以支持Android 卸载归因。</li></ul></li><li>开启**卸载衡量**。</li><li>点击**保存设置**。</li></ol>**停止卸载衡量：**<ol><li>关闭**卸载衡量**。</li><li>点击**保存设置**。</li></ol>即将支持一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。 |

### 高级设置

| 设置项 | 说明 |
| --- | --- |
| <span id="mask-ip-address-in-raw-data-reports"></span>隐藏 IP 地址 | 开启后，当前所选应用的原始数据报表以及发送给合作伙伴的回传数据中，终端用户设备的<Anchor target="_blank" href="/marketers/zh/docs/apply-ip-masking-to-user-data">IP 地址将被隐藏</Anchor>。<br /><br />您也可以一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。 |
| <span id="reinstall-detection-using-ondevice-storage-ios-only"></span>基于设备本地存储的重装检测（仅适用于 iOS） | 无需依赖广告标识符即可检测重装行为。具体做法是将应用最近一次安装的日期存储在设备的安全本地存储中（iOS 设备中存储于钥匙串 Keychain）。通过判断某次安装属于重装还是新装，您可以从「新增安装用户」（NOI）数据中剔除重装记录，从而使归因分析更加准确。注意：出于此目的，设备本地存储中仅会保存最近一次应用安装日期，不会存储任何其他设备标识符（如 IDFA、IDFV）。<br /><br />即将支持一次性修改多个应用的此项设置。了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>。 |
| <span id="ios-103-redirect-fallback"></span>iOS 10.3 跳转回退机制 | （已弃用）适用于 iOS 10.3 及以上版本。我们已简化 iOS 用户的跳转流程，该参数目前已不再使用。详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/uri-scheme-fallback-for-ios">iOS 跳转</Anchor>。<br /><br />此选项仅适用于 iOS 应用。 |
| <span id="change-app-name"></span>修改应用名称 | <ul><li>设置应用名称，该名称将显示在面板及数据报表中。如果同一应用存在多个版本（例如因区域分发需求而设置的不同版本），此设置会非常实用。</li><li>此修改仅影响应用的显示名称。用于在调用 AppsFlyer 各类 API 时识别应用的应用 ID **不会发生变化**。</li><li>名称长度上限为 50 个字符。</li></ul> |
| <span id="outofstore-app-url"></span>应用商店外下载链接 | <ul><li>设置应用下载 URL，该链接将作为与该应用关联的归因链接的默认跳转目的地。</li><li>对于设置为「应用商店外应用」的 Android 应用，此字段为必填项。</li><li>设置完成后，该 URL 将在约 1 小时内生效，成为默认跳转目的地。</li></ul> |

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销归因指南</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">自然搜索归因</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/apply-settings-to-multiple-apps-at-once">一次性将设置应用于多个应用</Anchor>

<div data-zendesk-anchors="app-settings=%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AE 01ECHQME56X51MDW9TMA6DBNCK=%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AE h_01M22QK1N5EMMPVZ7ZJ55Z3YFF=%E6%B3%A8%E6%84%8F general-app-settings=%E5%B8%B8%E8%A7%84%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AE h_01HAVS8CVPQKSDKCEM3YHHJ99Y=%E5%B8%B8%E8%A7%84%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AE reporting-tools-impacted-by-app-currency=%E5%BA%94%E7%94%A8%E8%B4%A7%E5%B8%81%E5%AF%B9%E6%8A%A5%E8%A1%A8%E5%B7%A5%E5%85%B7%E7%9A%84%E5%BD%B1%E5%93%8D h_01HAVS8CVQESWAQXKDW5SNVHCJ=%E5%BA%94%E7%94%A8%E8%B4%A7%E5%B8%81%E5%AF%B9%E6%8A%A5%E8%A1%A8%E5%B7%A5%E5%85%B7%E7%9A%84%E5%BD%B1%E5%93%8D attribution-settings=%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE h_01HAVS8CVQN1YYTT7S49VGB3J0=%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE h_01M1XPKX6DECQPK4R9X6Y4KMBP=%E6%B3%A8%E6%84%8F-1 advanced-settings=%E9%AB%98%E7%BA%A7%E8%AE%BE%E7%BD%AE h_01HAVS8CVQTKXVXSMT5KNYZ3T4=%E9%AB%98%E7%BA%A7%E8%AE%BE%E7%BD%AE h_01HDPCC9465DR4A3CCXYQC2M56=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85" />
