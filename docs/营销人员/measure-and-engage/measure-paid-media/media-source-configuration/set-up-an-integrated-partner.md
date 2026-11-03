---
title: 设置对接渠道
metadata:
  keywords:
    - Advertisers
    - Agencies
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
  created_at: '2021-11-08T08:02:46Z'
  edited_at: '2026-10-14T10:03:53Z'
  id: 4410395957521
  locale: zh-cn
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410395957521
---
> **概要：** 在AppsFlyer后台完成渠道对接配置后，您就可以对来自该渠道的流量进行归因、将数据回传给渠道，并启用其他对接功能。

## 概览

渠道、媒体和第三方平台通过API与AppsFlyer对接。本文将指导您如何激活并配置非SRN广告平台的对接，包括如何生成归因链接等。

* 本指南不适用于SRN的对接配置。如需配置SRN对接，请参阅<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">SRN</Anchor>专用指南。
* 我们针对一些广告平台编写了专门的说明文档。
* 配置对接前，请先联系相关渠道并在其平台上开设账户。

<div id="partner-types-in-the-ecosystem" />

<Accordion title="移动营销生态中的渠道类型">

下图显示了归因生态系统中的各种渠道类型。

[![Ecosystem.jpg](https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg)](https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg)

**扩展阅读**：<Anchor target="_blank" href="https://www.appsflyer.com/performance-index/">AppsFlyer的《广告平台综合表现报告》</Anchor>为您提供分类别和地区的移动端媒体渠道排名。

| 渠道类型 | 说明 |
| --- | --- |
| 广告平台 | 为您投放广告。 |
| 代理商 | 利用其专业技能和经验为您代投广告，获取高质量用户。了解有关<Anchor target="_blank" href="/marketers/zh/docs/view-agency-data">代理数据</Anchor>的更多信息。 |
| 平台官方合作渠道 | 这些渠道专攻某个特定广告平台的营销合作，如Meta投放管理合作平台、Apple Search Ads官方合作渠道、X官方合作渠道等。 |
| 再营销广告平台 | 专攻再营销投放的广告平台 |
| 第三方平台 | 提供BI相关服务，如分析和营销自动化平台。 |
| 假量监测 | AppsFlyer Protect360以外的第三方防作弊系统。 |

</Accordion>

<div id="partners-in-the-marketplace" />

<Accordion title="合作伙伴集成中的合作伙伴">

所有与 AppsFlyer 集成的合作伙伴、媒体来源和其他平台均可在合作伙伴集成页面上找到。无论其<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">活跃与否</Anchor>，便于您搜索并尝试新的渠道。

**要在合作伙伴集成中搜索和筛选所有合作伙伴、媒体来源或其他平台，请执行以下操作：**

* 从AppsFlyer后台的侧边栏中选择**协作** > **Partner Marketplace**。然后使用筛选条件选项缩小渠道范围。

#### 在AppsFlyer中添加新的对接渠道

如果您使用的渠道还未与AppsFlyer对接，您可以向他们<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#在appsflyer中添加新的对接渠道">发送邀请链接</Anchor>。

</Accordion>

<div id="your-integrated-partners" />

<Accordion title="活跃对接渠道">

合作伙伴集成中的 “活跃集成” 选项卡显示所有<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">活跃</Anchor>的集成合作伙伴。您可以在此页面中了解相关渠道的详情并管理其对接。

> 📘 **注意**
>
> 选项卡上显示的合作伙伴列表因所选应用程序而异。您可以点击左上角的应用图标，选择其他应用，查看与该应用对接的渠道。

**您可以按以下方式查看全部活跃渠道：**

* 在AppsFlyer中，从侧边菜单选择**协作**>**渠道对接**>**活跃对接**选项卡。

</Accordion>

<div id="about-the-integrated-partner-page" />

<Accordion title="渠道配置页面说明">

该页面的结构如下：

* **标题**：
  * 渠道名称
  * 相关渠道的专用指南链接；如果您想要查看的渠道没有相应的专用指南，可以直接参考本文内容。
  * 对接状态
  * 选定应用
* **设置选项卡**：选项卡可用性取决于渠道类型和适配功能。
* **页脚**：
  * **返回列表**：返回到筛选后的活跃对接列表。
  * **状态消息：** 选项卡数据的当前状态（如：正在保存、已保存、错误、有未保存的更改）
  * **取消更改：** 撤销最近一次更改且不保存。
  * **保存：** 仅保存当前选项卡中的设置。

#### 适用于各类渠道的设置选项卡

<table><thead><tr><th> </th><th colspan="2">设置选项卡</th><th> </th></tr><tr><th>渠道类型</th><th>对接 </th><th>授权</th><th>说明</th></tr></thead><tbody><tr><td>媒体渠道</td><td>Y</td><td>Y</td><td><p><strong>其他可用选项卡</strong>包括：成本、广告收入、归因链接</p><p>这类渠道包括广告平台、联盟营销平台、直接发行商、程序化广告平台、中国国内广告平台和再营销平台。<br/>归因链接不适用于SRN。</p></td></tr><tr><td>Agency（代理） </td><td>N</td><td>Y</td><td>不作为广告平台的纯代理</td></tr><tr><td>第三方平台</td><td>Y</td><td>N</td><td>分析或营销自动化平台</td></tr><tr><td>平台官方合作渠道 </td><td>Y</td><td>N</td><td> </td></tr></tbody></table>

</Accordion>

## 设置渠道对接（非SRN）

> 🚧 **重要提示！**
>
> 在启用渠道对接时，系统会默认您同意与对方共享某些数据，包括个人信息（如广告 ID、IP 地址）。请确保您拥有合法的依据和相应的权限来共享这些数据。如需限制与合作渠道之间的数据共享，可参考<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">《汇总层级的高级隐私保护框架》</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/apply-privacy-preserving-sdk-methods">《保护用户隐私的SDK配置》</Anchor>中的相关说明操作。

