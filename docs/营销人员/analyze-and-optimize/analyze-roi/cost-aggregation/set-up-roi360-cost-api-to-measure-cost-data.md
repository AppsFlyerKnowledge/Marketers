---
title: 设置ROI360 Cost API以衡量成本数据
metadata:
  keywords:
    - ROI
    - cost
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-19T12:50:13Z'
  edited_at: '2026-10-14T10:01:22Z'
  id: 360008850257
  locale: zh-cn
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/zh-cn/articles/360008850257
---
> **概览：** 通过Cost API，在应用或媒体渠道账号层级获取汇总营销成本数据（包括与成本相关的LTV表现指标）。

## 概览

ROI360提供应用层级和账号层级的成本衡量能力，便于相关方按应用分析投放支出明细，或对媒体渠道账号进行汇总分析。

成本对接的管理入口根据媒体渠道不同分为两类：

* **账号层级对接**在**成本设置**中管理。按广告账号层级进行配置。请参阅支持的广告平台列表。
* **应用层级对接**在**成本**标签页中管理，需要针对每个应用分别配置。如果某个媒体渠道未显示在成本设置中，请在应用层级的成本标签页完成其成本对接。

> 📘 **注意**
>
> 成本设置的访问权限受角色权限控制。如您无法访问**成本设置**，请联系管理员在**用户管理**页面更新您的角色权限，为您启用**成本对接**。

## 启用Cost API

您可在应用层级或账号层级启用成本对接：

<div id="enable-the-cost-integration-on-the-app-level-cost-tab" />

<Accordion title="在应用层级启用（成本选项卡）">

