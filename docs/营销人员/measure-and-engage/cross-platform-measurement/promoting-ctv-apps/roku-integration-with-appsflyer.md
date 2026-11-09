---
title: 将Roku与AppsFlyer对接
metadata:
  keywords:
    - Advertisers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2021-07-19T09:00:10Z'
  edited_at: '2026-10-14T10:08:16Z'
  id: 4404257169169
  locale: zh-cn
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/zh-cn/articles/4404257169169
---
> **概要：** Rokuads\_int是一种SRN类型的对接方式，可帮助广告主将其移动端或Roku CTV应用与Roku Ads连接，以获取Roku Ads的归因和事件数据。

<div id="about-roku-ads-attribution" />

## 关于Roku Ads归因

Roku是一个独特的广告平台，其广告资源覆盖连接电视（CTV）和移动应用两大渠道。通过将AppsFlyer与Roku Ads的SRN对接，广告主可以衡量多种用户路径，包括：

* CTV到CTV：CTV广告带来的CTV应用激活与事件。
* 移动端到移动端：移动端广告带来的移动应用的激活与事件。
* CTV到移动端/移动端到CTV：一个平台上的广告展示带来的另一平台的应用激活与事件。

<div id="roku-attribution-flow" />

### Roku归因流程

<Image align="center" alt="54525 inline.jpg" src="https://files.readme.io/5634ed65702e1d4c90250a7f7b4448c225d5f769936b2a120ddbac1a76752c09-39534517801617.jpg" width="895px" />

<div id="setting-up-roku-ads-integration-for-advertisers" />

## 广告主如何设置Roku Ads对接

