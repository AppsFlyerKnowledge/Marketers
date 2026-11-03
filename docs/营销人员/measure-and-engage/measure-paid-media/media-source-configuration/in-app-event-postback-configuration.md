---
title: 应用内事件回传配置
metadata:
  keywords:
    - In-App Events
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-11T08:47:14Z'
  edited_at: '2026-10-14T10:10:23Z'
  id: 208439256
  locale: zh-cn
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/zh-cn/articles/208439256
---
> **概要：** 本文介绍了如何使用应用事件数据来衡量应用互动及用户质量，并优化投放。

## 速览

广告主可通过应用内事件衡量用户与应用的互动，并比较不同渠道的用户质量，以打造高度契合的拉新策略。广告平台可通过实时发送的回传获得应用内事件数据，并使用该信息优化广告投放或投放CPA/CPE广告。<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">进一步了解富应用内事件</Anchor>。

## 选择要回传的应用内事件

广告主可以通过本文所述的回传设置，选择向广告平台发送哪些事件的回传。

> 📘 **注意**
>
> * 应用内事件也包括**被拦截的事件**，即被Protect360屏蔽的应用内事件，或不符合指定验证规则的事件。
> * 如果**对接**选项卡中不存在**应用内事件回传**部分，说明该渠道尚未在其初步配置中设置AppsFlyer应用内事件记录。有此情况的渠道可以通过<Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">渠道支持微件</Anchor>联系AppsFlyer渠道团队，从而完成对接。

## 应用内事件回传窗口期

投放<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary#cpa">CPA广告</Anchor>的广告主可以配置应用内事件回传窗口期，转化发生后过了这个窗口期就不再发送事件回传。

举例来说，假设您为用户激活后15天内发生的事件付费，则窗口期设置如下：

<Image alt="15-day_in_app_event_postback_setting.png" src="https://files.readme.io/6ffcd335b85334015f518895b317d3a5e273f4e00c31e3694c0f95a22ba6d4fb-33379700644497.png" width="529px" />

窗口期过后不再发送回传，也不会通知广告平台，但AppsFlyer仍会记录相关事件，并归因到对应的广告平台。

回传总是按照**当前**的窗口期设置来发送。请参考以下示例：

| 1月1日 | 窗口期设为15天。<br /><br />用户激活应用。 |
| --- | --- |
| 1月2日 | 窗口期更改到10天。 |
| 1月14日 | 用户完成一个购买事件。<br /><br />不向广告平台发送该事件的回传，因为该事件已经不在当前窗口期（10天）的范围内。 |
| 1月15日 | 窗口期更改为20天。 |
| 1月18日 | 用户再次完成购买事件。<br /><br />向广告平台发送该事件的回传，因为该事件仍在当前窗口期（20天）的范围内。 |