如需为某个应用单独与媒体渠道建立专属成本对接，请按以下步骤操作：

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**，然后选择相关渠道。
2. 点击**管理对接**。
3. 打开相关对接渠道的**成本**选项卡。
4. 打开**获取成本数据**的开关。系统将显示与该合作渠道对接所需的配置要求。
5. 配置并验证渠道对接设置。认证方式取决于具体媒体渠道，详见下文[成本对接方式](#成本对接方法)。
6. 如果渠道的成本配置中含有**子渠道映射**，请从下拉菜单中选择所需的子渠道配置。详见下文[Site ID映射](#子渠道映射)。
7. 点击**保存成本**。
   * 成本数据将在5–6小时内显示在您的面板中。
   * AppsFlyer每天从合作渠道拉取数据6次，平均每4小时一次。
   * 您在应用层级通过**成本**选项卡所做的配置，也会同步更新至**成本设置**中的媒体渠道账号信息。

</Accordion>

<div id="enable-the-cost-integration-on-the-account-level-cost-settings" />

<Accordion title="在账号层级启用成本对接（成本设置）">

如需为多个或全部应用启用成本功能，您只需为每个媒体渠道账号完成一次对接。

在账号层级启用成本对接，请按以下步骤操作：

1. 从AppsFlyer后台的侧边栏中选择**设置** > **ROI360** >**成本设置**。
2. 选择需要获取成本数据的媒体渠道，然后单击**下一步**。
3. 配置并完成与媒体渠道的成本对接认证。认证方式取决于具体媒体渠道， 详见下文[成本对接方式](#成本对接方法)。
4. 输入或自定义该成本对接名称。
5. 选择需要纳入此成本对接的应用。
6. 点击**保存对接**。
   * 成本数据将在5–6小时内显示在您的面板中。
   * AppsFlyer每天从媒体渠道拉取数据6次，平均每4小时一次。
   * 在**成本设置**中进行的账号层级更新，将自动同步至相关应用和媒体渠道的**活跃对接** > **成本选项卡**。

</Accordion>

> 📘 **注意**
>
> 如果广告主通过代理投放广告，代理需要与相关渠道进行对接，而广告主不需要。如果广告主和代理使用同一个证书针对同一个应用与渠道对接，成本数据就会出现重复。

## 成本对接方法

启用成本对接的方式取决于媒体渠道与AppsFlyer的对接模式，可能包括以下几种：

* **登陆**：单击**登录到`<媒体渠道>`**打开媒体渠道登录窗口，并根据提示完成登录。
* **凭证**：输入该渠道专属的参数值，如**API Key**。
* **无需操作：** 除按**上述**说明开启[获取成本数据](#启用cost-api)外，无需进行其他对接配置。

如需确认某个媒体渠道需采用哪种方式，可在媒体渠道成本对接表中的**对接方法**列查看。

## 子渠道映射

在上报成本数据时，<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">部分渠道对接</Anchor>允许广告主选择<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#attribution::e9b53459">子渠道</Anchor>字段的填充方式。这种方法可以确保AppsFlyer归因链接中的宏与媒体渠道预期的取值一致。

* 默认情况下，子渠道映射会与归因链接中的AppsFlyer宏一致。
* 如果您所选择的子渠道映射不同于归因链接中的宏，则无法正确填充子渠道数据。

在应用层级设置Site ID映射，请按以下步骤操作：

1. 在对接合作伙伴**成本**选项卡中，前往**Site ID映射**，然后从下拉菜单中选择配置。
2. 点击**保存成本**。更改后的设置将从UTC时间的次日起生效。

## 删除成本对接

您可以在应用层级或账号层级删除成本对接。删除后，AppsFlyer将无法再从该账号拉取成本数据。删除操作不会影响已收集的历史数据。

<div id="delete-the-cost-integration-on-the-app-level-cost-tab" />

<Accordion title="在应用层级删除成本对接（成本选项卡）">

您可随时删除对接。

操作步骤如下：

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 选择相关对接渠道，如Meta ads。
3. 点击**管理对接**。
4. 进入**成本**选项卡。界面会显示已对接的账户列表。
5. 在**行动栏**中，将鼠标悬停在账户上，点击**删除对接**。
6. 在确认提示中，单击**确认，删除**。

此前在应用层级配置的成本对接将同时从应用层级和账号层级移除，成本数据将立即停止拉取。该变更不会影响已收集的历史成本数据。

</Accordion>

<div id="delete-the-cost-integration-on-the-account-level-cost-settings" />

<Accordion title="在应用层级删除成本对接（成本选项卡）">

在账号层级删除成本对接，请按以下步骤操作：

1. 在AppsFlyer侧边菜单中，选择**设置** > **ROI360 > 成本设置**，并选择需要删除对接的媒体渠道。
2. 在媒体源的集成列表中，点击集成记录。
3. 在确认弹窗中点击**确认，删除**。

此前在账号层级配置的成本对接将同时从账号层级和应用层级移除，成本数据将立即停止拉取。该变更不会影响已收集的历史成本数据。该变更不会影响已收集的历史成本数据。

</Accordion>

## 停用Cost API

停用Cost API仅支持在应用层级操作。

停用步骤如下：

1. 前往**活跃对接**并选择对应媒体渠道。
2. 进入**成本**选项卡。
3. 关闭**获取成本数据**。
4. 点击**保存成本**。

> 📘 **注意**
>
> 如果广告主停止与代理合作，并在应用层级关闭代理权限，但代理仍为该应用配置了成本对接，成本数据仍会继续拉取。广告主需联系代理关闭其成本对接，才能停止数据拉取。

## Cost API状态

您可通过以下方式检查成本对接状态：

* <Anchor target="_blank" href="/marketers/zh/docs/dashboard-cost-and-ad-revenue-status">成本（及广告收入）对接状态面板：</Anchor>集中展示当前账号下，已为一个或多个应用启用成本对接的媒体渠道列表。
* 对接渠道：可进入具体应用的面板中查看Cost API的对接状态。
* 成本设置: 可同时查看账号层级和应用层级的成本API状态。详见下文[查看媒体渠道汇总成本对接状态](#view-the-media-source-aggregate-cost-integration-status-cost-settings)。

<div id="view-the-media-source-cost-integration-status-cost-tab" />

<Accordion title="查看媒体渠道的成本对接状态（成本选项卡）">

媒体渠道的**活跃对接页面** > **成本选项卡**（适用于支持通过API获取成本数据的媒体渠道）会显示：

* 当前所选应用的成本对接状态。
* AppsFlyer最近一次成功拉取该应用匹配成本数据的时间。

查看某个应用在指定媒体渠道下的成本对接状态，请按以下步骤操作：

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 选择媒体渠道。
3. 在该媒体渠道的**活跃对接**页面中，从选项卡上方的**应用**列表选择需要查看的应用。
4. 单击**成本**选项卡，即可查看状态及最近同步时间。

</Accordion>

<div id="view-the-media-source-aggregate-cost-integration-status-cost-settings" />

<Accordion title="查看媒体渠道的汇总成本对接状态（成本设置）">

查看媒体渠道的汇总成本对接状态，请按以下步骤操作：

1. 从AppsFlyer后台的侧边栏中选择**设置** > **ROI360 > 成本设置**。
2. 选择相关媒体渠道。
3. 在媒体渠道页面的**状态**列中查看媒体渠道账号状态。若该账号下所有应用状态一致，将显示统一状态。若不同应用状态不同，则显示为**混合状态**。
4. 如需查看某个具体应用的状态，请点击对应媒体渠道账号行，进入**成本对接**页面，
5. 并在关联应用列表中查看应用状态。

</Accordion>

<div id="status-table" />

<Accordion title="状态说明表">

| 状态 | 说明/所需操作 |
| --- | --- |
| 活跃 | 对接已启用，且与媒体渠道绑定成功。 |
| API未返回匹配的费用数据 | 可能原因：  <br />未提供广告系列ID信息，因此成本无法匹配到广告系列。  <br />  <br />与AppsFlyer绑定的渠道账户不是您的投放账户（比如Meta ads上不同的账户之间有所混淆）。请检查您所绑定的渠道账户是否正确。  <br />  <br />渠道成本对接的证书字段有误，如Bundle ID。请检查并更正对接证书。  <br />  <br />您的广告已停投，因而没有数据。 |
| 合作伙伴 API 没有响应 | 对接渠道的服务器没有对AppsFlyer做出响应。  <br />请等待6小时。如果之后仍出现该报错消息，请联系AppsFlyer技术支持团队。 |
| Invalid credentials（证书无效） | 由于证书无效，因此AppsFlyer无法通过API获取数据。  <br />请使用正确的证书重新绑定。 |
| Reach out to your ad network account manager to get access to their reporting API（请联系您的广告平台客户经理，获取报告API权限。） | 请与渠道客户经理配合，启用其系统中的成本对接。 |
| Partner API is not returning data.Review integration.（渠道API未返回数据，请检查对接） | 出现这种情况可能有以下几种原因：  <br />您的广告已停投，因而没有数据。 |
| Your account is not enabled on the partner system to get cost（您的账户在渠道系统中未启用成本数据获取） | 请联系相关渠道。 |
| 混合状态 | 仅在成本设置 > **媒体渠道**页面显示。当关联应用状态不一致时显示该状态。从**媒体渠道**页面进入**对接**页面查看各应用的具体状态。该状态不会显示在状态面板中。 |

</Accordion>

## 支持账号层级成本配置的媒体渠道

ROI360客户可以在**成本设置**和**成本**选项卡中创建和编辑账户层级成本对接。以下媒体渠道支持账户级成本配置：

<div id="supporting-media-sources" />

<Accordion title="支持的媒体渠道">

| 显示名称 | 对接ID |
| --- | --- |
| AdAction3 | `adaction5_int` |
| Adbloom | `adbloom_int` |
| AdColony | `adcolony_int` |
| AdGate Media | `adgatemedia_int` |
| adjoe GmbH | `adjoe_int` |
| Adikteev Retargeting | `trademob_int` |
| Apple Search Ads | `iossearchads_int` |
| AppLift | `applift_int` |
| AppLovin | `applovin_int` |
| Aura | `aura_int` |
| Blind Ferret Agency | `blindferret_int` |
| Bluestacks | `bluestacks_int` |
| bytedance | `bytedance_int` |
| Chartboost | `chartboost_int` |
| Dataseat | `dataseat_int` |
| Digital Turbine Legacy | `appia_int` |
| Digital Turbine On Device | `digitalturbine_int` |
| Domob | `domobc_int` |
| DV360 | `dv360_int` |
| GlobalWide Media | `globalwide_int` |
| Google Ads | `googleadwords_int` |
| InMobi | `inmobi_int` |
| InMobi DSP | `inmobidsp_int` |
| Liftoff Influence | `jetfuelit_int` |
| Mediaforce | `mediaforce_int` |
| Meta Ads | `facebook` |
| Mintegral | `mintegral_int` |
| Mobupps | `mobupps_int` |
| Moloco | `moloco_int` |
| MoPub Acquire | `crossinstall_int` |
| Opera Mobile | `operaevent_int` |
| Persona.ly RTB | `personalyrtb_int` |
| pinterest | `pinterest_int` |
| Pinsight | `pinsight_int` |
| Point2Web | `point2web_int` |
| Reddit | `reddit_int` |
| Smadex | `smadex_int` |
| Snapchat | `snapchat_int` |
| Tapjoy | `tapjoy_int` |
| Taptica | `taptica_int` |
| TikTok | `tiktokglobal_int` |
| TUNE | `hasoffers_int` |
| Unity Ads | `unityads_int` |
| X (Twitter) | `twitter` |

> 📘 **注意**
>
> 您也可通过InCost广告平台接入更多媒体渠道。如需获取InCost支持的广告平台完整列表，请联系您的CSM。

</Accordion>

## 特性与限制

| 特点 | 说明 |
| --- | --- |
| 代理 | 代理机构不能同时使用成本设置在多个应用间进行成本整合。 |
| 新增应用是否自动继承账号层级成本设置。 | 当前暂不支持 |
| 广告主与代理同时连接同一广告平台时的成本数据处理逻辑 | 如果广告主和代理同时为同一个广告平台账户（例如 Google Ads）配置了成本对接，系统会从获得归因的账户拉取成本数据。<br /><br />示例：<ul><li>广告主使用广告主凭证完成成本对接</li><li>代理使用代理凭证完成成本对接</li><li>归因分配给代理账户</li></ul>**结果：**<ul><li>ROI360将从代理连接中拉取成本数据。</li><li>广告主连接将显示为“无数据（NO-DATA）”。</li></ul> |
| Google 成本集成自动断开连接 | 显示 **无数据** 或 **凭据无效** 状态超过 365 天的成本集成将被自动断开连接。这仅适用于 Google 集成。 |
| TikTok 广告主 ID 列表配置 | 在账户级别配置广告主 ID 列表，且仅使用已连接到广告网络中 TikTok 用户的广告主 ID。<br /><br />添加到列表中但与广告网络中的用户不匹配的广告主 ID 不会返回成本数据。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01K3DGA6SJ82CGNT0R422CF7RY=%E6%A6%82%E8%A7%88 h_01KDA6722FKAADA1VM3RC2FNBC=%E6%B3%A8%E6%84%8F enabling-cost-api=%E5%90%AF%E7%94%A8cost-api h_01K3DGA6SJB0R7G9EKH1G76R8K=%E5%90%AF%E7%94%A8cost-api h_01K3DGA6SJCDQCDVKSMVVCV6P5=enable-the-cost-integration-on-the-app-level-cost-tab h_01K3DGA6SK25RF53A608BAE1XW=enable-the-cost-integration-on-the-account-level-cost-settings h_01K3DGA6SK5DNZ1BT1BGAJCNCK=%E6%B3%A8%E6%84%8F-1 cost-integration-methods=%E6%88%90%E6%9C%AC%E5%AF%B9%E6%8E%A5%E6%96%B9%E6%B3%95 h_01K3DGA6SK18MHM5FR6ZDR8Y2G=%E6%88%90%E6%9C%AC%E5%AF%B9%E6%8E%A5%E6%96%B9%E6%B3%95 site-id-mapping=%E5%AD%90%E6%B8%A0%E9%81%93%E6%98%A0%E5%B0%84 h_01K3DGA6SKDTTPY8Q1JBTCTY7H=%E5%AD%90%E6%B8%A0%E9%81%93%E6%98%A0%E5%B0%84 deleting-cost-integrations=%E5%88%A0%E9%99%A4%E6%88%90%E6%9C%AC%E5%AF%B9%E6%8E%A5 h_01K3DGA6SKF8ZA5M9AW6DA0V3J=%E5%88%A0%E9%99%A4%E6%88%90%E6%9C%AC%E5%AF%B9%E6%8E%A5 h_01K3DGA6SKCC2H8PRGDPY5XA9C=delete-the-cost-integration-on-the-app-level-cost-tab h_01K3DGA6SKGQ1G1S8AK9X6WKGA=delete-the-cost-integration-on-the-account-level-cost-settings disabling-cost-api=%E5%81%9C%E7%94%A8cost-api h_01K3DGA6SK93AZ8MNMS0VB87YK=%E5%81%9C%E7%94%A8cost-api h_01K3DGA6SKB0V53DM8RQ4HWZ90=%E6%B3%A8%E6%84%8F-2 cost-api-status=cost-api%E7%8A%B6%E6%80%81 h_01K3DGA6SKCZYP5AX29PW7JQ1T=cost-api%E7%8A%B6%E6%80%81 h_01K3DGA6SKCKYHD4EG28NMEGX5=view-the-media-source-cost-integration-status-cost-tab h_01K3DGA6SKBPXEY18VJBCBNCJS=view-the-media-source-aggregate-cost-integration-status-cost-settings h_01K3DGA6SKWR56RRZQB23GMA43=status-table account-level-cost-configuration-supporting-media-sources=%E6%94%AF%E6%8C%81%E8%B4%A6%E5%8F%B7%E5%B1%82%E7%BA%A7%E6%88%90%E6%9C%AC%E9%85%8D%E7%BD%AE%E7%9A%84%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93 h_01KQ7V7Q6M2SZX4KWNEM1MQEJV=%E6%94%AF%E6%8C%81%E8%B4%A6%E5%8F%B7%E5%B1%82%E7%BA%A7%E6%88%90%E6%9C%AC%E9%85%8D%E7%BD%AE%E7%9A%84%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93 h_01KQ7V7Q6MAEMXKKJ7TV8GC1YR=supporting-media-sources h_01KQY5ZYGWAAYAQX4V10SXJ722=%E6%B3%A8%E6%84%8F-3 specification-and-limitation=%E7%89%B9%E6%80%A7%E4%B8%8E%E9%99%90%E5%88%B6 h_01K3DGA6SKVZ347ZDY599S0Y7Y=%E7%89%B9%E6%80%A7%E4%B8%8E%E9%99%90%E5%88%B6" />