**前提条件：** 设置对接前，请务必先[联系该渠道](#)并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. 启用方式：从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   修改方式如下：进入**协作** > **活跃对接**。
2. 搜索合作渠道（`rokuads_int`）并点击进入。
3. 点击**设置对接**，然后界面会跳转到活跃对接设置页面。
4. 在**渠道对接**选项卡中，打开**启用该渠道**开关。  
   请注意<strong>：</strong>在您与该渠道合作期间，请确保该开关总是处于打开（即启用）状态。[详情请见渠道激活](#)。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

请注意<strong>：</strong>iOS、Android与Roku的应用设置存在差异。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

<div id="general-settings" />

#### 通用设置

* **Event Group ID：** 输入从Roku Ads管理器获得的Event Group ID，将您的应用与AppsFlyer连接。有关更多信息，请参见<Anchor target="_blank" href="https://help.ads.roku.com/en/articles/11885912-setting-up-an-integration-with-appsflyer-a-mobile-measurement-partner-mmp">Roku ads说明文档</Anchor>。
* **高级数据共享（Advanced data sharing）：** 开启后，Roku将接收所有设备（包括未提供广告标识符IDFA的设备）的回传和事件数据（包含IP地址）。若保持关闭状态，Roku仅接收已提供IDFA的设备回传与事件数据。
* **有限的数据使用（Limited Data Usage）：** 启用后，Roku Ads会在美国特定州限制其在指定事件中对个人信息的使用。有关更多信息，请参见<Anchor target="_blank" href="https://help.ads.roku.com/en/articles/8766138-limited-data-use">Roku ads说明文档</Anchor>。

<div id="install-attribution" />

#### 激活归因

您可以为不同的广告交互类型设置不同的归因窗口，分别针对仅浏览广告、点击广告或与广告交互的用户所完成的新增激活（首次打开）进行归因。请注意<strong>：</strong>该对接不支持重装激活（即相关设备上除了初次激活以外的任何其他激活）的归因。

* 设置**点击型激活回溯窗口**，可用的时长范围为1-23小时或1-14天。请注意<strong>：</strong>Roku Ads建议将此设置为14天。
* 【可选】打开**浏览型激活归因**，并设置**浏览型激活归因窗口**，可用的时长范围为1–23小时或1–14天。**请注意**：**Roku Ads建议将此设置为14天。**

<div id="re-engagement-attribution" />

#### 再互动归因

* 设置**点击型激活回溯窗口**，可用的时长范围为1-23小时或1-14天。**请注意**：**Roku Ads建议将此设置为14天。**
* 【可选】打开**浏览型再互动归因**，并设置**浏览型再互动归因窗口**，可用的时长范围为1–23小时或1–14天。**请注意**：**Roku Ads建议将此设置为14天。**
* 设置**再互动窗口**，可用的时长范围为1-23小时、1-90天或用户的整个**生命周期**。

进一步了解再互动归因的[规则和窗口期](#)。

<div id="ignore-active-users-for-retargeting" />

#### 再营销广告中忽略活跃用户

打开这个开关并设置其窗口期后，AppsFlyer会<Anchor target="_blank" href="/marketers/zh/docs/set-retargeting-inactivity-window#不活跃时长">忽略在此期间打开相关应用的用户所完成的再互动和再归因</Anchor>。也就是说，在此时间范围内的用户活动将不会被归因。有关更多信息，请参见<Anchor target="_blank" href="/marketers/zh/docs/set-retargeting-inactivity-window#不活跃时长">非活跃期</Anchor>。

1. 打开**在再营销广告中忽略活跃用户**的开关。
2. 设置**不活跃窗口**。

<div id="cross-platform-attribution" />

#### 跨平台归因

该功能在此对接中默认启用。

* 将**跨平台回溯窗口**设置为1-23小时或1-3天。
* [可选] 启用**跨平台平等优先级**。启用后，Roku报告的跨平台曝光将提升至与其他渠道点击相同的优先级。若启用，可将**跨平台平等优先级窗口**设置为1-6小时（默认：3小时）。

<div id="in-app-events-postbacks" />

#### 应用内事件回传

将AppsFlyer应用内事件映射到Roku Ads事件，通过回传发送：

1. 打开**应用内事件回传**开关。
2. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。下表列出了必须配置的字段：

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。 |
| **渠道映射事件** | 从Roku预定义事件列表中选择对应事件。请参见AppsFlyer事件与Roku Ads事件的<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#预定义事件名称">映射建议</Anchor>。  <br />请注意<strong>：</strong>Roku不支持发送自定义事件。 |
| **事件来源** | <ul><li>**仅该合作渠道**（默认）：仅回传归因到该渠道的事件。<br />或</li><li>**所有媒体渠道，包括自然流量：** 回传所有带量渠道以及自然量的事件。</li></ul> |
| **包含数据** | <ul><li>**不发送值与收入**（默认）：仅发送事件本身，不带任何事件值。</li><li>**仅发送值：** 发送除收入以外的所有参数。</li><li>**发送值与收入：** 发送所有事件参数，包括收入（若有）。</li></ul> |

* 【可选】点击**添加条件**图标，设置事件的映射条件。
* 点击**保存对接**。
* [可选] 如需对接更多应用：
  1. 点击页面左上角渠道名称下方的应用名称，打开应用列表。
  2. 在列表中选择其他应用。
  3. 按相同步骤完成设置。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

在SRN和高级SRN对接中，归因链接不可用。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡（用于成本、点击和展示数据）">

目前Roku Ads不支持成本对接。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

Roku Ads不提供广告收入。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

在此标签页中，您可以选择为Roku Ads授权，无论其作为广告平台、代理还是同时担任这两种角色。即使Roku Ads的归因功能被禁用，该标签页依然可用，您仍可为其分配访问权限。

当为Roku Ads启用权限后，您可以添加团队成员，并根据选定的权限为其分配访问范围。**注意：** 您只能给在AppsFlyer中拥有广告平台团队成员账户的Roku Ads员工授权。

**如需为广告网络平台成员权限，请按照以下步骤操作：**

1. 点击**添加团队成员**。
2. 输入广告平台团队成员的电子邮箱地址。
3. 点击**添加**。

<div id="important" />

> 🚧 **重要提示！**
>
> * 当您授予Roku Ads配置对接或修改应用内事件回传的权限时，即表示允许其访问所有归因事件数据，包括来自所有媒体渠道的自然和非自然流量。
> * 此外，Roku Ads在此权限下所做的任何更改都会覆盖您（广告主）现有的配置。

<div id="types-of-permissions-advertisers-can-grant-to-roku-ads" />

#### 广告主可授予Roku Ads的权限类型

| 权限 | 授权后的可用功能 |
| --- | --- |
| 配置对接 | 允许该渠道设置对接选项卡（应用内事件回传除外）。 |
| 配置应用内事件回传 | 允许合作渠道配置应用内事件回传。<br /><br />**注意：** 若与“配置对接”同时启用，该权限将允许合作渠道访问所有归因事件，包括来自所有媒体渠道的自然和非自然流量。 |
| 访问留存报告 | 允许合作渠道访问自身的留存数据。 |
| 忠诚用户汇总数据 | 允许合作渠道访问您的忠诚用户指标。 |
| 汇总转化数据 | 允许访问包括激活、再互动、重装激活和再归因（例如<Anchor target="_blank" href="/partners/zh/docs/aggregated-campaign-performance-report-for-ad-networks">活动表现汇总报告</Anchor>）。 |
| 汇总应用内事件数据 | 允许访问所有应用内事件的汇总数据（包括Protect360数据），不限于已在回传映射中配置的事件。  <br />此权限还包括访问广告变现数据，其中可能包含来自其他媒体渠道的事件。 |
| 查看验证规则 | 允许合作渠道查看您的验证规则详细信息。 |
| 汇总收入数据 | 允许访问广告收入数据，用于获客优化。 |
| 使用成本导入功能 | 允许合作渠道使用成本导入功能上传成本数据。 |
| 访问Protect360面板和原始数据 | <ul><li>若您订阅了Protect360、验证规则或收入数据，则合作渠道可访问Protect360面板和原始数据。</li><li>允许访问Protect360面板（包括ProtectLITE）。</li><li>请注意<strong>：</strong>ProtectLITE可提供数据面板访问权限，但不提供原始数据访问权限。</li></ul> |

</Accordion>

<div id="setting-up-roku-ads-integration-for-agencies" />

## 代理如何设置Roku广告对接

代理可代表广告主启用Roku Ads对接并获取其活动的归因数据。 但是代理在使用该对接时有一定的局限性。

<div id="agency-limitations" />

### 代理限制

* 只有在广告主侧启用Roku对接后，代理才能访问该对接。
* 代理的对接页面中显示的对接参数出自广告主侧的对接，且这些参数呈只读模式。

代理设置Roku Ads的操作如下：

1. 从AppsFlyer的侧边栏中选择<Image alt="" src="https://files.readme.io/70400e32ef967b981aabd47faf97880368585fdf52ad29c0d4c2d4c31751e6a3-37844129188753.png" width="2%" />协作 > altPartner Marketplacealt。
2. 查找并选择**Roku Ads（rokuads\_int）**。
3. 输入您代理的**Roku Ads账户ID**。这是为了识别代理流量，并将其与广告主的流量区分开来。
4. 点击**保存对接** 。

<div id="warning" />

> ❗️ **重要提示**
>
> 广告主和代理之间切勿共享Roku Ads账户ID，否则所有的广告主侧激活全部都会被自动记录到代理面板中。

<div data-zendesk-anchors="overview=%E5%85%B3%E4%BA%8Eroku-ads%E5%BD%92%E5%9B%A0 roku-attribution-flow=roku%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B 01H7Z13QPBTKZ9BVCMGASYEM0R=roku%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B setting-up-roku-ads=%E5%B9%BF%E5%91%8A%E4%B8%BB%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AEroku-ads%E5%AF%B9%E6%8E%A5 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01K0P7PHA89T432XNW0C4BZ4VH=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE install-attribution=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 h_01K0P7PHA8X7E7MC7JNVG86JAV=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 reengagement-attribution=%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 h_01K0P7PHA8GR0SYPNKSP4D90AF=%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 ignore-active-users-for-retargeting=%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E4%B8%AD%E5%BF%BD%E7%95%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7 h_01K0P7PHA85619R1SM4SR49TQ3=%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E4%B8%AD%E5%BF%BD%E7%95%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7 crossplatform-attribution=%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0 h_01K0P7PHA80KKG06719ZWE8JB0=%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0 inapp-events-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01K0P7PHA89Y8W70NTF40S6PC4=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 cost-tab-for-cost-clicks-and-impressions=cost-tab h_01K0P7PHA840N225ABCSGTTCAN=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA types-of-permissions-advertisers-can-grant-to-roku-ads=%E5%B9%BF%E5%91%8A%E4%B8%BB%E5%8F%AF%E6%8E%88%E4%BA%88roku-ads%E7%9A%84%E6%9D%83%E9%99%90%E7%B1%BB%E5%9E%8B h_01K0P7PHA8D7WQR02129YADZZP=%E5%B9%BF%E5%91%8A%E4%B8%BB%E5%8F%AF%E6%8E%88%E4%BA%88roku-ads%E7%9A%84%E6%9D%83%E9%99%90%E7%B1%BB%E5%9E%8B setting-up-agencies=%E4%BB%A3%E7%90%86%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AEroku%E5%B9%BF%E5%91%8A%E5%AF%B9%E6%8E%A5 setting-up-roku-ads-integration-for-agencies=%E4%BB%A3%E7%90%86%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AEroku%E5%B9%BF%E5%91%8A%E5%AF%B9%E6%8E%A5 agency-limitations=%E4%BB%A3%E7%90%86%E9%99%90%E5%88%B6 h_01K0P7PHA8MSV6Q13P9ATAX8SJ=%E4%BB%A3%E7%90%86%E9%99%90%E5%88%B6 h_01K0P7PHA8KXP5H9WXJ1J2VFR2=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1" />