**如需查看对接设置并配置您在该渠道上的投放，请按以下方式操作：**

[从 “合作伙伴集成” 中搜索并选择您的合作伙伴](/docs/set-up-an-integrated-partner#partners-in-the-marketplace)。

> 📘 **注意**
>
> [对接](#d-general-settings)页面中的**通用设置**是广告主必须为所有合作渠道都配置的内容。此外，您还需要配置非SRN广告平台的**归因链接**。其他选项卡中的内容为可选配置。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

各类渠道的对接要求各不相同，有的可能会涉及到本章所述的所有选项。iOS和安卓的设置之间也存在差异。

![set_up_an_integrated_partner.png](https://files.readme.io/441ddfcd784a000099ae75acdb234d32bfe75ab598a34a88c7f9ed651fe8f7ec-15520850610449.png)

请填写完成必填字段。

#### 渠道对接部分详解

下表列出了对接页面中的各个板块，其中包含所有渠道的通用板块以及部分渠道的专用板块。

<Table>
  <thead>
    <tr>
      <th>
        板块
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="a-activate-partner"></span>
        启用渠道
      </td>
      <td>
        将归因链接发送给渠道之前，必须先打开**启用该渠道**开关，并完成对接选项卡中相关的设置。

        * 请勿通过关闭**激活渠道**开关来暂停或关闭广告活动归因
        * 关停渠道对接**可能会对正在投放中的广告活动造成不可逆的损害**。
        * 如需进一步了解渠道激活的方式以及渠道关停的影响，请参考<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。

        **请按以下步骤激活渠道**：

        1. 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。
        2. 搜索并选择相关渠道。您会跳转到对应的渠道配置页面。
        3. 打开<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">**激活渠道开关**</Anchor>。
        4. 点击**保存对接**。
        5. 【可选】如需授权某个渠道<Anchor target="_blank" href="/marketers/zh/docs/manage-data-access-permissions">查看归因到该渠道的数据</Anchor>，请在[授权选项卡](/docs/set-up-an-integrated-partner#广告平台权限)中开通[广告平台权限](/docs/set-up-an-integrated-partner#permissions-tab)。
      </td>
    </tr>
    <tr>
      <td><span id="b-advanced-privacy"></span>
        高级隐私保护
      </td>
      <td>
        仅适用于iOS应用：  
        启用<strong>高级隐私保护（iOS 14.5+）</strong>后，您可以自行<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">调整在回传和报告中与相关渠道共享</Anchor>的信息。该操作会限制相关渠道共享用户标识符信息。请注意：当应用设置中的<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">汇总层级高级隐私保护</Anchor>处于打开状态时，系统会默认启用并锁定<strong>高级隐私保护（iOS 14.5+）</strong>功能。
      </td>
    </tr>
    <tr>
      <td><span id="c-transaction-id"></span>
        Transaction ID
      </td>
      <td>
        仅适用于iOS应用：  
        **共享SKAN交易ID**开关打开即表示您正在与渠道<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">共享SKAdNetwork回传的交易ID</Anchor>。这是为了让渠道解析您的SKAdNetwork转化值。
      </td>
    </tr>
    <tr>
      <td><span id="d-general-settings"></span>
        通用设置
      </td>
      <td>
        **渠道ID - 证书**  
        一些渠道在与AppsFlyer对接时需要证书，渠道侧一般称其为应用ID、账户ID、用户ID或广告平台ID。如果您看到这个字段，请从面板的渠道页面中获取该ID并填入。
      </td>
    </tr>
    <tr>
      <td><span id="non-eu-users"></span>
        非欧盟用户
      </td>
      <td>
        确定是否打开<Anchor target="_blank" href="/marketers/zh/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**非欧盟用户**</Anchor>开关。
      </td>
    </tr>
    <tr>
      <td><span id="e-install-attribution"></span>
        激活归因
      </td>
      <td>
        您可以分别针对广告浏览和广告点击设置不同的归因窗口，对相关用户完成的新增激活（首次打开）进行归因。点击或浏览您广告的用户在指定的归因回溯窗口期内完成激活时，才会被归因到相关渠道。

        * **点击型激活回溯窗口期：** 设置点击到激活的限期，在此期间完成的激活才会被归因到对应的点击。

        **浏览型激活归因：打开该开关后，可对仅浏览而未点击广告的用户所完成的激活进行归因。**

        * **浏览型激活回溯窗口期：** 设置广告浏览到激活的限期，在此期间完成的激活才会被归因到对应的广告展示。

        <Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">进一步了解回溯窗口</Anchor>。
      </td>
    </tr>
    <tr>
      <td><span id="e-re-engagement-attribution"></span>
        再互动归因
      </td>
      <td>
        打开“再互动归因”开关，并设置回溯窗口期，即可对您的现有用户进行再互动归因。非SRN的再互动归因设置位于[“渠道对接”](/docs/set-up-an-integrated-partner#再营销设置)或归因链接选项卡中。

        * **点击型再互动回溯窗口：** 设置从点击到应用打开之间的限期，在此期间完成的应用打开才会被记录为再互动，并归因到对应的点击。

        **浏览型再互动归因**打开该开关后，可对仅浏览而未点击广告的现有用户所完成的再互动进行归因。

        * **浏览型再互动归因回溯窗口：** 设置从广告浏览到应用打开之间的限期，在此期间完成的应用打开才会被记录为再互动，并归因到对应的广告展示。

        <Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">进一步了解回溯窗口</Anchor>。
      </td>
    </tr>
    <tr>
      <td><span id="reengagement-window"></span>
        再互动窗口期
      </td>
      <td>
        设置该窗口期后，在此期间发生的应用内事件会被记录再互动转化，且促成该事件的渠道会被归因为主要带量渠道。详情请见<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide#setup-reengagement-window">此文档</Anchor>。
      </td>
    </tr>
    <tr>
      <td><span id="ignore-active-users"></span>
        再营销广告中忽略活跃用户
      </td>
      <td>
        设置不活跃窗口期后，可忽略在此期间的活跃用户，避免将其行为记录为再营销转化。详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-retargeting-inactivity-window">再营销中的不活跃窗口</Anchor>说明。

        **适用于**<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">**SRN**</Anchor>**的设置方式：**

        1. 进入渠道对接选项卡，打开**再互动归因**的开关。
        2. 打开**在再营销广告中忽略活跃用户**的开关。
        3. 设置**不活跃窗口**。

        **适用于非SRN的设置方式：**

        1. 进入归因链接选项卡，打开**再营销设置**的开关。
        2. 打开**在再营销广告中忽略活跃用户**的开关。
        3. 设置**不活跃窗口**。
      </td>
    </tr>
    <tr>
      <td><span id="e-cross-platform-attribution"></span>
        跨平台归因
      </td>
      <td>
        如果您打开了**跨平台归因具有同等优先级**的开关，选定时段内的跨平台展示会与确定性点击具有同等的归因优先级。
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-attribution"></span>
        预装归因
      </td>
      <td>
        打开**预装归因**开关后，就可以将激活归因到<Anchor target="_blank" href="/marketers/zh/docs/measure-preload-campaigns-with-google-play-install">预装推广</Anchor>。您可以设置**预装回溯窗口**——用户激活设备后，只有在这个窗口期内发生的预装应用激活才会被归因到相关渠道。
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-equal-attribution-priority"></span>
        预装归因同等优先级
      </td>
      <td>
        如果您打开了**预装归因具有同等优先级**的开关，指定回溯窗口内的预装互动就会与确定性点击具有同等的<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#归因方法">归因优先级</Anchor>。
      </td>
    </tr>
    <tr>
      <td><span id="advanced-data-sharing"></span>
        高级数据共享
      </td>
      <td>
        **高级数据共享开关**打开时，可通过归因链接与渠道共享额外数据。  
        **请注意：** 这个数据共享方式不同于<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-aggregate-event-measurement-aem-for-ios#aem数据共享">Meta ads的AEM高级数据共享</Anchor>。
      </td>
    </tr>
    <tr>
      <td><span id="default-postbacks"></span>
        默认回传
      </td>
      <td>
        启用渠道对接后，就会向渠道发送默认回传，与其共享应用打开前发生的用户行为，如激活、被拦截的激活以及再互动等。

        > 📘 **注意**
        >
        > * 被拦截的假量是指被<Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide">Protect360</Anchor>屏蔽的应用内事件，或者未通过自定义验证规则的事件。如果出现被拦截的假量，请与渠道确认他们已启用AppsFlyer的假量拦截对接。
        > * 技术合作平台会收到激活和再互动的默认回传。部分情况下，这些平台还会收到应用内激活回传。

        **如需配置渠道的默认回传**，请选择回传数据的流量来源，具体如下：

        * **仅该合作渠道**：仅回传归因到该渠道的事件，也就是说完成这些事件的用户来自该渠道。  
          **请注意：** 在以下场景中，默认回传总是设定为**仅该合作渠道**：
          * 被拦截的激活
          * 代理（具有相关[权限](/docs/set-up-an-integrated-partner#代理权限)）
        * **所有媒体渠道，包括自然流量**：回传归因到任何渠道以及自然量的事件，也就是说完成这些事件的用户来自各个渠道。
        * **停用**：不向该渠道发送默认回传。
      </td>
    </tr>
    <tr>
      <td><span id="g-in-app-event-postback-configuration"></span>
        <Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration">应用内事件回传</Anchor>
      </td>
      <td>
        通过回传将AppsFlyer事件<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#事件映射">映射</Anchor>到渠道。启用回传后，被拦截的应用内事件（被Protect360屏蔽的事件或未通过验证的事件）也会被一并发送。

        **请按以下步骤配置应用内事件回传：**

        1. 设置**渠道ID** （如有需要）。
        2. 启用**应用内事件回传**。
        3. 设置**应用内事件回传窗口**（如有需要）。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">应用内事件回传窗口配置</Anchor>。
        4. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。
        5. 按照<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#映射方式">映射方式</Anchor>说明完成必要的参数配置。
        6. 【可选】点击altconditional-iae-postbacks-icon.pngalt设置应用内事件的<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">发送条件</Anchor>。

        | 参数名称 | 说明 |
        | --- | --- |
        | <span id="appsflyer-event"></span>**AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。  <br />**提示**：如果找不到您要查看的事件：<br /><br />* 请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。<br />* 在**AppsFlyer事件**中输入该事件的名称，然后点击**创建自定义事件**。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">自定义事件映射</Anchor>。 |
        | <span id="mapped-to-partner-event"></span>**渠道映射事件** | Meta Web为每个事件定义的专属名称或ID。<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#映射方式">映射配置包括以下几种</Anchor>：<br /><br />* **文本字段：** 从渠道处获取相应的事件ID。<br />* **下拉菜单：** 选择最合适的渠道侧预定义事件。<br />* **按原样**：按原样发送事件，不对事件名称进行映射。 |
        | <span id="for-users-from"></span>**事件来源** | 选择事件回传的范围：<br /><br />* **仅该合作渠道**：仅回传归因到该渠道的事件，也就是说完成这些事件的用户来自该渠道。<br />* **所有媒体渠道，包括自然流量**：回传归因到任何渠道以及自然量的事件，也就是说完成这些事件的用户来自各个渠道。 |
        | <span id="including"></span>**回传内容** | 您可以使用以下三个选项界定回传到渠道的<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#回传内容">事件数据</Anchor>：<br /><br />* **不发送值与收入：** 仅发送不带任何参数的事件本身（即没有值或收入）。<br />* **仅发送值：** 发送**除**收入以外的所有参数。<br />* **发送值与收入**：发送所有事件参数，**包括**收入（若有）。 |

         说明：

        * 在对接选项卡中针对具体渠道映射的事件在标准回传和<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAN回传</Anchor>中都适用。
        * 回传会实时发送到渠道。
        * 您可以从下拉菜单中选择AppsFlyer事件名称，也可以直接输入事件名称。  
          输入的事件名称前后可以带下划线，但必须与AppsFlyer发送的事件名称一致。
        * <strong>重要提示！</strong>事件名称区分大小写。为避免出现数据差异，请确保所有媒体渠道和应用程序的各个版本中使用的事件名称完全一致。
        * 如果**对接**选项卡中不存在**应用内事件回传**部分，说明该渠道尚未在其初步配置中设置AppsFlyer应用内事件记录。有此情况的渠道可以通过<Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">渠道支持微件</Anchor>联系AppsFlyer渠道团队，从而完成对接。
        * 为了防止广告主无意中与第三方平台分享过多信息, 我们已从2019年3月起移除了<strong>发送所有事件（卸载、session和af\_ad\_revenue除外）</strong>的选项。在此之前配置的第三方平台仍保留此设置选项。

        相关文档：

        * <Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration">应用内事件回传</Anchor>配置
        * <Anchor target="_blank" href="/marketers/zh/docs/share-ad-revenue-data-with-partners#ad-revenue-event-postbacks-for-ad-networks">广告收入事件回传</Anchor>配置
      </td>
    </tr>
    <tr>
      <td><span id="h"></span>
        保存对接
      </td>
      <td>
        修改设置后点击**保存对接**。
      </td>
    </tr>
    <tr>
      <td><span id="i-connect-more-apps-optional"></span>
        关联其他应用（可选）
      </td>
      <td>
        您可以在保存对接后留在配置页面，将其他应用也对接到该渠道。

        1. 点击页面左上角渠道名称下方的应用名称，打开应用列表。
        2. 在下拉菜单中选择一个其他应用。
        3. 为选定应用完成对接设置。
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

请生成并保存归因链接，用于（非SRN）广告平台上的投放。然后将归因链接发送给渠道，从而对具体的广告系列、广告组或单个广告进行归因。

**请注意：** SRN不使用广告主生成的归因链接，所以此选项卡不适用于SRN上的广告投放。

**请按以下方式生成归因链接** ：

1. 选择**使用单平台链接**或**使用OneLink**。

   如果符合以下任意一种情况，请选择**使用单平台链接**：

   * 您只打算使用<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">URI schemes</Anchor>调起应用。
   * 您不需要在URL中加入深度链接功能。

   如果符合以下任意一种情况，请选择**使用OneLink**：

   * 您想要使用同一个链接进行安卓和iOS应用的推广。
   * 您想要使用安卓的App Link或iOS的Universal Link调起应用。
   * 您需要链接带有深度链接功能。

   **请注意**：选择OneLink会改变点击记录链接，从具体应用的专用链接变为<Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink链接</Anchor>。
2. 如果您选择**使用OneLink**：
   1. 需要选择一个OneLink模板，用于打开应用（并实现深度链接）。
   2. 【可选】输入**深度链接值**。
   3. 【可选】输入**其他的深度链接值**。
3. 根据需要添加用于<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#安卓专用参数">安卓</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#ios专用参数">iOS</Anchor>应用的参数。
4. 【可选】选择其他的归因参数。

#### 归因链接参数

[![attribution-link-parameters-en_us.png](https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png)](https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png)

在归因链接中添加参数后，您可以对数据进行深度剖析。归因链接中预定义的参数，可以通过添加参数和定义新值的方式进行编辑。保存归因链接时，系统会保存此选项卡中配置的所有参数。

选择要添加到归因链接的参数。

#### 归因链接参数

| 特点 | 说明 | 归因链接中的参数 |
| --- | --- | --- |
| Campaign | **这是您必须配置的参数。**  <br />比较该渠道投放的不同广告系列。 | c |
| 广告组 | 比较该渠道投放的某个广告系列下不同的广告组。 | af\_adset |
| 广告名称 | 比较该渠道投放的某个广告系列下某个广告组中的不同素材。 | af\_ad |
| 自渠道和次级子渠道 | **这是您必须配置的参数。**<br /><br />设置子渠道后可将激活归因到具体的媒体平台。<br /><br />请务必通过归因链接将子渠道信息发送给AppsFlyer，因为：<ul><li>这能让该媒体的数据更加清晰透明</li><li>AppsFlyer会通过该信息来识别并剔除作弊媒体以及其他的虚假流量。</li></ul>请注意：不设置子渠道（Site ID）不会影响归因，详情请见<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#site-id-parameter">子渠道参数</Anchor>。<br /><br />如果您在多个媒体上投放, 建议限制子渠道的数量，并使用次级子渠道参数，以免<Anchor target="_blank" href="/marketers/zh/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">超出子渠道数量</Anchor>上限。 | af\_siteid和af\_sub\_siteid |
| 可配置参数 | 您共有5个可配置参数可以使用，并为其添加对应的参数值。请注意，这些参数会被解析并出现在原始数据报告中，便于汇总或筛选数据。 | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |

您可在新参数框中键入其他参数，从而将其添加到归因链接中，这些参数包括<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">AppsFlyer的所有可用URL参数</Anchor>。请注意：在归因链接中，只有URI scheme和OneLink参数是加密的。

#### 再营销设置

**启用再营销时**：AppsFlyer会在归因链接中添加`&is_retargeting=true`，将其标记为<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销</Anchor>链接，与用户获取链接做出区分。  
**归因链接参数：** is\_retargeting

将归因链接用于再营销投放的方法如下：

1. 打开**再营销设置**开关。
2. 【可选】如果您想要通过URI scheme来调起应用，请输入相关的URI scheme。  
   **请注意**：
   * 建议您将URI scheme作为备用方案，以在Universal Link或App Link失效时调起应用。
   * 您在此处添加的URI scheme会覆盖OneLink模板中设置的所有其他URI scheme。
   * URI scheme会以af\_dp参数的形式体现在归因链接中。
3. 【可选】打开**在再营销广告中忽略活跃用户**的开关。
4. 设置“不活跃窗口期”，以界定哪些用户是活跃用户，哪些是沉睡用户。
5. 设置再互动窗口期。用户再次打开应用后，在该窗口期以内的应用内事件会归因到再营销渠道。
   * 这个值可以设置为数天（1-90天）、数小时（至多23小时）或用户的整个生命周期。
   * 再互动窗口期会以af\_reengagement\_window参数的形式体现在归因链接中。

#### 点击型归因

您可通过该设置来调整**点击到激活的最长时限**。只有在回溯窗口内发生的激活（首次启动）才会被归因。

窗口期时长可选范围：1-23小时或1-30天。

**归因链接参数：** af\_click\_lookback

详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">点击回溯窗口</Anchor>。

**点击归因链接**

[![click-through-attribution-link_en-us.png](https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png)](https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png)

上方截图中显示了包含所有设置信息的归因链接。您可以点击**保存归因链接**进行保存，以留作参考。

**复制点击归因链接的步骤如下：**

1. 点击**保存归因链接**。
2. 将生成的链接复制下来。

当您的潜在客户点击广告时，您可将链接发送给相应的渠道进行激活。

#### 浏览型归因窗口期

您可通过该设置调整**展现到激活的最长时限**。如果用户浏览广告后在该回溯窗口内激活（首次启动）应用（且未点击其他相关广告），这样的广告展示才会归因到展示广告的渠道。

您可以在1-24小时的范围内自行设置该窗口期的时长。

**归因链接参数:** af\_viewthrough\_lookback

详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">浏览型归因</Anchor>。

**展示归因链接**

[![impressions-attribution-link_en-us.png](https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png)](https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png)

展示归因链接里含有与点击归因链接相似的归因数据（除了窗口期不同之外）。您可以点击**保存归因链接**进行保存，以留作参考。

点击“保存归因链接”，然后将生成的链接复制下来。

**请按以下步骤复制展示归因链接：**

1. 点击**保存归因链接**。
2. 将生成的链接复制下来。

将该链接发送到渠道，当用户观看相应广告超过1秒时触发该链接中的归因流程。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

* 您的对接渠道可以通过点击或Cost API上报成本数据。
* 建议您配置Cost API（需要购买ROI360）。
* 成本API包括点击次数和展现次数报告。详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">广告平台成本对接表</Anchor>，其中详细说明了适用维度、指标和功能。

> 📘 **注意**
>
> 如果广告主通过代理商投放广告，代理商需要与相关渠道进行对接，而广告主不需要。如果广告主和代理商使用同一个证书针对同一个应用与渠道对接，成本数据就会出现重复。

#### 通过API启用成本数据

**成本API的启用方式如下**：

* 请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">对接指南</Anchor>进行操作。

#### 成本数据同步状态

您可以在成本（及广告收入）对接状态面板或单独的广告平台面板中查看AppsFlyer最近一次获取匹配成本数据的时间以及<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">API状态</Anchor>。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

如果您作为发行商在应用程序中展示广告，就可以使用广告收入功能将广告收入归因到带来用户的媒体渠道。<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution">详情请见广告收入归因。</Anchor>

#### 启用广告收入归因

1. 确认渠道支持的<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#list-of-ad-revenue-integrated-partners">归因级别</Anchor>（汇总级别或用户级别）。
2. 按照<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#启用方式">广告收入对接指南</Anchor>进行设置。

#### 广告收入API状态信息

| 状态码 | 说明/所需操作 |
| --- | --- |
| Active（活跃） | 对接处于活跃状态，正在拉取数据。 |
| No data to pull was found.（未发现可拉取的数据） | 连接成功，但渠道没有与此应用相关的任何数据。 |
| Partner API not responding.Contact AppsFlyer support.（渠道API未响应，请联系AppsFlyer技术支持团队） | 渠道的服务器没有对AppsFlyer作出响应。 |
| Invalid credentials.Enter updated credentials.（证书无效，请输入更新后的证书信息） |  |
| Something went wrong.Contact AppsFlyer support.（渠道API未响应，请联系AppsFlyer技术支持团队） | 出现了技术问题。 |
| Partner data not yet ready.If the problem persists, contact AppsFlyer support.（渠道数据尚未就绪。如果持续出现问题，请联系AppsFlyer技术支持团队。） |  |
| Data is being processed and will be available soon.（数据正在处理中，请稍等。） | 我们目前正在处理从渠道处接收到的数据，您稍后可在面板和报告中看到这些数据。 |
| Data was never successfully pulled（未成功拉取数据） | 如果此状态持续长达一小时，请联系AppsFlyer技术支持团队。 |

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

您可以向广告平台和代理开放具体权限，允许其访问您的数据并完成各种操作。

* 即使您未启用相关渠道的对接，也可对其进行授权。
* **由代理设置的广告平台：** 如果某个渠道是由代理设置的，那么广告主无法查看该渠道的启用状态或其权限。
* 如果对方仅作为代理与您合作，请忽略**广告平台权限**部分，在**代理权限**部分中进行权限管理。通过开启代理权限开关，您可以允许代理机构控制广告网络权限。有关更多信息，请参阅<Anchor target="_blank" href="/partners/zh/docs/getting-started-agency-onboarding#广告主授权的作用">获得营销人员许可意味着什么</Anchor>中的注释。
* 授权仅对当前选定应用生效。

#### 广告平台权限

开启**广告平台权限**后，广告平台即可访问您的面板，您也可以再向其授予其他权限，详情请见下表。

> 📘 **注意**
>
> 授权后，广告平台可访问的数据仅限其自有数据。

**如需授权给广告平台及其团队成员：**

1. 打开**广告平台权限**开关。

   * 广告平台的面板上会显示您的应用。
   * 广告平台管理员可以<Anchor target="_blank" href="/marketers/zh/docs/manage-data-access-permissions">看到该应用的基本数据</Anchor>。

   **请注意：** 广告网络团队成员由广告网络直接管理。如果您希望特定团队成员有访问权限，请联系您的广告网络。<Anchor target="_blank" href="/partners/zh/docs/user-management-for-ad-networks#creating-a-user">了解详情</Anchor>
2. 选择要向广告平台开放的其他权限：

| **权限** | **授权后的可用功能** |
| --- | --- |
| <span id="configure-integration"></span>配置对接 | 广告平台可以在渠道对接选项卡中修改参数，但不能更改应用内事件回传配置。 |
| <span id="configure-inapp-event-postbacks"></span>配置应用内事件回传 | 广告平台可以配置应用内事件回传，即创建、定义（映射）和更改回传设置。<br /><br />**请注意**！如果您向广告平台同时开放应用内事件和**渠道对接**的配置权限，该广告平台就能够访问所有事件，包括自然量以及所有带量渠道的非自然量。 |
| <span id="access-retention-report"></span>访问留存和群组报告 | 代理仅可以访问自己带来的流量所形成的留存/群组数据。 |
| <span id="access-aggregate-loyal-users-data"></span>访问忠诚用户汇总数据 | 广告平台可以访问其平台的<Anchor target="_blank" href="/marketers/zh/docs/about-a-loyal-user">忠诚用户</Anchor>指标。 |
| <span id="access-aggregate-conversions-data"></span>访问汇总转化数据。 | 广告平台可以访问自己平台的汇总转化事件指标报告，包括激活、再互动、重装激活和再归因，举例来说，<Anchor target="_blank" href="/partners/zh/docs/aggregated-campaign-performance-report-for-ad-networks">广告平台的汇总投放效果报告</Anchor>。 |
| <span id="access-aggregate-inapp-events-data"></span>访问汇总应用内事件数据 | 广告平台可以：<ul><li>访问汇总级别的应用内事件数据报告。访问权限覆盖选定应用的所有应用内事件数据，包括 Protect360的应用内事件数据。也就是说，除了在回传配置中映射到该平台的事件之外，该平台可以访问其他事件。</li><li>访问广告变现数据汇总报告，其中可能包括其他媒体渠道的广告变现事件。</li></ul> |
| <span id="view-validation-rules"></span>查看验证规则 | 广告平台可以查看验证规则的详细信息。 |
| <span id="access-aggregate-revenue-data"></span>访问收入汇总数据 | 广告平台可以访问自身流量的应用内购及广告收入数据汇总报告。**请注意：** 广告平台不能通过此权限直接识别广告收入来自哪个平台。但是，如果您设置的变现事件名称中含有渠道名称，则可能会无意中透露变现平台的身份。 |
| <span id="use-ad-spend-ingestion"></span>使用广告消耗数据上传 | 广告平台可以：<ul><li>访问<Anchor target="_blank" href="/marketers/zh/docs/import-cost-data">广告消耗数据上传</Anchor>界面。此界面仅展示该平台有权访问的应用。</li><li>发送广告消耗文件，用于接入数据。</li></ul> |
| <span id="access-protect360-dashboard-raw-data"></span>访问Protect360面板和原始数据 | 广告平台可以：<ul><li>访问其Protect360面板（包括<Anchor target="_blank" href="/marketers/zh/docs/basic-fraud-detection-and-insights-with-protectlite-dashboard-and-reporting">ProtectLITE</Anchor>）。</li><li>查看Protect360、验证规则、以及原始数据（如果套餐中包含）。ProtectLITE不包括原始数据权限。</li></ul>**请注意：** 如果您购买了<Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide">Protect360</Anchor>，广告平台就能看到完整的面板。如果没有Protect360，则该平台只能看到精简面板。 |
| <span id="access-ad-revenue-raw-data"></span>访问广告收入原始数据 | <Anchor target="_blank" href="/partners/zh/docs/ad-revenue-signals-for-ua-ad-networks">广告平台可以访问其广告收入数据，用于UA优化</Anchor>。  <br />**请注意：** 此权限仅在已购买<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>的应用下可用。 |

#### 代理权限

如需详细了解各项代理权限的具体内容，请参考<Anchor target="_blank" href="/partners/zh/docs/getting-started-agency-onboarding#广告主授权的作用">此文档</Anchor>。

> 🚧 **重要提示！**
>
> 与代理机构合作时，关闭集成合作伙伴并不会自动禁用与该合作伙伴关联的代理机构的某些归因功能：
>
> 要完全停用代理机构的这些功能，广告商必须在停用合作伙伴之前手动关闭以下设置：
>
> 1.浏览型激活归因
> 2. 跨平台归因具有同等优先级
>
> 只有在禁用这些开关后，广告商才能继续停用合作伙伴。
>
> **请注意：** 如果广告商在未事先关闭这些设置的情况下停用了合作伙伴，则代理机构可以继续使用这些归因功能。

**请注意：该控件关闭时，代理商带来的新增用户不会归因到该代理，也不会出现在其面板和数据中。详情请见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation#代理权限">代理启用说明</Anchor>。**

**请按以下步骤向代理商授权：**

1. 打开**代理权限**开关。
2. 选择要向代理开放的权限：

| **权限** | **授权后的可用功能** |
| --- | --- |
| <span id="change-advanced-privacy-configuration"></span>更改高级隐私配置 | 代理可以更改广告平台的<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">高级隐私保护数据共享</Anchor>设置。   <br />**请注意：** 该权限不适用于TikTok for Business和Snapchat，这些渠道的高级隐私保护设置会显示为灰色，锁定在广告主所配置的选项，无法更改。 |
| <span id="access-retention-and-cohort-reports"></span>访问留存和群组报告 | 代理仅可以访问自己带来的流量所形成的留存/群组数据。 |
| <span id="access-aggregate-organic-data"></span>访问汇总自然数据 | 代理可以访问汇总的自然量数据。 |
| <span id="view-validation-rules::6872643b"></span>查看验证规则 | 代理可以查看验证规则的详细信息。 |
| <span id="add-validation-rules"></span>添加验证规则 | 代理可以添加并编辑验证规则。必须先打开**查看验证规则**开关后才能使用该控件。   <br />**请注意**：代理无法编辑由广告主创建的规则。 |
| <span id="access-rawdata-reports"></span>访问原始数据报告 | 对于归因到代理的流量，代理可以访问其原始数据。广告主不能对相关报告中代理可以查看的事件设限。 |
| <span id="access-protect360-dashboard-raw-data::dd9829fd"></span>访问Protect360面板和原始数据 | 代理可以：<ul><li>访问Protect360汇总面板</li><li>查看Protect360、验证规则、以及原始数据（如果套餐中包含）</li></ul>**请注意：** 如果广告主通过代理商在广告平台上进行投放，并且需要让广告平台和代理商都能取数，那么广告主必须在AF中同时对接代理商和广告平台，并为他们开通数据权限。如果仅接入了代理商并为其开通了权限，这种情况下广告平台是没有数据权限的。 |
| <span id="configure-inapp-event-postbacks::8743ba60"></span>配置应用内事件回传 | 代理可以配置您指定的应用内事件回传：<ul><li>**添加事件：** 在下拉菜单中选择您同意为代理开通权限的事件。</li></ul>对于您指定的事件，代理可用的配置选项如下：<ul><li>**发送事件收入：** 授权后，代理可在发送的事件中包含收入值。</li><li>**事件发送选项：**<ul><li>**仅该合作渠道：** 选择此选项后，代理可以针对归因到自身流量的事件配置回传。</li><li>**所有媒体渠道，包括自然流量：** 选择此选项后，代理可以针对归因到所有媒体渠道、代理和自然量的事件配置回传。</li></ul></li></ul> |

如需进一步了解代理合作的相关事宜，请参考<Anchor target="_blank" href="/partners/zh/docs/about-agency-accounts#代理对广告主数据的访问权限">此文档</Anchor>。

</Accordion>

## 测试对接

完成渠道配置后，强烈建议您在正式投放前先对新添加的渠道进行对接测试。由于设置过程中最容易发生错误，因此建议提前测试，避免在投入大量资源后才发现归因数据丢失或有误。

> 📘 **注意**
>
> 在测试对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/testing-the-sdk-integration-for-marketers">测试相关应用的基础SDK对接</Anchor>，包括自然激活和非自然激活。

<div id="test-the-attribution-link-for-nonsrns" />

<Accordion title="测试非SRN的归因链接">

非SRN广告平台（占对接平台总量的99.5%）使用AppsFlyer的归因链接。自有媒体的归因与其相似，通过AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink链接</Anchor>完成。

归因正确与否取决于归因链接上的参数，因此建议您在使用非SRN广告平台或自定义归因链接投放广告前，请先测试这些链接。

**请按以下步骤测试归因链接：**

1. 创建[归因链接](/docs/set-up-an-integrated-partner#attribution-link-tab)。
2. 通过电子邮件或二维码，将新建的归因链接发送到您<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices">注册的</Anchor>测试（加白）设备。
3. 点击链接，确保可以跳转到应用商店。
4. 安装相关应用。
5. 打开该应用。
6. 查看AppsFlyer面板，检查该次激活是否出现在对应的渠道名称下。从激活完成到面板显示最多需要30分钟。
7. 在广告系列层级（在数据总览页面顶部的**媒体渠道**下拉菜单中选择相应渠道）检查该次激活是否出现在正确的广告系列名称下。
8. 如有必要，请继续细化检查范围，查看广告组和广告是否正确对应。

</Accordion>

<div id="test-the-srn-integration" />

<Accordion title="测试SRN对接">

Meta ads、Apple Search Ads和Google Ads等SRN不依赖外部归因链接进行归因，而是接收AppsFlyer的查询，自行归因后返回答案。因此在测试对接时不能完全脱离于平台系统，这与常规平台的对接测试不同。您必须单独测试每个合作SRN的对接。

**请按以下步骤测试SRN对接**[：](/docs/set-up-an-integrated-partner)

1. 请按<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#与appsflyer对接的srn">相关SRN的专用配置</Anchor>指南，在AppsFlyer后台对其进行全面配置。
2. 以少量预算通过SRN渠道投放广告。
3. 当渠道面板出现新增激活时，在AppsFlyer控制面板中检查这些激活是否出现在对应的渠道名称下。
4. 在数据总览面板顶部的**媒体渠道**下拉菜单中选择该渠道，然后深入到广告系列层级，检查激活是否出现在正确的广告系列名称下。从激活完成到面板显示最多需要30分钟。
5. 如有必要，请继续细化检查范围，查看广告组和广告是否正确对应。

如果一切正常，就可以投入更多预算通过该渠道进行投放。一个SRN渠道的对接只需测试一次。也就是说，您无需针对每个广告系列进行测试。

</Accordion>

<div id="test-the-raw-data" />

<Accordion title="测试原始数据">

如果您订阅的产品中包含原始数据权限，建议您测试原始数据。

**请按以下步骤测试原始数据**：

1. 完成上述测试后，前往**报告**><Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">**导出数据**</Anchor> 。
2. 选择已测试完毕的媒体渠道。
3. 激活后最多需要等待15分钟，然后下载激活报告。
4. 确认报告中包含来自该渠道的激活记录，并正常显示媒体渠道、广告系列名称、触达时间和类型、设备ID（如适用）、代理名称（报告中显示为 "Partner"）等参数。

> 🚧 **重要提示！**
>
> 有些广告平台需要进行特殊操作才能收集用户级别的原始数据。
>
> 如果您在面板上看到了新增激活, 但在原始数据中看不到对应的数据, 请在帮助中心中查看针对具体广告平台的专用指南（如<Anchor target="_blank" href="/marketers/zh/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies#do-you-make-twitters-raw-data-available-to-agencies">X Ads</Anchor>）。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 01H80XGTBQ6MAK3VG0X6QMAYMP=%E6%A6%82%E8%A7%88 01H80XGTBQPPZV7WR5JBHQFB0B=partner-types-in-the-ecosystem 01H80XGTBQ4CPMBRVSMM7TD4VD=partners-in-the-marketplace invite-new-partners-to-appsflyer=%E5%9C%A8appsflyer%E4%B8%AD%E6%B7%BB%E5%8A%A0%E6%96%B0%E7%9A%84%E5%AF%B9%E6%8E%A5%E6%B8%A0%E9%81%93 01H80XGTBQRJ78XCGNZBTJVYEQ=%E5%9C%A8appsflyer%E4%B8%AD%E6%B7%BB%E5%8A%A0%E6%96%B0%E7%9A%84%E5%AF%B9%E6%8E%A5%E6%B8%A0%E9%81%93 01H80XGTBQ8VF6V9WARZRECWVR=your-integrated-partners 01H80XGTBQJQYD3R46H95WVVM0=%E6%B3%A8%E6%84%8F 01H80XGTBQ5BE24X219BVZBMDG=about-the-integrated-partner-page applicable-settings-tabs-per-partner-type=%E9%80%82%E7%94%A8%E4%BA%8E%E5%90%84%E7%B1%BB%E6%B8%A0%E9%81%93%E7%9A%84%E8%AE%BE%E7%BD%AE%E9%80%89%E9%A1%B9%E5%8D%A1 01H80XGTBQPP74G38YNNYVXWP2=%E9%80%82%E7%94%A8%E4%BA%8E%E5%90%84%E7%B1%BB%E6%B8%A0%E9%81%93%E7%9A%84%E8%AE%BE%E7%BD%AE%E9%80%89%E9%A1%B9%E5%8D%A1 set-up-a-partner-nonsrn=%E8%AE%BE%E7%BD%AE%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5%E9%9D%9Esrn 01H80XGTBQXNQ7SFXZ5PBQGS1V=%E8%AE%BE%E7%BD%AE%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5%E9%9D%9Esrn 01JDM949M75Q3BAG6M65DYMHZT=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA 01H80XGTBQZXZARZCM61CMG0K3=%E6%B3%A8%E6%84%8F-1 01H80XGTBQB9T22GQ7CSHS2S1X=integration-tab integration-tab-sections=%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5%E9%83%A8%E5%88%86%E8%AF%A6%E8%A7%A3 01H80XGTBQ0531M2RS3DH7E4Z0=%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5%E9%83%A8%E5%88%86%E8%AF%A6%E8%A7%A3 d-general%20settings=d-general-settings default%20postbacks=default-postbacks 01H80XGTBQ4MPGGKSZW0D9GG9H=%E6%B3%A8%E6%84%8F-2 01H80XGTBRT41FGP5107G96TWC=attribution-link-tab attribution-link-parameters=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 01H80XGTBRPENCTCRK8PPYSCGX=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 attribution-link-parameters::3874dfb8=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0-1 01H80XGTBR8630SEV80K9RD6V9=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0-1 retargeting-settings=%E5%86%8D%E8%90%A5%E9%94%80%E8%AE%BE%E7%BD%AE 01H80XGTBRT57QMPRENYSS81Z3=%E5%86%8D%E8%90%A5%E9%94%80%E8%AE%BE%E7%BD%AE clickthrough-attribution=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 01H80XGTBREZTJ6B0Y08JCKN1E=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 viewthrough-attribution-lookback-window=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F 01H80XGTBRXC1YYX4FW94NDR2Z=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F 01H80XGTBRERTJ9XHGDV416T7V=cost-tab 01H80XGTBR54TQ0DNY1JR36GXN=%E6%B3%A8%E6%84%8F-3 enabling-cost-data-by-api=%E9%80%9A%E8%BF%87api%E5%90%AF%E7%94%A8%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE 01H80XGTBRV6BHWS76HWHK933M=%E9%80%9A%E8%BF%87api%E5%90%AF%E7%94%A8%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE cost-data-sync-status=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E5%90%8C%E6%AD%A5%E7%8A%B6%E6%80%81 01H80XGTBRPWREFYFXA0A6VD47=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E5%90%8C%E6%AD%A5%E7%8A%B6%E6%80%81 01H80XGTBRJ1AKX2Q7WPXFVA49=ad-revenue-tab enable-ad-revenue-attribution=%E5%90%AF%E7%94%A8%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E5%BD%92%E5%9B%A0 01H80XGTBRHE9PPRA9X46M4TGZ=%E5%90%AF%E7%94%A8%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E5%BD%92%E5%9B%A0 ad-revenue-api-status-messages=%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5api%E7%8A%B6%E6%80%81%E4%BF%A1%E6%81%AF 01H80XGTBRNT4K4ZNPKVV25ESJ=%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5api%E7%8A%B6%E6%80%81%E4%BF%A1%E6%81%AF 01H80XGTBRGXS97JMG45QR4BEQ=permissions-tab ad-network-permissions=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90 01H80XGTBRS9BTT2F8F95BCE9Z=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90 h_01HGFD78GRX9P2G58W21QZN4X7=%E6%B3%A8%E6%84%8F-4 agency-permissions=%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90 01H80XGTBRTVP407AAA77N090E=%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90 h_01KC9MDDRPTB05PV6NCGZVFRMJ=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 test-the-integration=%E6%B5%8B%E8%AF%95%E5%AF%B9%E6%8E%A5 01H80XGTBSEWPHCPQF29XD6Y4W=%E6%B5%8B%E8%AF%95%E5%AF%B9%E6%8E%A5 01H80XGTBSTHG2FC2M31F83RGK=%E6%B3%A8%E6%84%8F-5 01H80XGTBS4P06757QXHDKYAHT=test-the-attribution-link-for-nonsrns 01H80XGTBS2K9SPQ1MTAV7GP2H=test-the-srn-integration 01H80XGTBSTBV4RC3V279WNNB1=test-the-raw-data 01H80XGTBSN0VAX76XW9Y77T04=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2" />
