---
title: 合作渠道的启用和停用
metadata:
  keywords:
    - Advertisers
    - Agencies
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
    - Agencies
    - Ad Networks
  created_at: '2019-01-29T08:53:31Z'
  edited_at: '2026-10-14T10:04:19Z'
  id: 360000844778
  locale: zh-cn
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000844778
---
> **概要：** 您可以通过启用或停用渠道对接来控制渠道的数据访问和面板操作权限。

## 启用渠道对接

渠道对接分为活跃和不活跃两种状态。在渠道对接配置的主页面中打开**启用该渠道**的开关后，该对接就变为活跃对接。渠道对接分为多种不同的类型。即使**启用该渠道**的开关处于关闭状态，只要您启用了其他任何[对接类型](#id)，AppsFlyer则会将该对接视为活跃对接。

> 🚧 **重要提示！**
>
> 在启用渠道对接时，系统会默认您同意与对方共享某些数据，包括个人信息（如广告 ID、IP 地址）。请确保您拥有合法的依据和相应的权限来共享这些数据。如需限制与合作渠道之间的数据共享，可参考<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">《汇总层级的高级隐私保护框架》</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/apply-privacy-preserving-sdk-methods">《保护用户隐私的SDK配置》</Anchor>中的相关说明操作。

**请按以下方式进入当前选定应用的渠道对接页面：**

* 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**，然后选择相关渠道。

下文介绍了各种对接类型，以及对接的启用/停用会产生的具体影响。

<div id="id" />

<Accordion title="对接类型">

主要对接的设置（即**启用该渠道**开关）位于渠道主页面中的第一个选项卡中。其他的对接类型在其右侧的各个选项卡中配置（详见下表）。**各个类型的对接独立生效**。只要相关渠道对接的配置页面中有至少一个对接类型处于启用状态，AppsFlyer就会将其视为活跃对接，无论广告主是否已打开其“启用该渠道”开关。

| 对接类型 | 说明 |
| --- | --- |
| **主要对接（**<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#a-activate-partner">**启用该渠道**</Anchor>） | 启用后，AppsFlyer会将相关转化归因到该渠道，并向其发送回传 |
| <Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview">**成本**</Anchor>（若适用） | 用于获取广告系列、广告组、广告以及国家/地区维度的成本、点击和展示数据 |
| <Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution">**广告收入**</Anchor>（若适用） | 用于获取您分发的广告所产生的收入数据 |
| <Anchor target="_blank" href="/marketers/zh/docs/skan-integrated-partners-list">**SKAN**</Anchor>（若适用） | 用于获取来自渠道的SKAN回传 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">**授权**</Anchor> | 用于向广告平台和代理商开通数据权限并允许其在您的对接中完成相关操作 |

</Accordion>

<div id="effect-of-the-partner-activation-setting" />

<Accordion title="启用渠道对接后的效果">

下表分场景说明了启用渠道对接对于归因和回传的影响。

<table><thead><tr><th>场景</th><th>启用该渠道开关<br/>打开</th><th>启用该渠道开关关闭</th></tr></thead><tbody><tr><td>对于新增激活、再归因和再互动的归因和回传 </td><td><p><strong>是否归因：</strong>是</p><p><strong>是否回传：</strong>是</p></td><td><p><strong>是否归因：</strong>否</p><p><strong>是否回传：</strong>否</p></td></tr><tr><td><span>对接停用前发生的广告交互（点击）；对接停用后发生的激活/再归因/再互动</span></td><td><p><span>不适用</span></p></td><td><span>已停用的渠道不会再获得归因。</span></td></tr><tr><td>点击和展示</td><td>广告交互会得到归因，并显示在面板中。</td><td><ul><li>点击后会跳转到“403 禁止访问”的报错页面。</li><li>广告交互不会得到归因，也不会在面板中显示。</li></ul></td></tr><tr><td>SKAN归因</td><td colspan="2"><p>不适用</p><p>若配置了SKAN归因，则无论<strong>启用该渠道</strong>的开关是否打开，都会记录SKAN数据。 </p></td></tr></tbody></table>

</Accordion>

## 渠道对接的启用方式

**如需为当前选定应用启用或修改主要对接（渠道对接选项卡）：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式如下：** 从AppsFlyer面板左侧的菜单栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。界面会跳转到对接设置页。
3. 打开**渠道对接**选项卡中的**启用该渠道**开关。
4. 点击**保存对接** 。

查看[其他对接类型](#id)。

> ❗️ **注意事项**
>
> 切勿使用**启用渠道**开关来暂停或关停广告，否则会对在投广告的归因衡量造成不可逆的破坏。

#### 启用渠道的操作权限

渠道对接可由广告主和代理商启用，具体细节请见下表。

| 启用人员 | SRN | 非SRN |
| --- | --- | --- |
| 广告主 | 可以为自己或为代理启用SRN | 可为自己启用非SRN |
| 代理 | 无法启用SRN | 可启用指定的非SRN |

## 停用渠道对接

在具体渠道的配置页面中关闭**启用渠道**开关后，即可停用该渠道。停用后，AppsFlyer就不会再将转化归因到该渠道，也不会向其发送回传。但是如果您在关闭启用渠道开关后未关闭其他[对接类型](#id)，那么这些对接功能仍会继续生效。也就是说**对接仍会处于活跃状态**，并且会继续收集相关数据。

<span id="deactivating-a-partner"></span>**渠道对接的停用方式：**

1. 从AppsFlyer的左侧菜单栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。界面会跳转到对接设置页。
3. 关闭**渠道对接**选项卡中的**启用该渠道**开关。
4. 点击**保存对接** 。
5. 如需完全停用某个渠道，请在各个选项卡中检查所有[其他对接类型](#id)，并分别将其关闭。  
   **请注意：** 如需停止Google和Meta ads侧的SKAN数据记录，请在SKAN选项卡中删除相关连接。
6. 点击**保存对接** 。
7. 【可选】您可以在保存对接后留在配置页面，**停用该渠道在其他应用中的对接**：
   1. 点击页面左上角渠道名称下方的应用名称，打开应用列表。
   2. 在下拉菜单中选择一个其他应用。
   3. 重复第2-4步。

## 渠道和代理的面板权限

渠道和代理的面板视图和配置选项各不相同，具体取决于广告主的授权情况。

### 渠道可见的面板内容

* 即使渠道具有配置对接的权限，也仅能以只读模式查看**启用渠道**开关的状态。
* 渠道设置的可见性取决于对接配置人员的身份（广告主或代理），具体请见下表：

| 对接配置人员 | 设置是否对渠道可见 |
| --- | --- |
| 广告主 | 是 |
| 代理 | 否 |

### 代理权限

您可以为代理开放相关应用的权限，以便其处理代投工作。

**如需向代理开放某个应用的权限，请按以下方式操作：**

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关代理。
3. 进入**授权**选项卡并打开**代理权限**开关。
4. 【可选】向代理开放其他<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#代理权限">权限</Anchor>。

> 📘 **注意**
>
> * **代理**可以打开或关闭**非SRN**的**启用渠道**开关。
> * **广告主**可以打开或关闭**SRN**的**启用渠道**开关。启用后，相关SRN带来的激活**不会归因到代理**。

#### 关闭代理权限

关闭代理权限后：

* 该代理无法在AppsFlyer面板中访问该应用。
* 新增激活及其事件不会再归因给该代理。
* 该代理使用的所有渠道都不会收到回传。
* 停用前的转化所产生的新增事件仍会归因到该代理，并显示在广告主的面板中，但不会再向相关渠道发送回传。

**请注意：** 如果广告主关闭了代理权限，则代理的历史数据（如激活和成本）不可见。

以下示例说明了广告主在关闭代理权限后的流量归因方式：

> 📄 **示例 1**
>
> **代理通过非SRN（使用归因链接的渠道）投放**
>
> 流量会归因到自然量或之前的转化（若仍在回溯窗口期内）， 但不会归因到该代理。
>
> 该示例也适用于AppsFlyer通过点击归因链接和相关渠道的API获取信息的场景。

> 📄 **示例 2**
>
> **代理通过SRN（不使用归因链接的渠道）投放**
>
> 流量会归因到相关SRN并显示在广告主的面板中，而不会再归因到该代理。

<div data-zendesk-anchors="overview=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5 h_01HRA982WC3519NMGXV5WEY1AZ=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5 01JDM949M75Q3BAG6M65DYMHZT=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA %20id%3D=id integration-types=id h_01HRAERWRJ2SBRY9XQG983WP5M=effect-of-the-partner-activation-setting activating-a-partner=%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5%E7%9A%84%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HJR1D6THJ9TNGZZV78SEVBZN=%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5%E7%9A%84%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HJR1D6THSEA65CY71VWJYX1P=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 who-can-activate-partners=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93%E7%9A%84%E6%93%8D%E4%BD%9C%E6%9D%83%E9%99%90 h_01HJR1D6THRMF854SCSFVZFWM9=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93%E7%9A%84%E6%93%8D%E4%BD%9C%E6%9D%83%E9%99%90 deactivated-partners=%E5%81%9C%E7%94%A8%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5 h_01HJR1D6THE2QWSF971VQFXCBX=%E5%81%9C%E7%94%A8%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5 h_01HJR1D6THS60X7VTDN2X6FT0K=deactivating-a-partner partner-and-agency-dashboards=%E6%B8%A0%E9%81%93%E5%92%8C%E4%BB%A3%E7%90%86%E7%9A%84%E9%9D%A2%E6%9D%BF%E6%9D%83%E9%99%90 h_01HJR1D6THB0N1C8XCC5YAMQQ3=%E6%B8%A0%E9%81%93%E5%92%8C%E4%BB%A3%E7%90%86%E7%9A%84%E9%9D%A2%E6%9D%BF%E6%9D%83%E9%99%90 partner-visibility=%E6%B8%A0%E9%81%93%E5%8F%AF%E8%A7%81%E7%9A%84%E9%9D%A2%E6%9D%BF%E5%86%85%E5%AE%B9 h_01HJR1D6TJ6D3TV2PCFWP4SEAR=%E6%B8%A0%E9%81%93%E5%8F%AF%E8%A7%81%E7%9A%84%E9%9D%A2%E6%9D%BF%E5%86%85%E5%AE%B9 agency-permissions=%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90 h_01HJR1D6TJ9PHVG6GGQ2Z1KJRQ=%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90 h_01HJR1D6TJ9T55PSPBRNW1XXS7=%E6%B3%A8%E6%84%8F disabled-agency-permissions=%E5%85%B3%E9%97%AD%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90 h_01HJR1D6TJ1ABQM6HCPK277R0Z=%E5%85%B3%E9%97%AD%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90 h_01HJR1D6TJBT0D3G2KWKFKEW5S=%E7%A4%BA%E4%BE%8B-1 h_01HJR1D6TJTXF49JP3VJE6ZYC9=%E7%A4%BA%E4%BE%8B-2" />