> 📘 **注意**
>
> 当选择 该[所有媒体来源，包括有机设置](#回传中的事件来源选项)时，此规则不适用。在这种情况下，配置此设置的合作伙伴会收到每个转化事件的回调，即使该事件被归因于其他合作伙伴，只要事件发生在为配置该设置的合作伙伴定义的回调窗口内。

### 默认回传窗口

首次设置应用内事件回传时，窗口期默认为六个月。

> 📘 **注意**
>
> 对于2019年7月30日之前开始的应用内事件回传，窗口期默认为“全周期”。也就是说，在这种情况下AF总是会向广告平台发送应用内事件回传。

### 回传窗口期配置权限

* 营销人员
* 代理商，前提是广告主事先向其开放**配置应用内事件回传**<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#代理权限">权限</Anchor>。  
  请注意<strong>：</strong>广告主和代理同时在同一个广告平台上投放时，可各自根据其与广告平台协定的计费方式分开设置单独的回传窗口期。
* 合作渠道，前提是广告主事先向其开放**配置应用内事件回传**<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">权限</Anchor>。

## 事件映射

应用代码中对某类事件的称法因广告主而异，不同的渠道对同类事件也可能有不同的称法。

例如，对于通过应用购买商品这样的用户行为，有的广告主称之为“`purchase`”（购买），有的可能以更为晦涩的ID来命名，如“`event5`”，而渠道可能会称之为“`purchase_event`”（购买事件）。

因此，您必须对事件名称进行映射，这样才能确保广告主侧的事件能正确地匹配到对应的渠道事件。

> 📘 **注意**
>
> 在具体渠道配置页面的对接选项卡中设置的事件映射对标准回传和<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAN回传</Anchor>都生效。

### 映射方式

应用内事件的映射方式取决于渠道，共有以下三种方式：

* [输入渠道事件ID](/docs/in-app-event-postback-configuration#h_c513e6d4-d46f-4070-a98d-1888a5ea939d)
* [从列表中选择相关事件ID](/docs/in-app-event-postback-configuration#select-an-event-id-from-the-list)
* [按原样发送事件（不映射）](/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped)

> 📘 **注意**
>
> * 不是每个渠道的配置中都会显示所有的映射方式。
> * 您也可以[为渠道开通权限](/docs/in-app-event-postback-configuration#广告平台的事件映射)，让渠道来完成事件映射。

<div id="h_c513e6d4-d46f-4070-a98d-1888a5ea939d" />

<Accordion title="输入渠道事件ID">

* **AppsFlyer事件**：从应用事件的下拉列表中选择一个事件。
* **渠道映射事件**：在文本字段中输入与您的应用事件（即AppsFlyer事件）对应的渠道侧事件ID。

> 📘 **注意**
>
> * 事件名称区分大小写。为避免出现数据差异，请确保所有媒体渠道和应用程序的各个版本中使用的事件名称完全一致。
> * 手动输入的事件名称名称前后可以带下划线，但必须与AppsFlyer发送的事件名称一致。

[![enter_event_name.png](https://files.readme.io/b9d65d3a6b4c1ab4d3f7e83cc2226af5c5a83e1e83cfbfa3df36d295ae568a45-33379700646545.png)](https://files.readme.io/b9d65d3a6b4c1ab4d3f7e83cc2226af5c5a83e1e83cfbfa3df36d295ae568a45-33379700646545.png)

</Accordion>

<div id="select-an-event-id-from-the-list" />

<Accordion title="从列表中选择相关事件ID">

* **AppsFlyer事件**：**从应用事件的下拉列表中选择一个事件**。
* **渠道映射事件**：**从预定义的渠道事件列表中选择与相关应用事件（即AppsFlyer事件）对应的事件**。

[![In-app_event_postbacks_en-us.png](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

</Accordion>

<div id="send-events-as-they-are-unmapped" />

<Accordion title="按原样发送事件（不映射）">

有些渠道更偏向接收未映射的应用内事件回传，即相关事件在应用代码中的名称。这个事件可以叫做`purchase`、`acquisition`、`event5`或其他任何名称，事件的命名方式对事件的发送/接收没有任何影响。

您可以选择向相关渠道发送哪些未映射事件：

* 手动添加<strong>：</strong>选择具体的事件。
* **发送所有事件（卸载和session除外）**：将您的所有事件都发送给渠道，但这不包括卸载、session（即应用打开）和`af_app_opened`事件。

> 📘 **注意**
>
> 为了防止广告主无意中与第三方分析平台分享过多信息, 我们已从2019年3月起移除了这些平台的**发送所有事件**（卸载和session除外）选项。在此之前配置的分析平台仍保留此设置选项。

**如需手动添加事件，请完成以下操作：**

1. 点击**添加事件**。
2. 选择回传方式：
   * **AppsFlyer事件**：**从应用事件的下拉列表中选择一个事件**。
   * **事件来源**：选择<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#for-users-from">事件回传</Anchor>的范围：
   * **回传内容**：选择要发送的[回传数据](/docs/in-app-event-postback-configuration#回传内容)。
3. 然后重复以上步骤，逐个添加所有需要发送的事件。

![send_postbacks_as_is_en-us.png](https://files.readme.io/cc6b2bb1a381d88add035b9f369b0ba68dee8744aa3c2ee2f8f6f054b365a0dd-33379684962705.png)

**如需发送所有事件，请完成以下操作：**

1. 选择**发送所有事件（卸载和session除外）**。
2. 选择回传方式：  
   * **事件来源**：选择相关事件的[发送方式](/docs/in-app-event-postback-configuration#回传中的事件来源选项)。
   * **回传内容**：选择要发送的[回传数据](/docs/in-app-event-postback-configuration#回传内容)。

![send_postbacsk_as_is_no_mapping.png](https://files.readme.io/458ca832d4176ccd306236cf10f211499e841dc9f550558987dff3ee683bd2d1-33379700651665.png)

</Accordion>

如需进一步了解事件映射，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">应用内事件回传</Anchor>说明文档。

### 回传中的事件来源选项

您可以为每个事件设置回传发送对象（在回传窗口内），共有以下两个选项：

* **仅该合作渠道**：仅回传归因到该渠道的事件，也就是说完成这些事件的用户来自该渠道。
* **所有媒体渠道，包括自然流量**：回传归因到任何渠道以及自然量的事件，也就是说完成这些事件的用户来自各个渠道。**请注意**：选择“所有媒体渠道，包括自然流量”时，对于归因到其他渠道的事件，其回传中不包含归因数据。

### 回传内容

您可以选择回传到渠道的事件数据类型，共有以下三个选项：

* **不发送值与收入：** 仅发送不带任何参数的事件本身（即没有值或收入）。
* **仅发送值：** 发送**除**收入以外的所有参数。
* **发送值与收入**：发送所有事件参数，包括收入（若有）。
* 事件值、收入和净收入发送所有事件参数，包括收入值和净收入值（如果它们在事件中存在）。

> 📘 **注意**
>
> 选项需要一个**ROI360高级**订阅，并且仅适用于`af_purchase*`和`af_ars_*`事件。

收入共享并不是必须配置的内容，但如果您想让广告平台帮助您优化投放并提升投放效果，建议您与其共享收入数据。请确保仅为事件值中带有`af_revenue`或`af_projected_revenue`的事件开放收入共享，否则广告平台会收到收入值为空的事件。

#### 共享收入

回传中的`af_revenue`和`af_currency`是跟event\_value的JSON分开写入的，分别呈现为`event_value`monetaryevent\_value（金额）及**currency**（货币），并且可以单独发送。回传结构示例：

```http
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&content_id=(af_content_id)
```

当选择**值、收入和净收入**选项时，`af_net_revenue`也可以在`event_value` JSON之外写为**净货币**并单独发送。回传结构示例：

```http
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&net-monetary=(net-monetary)&content_id=(af_content_id)
```

> 📘 **注意**
>
> 选择**无值和无收入**或**值和无收入**时，相应的参数会被标记为N/A。

> 📘 **提示**
>
> 您还可以配置您的应用内事件回调，以在标准收入（货币)参数中发送净收入，而不是毛收入。要获取此配置的访问权限，请联系您的客户成功经理（CSM）。

> 📄 **示例**
>
> 广告主发送带有以下event\_value（事件值）的购买事件：`event_value`
>
> ```json
> {"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_content_type":"category_a"}
> ```
>
> 下表列出了各“回传内容”选项对应的回传参数：
>
>
>
> | 字段名称 | event\_value | monetary | currency | 净货币 |
> | --- | --- | --- | --- | --- |
> | **不发送值与收入** | N/A | N/A | N/A | N/A |
> | **仅发送值** | `{"af_currency":"N/A","af_content_id":"1234567","af_revenue":"N/A","af_content_type":"category_a"}&monetary=N/A&content_id=1234567` | N/A | N/A | N/A |
> | **发送值与收入** | `{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_content_type":"category_a"}&monetary=50.87&content_id=1234567` | 50.87 | USD | N/A |
> | **事件值、收入和净收入** | `{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_net_revenue":35.61,"af_content_type":"category_a"}&monetary=50.87&net-monetary=35.61&content_id=1234567` | 50.87 | USD | 35.61 |

### 带条件的应用内事件回传

您可以将应用内事件映射到多个渠道，然后使用多重条件筛选这些事件的回传，仅将符合条件的事件发送给相应的渠道，包括SRN和数据分析平台。这一功能主要用于：

* 优化人群分组、内容个性化以及改善用户留存
* 避免发送多余数据
* 保护用户隐私

> 📄 **示例**
>
> 某游戏应用的广告主想要优化在某广告平台上投放的广告系列，同时需要使优化范围精确到已通关10级或50级的用户，或应用内购金额达3美金的用户。
>
> [![in_app_event_condition__1_.png](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)
>
> **该广告主应对相关事件及其条件做如下设置：**
>
> * 当<strong><em>level</em></strong>等于<strong><em>10</em></strong>时，映射到<em>`fb_mobile_level_acheived`</em>
>   或（**OR**），
> * 当<strong><em>level</em></strong>等于<strong><em>50</em></strong>时，映射到<em>`fb_mobile_level_acheived`</em>
>   或（**OR**)，
> * 当<strong><em>cost</em></strong>等于<strong><em>3</em></strong>时，映射到<em>`fb_mobile_purchase`</em>

**请按以下步骤为事件设置发送条件：**

1. 在合作伙伴配置页中<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">定义并映射</Anchor>所需的应用内事件，以将其发送到相关渠道。
2. 点击指定事件右侧的![](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png)添加条件图标![image.png](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png)。
3. 按相关<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview#event-values">事件值</Anchor>的结构和内容填写条件字段：
   * 参数名称
   * 参数值
   * 满足条件时的渠道映射事件（从[映射选项](/docs/in-app-event-postback-configuration#映射方式)中选择任意一种）
4. 完成现有条件中的所有字段后，您可以添加其他条件。
5. 点击**保存对接**。

#### 注意事项

配置条件时，请确保回传给渠道的事件符合以下要求：

<div id="condition-structure" />

<Accordion title="条件结构">

* 条件中的参数和参数值必须与事件数据一致。
* 目前只能使用“等于”逻辑来配置条件
* 不支持数组等较为复杂的结构。

</Accordion>

<div id="multiple-conditions-for-an-event" />

<Accordion title="为一个事件配置多个条件">

* 每个事件最多可配5个条件。
* 事件必须符合至少一个条件，AF才会向渠道发送其回传。
* AF会按条件显示的顺序一一检查，并按首个匹配条件映射事件。
* 各个条件的事件映射相互独立。渠道映射事件变为**视条件而定**（Based on conditions）。
* 不同条件的参数和参数值不能完全重合。
* 可以将多个条件映射到同一个事件。

</Accordion>

> 📘 **注意**
>
> * 建议您在全面启用该功能前先通过测试应用或次要事件进行测试，了解其对投放优化的具体影响。
> * 如需查看<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">回传内容</Anchor>，请下载原始数据回传报告。

### 批量编辑事件

映射事件时，您可以针对多个事件批量编辑**事件来源和回传内容字段。**

**请按以下步骤对事件进行批量编辑：**

1. 选择要编辑的事件。
2. 选择**批量操作**。
3. 更新设置，使其对所有选定事件生效：
   * **事件来源**（二选一）
     * 仅该合作渠道
     * 所有媒体渠道，包括自然流量
   * **回传内容**（三选一）
     * 无数据（默认）
     * 仅发送值
     * 发送值与收入

[![In-app_event_postbacks_en-us.png](https://files.readme.io/559265d0e12e9e2ef62e0a19c5833465ee758821654877cffa4e75f6ff3f99b9-33379700657169.png)](https://files.readme.io/559265d0e12e9e2ef62e0a19c5833465ee758821654877cffa4e75f6ff3f99b9-33379700657169.png)

### 自定义事件

可映射的事件列表中仅显示SDK或S2S已经上报过的事件。如果下拉菜单中没有您想要映射的事件，可能是由下列情况造成的：

* 尚无用户完成该事件。
* 该事件的最近一次发生时间是两周前
* 您的活跃事件较多

**如果出现以上任一情况，您可以通过以下方式将相关事件关联到渠道侧对应的事件ID：**

1. 在下拉菜单中点击 **+ 添加项目**。
2. 在文本框中输入您要添加的事件名称。
3. 点击勾选符号，确认添加该事件。这时，您添加的事件会出现在下拉菜单中，供您选择。![add-custom-event-name.jpg](https://files.readme.io/cab91e281e863e7bbe0e3a96392552a149f7ccccd41695f2e4579089256e8dd1-33379684971793.jpg)
4. 将该事件关联到该渠道中对应的事件标识符。
5. 点击**保存对接**，确保将映射设置录入系统。

> 📘 **注意**
>
> * 在回传配置页面中添加自定义事件后，这一操作本身不能自动从您的应用中拉取这些事件。您必须先在SDK或S2S中配置这些事件，才能正常进行回传。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#发送事件">向AppsFlyer发送事件的方式</Anchor>说明。
> * 在某个渠道下添加自定义条件后，该事件会出现在所有渠道的事件列表中。也就是说，您可以在任何一个渠道的事件下拉菜单中看到这个自定义事件。
> * 另请参阅有关事件名称和参数设置的<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#tips">建议</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#limitations">限制</Anchor>。

**代理和广告平台：**

* 无法添加自定义事件
* 仅在广告主添加事件并开放相关<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">权限</Anchor>后才能查看和/或映射事件

## 广告平台的事件映射

营销人员可以允许广告网络自行映射事件。您可以按以下方式为广告平台开放相关权限：

1. 在**活跃对接**页中找到您要授权的渠道。
2. **打开**“权限”选项卡中的**允许配置应用内事件回传**开关。

![adnetwork-permissions-postbacks.png](https://files.readme.io/f8369f6a0a60d3c48ef66b51f61b3c81f00f6c88511f5f69b2c927788a64f018-33379700661265.png)

广告平台获得权限后，就能按[在文本字段中输入事件ID](/docs/in-app-event-postback-configuration#映射方式)的方式进行事件映射。

## 代理的事件映射

广告主可为代理开放权限，让代理配置应用内事件回传。

> 📘 **注意**
>
> 如果广告主和代理同时将相同的应用内事件回传启用到同一个广告平台，AppsFlyer只会发送一次回传。该机制可以避免事件被重复上报。

**请按以下步骤向代理开放应用内事件回传的配置权限：**

1. 在**活跃对接**页中选择相关的代理。
2. 选择该代理可共享的数据：所有事件或仅归因到指定渠道的事件。
3. 选择代理的事件收入发送权限。
4. 选择该代理可共享的具体事件。

![agency-events.png](https://files.readme.io/194b9a18f7721d4cc159f6385140cbb989108b70110e2e0d0f29f90d6115b10a-33379684973969.png)

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件 — 概览</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure">富应用内事件 — 事件结构</Anchor>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01HE0FQ1AB6NQCTKFTDW22SRYC=%E9%80%9F%E8%A7%88 postback-inapp-event-selection=%E9%80%89%E6%8B%A9%E8%A6%81%E5%9B%9E%E4%BC%A0%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HBZCRNKGH1PAK8RC846PPRTS=%E9%80%89%E6%8B%A9%E8%A6%81%E5%9B%9E%E4%BC%A0%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HBZCRNKGQTJ4VJ00TVTS14N2=%E6%B3%A8%E6%84%8F inapp-event-postback-window=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0%E7%AA%97%E5%8F%A3%E6%9C%9F h_01HBZCRNKGS71QGK5506N07K84=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0%E7%AA%97%E5%8F%A3%E6%9C%9F h_01K9MBNYC6PPHXSZ3KNVNSDASJ=%E6%B3%A8%E6%84%8F-1 default-postback-window=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0%E7%AA%97%E5%8F%A3 h_01HBZCRNKGV5CREN5K0RBDMBH6=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0%E7%AA%97%E5%8F%A3 h_01HBZCRNKGVXN233AFFHG42NW9=%E6%B3%A8%E6%84%8F-2 who-can-configure-postback-windows=%E5%9B%9E%E4%BC%A0%E7%AA%97%E5%8F%A3%E6%9C%9F%E9%85%8D%E7%BD%AE%E6%9D%83%E9%99%90 h_01HBZCRNKG7AECFSBXV2WDD9AR=%E5%9B%9E%E4%BC%A0%E7%AA%97%E5%8F%A3%E6%9C%9F%E9%85%8D%E7%BD%AE%E6%9D%83%E9%99%90 event-mapping=%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84 h_01HBZCRNKG7SZ4T41BY60BAJZN=%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84 h_01HBZCRNKGT64TE2XYK9VS4ATD=%E6%B3%A8%E6%84%8F-3 mapping-methods=%E6%98%A0%E5%B0%84%E6%96%B9%E5%BC%8F h_01HBZCRNKG4EF9MSY696SD5VQ9=%E6%98%A0%E5%B0%84%E6%96%B9%E5%BC%8F h_01HBZCVAGPSNDJMWRWENEP45N7=%E6%B3%A8%E6%84%8F-4 enter-the-partner-event-id=h_c513e6d4-d46f-4070-a98d-1888a5ea939d h_01HBZCRNKG1E63DZRSDWTB8CJN=%E6%B3%A8%E6%84%8F-5 h_01HBZCRNKGWQBNY8RP4MTW3DXV=select-an-event-id-from-the-list h_01HBZCRNKG4981T00N70X2GP0J=send-events-as-they-are-unmapped h_01HBZCRNKGXJ683VHFTE277ER9=%E6%B3%A8%E6%84%8F-6 options-for-sending-postbacks=%E5%9B%9E%E4%BC%A0%E4%B8%AD%E7%9A%84%E4%BA%8B%E4%BB%B6%E6%9D%A5%E6%BA%90%E9%80%89%E9%A1%B9 h_01HBZCRNKG1VN7E6TVCPDW7M73=%E5%9B%9E%E4%BC%A0%E4%B8%AD%E7%9A%84%E4%BA%8B%E4%BB%B6%E6%9D%A5%E6%BA%90%E9%80%89%E9%A1%B9 data-to-include-in-the-postbacks=%E5%9B%9E%E4%BC%A0%E5%86%85%E5%AE%B9 h_01HBZCRNKGESY50NSZGTVPT25M=%E5%9B%9E%E4%BC%A0%E5%86%85%E5%AE%B9 h_01KRKDVVV246YZYGM5G2ZJR63W=%E6%B3%A8%E6%84%8F-7 sharing-revenue=%E5%85%B1%E4%BA%AB%E6%94%B6%E5%85%A5 01J9Y0T400M5Z62Q9CKF8M75WR=%E5%85%B1%E4%BA%AB%E6%94%B6%E5%85%A5 h_01KRKDVVV2YF4XMKNCVEG1FFSG=%E6%B3%A8%E6%84%8F-8 h_01KRKDVVV242YPHP2W8EWTBSMD=%E6%8F%90%E7%A4%BA h_01HBZCRNKGBEDSBZEY87KYQ60G=%E7%A4%BA%E4%BE%8B conditional-inapp-event-postbacks=%E5%B8%A6%E6%9D%A1%E4%BB%B6%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01HBZCRNKG5X3B2NJZZP6ER2CX=%E5%B8%A6%E6%9D%A1%E4%BB%B6%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01HBZCRNKHRTMHP3JPFVCS8D6N=%E7%A4%BA%E4%BE%8B-1 considerations=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01HBZCRNKHBR57YVHZQP7NJBAP=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01HBZCRNKHJGBYNP9JN24CQ3CC=condition-structure h_01HBZCRNKH1R0FR61C6TA0MCTN=multiple-conditions-for-an-event h_01HBZCRNKHF6TFP0N302D7DCMD=%E6%B3%A8%E6%84%8F-9 editing-multiple-events=%E6%89%B9%E9%87%8F%E7%BC%96%E8%BE%91%E4%BA%8B%E4%BB%B6 h_01HBZCRNKHHD3WC4GTJT9NSJ4C=%E6%89%B9%E9%87%8F%E7%BC%96%E8%BE%91%E4%BA%8B%E4%BB%B6 custom-events=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6 h_01HBZCRNKH754PANWSZ4FMXJVQ=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6 h_01HBZCRNKH4PVR3FEMTMERW3M1=%E6%B3%A8%E6%84%8F-10 event-mapping-by-ad-networks=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E7%9A%84%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84 h_01HBZCRNKH1GCZY17R04WTZ0MQ=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E7%9A%84%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84 event-mapping-by-agencies=%E4%BB%A3%E7%90%86%E7%9A%84%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84 h_01HBZCRNKHHF3E6CZNQQG0Q4VS=%E4%BB%A3%E7%90%86%E7%9A%84%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84 h_01K5B6QS6YXKMJSEWE2WFT5AQC=%E6%B3%A8%E6%84%8F-11 h_01HDP3XHBPA5GZEVERMBN43JH0=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
