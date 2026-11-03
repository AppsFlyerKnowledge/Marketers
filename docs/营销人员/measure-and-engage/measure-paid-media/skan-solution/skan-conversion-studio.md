---
title: SKAN转化值操作台
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-07-08T09:26:58Z'
  edited_at: '2026-10-14T10:03:58Z'
  id: 4403727223185
  locale: zh-cn
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/zh-cn/articles/4403727223185
---
> **概要**：本文重点说明了如何通过SKAN转化值操作台设置您想要衡量的用户互动类型以及衡量时长。您可以在用户激活后的一定时间内衡量收入、转化、互动以及留存。您还可以通过单一可信数据源（SSOT）的衡量方式查看用户是否同时被AppsFlyer和SKAN归因。

<Embed title="SKAN 4转化值操作台（包含锁定窗口功能）" typeOfEmbed="iframe" url="https://player.vimeo.com/video/810457121?h=a3acc3ee41&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" providerUrl="https://player.vimeo.com" />

## SKAN转化值操作台基础操作指南

在SKAN的归因链路中，iOS设备会在每个衡量窗口结束后发送SKAN回传数据，其中包含最近更新的转化值（conversion value，简称CV）。

在SKAN 3及以下版本中，iOS会在最初的用户行为窗口期（Activity Window）结束后发送1次回传。用户行为窗口期的范围可为12小时-63天不等。CV值不能超过6比特，也就是说最多只能有64个CV值（即0-63）。

在SKAN 4中共有3次回传，对应3个窗口期，每个窗口期结束后即发送一次回传。这3个窗口期的时长依次为2天、7天和35天，其回传数据的规则如下：

* 窗口1的细粒度CV不超过6比特，也就是说最多可以有64个CV值（即0-63）。
* 窗口1-3的粗粒度CV值只能是low、medium或high。（窗口2和3没有细粒度CV）。

这些CV限制出台后，广告主不得不在衡量对象上做出一些取舍，以充分利用64个细粒度CV值和3个粗粒度CV值。

转化值操作台的可配置性极高，可细化到每一个值、每一位比特，便于广告主充分利用SKAN回传。您可以精确设置CV中需要对哪些数据进行加密以用于衡量，比如在激活后要衡量多长时间内的哪些用户行为。我们提供多个衡量模式，用于CV值的配置。

| 类型 | 衡量模式 | 说明 | 用户行为窗口期 |
| --- | --- | --- | --- |
| 可配置 | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />【推荐】<br /><br />【默认】 | 针对3个可配置的衡量窗口期，分别设置收入、转化（应用内事件）和互动的衡量方式。<br /><br />这3个窗口的时间段不能互相重叠。也就是说，窗口2衡量的是激活后3-7天内的数据，而不是0-7天内的数据。 | <ul><li>窗口1（Window 1）：1-2天</li><li>窗口2（Window 2）：3-7天</li><li>窗口3（Window 3）：8-35天</li></ul> |
| 可配置 | 自定义 | 在可配置的用户行为窗口期内设置收入、转化（应用内事件）和互动的衡量方式 | 12-1512小时（默认最长72小时，但可以延长） |
| 固定* | 收入<br /><br />【历史版本】 | 在下列区间中任选一个，用以衡量收入：<ul><li>1-630美元，以10美元为最小单位</li><li>1-63美元，以1美元为最小单位</li><li>0.01-0.63美元，以0.01美元为最小单位</li></ul> | 24小时 |
| 固定* | 转化<br /><br />【历史版本】 | 选择1-6个应用内事件 | 24小时 |
| 固定* | 广告交互<br /><br />【历史版本】 | 用户完成某一事件的次数 | 24小时 |
| 可配置 | <Anchor target="_blank" href="/marketers/zh/docs/skan-cv-decode-map-your-cv-to-events">Decode（解析）</Anchor> | <ul><li>手动创建用于事件映射的CV值，并在应用中进行对应的CV设置。该方案适用于无法在应用中接入AppsFlyer SDK的广告主。Decode（解析）模式的启用方式如下：从AF后台进入**SKAN转化值操作台**，点击“⋮”选项图标，选择**上传自定义解析映射文件**。</li></ul> | 12-1512小时（63天） |

*自2024年6月23日起，固定模式不再对新增应用开放。  AppsFlyer通过自定义模式和SKAN 4模式支持所有相关功能。

**小贴士：** 您可以从AF后台进入**配置** > **SKAN转化值操作台**，探索一下转化值操作台的界面和功能。

<div id="measurement-principles-and-definitions" />

<Accordion title="衡量原理及定义">

**定义**

* **SKAN衡量窗口**适用于SKAN 4+。用户激活应用后共有3个窗口期，用于衡量用户行为，分别是：
  * 窗口1（Window 1）：1-2天
  * 窗口2（Window 2）：3-7天
  * 窗口3（Window 3）：8-35天
  * 这3个窗口的时间段不能互相重叠。也就是说，窗口2衡量的是激活后3-7天内的数据，而不是0-7天内的数据。
* **用户行为窗口期：** 仅适用于SKAN 3及以下版本。该窗口期有固定的时长，默认为24小时，从应用首次启动开始计时。如果您启用了SKAN 4+，但用户设备或广告平台尚不支持SKAN 4，则用户行为窗口期自动设置为48小时。
* **转化值（CV）**：在SKAN 4的窗口期或SKAN 3及以下的用户行为窗口期（Activity Window）结束后，基于iOS的回传数据得出的用户质量信息。您可以直接通过AppsFlyer SDK设置CV值，也可以手动设置CV值。如需手动设置，请使用<Anchor target="_blank" href="/marketers/zh/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor>（解析）模式上传您的CV映射文件。
  * SKAN 4+中的CV值有精细值和粗略值两种。
* **转化值额度：** 映射您的设置所需要的CV值数量。您在设置中选择的衡量维度和衡量元素越多，需要消耗的转化值就越多。您每添加一个范围或设置元素，转化值额度的消耗量就会随之变高（在单个维度中每添加一个设置单元，转化值消耗度就会呈指数增长）。[具体请见转化值耗尽示例。](/docs/skan-conversion-studio#maximized-custom-cv-examples)
* **单一可信数据源（SSOT）：** 这是一种<Anchor target="_blank" href="/marketers/zh/docs/single-source-of-truth-ssot-guide-for-ios-attribution">标识机制</Anchor>，用于说明相关流量的归因方式（即SKAN或其他匹配方式）。您可以使用这一机制对SKAN原始数据中的激活进行排重，并计算出真实的投放效果指标
* **衡量维度**：  
  * **收入：** 用于衡量相关应用带来的收入
  * **应用内事件**：用于衡量转化（完成某一事件的独立用户数量）和/或  
    互动（某一事件的发生次数）。
  * **漏斗**：您可以根据一系列有先后顺序的事件组成的漏斗来衡量应用内事件。用户在漏斗中执行的任何事件都将被视为已执行该事件之前的所有事件。
  * **优先级**：该维度包含收入和/或应用内事件。

**原理**

* **![Admin.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)管理员权限：只有管理员可以保存转化值操作台的设置，账户用户只能查看该设置。**
* 任何时刻的在用衡量模式都只有一个。
* 在具体的衡量模式中，AppsFlyer会把基于您的设置生成的衡量对象组合映射到CV值。您可以[查看并下载映射表格](/docs/skan-conversion-studio#view-cv-mapping)。
* 在应用侧，AppsFlyer会在每次出现可衡量的用户行为时，通过用户首次启动应用时使用的衡量模式设置CV值。
* iOS会先考量转化量是否达到了<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">Apple的群组匿名性阈值</Anchor>（Crowd Anonymity），然后再填充回传里的CV值。
* 在窗口期结束后发生的用户行为不会被记录。
* SKAN面板和报告：
  * SKAN面板的版式和指标取决于具体的衡量模式和配置。
  * 面板版式会根据每天UTC时间凌晨时在用的衡量模式自动更新。一般情况下，您可以在UTC时间05:00前看到更新后的版式。
  * 在SKAN 4的自定义（Custom）和解析（Decode）模式下，应用内事件和总收入的自然量数据不可用。

#### **S2S原理**

可衡量的用户行为可以通过[服务器到服务器（S2S）](/docs/skan-conversion-studio#report-events-by-servertoserver-api) API上报。各个模式的S2S适配情况如下：

* SKAN 4及自定义模式（Custom）：S2S总是开启。
* 解析模式（Decode）：S2S在这个模式下既不适用也不可用，因为该模式下的CV值不是由AppsFlyer设置的。
* 【历史版本】收入、转化和互动模式：在发送事件之前，您必须先打开[S2S事件记录](/docs/skan-conversion-studio#report-events-by-servertoserver-api)开关。

</Accordion>

## 在SKAN转化值操作台中设置转化值

SKAN转化值操作台提供多种衡量模式，用于设置转化值：

* SKAN 4：使用收入、应用内事件、优先级和单一可信数据源等不同的衡量维度，来设置三个衡量窗口内分别要衡量的对象。
* 自定义模式（Custom）：使用收入、应用内事件、优先级和单一可信数据源等不同的衡量维度，来设置用户行为窗口期内的衡量对象。
* 【历史版本】固定模式：使用以下任一维度衡量用户价值：
  * 收入
  * 转化
  * 广告交互

下文分章节介绍了各种不同的衡量模式。

> 🚧 **重要提示！**
>
> 只有AF账户的管理员或者在**SKAN转化值操作台**中具有**管理**权限的用户才能在SKAN转化值操作台中设置转化值。
>
> **请按以下步骤查看或更改用户权限：**
>
> 1. 进入AF后台，点击右上角的邮箱地址。
> 2. 点击**用户管理** > 选择具体用户。
> 3. 根据实际需要向相关用户开放**SKAN转化值操作台**的**管理**权限。另请参考<Anchor target="_blank" href="/marketers/zh/docs/user-management">用户管理</Anchor>，了解其他的权限设置。
>
> *请注意：

<div id="skan-4" />

<Accordion title="SKAN 4">

在SKAN 4模式中，您可以使用收入、应用内事件、优先级和单一可信数据源等不同的衡量维度，来设置三个衡量窗口内分别要衡量的对象。您可以综合利用这些维度，创建适合自己的自定义衡量模式。

如果您从之前的SKAN模式升级到SKAN 4，则窗口1的配置会沿用您当前使用CV值映射架构。AppsFlyer会自动映射窗口1-3的粗略值。

如需手动配置SKAN 4，建议您先探索一下SKAN 4中的各种选项。您更改配置时，**转化值额度**总结也会随之更新。您可以通过优化设置，以有限的转化值攫取最有价值的数据。详情请见[转化值额度的计算方式](/docs/skan-conversion-studio#conversion-value-capacity-formula)。

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**请注意：如果您从之前的SKAN模式升级到SKAN 4，则SKAN 4中的细粒度衡量配置会沿用您当前使用的CV值映射架构。AppsFlyer会自动映射粗略值。如果您之前没有使用过SKAN，AppsFlyer会提供初始默认映射配置。**

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)请按以下步骤在转化值操作台中使用SKAN 4模式手动设置转化值：**

1. 从AppsFlyer面板进入配置 > **SKAN转化值操作台**。
2. 点击选项按钮（⋮）查看选项菜单，确认**SKAN衡量**开关已打开。**请注意**：如果未打开该开关，则SDK不会调用*registerAppForAdNetworkAttribution*和*updateConversionValue*等SKAN功能。
3. 选择**SKAN 4.0**衡量模式。
4. 点击**继续**，进入下一步。  
   界面打开**窗口1（1-2天）细粒度CV**的设置窗口。
5. 【可选】打开<strong>单一可信数据源（SSOT）</strong>开关。  
   SSOT机制会标出由不同方式重复归因的激活并去重。<Anchor target="_blank" href="/marketers/zh/docs/single-source-of-truth-ssot-guide-for-ios-attribution">了解详情</Anchor>
6. 点击**添加衡量维度**，添加各种[衡量维度](/docs/skan-conversion-studio#衡量维度)。  
   以下章节详细说明了各个设置选项和维度，帮助您探索不同的SKAN衡量设置：
   * 收入
   * 应用内事件
   * 漏斗
   * 优先级
7. 点击**粗略值**并重复第6-7步，设置**窗口1（1-2天）粗粒度CV**。   
   **请注意**：
   * 仅支持收入和应用内事件衡量维度。
   * Low值必须设置为应用打开（user session），以确保回传得以发送。
8. 【可选】打开**锁定窗口**开关，并设置条件（事件或粗略值）锁定SKAN窗口，使其短于默认窗口。[了解详情](/docs/skan-conversion-studio#lock-window)
9. 点击<strong>窗口2（3-7天）</strong>并重复第6-8步，设置窗口2的CV值。   
   **请注意**：
   * 仅支持收入和应用内事件衡量维度。
   * 【推荐】Low值必须设置为应用打开（user session）。
10. 点击<strong>窗口3（8-35天）</strong>并重复第6-8步，设置窗口3的CV值。   
    **请注意**：
    * 仅支持收入和应用内事件衡量维度。
    * 【推荐】Low值必须设置为应用打开（user session）。
11. 点击**保存**。
12. 确认您配置的事件能映射到渠道的应用内事件回传中。

</Accordion>

<div id="custom" />

<Accordion title="自定义">

在自定义模式（Custom）中，您可以使用收入、应用内事件、优先级和单一可信数据源等不同的衡量维度，来控制衡量的对象。您还可以设置用户行为窗口期，调整衡量的时长及间隔。您可以综合利用这些维度，创建适合自己的自定义衡量模式。

如需配置自定义模式（Custom），建议您先探索一下其中的各种选项。您更改配置时，**转化值额度**总结也会随之更新。您可以通过优化设置，以有限的转化值攫取最有价值的数据。详情请见[转化值额度的计算方式](/docs/skan-conversion-studio#conversion-value-capacity-formula)。

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

请注意：

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)请按以下步骤在转化值操作台中使用自定义模式（Custom）手动设置转化值：**

1. 从AppsFlyer面板进入配置 > **SKAN转化值操作台**。
2. 点击选项按钮（⋮）查看选项菜单，确认**SKAN衡量**开关已打开。 **请注意**：如果未打开该开关，则SDK不会调用*registerAppForAdNetworkAttribution*和*updateConversionValue*等SKAN功能。
3. 选择**自定义**（Custom）衡量模式。
4. 点击**继续**，进入下一步。
5. 【可选】打开<strong>单一可信数据源（SSOT）</strong>开关。  
   SSOT机制会标出由不同方式重复归因的激活并去重。<Anchor target="_blank" href="/marketers/zh/docs/single-source-of-truth-ssot-guide-for-ios-attribution">了解详情</Anchor>
6. 点击**添加衡量维度**，添加各种衡量维度。  
   以下章节详细说明了各个设置选项和维度，帮助您探索不同的SKAN衡量设置：
   * 收入
   * 应用内事件
   * 漏斗
   * 优先级
7. 设置用户行为窗口期（Activity Window，可用范围为12小时-63天），以衡量在此期间发生的用户行为。  
   默认的**用户行为计时器**支持24-72小时的窗口期。默认的**间隔**设置有12小时和24小时两个选项。您可以使用**自定义窗口**设置延长用户行为窗口期（最长可达63天）并和间隔时间。
8. 点击**保存**。
9. 确认您配置的事件能映射到渠道的应用内事件回传中。

</Accordion>

<div id="fixed-modes" />

<Accordion title="【历史版本】固定模式">

> 📘 **注意**
>
> 自2024年6月23日起，固定模式不再对新增应用开放。  AppsFlyer通过自定义模式和SKAN 4模式支持所有相关功能。

在固定模式中，您可以使用以下任一维度衡量用户价值：

* * 收入
  * 转化
  * 广告交互

您更改配置时，**转化值额度**总结也会随之更新。您可以通过优化设置，以有限的转化值攫取最有价值的数据。详情请见[转化值额度的计算方式](/docs/skan-conversion-studio#conversion-value-capacity-formula)。

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**请注意：**

* 固定模式从用户首次打开应用开始，观测其24小时内的行为。
* 如果您想要通过S2S的方式发送事件数据，需要手动启用[SKAN S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api)。

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)请按以下步骤在转化值操作台中使用固定模式手动设置转化值：**

1. 从AppsFlyer面板进入配置 > **SKAN转化值操作台**。
2. 点击（⋮<strong><em> 确认SKAN衡量开关已打开。 </em></strong>请注意：如果未打开该开关，则SDK不会调用registerAppForAdNetworkAttribution和updateConversionValue等SKAN功能。
   * 【可选】[启用S2S事件发送功能](/docs/skan-conversion-studio#report-events-by-servertoserver-api)。该功能在收入、转化或互动模式中可用。
3. 选择一个固定衡量模式。
4. 根据下表信息和说明完成选定固定衡量模式的设置。
5. 点击**保存**。
6. 确认您配置的事件能映射到渠道的应用内事件回传中。

#### 固定衡量模式

| 衡量模式 | 说明 |
| --- | --- |
| 收入 | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**在24小时的窗口期内产生的收入**<br /><br />从以下三个收入范围（货币为美元，最小单位为低线值）中选择一个：<ul><li>$0.01到$0.63</li><li>$1到$63</li><li>$10到$630</li></ul>AppsFlyer会自动填充收入衡量范围中的63个值，确保将名为“`af_skad_revenue`”的事件正确映射到渠道侧的对应事件。面板会以对应范围的最高值来记录收入。比如在$60-$61这个范围中，最后记录到的收入为$61。请注意：自定义模式中的收入计算方法与此不同。<br /><br />**可用指标：**<ul><li>收入<ul><li>ROI</li><li>ROAS（广告支出回报率）</li><li>ARPU：收入/用户激活数</li><li>用户转化率：完成购买的用户数量/激活应用的用户数量</li><li>eCPA</li></ul></li></ul> |
| 转化 | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**在24小时的用户行为窗口期内至少发生过一次的应用内事件**<br /><br />**设置**：<ul><li>从下拉菜单中选择1-6个应用内事件进行衡量。局限性：该菜单中仅包含过去30天内发生次数最高的300个事件。</li><li>在SKAN面板中选定一个事件作为<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">转化事件</Anchor>。</li></ul>**分应用内事件的指标：**<ul><li>某个事件的发生次数<ul><li>转化率：完成转化事件的用户/激活应用的用户</li><li>eCPA</li><li>应用打开（session）（通过*af\_app\_opened*事件衡量）</li></ul></li></ul>可衡量的用户行为包括：<ul><li>完成注册</li><li>完成购买</li><li>游戏通关</li></ul>**请注意：** 转化衡量用于判断用户**是否**完成了某个事件，如果您需要了解某个事件的完成次数，请使用互动衡量。 |
| 广告交互 | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**在用户行为窗口期内指定事件的发生次数**<br /><br />**设定：**<ul><li>从下拉菜单中选择一个应用内事件。</li><li>选定一个应用内事件作为转化事件。</li><li>可用的窗口期范围：0-63</li></ul>**应用内事件指标**：<ul><li>用户执行某事件的次数<ul><li>人均事件完成数</li><li>转化率</li><li>eCPA</li><li>应用打开（Sessions）</li></ul></li></ul>如<ul><li>可衡量次数的事件：<ul><li>应用打开</li><li>广告浏览</li></ul></li></ul> |

</Accordion>

<div id="decode" />

<Accordion title="Decode（解析）">

在该模式中，您可以自己创建CV-事件映射构架，并在应用中设置CV。该方案适用于无法在应用中接入AppsFlyer SDK的广告主。

**解析模式的使用方式如下**：

1. 从AppsFlyer面板进入配置 > **SKAN转化值操作台**。
2. 点击（⋮<strong><em> 确认SKAN衡量开关已打开。 </em></strong>请注意：如果未打开该开关，则SDK不会调用registerAppForAdNetworkAttribution和updateConversionValue等SKAN功能。
   * 上传您的解析映射文档。
3. 点击**保存**。
4. 确认您配置的事件能映射到渠道的应用内事件回传中。

</Accordion>

## 衡量维度

<div id="single-source-of-truth" />

<Accordion title="单一可信数据源（SSOT）">

<table><tbody><tr><td colspan="2"><p><img alt="SSOTControl.png" src="https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png"/></p><p><a href="./single-source-of-truth-ssot-guide-for-ios-attribution" target="_blank">Single Source of Truth</a>（单一可信数据源，简称SSOT）机制会标出由不同方式重复归因的激活并去重。这里的“不同归因方式”分为SKAN及非SKAN方式。您可以在SKAN原始数据报告看到该标签，该标签也会用于计算总览面板<a href="./single-source-of-truth-ssot-guide-for-ios-attribution#数据总览面板的ssot视图" target="_blank">SSOT视图</a>中的指标。 </p></td></tr><tr><td>是否必须配置</td><td>否</td></tr><tr><td>能否设置多个</td><td>否</td></tr><tr><td>设置选项</td><td><p>如果您启用了SSOT，则可以通过CV值标记出由SKAN和非SKAN方式重复归因的用户。 </p><p>SSOT标签用于以下场景：</p><ul><li>AppsFlyer数据总览面板SSOT视图</li><li>SKAN原始数据报告中的<em>af_attribution_flag</em>字段。如果该字段的值为true，即表示该用户由SKAN和非SKAN方式重复归因。 </li><li>SKAN汇总归因API报告</li></ul></td></tr></tbody></table>

</Accordion>

<div id="inapp-event-component" />

<Accordion title="应用内事件维度">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioIn-app-event.png](https://files.readme.io/7b110093a72b13c0750ccb66da5efe737b8f83c0adcb95eb35185a4dc77bad6c-4406051824657.png)
      </td>
    </tr>
    <tr>
      <td>
        是否必须配置
      </td>
      <td>
        否
      </td>
    </tr>
    <tr>
      <td>
        能否设置多个
      </td>
      <td>
        是
      </td>
    </tr>
    <tr>
      <td>
        设置选项
      </td>
      <td>
        选择一个应用内事件，然后根据您的衡量目标设置范围，具体如下：

        * **仅衡量转化：** 配置一个0–1的范围
        * **同时衡量互动和转化：** 配置多个范围，并根据业务需求设置范围值
      </td>
    </tr>
    <tr>
      <td>
        用于衡量互动的范围
      </td>
      <td>
        您必须先创建事件发生次数的范围，才能衡量互动。选定的互动事件发生时，SKAN会根据发生的次数将该事件与对应的范围相关联。

        **说明**

        * 每个范围都包含了发生次数的**低线**值和**高线**值，低线值不计入范围，而高线值计入范围。比如一个5–10的范围包括大于5且小于等于10的值。
        * 低线值最低为0（但低线值为0的范围不包括0本身）。
        * 您可以创建的范围数量不限，但每创建一个范围，就会消耗更多的转化值。
        * 范围必须按顺序设置（范围之间不能跳数）

        **通过范围衡量互动**

        * 系统上报事件后，SKAN会将该事件与对应的范围相关联。最后记录到的事件发生次数是根据该范围的平均值就近取整得出的，假设平均值为5.7，那么最后记录的次数就是6。
        * 如果事件发生次数超过最高范围的高线值，则该事件会被归到最高范围内，最后记录到的事件发生次数是最高范围的平均值。也就是说，最后记录到的事件发生次数并不是该事件的实际发生次数。
        * 在原始数据中，您可以同时看到事件的实际发生次数和范围值。

        **举例来说，**

        上图显示了以下三个事件次数范围：

        事件次数范围设置如下：

        * A：0-5
        * B：5-10
        * C：10-20

        事件发生次数是根据这几个范围来记录的，具体如下：

        | 示例 | SDK上报的事件次数 | 关联到的范围 | 最后上报的事件次数 |
        | --- | --- | --- | --- |
        | 1 | 5 | A | 3 |
        | 2 | 6 | B | 8 |
        | 3 | 10 | B | 8 |
        | 4 | 125 | C | 15 |
      </td>
    </tr>
    <tr>
      <td>
        局限性
      </td>
      <td>
        一个应用内事件只能与该维度关联一次。
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="revenue-component" />

<Accordion title="收入维度">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioRevenue.png](https://files.readme.io/202c258f11cd93248f8aceff410126efc02ced11e9a9b159bac8ba81cbc8d9fe-4406075612305.png)
      </td>
    </tr>
    <tr>
      <td>
        是否必须配置
      </td>
      <td>
        否
      </td>
    </tr>
    <tr>
      <td>
        能否设置多个
      </td>
      <td>
        是（即分收入来源记录应用内事件收入）
      </td>
    </tr>
    <tr>
      <td>
        设置选项
      </td>
      <td>
        您可以通过单个事件来记录收入，也可以按收入来源将收入关联到指定的应用内事件。

        您可以使用的收入来源选项有以下几种：

        * **总体收入**
          * SKAN仅通过`af_skad_revenue`一个事件来记录所有应用内事件以及广告变现所产生的总体收入。请确保将`af_skad_revenue`事件正确映射到渠道侧的对应事件。
          * 该选项只能使用一次。
        * **应用内事件**
          * 如需按具体的收入来源衡量收入，可以在CV值映射架构中选择特定的应用内事件。添加收入维度后，请在收入来源部分选择“应用内事件”。请确保所有相关事件都正确映射到渠道侧的对应事件。  
            请注意：衡量特定事件所带来的收入时，请不要映射`af_skad_revenue`。
          * 该选项可使用多次。
          * 如需通过向广告平台回传数据来上报收入，请确保您已经在回传中设置了相关应用内收入事件的映射。
      </td>
    </tr>
    <tr>
      <td>
        范围
      </td>
      <td>
        您必须先创建收入范围才能衡量收入，因为在记录收入时，SKAN会将SDK上报的收入关联到对应的范围。

        **说明**

        * 每个收入范围都包含一个**低线**值和一个**高线**值。低线值不计入范围，而高线值计入范围。比如一个5–10的范围包括大于5且小于等于10的值。
        * 低线值最低为0（但低线值为0的范围不包括0本身）。
        * 您可以创建的范围数量不限，但每创建一个范围，就会消耗更多的转化值。
        * 范围必须按顺序设置（范围之间不能跳数）。
        * 收入金额的单位是美元。
        * 如果您在Meta ads上投放广告，必须设置至少4个范围。
        * 范围值最多可以精确到小数点后4位。

        **按范围记录收入**

        * SDK上报收入时，SKAN会将该收入关联到对应的范围。最后记录到的收入是其对应范围的平均值。
        * 如果上报的收入超过了最高范围的平均值，那么该收入会被归到最高范围内。**请注意**：最后记录到的收入是该范围的平均值，也就是说，最后记录到的收入并不是实际收入。
        * 您可以在原始数据中看到记录到的收入及其对应的范围。

        **举例来说，**

        上图显示了以下三个收入范围：

        * A：0-5
        * B：5-10
        * C：10-20

        收入是根据这几个范围来记录的，具体如下：

        | 示例 | SDK上报的收入 | 关联到的范围 | 最后记录到的收入 |
        | --- | --- | --- | --- |
        | 1 | 5 | A | $2.5 |
        | 2 | 6 | B | $7.5 |
        | 3 | 10 | B | $7.5 |
        | 4 | 125 | C | $15 |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="funnel-component" />

<Accordion title="漏斗维度">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionValueFunnel.png](https://files.readme.io/b43b5db0cee11c9addd50fb56af1ac6d3221e1956e2ee3c4c21a6940e9dfe61b-4406051997969.png)
      </td>
    </tr>
    <tr>
      <td>
        是否必须配置
      </td>
      <td>
        否
      </td>
    </tr>
    <tr>
      <td>
        能否设置多个
      </td>
      <td>
        否
      </td>
    </tr>
    <tr>
      <td>
        设置选项
      </td>
      <td>
        形成漏斗的一系列有先后顺序的事件。由于该逻辑将单个事件的发生次数视为漏斗内之前所有事件的发生次数，因此请务必认真谨慎地设置事件漏斗，具体请参考下表示例。
      </td>
    </tr>
    <tr>
      <td>
        示例
      </td>
      <td>
        假设一个漏斗中包含a、f、b、k和z五个事件，如下所示。

        | 示例 | 用户完成的事件 | 记录到的事件 |
        | --- | --- | --- |
        | 1 | a | a |
        | 2 | b | a、f、b |
        | 3 | z | a、f、b、k、z |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="priority-measurement-component" />

<Accordion title="优先级衡量维度">

自定义模式中的优先级衡量维度能让您基于自己的业务逻辑对应用中的用户行为链路进行排列，让高优先级衡量覆盖低优先级衡量。这样，您就能为转化漏斗中的每一步都选择最合适的衡量对象。

每个优先级（共63个）都可包含收入和/或应用内事件。当用户完成应用内事件时，AppsFlyer会判断该用户行为对应到哪个优先级，并根据判定结果来设置CV值。

在自定义模式中，不包含优先级与包含优先级的区别如下：**不包含**优先级时，AppsFlyer会将所有可能的衡量组合映射到CV；**包含**优先级时，AppsFlyer仅将您明确设置的衡量组合映射到CV。

详情请见优先级[示例说明](/docs/skan-conversion-studio#priority-measurement-detailed-example)。

**优先级的主要原理**

* 您可以设置1-63个优先级。可用的优先级个数取决于您的用户行为窗口期以及SSOT（单一可信数据源）设置。
* 优先级1是最高的优先级。优先级的序号数字越大，优先级就越低。
* 一个优先级由[收入](/docs/skan-conversion-studio#revenue-component)维度和/或[应用内事件](/docs/skan-conversion-studio#inapp-event-component)维度构成，其中可包含多个应用内事件和收入来源。
* 在优先级中无法使用漏斗维度。但您可以在一个优先级中设置多个应用内事件来衡量某个漏斗中的用户转化。
* 如需使用优先级衡量维度，则不能配置应用内事件或收入等其他维度。

**请按以下步骤启用优先级衡量：**

1. 从AppsFlyer后台进入**SKAN转化值操作台**。
2. 选择**自定义**模式，然后点击**继续**。
3. 如有必要，请点击**删除**以清除当前设置。
4. 点击 **+ 添加衡量维度**。 选择优先级。   
   界面显示优先级1。  
   [![Priority1.png](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)
5. 从以下衡量维度中选择一个：
   * 收入
   * 应用内事件
6. 按界面提示填写相关字段。
   * 请注意：一个优先级中可以包含收入和/或应用内事件。
   * 事件发生次数以及收入的范围值可以设置为升序或降序，但各个区间之间必须是连续的，如1-5、5-8、8-10等等。同一个收入范围可以重复使用，但第二次使用时必须与上一个优先级中的范围相同，且其所在优先级必须是一个独立的事件组合。如1-5、1-5 + add to cart（加购）。  
     **另请参考升序和降序收入范围示例。**  

| 事件 | 发生次数 | 收入 |
| --- | --- | --- |
| P1 event\_a | 2-3 | $5 - $50 |
| P2 event\_a | 2-3 | $0-$5 |
| P3 event\_a | 1-2 | $5 - $50 |
| P4 event\_a | 1-2 | $0-$5 |
| P5 event\_a | 0-1 | $5 - $50 |
| P6 event\_a | 0-1 | $0-$5 |

7. 点击**验证**。  
   界面显示消息“**Priority is valid**”（优先级有效）。如果没有显示该消息，请先更正您的优先级设置，然后再进行下一步操作。
8. 此时可完成以下任一操作：
   * 如需添加新的优先级，请点击 **+ 添加优先级。** 当前的优先级1会下移至优先级2。请按上文所述步骤完成优先级设置。
   * 如需删除一个优先级，请点击… > **删除**。
   * 如需更改优先级，请点击**选项**（⋮），然后选择**更改顺序**或**改为最低优先级**。
   * 如需创建优先级副本，请点击**选项**（⋮），然后选择**创建副本**。
   * 点击**保存**，完成优先级设置。

</Accordion>

<div id="lock-window" />

<Accordion title="锁定窗口">

**请注意**：锁定窗口功能仅适用于SKAN 4及以上版本。

<table><tbody><tr><td colspan="2"><img alt="lock_window.png" src="https://files.readme.io/d9db51890a5d589b7343ed389d55af0c4181b249a2c5e970b9a5e1244c489abc-14240675527057.png"/></td></tr><tr><td>使用</td><td>默认的SKAN窗口期指用户激活后特定的几段时间，在此期间iOS会衡量用户价值。您可以锁定这几个窗口期，使其短于默认窗口期，让iOS提前将当下所有可用数据的回传发送给您。如需锁定窗口，需要先设置锁定条件。</td></tr><tr><td>是否必须配置</td><td>否</td></tr><tr><td>能否设置多个</td><td>是的，每个SKAN窗口都可以锁定</td></tr><tr><td>条件选项</td><td>SKAN窗口的锁定条件有两种选项：<ul><li>时间：选择一个时间段（必须短于默认时间段），将窗口期锁定在激活后的这个时间段内。<strong>请注意</strong>：按时间段锁定窗口期时，用户必须打开应用才能使窗口期生效。</li><li>粗略值为High：当粗略值达到High时窗口期结束。</li></ul></td></tr><tr><td>锁定窗口后的影响</td><td>SKAN回传不包含窗口期结束时间，所以计算激活时间时不考虑窗口的锁定状态，因此使窗口期提前结束会影响激活时间估算的准确性。</td></tr></tbody></table>

</Accordion>

<div id="activity-window" />

<Accordion title="用户行为窗口期">

**请注意**：

* 用户行为窗口期仅适用于SKAN 3及以下版本（即自定义模式和固定模式）。
* 如果您启用了SKAN 4+，但用户设备或广告平台尚不支持SKAN 4，则用户行为窗口期自动设置为48小时。

<table><tbody><tr><td colspan="2"><img alt="flex_activity_window.jpg" src="https://files.readme.io/ac51126eda5b9d319ccdd90adb936baaa512dcd844ad191cac6c20a45cd4aae8-6390396808081.jpg"/></td></tr><tr><td>是否必须配置</td><td>是 </td></tr><tr><td>能否设置多个</td><td>否</td></tr><tr><td>时间特征</td><td><ul><li>用户行为窗口期计时器的时长由广告主设置，设置后固定不变，与iOS计时器互不干涉。</li><li>iOS计时器的最初时长是24小时，每次转化值升高时，该计时器就会归零重启。</li><li>默认时长为24小时</li><li>这两个计时器中的任意一个走完时衡量就会停止。 </li></ul></td></tr><tr><td>时长</td><td><ul><li>范围：12-72小时。其他选项请见本表中的<strong>可调节的衡量窗口</strong>部分。  </li><li>计时器走完时，AppsFlyer就会停止衡量。</li><li>如果计时器的时长超过24小时，用户必须在每个间隔期间至少与应用互动一次，否则可能会导致衡量过早停止。AppsFlyer无法拖延iOS计时器的停止，因此在这种情况下iOS计时器会先走完然后终止衡量。 </li></ul></td></tr><tr><td>间隔</td><td><p>12或24小时。间隔会影响末次互动时间范围以及激活时间的准确性。其他选项请见本表中的<strong>可调节的衡量窗口</strong>部分。 </p><p>您可以在原始数据报告的<em>min_install_time</em>和<em>max_install_time</em>这两列中查看末次互动时间范围，该指标用于确定激活时间（见下文）。</p><p>举例来说，</p><ul><li>计时器时长设置为48小时</li><li>用户在第40个小时的时候与应用进行了最后一次互动</li><li>基于不同的间隔设置，末次互动时间范围分别为： <br/> <ul><li>12小时间隔：36-48小时</li><li>24小时间隔：24-48小时</li></ul></li></ul></td></tr><tr><td>激活时间</td><td><p>激活时间的推算方法如下：</p><p>激活时间 = 回传数据接收时间 -[平均末次互动范围] - [iOS回传延时]</p><ul><li> 回传数据接收时间：  最初从用户设备接收到iOS回传数据的时间，接收方通常是广告平台。 </li><li> 平均末次互动范围根据CV值按以下方式计算：<ul><li>如果CV = 0：末次互动范围默认为0。 </li><li>如果CV &gt; 1或CV = null：通过min_install_time和max_install time，根据间隔和用户最后一次与应用互动的时间来确定。  比如，假设间隔是12小时，用户最后一次与应用互动是在应用激活后的第25个小时，那么末次互动范围就是[24 + 36] / 2 = 30。 </li></ul></li><li> iOS回传延时：[24 + 48 ] / 2 = 36.iOS计时器在CV值最后一次发生变化后的24小时走完，iOS系统在计时器走完后的0-24小时内发出回传数据。在这个公式中，<strong>36小时是一个常数</strong>。 </li></ul></td></tr><tr><td>设置选项</td><td>用户行为窗口期的设置包含时长和间隔两个方面。 <ul><li>时长：24-72小时，每24小时一次间隔，最多3次间隔。</li><li>时长：12-72小时，每12小时一次间隔，最多6次间隔。</li></ul></td></tr><tr><td>更改用户行为窗口期时长的影响</td><td><ul><li>回传数据在iOS计时器走完后的0-24小时内发出。 </li><li>iOS计时器本来会在24小时后走完。 </li><li>但如果您设置的用户行为窗口期超过24个小时，那么用户必须在每个间隔期间至少与应用互动一次，才能确保iOS计时器能不断归零重启，继续计时，否则它会在用户行为窗口期结束前就走完。</li></ul></td></tr><tr><td><p>与广告平台相关的因素</p></td><td><ul><li>计时器的默认时长为24小时。</li><li>如果您想设置其他时长，请先跟渠道确认他们是否支持默认时长以外的计时器。 </li><li><span>如果您把窗口期时长设置为24小时，可以将这24小时切分成2个12小时的间隔，这样可以优化指标使用效率，因为您可以看到用户是否在最初的12小时之后持续与应用互动。</span></li></ul></td></tr><tr><td>范围设置要求示例</td><td>上图显示了以12小时为间隔、总时长为60小时的计时器。 </td></tr><tr><td>可调用户行为窗口期选项</td><td><p>您可以使用可调衡量选项将用户行为窗口期设置得更长，且窗口期可以以小时为单位。间隔的设置也是如此。可调衡量设置具有以下特点：</p><ul><li>用户行为窗口期：<ul><li>范围：12-1512小时（63天）  </li><li>颗粒度：1小时</li></ul></li><li>间隔：<ul><li>范围：<span>最短1小时，其他选项为用户行为窗口期的因数</span> </li><li>颗粒度：1小时</li></ul></li></ul><p>请注意：用户行为窗口期必须可以被间隔时间整除。</p><p>推荐方法：间隔时间最好不要超过24小时，否则会影响激活时间推算的准确性。</p></td></tr></tbody></table>

</Accordion>

## 其他相关信息

<div id="view-cv-mapping" />

<Accordion title="查看CV值映射">

* 选择具体CV值后，您可以在表格下方看到映射到该CV值的事件。
* 点击**下载映射文件**，就能下载CSV格式的CV映射表。
* 您也可以使用<Anchor target="_blank" href="/marketers/zh/docs/skan-cv-schema-api-for-advertisers">广告主的SKAN CV映射构架API</Anchor>获取CV映射信息。

![CVmapping.png](https://files.readme.io/b337ac089f70a5eff76ac6a56841b420cff9f4bff7aba8c18acddd04acfd82f6-51911424397585.png)

#### CV映射文件各列说明

| 栏位 | 说明 |
| --- | --- |
| app\_id |  |
| conversion\_value | CV值：<ul><li>0-63</li><li>Low、medium或high</li></ul> |
| event\_name |  |
| min\_event\_counter | 事件发生次数范围的低线值 |
| max\_event\_counter | <ul><li>事件发生次数范围的高线值</li><li>在AppsFlyer生成的报告中，事件发生次数的计算方式如下：[min\_event\_counter + max\_event\_counter] / 2，然后取整</li></ul> |
| min\_event\_revenue | 事件收入范围的低线值（单位为美元） |
| max\_event\_revenue | <ul><li>事件收入范围的高线值（单位为美元）</li><li>在AppsFlyer生成的报告中，收入的计算方式如下：[min\_event\_revenue + max\_event\_revenue] / 2</li></ul> |
| min\_time\_post\_install | 激活后小时数（即用户最后一次与应用互动是在激活后的第几个小时）的低线值 |
| max\_time\_post\_install | 激活后小时数（即用户最后一次与应用互动是在激活后的第几个小时）的高线值 |
| last\_config\_change | 您在SKAN转化值操作台中保存配置的日期 |

</Accordion>

<div id="conversion-value-capacity-formula" />

<Accordion title="转化值消耗度的计算方式">

如上文所述，您最多可以使用64个转化值。您可以使用以下公式来计算某个衡量模式下的转化值消耗数量。

```http
(activity time duration in hours / interval size in hours) * 
(number of revenue ranges + 1 ) * 
(number of in-app event ranges + 1 ) * 
(number of steps in a funnel + 1)
```

请根据实际添加的衡量维度数量来调整公式。

</Accordion>

<div id="maximized-custom-cv-examples" />

<Accordion title="自定义模式下CV值完全消耗示例">

#### 示例 1

| 组成部分 | 说明 |
| --- | --- |
| 用户行为窗口期 | <ul><li>时长：24小时</li><li>间隔：每24小时为1个间隔</li></ul> |
| 收入 | <ul><li>通过单个应用内事件上报总体收入</li><li>收入范围：15</li></ul> |
| 应用内事件 | 无 |
| 漏斗 | 3个应用内事件 |

#### 示例 2

| 组成部分 | 说明 |
| --- | --- |
| 用户行为窗口期 | <ul><li>时长：24小时</li><li>间隔：每12小时为1个间隔，共2个间隔</li></ul> |
| 收入 | <ul><li>上报的收入按类型关联到2个不同的应用内事件</li><li>收入范围：3个（每个应用内事件配有一个范围）</li></ul> |
| 转化事件 | 1个用于衡量转化的应用内事件，每个事件配有1个范围 |
| 漏斗 | 无 |

#### 示例3

| 组成部分 | 说明 |
| --- | --- |
| 用户行为窗口期 | <ul><li>时长：24小时</li><li>间隔：每24小时为1个间隔</li></ul> |
| 收入 | <ul><li>通过单个应用内事件上报总体收入</li><li>收入范围：3</li></ul> |
| 互动事件 | <ul><li>2个用户衡量互动次数的应用内事件</li><li>事件发生次数范围：每个事件配有3个范围</li></ul> |
| 漏斗 | 无 |

#### 示例4

| 组成部分 | 说明 |
| --- | --- |
| 用户行为窗口期 | <ul><li>时长：48小时</li><li>间隔：每12小时为1个间隔，共4个间隔</li></ul> |
| 收入 | <ul><li>通过单个应用内事件上报总体收入</li><li>收入范围：7</li></ul> |
| 转化事件 | 1个用于衡量转化的应用内事件，需配置1个范围 |
| 漏斗 | 无 |

</Accordion>

<div id="priority-measurement-detailed-example" />

<Accordion title="优先级衡量示例说明">

广告主希望在自己的购物应用中重点衡量以下内容：

* **非付费**用户的行为
* **付费**用户的收入

这样，广告主就能利用CV更精准地记录收入。上述衡量目标可转化为下表所列的一系列衡量优先级。

这里需要注意以下几点：

* 最高的优先级永远是1。**请注意**：优先级的序号不直接对应到CV值。CV值的映射按界面显示为准。
* 您最多可以设置63个优先级。实际的优先级数量上限取决于用户行为窗口期以及SSOT的使用状态。
* 每个优先级可包含收入范围和/或应用内事件发生次数范围。
* 范围值：范围中不包含其最小值，但包含最大值。比如在$5-$10这个范围中，不包含5，但包含10。

#### 优先级设置示例

<table><thead><tr><th>优先级序号</th><th>收入范围</th><th>应用内事件</th></tr></thead><tbody><tr><td>1【最高优先级】</td><td>$5-$10</td><td>send_recommendation</td></tr><tr><td>2</td><td>$5-$10</td><td>--</td></tr><tr><td>3</td><td>$0-$5</td><td>send_recommendation</td></tr><tr><td>4</td><td>$0-$5</td><td>--</td></tr><tr><td>5</td><td>--</td><td>send_recommendation<br/>add_to_cart</td></tr><tr><td>6</td><td>--</td><td>send_recommendation</td></tr><tr><td>7【最低优先级】</td><td>--</td><td>add_to_cart</td></tr><tr><td colspan="3">-- 未设置值</td></tr></tbody></table>

下表列出了用户链路场景。每个场景都包含了在用户链路中发生的一系列行为以及由AppsFlyer判定的优先级。

表格说明：

* 用户行为之间以 > 隔开。
* 括号中的值指用户行为发生后由AppsFlyer判定的优先级。AppsFlyer会根据该优先级来更新应用中的CV。

#### 用户链路场景

| 用户链路场景 | 用户行为及优先级 |
| --- | --- |
| A | add\_to\_cart (7) |
| B | add\_to\_cart (7) > send\_recommendation (5) |
| C | Purchase $3 (4) |
| D | Purchase $6 (2) |
| E | Purchases $6 (2) > send\_recommendation (1) |

</Accordion>

<div id="fixed-mode-examples" />

<Accordion title="【历史版本】固定模式示例">

> 📘 **注意**
>
> 自2024年6月23日起，固定模式不再对新增应用开放。AppsFlyer通过自定义模式和SKAN 4模式支持所有相关功能。

#### 示例A：衡量收益

| 考量因素 | 说明 |
| --- | --- |
| 场景 | <ul><li>20个用户激活应用并完成了以下购买事件：<ul><li>9个用户各购买了10美元的商品</li><li>5个用户各购买了5美元的商品</li><li>1个用户分次下单购买了1美元、3美元、5美元和1美元的商品，共计花费10美元。</li></ul></li><li>广告平台通过API上报的成本为30美元。</li></ul> |
| SKAN配置 | <ul><li>选择衡量类型：收入</li><li>设置转化系数：1个转化单位 = $1</li><li>指定转化事件：您必须在SDK中使用*af\_revenue*参数发送收入数据。</li></ul> |
| 指标选择 | 与收入相关的可用指标<ul><li>激活：20</li><li>收入：$125</li><li>转化：15</li><li>ARPU：$6.25</li><li>ROI：316%</li></ul> |
| 各报告中的原始数据行数 | <Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports">您可以通过Data Locker拉取原始数据报告</Anchor><ul><li>设备回传：20行</li><li>激活：20行</li><li>应用内事件：15行请注意：多次购买的用户在报告中仅以1行显示，收入为10美元。</li></ul> |
| 开发侧注意事项 | 带着金额的事件会被记录到 |

#### 示例B：衡量转化

<Table>
  <thead>
    <tr>
      <th>
        考量因素
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        示例
      </td>
      <td>
        * 5个用户（A-E）激活应用
        * 他们完成了0-3个不同的应用内事件，具体如下表所示
        * 广告平台通过API上报的成本为30美元。

        #### 各用户完成的应用内事件

        |  | 事件1 | 事件2 | 事件3 |
        | --- | --- | --- | --- |
        | 用户A | 完成 | 完成 | - |
        | 用户B | 完成 | - | 完成 |
        | 用户C | 完成 | 完成 | - |
        | 用户D | 完成 | 完成 | - |
        | 用户E | - | - | - |
      </td>
    </tr>
    <tr>
      <td>
        SKAN归因配置
      </td>
      <td>
        选择衡量类型：转化

        * 选择应用内事件：事件1、事件2、事件3
        * 在SKAN<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">面板</Anchor>中，选择一个事件来计算用户转化指标。您可以根据需要更改选定事件。
      </td>
    </tr>
    <tr>
      <td>
        指标选择
      </td>
      <td>
        #### 与应用内事件相关的可用指标

        | 指标 | 应用 | 事件1 | 事件2 | 事件3 |
        | --- | --- | --- | --- | --- |
        | 激活假量 | 5 |  |  |  |
        | 转化 | 4 |  |  |  |
        | 独立用户数 |  | 4 | 3 | 1 |
        | eCPA | $7.5 |  |  |  |

        **请注意： 由于事件1被指定为转化事件，因此其对应的值（4）被同时用作应用层级指标以及事件1的指标。**
      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports">您可以通过Data Locker拉取原始数据报告</Anchor>

        * 设备回传：5行
        * 激活：5行
        * 应用内事件：8行
      </td>
    </tr>
    <tr>
      <td>
        开发侧注意事项
      </td>
      <td>
        * 请确保应用内事件的正确打点。
        * SKAN解决方案不记录事件值（收入衡量场景除外）
      </td>
    </tr>
  </tbody>
</Table>

#### 示例C：衡量事件

<Table>
  <thead>
    <tr>
      <th>
        考量因素
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        示例
      </td>
      <td>
        5个用户激活应用后分别打开应用若干次，具体如下：

        #### App opens（应用打开）

        |  | 应用打开次数 |
        | --- | --- |
        | 用户A | 63 |
        | 用户B | 10 |
        | 用户C | 5 |
        | 用户D | 1 |
        | 用户E | - |
      </td>
    </tr>
    <tr>
      <td>
        SKAN归因配置
      </td>
      <td>
        * 选择衡量类型：广告交互
        * 指定转化事件：af\_app\_opened。请注意：您可以选择任何一个可用事件。
      </td>
    </tr>
    <tr>
      <td>
        指标选择
      </td>
      <td>
        该场景中的可用指标：

        * 激活：5
        * 转化：4
        * 应用打开（Sessions）：79
      </td>
    </tr>
    <tr>
      <td>
        各报告中的原始数据行数
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports">您可以通过Data Locker拉取原始数据报告</Anchor>

        * 设备回传：5行
        * 激活：5行
        * 应用内事件：4行；每行代表一次应用打开（session）  
          请注意：在本示例中，由于有四个不同的独立用户分别完成了这个事件，因此会分四行显示。  
          为了统计并计算实际的事件发生次数，每行会附有事件计数的最小值和最大值。
      </td>
    </tr>
    <tr>
      <td>
        开发侧注意事项
      </td>
      <td>
        用户每次完成选定的互动事件后，应用侧都需要发送应用内事件，因为SKAN会记录事件发送的次数。
      </td>
    </tr>
  </tbody>
</Table>

<div id="skan-conversion-studio-api" />

<Accordion title="SKAN Conversion Studio API">

如果您想要为多个应用配置相同的SKAN转化值映射，这时在转化值操作台中为每个应用分别设置映射构架不仅费时费力，而且操作起来也很麻烦。这种情况下，您可以使用SKAN Conversion Studio API来减轻相关的工作量。只需在转化值操作台的面板中完成一个SKAN映射构架的配置，然后即可通过该API让这个构架在多个应用中生效。**请注意**：该API仅支持通过转化值操作台面板的SKAN 4或自定义模式配置的映射构架。

**SKAN Conversion Studio API的使用方法如下：**

1. 获取<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">API token</Anchor>。只有账户管理员才能获取该token。
2. 将该API token发送给您的开发人员，用于认证头（Authentication Header）中。
3. 请将以下应用的ID发给您的开发人员：
   * 已在面板中配置了SKAN映射构架的应用（后续要将这个应用的SKAN映射构架复制到其他应用）
   * 需要使用这个SKAN映射构架的所有应用。
4. 让您的开发人员按照开发者资源中心的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-studio-config-overview-1">SKAN Conversion Studio API</Anchor>使用指南

**请注意**：

* 调用该API时，一次仅可将相关映射构架复制到一个应用中。但您也可以让开发人员创建一个脚本，用于将所需的映射构架复制到多个应用中。
* 代理无法使用SKAN Conversion Studio API。

</Accordion>

</Accordion>

## 其他操作

<div id="change-skan-measurement-mode" />

<Accordion title="切换SKAN衡量模式">

这里需要注意以下几点：

* 启用SKAN 4衡量模式后，建议不要再切换到之前的模式。
* 更改后的设置会在UTC时间00:00 AM生效，此后有一段过渡期，在此期间AF会根据更改后的设置来解析转化值，但有时在更改后接收到的回传数据中实际包含的是更改前的激活。
* 更改设置不会影响上报的激活数量，该数据保持准确。

</Accordion>

<div id="disable-skan-measurement" />

<Accordion title="停用SKAN衡量">

请按以下步骤关闭SKAN衡量：

1. 从AF后台进入**配置** > **SKAN转化值操作台**。
2. 点击 ⋮ 图标。
3. 关闭**SKAN衡量**。  
   *SDK会停止调用registerAppForAdNetworkAttribution和updateConversionValue等函数。*
4. 点击**保存更改**。

</Accordion>

<div id="report-events-by-servertoserver-api" />

<Accordion title="通过S2S API上报事件">

![SKAdNetwork_-_S2S__2_.png](https://files.readme.io/ed55e5c10184afcc27ce7e414a3213f69d2c20bd70d38f78be338f1b17254ee2-16281446657937.png)

SDK和<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API</Anchor>都可以向AppsFlyer服务器发送应用内事件。

**S2S**的数据发送链路如下：

* 广告主服务器中的用户完成了一个事件，此时的应用可以是打开的，也可以是关闭的。
* 广告主服务器通过S2S向AppsFlyer上报该事件。
* AppsFlyer计算更新后的转化值，然后：
  * 如果应用在用户设备上处于打开状态：SDK会收到更新后的转化值，并更新设备的iOS转化值。
  * 如果应用在用户设备上处于关闭状态：服务器会等到应用打开后再向SDK发送转化值，但应用必须在用户行为窗口期结束前打开，否则该事件会流失。

**SDK版本要求**

* 请在应用中接入最新版本的SDK。**请注意：** 这里无需开发人员进行任何操作。

**请按以下步骤启用S2S API的应用内事件发送：**

1. 此时可完成以下任一操作：
   * 如果您选择了SKAN 4或自定义（Custom）衡量模式：
     * 无需更改设置。
   * 如果您选择了收入、转化或互动模式：
     1. 从AF后台进入**配置** > **SKAN转化值操作台**。
     2. 点击（⋮）选项图标。
     3. 打开**通过S2S API记录应用内事件**的开关。
2. 通过S2S发送事件。

**局限性**

* 如果您对用户启用了*匿名化*功能，则无法通过S2S发送该用户的事件。

</Accordion>

<div id="add-ssot-to-fixed-mode-measurements" />

<Accordion title="在固定衡量模式中添加SSOT">

> 📘 **注意**
>
> 自2024年6月23日起，固定模式不再对新增应用开放。AppsFlyer通过自定义模式和SKAN 4模式支持所有相关功能。

如果您设置了收入或互动衡量模式，则单一可信数据源（即SSOT，该机制可对数据去重并准确地上报iOS数据）默认处于关闭状态。<Anchor target="_blank" href="/marketers/zh/docs/single-source-of-truth-ssot-guide-for-ios-attribution">详情请见SSOT指南</Anchor>

**如果您已设置了收入或互动模式，可以按以下方式启用SSOT**：

1. 从AF后台进入**配置** > **SKAN转化值操作台**。
2. 向下滚动到您正在使用中的衡量模式。
3. 点击 **+ 添加单一可信数据源**。
   * 单一可信数据源开关自动打开。
   * SSOT开启后衡量模式中的范围会自动调整，这是为了给SSOT留出一定的转化值空间。
4. 点击**保存**。

<div id="conversion-value-decrease" />

<Accordion title="转化值降低">

在[SKAN 4](/docs/skan-conversion-studio#skan-4)模式中，您可以选择让转化值（CV）升高或降低。默认设置下，CV值仅可升高。允许转化值降低后，发送负向的收入时，相关窗口期内的回传中会包含最新值（而非最高值），即使之前出现过更高的值。[三个窗口期](/docs/skan-conversion-studio#measurement-principles-and-definitions)内产生的所有精细值和粗略值都会消耗转化值额度。   
**请注意：** 广告收入永远不会出现负值。

如需将转化值设置为允许降低，请按以下方式操作：

1. 从AF后台进入**配置** > **SKAN转化值操作台**。
2. 选择**SKAN 4.0**衡量模式。
3. 点击（⋮）选项图标，界面会显示选项菜单。
   * 请确保**允许转化值降低**的开关已打开。   
     **请注意**！必须符合以下条件才能够使用该开关：
     * 进行操作之前，相关应用已保存在转化值操作台的SKAN 4模式中
     * 进行操作的用户具有编辑权限

#### 示例

**负向收入示例**

| CV | 收入 | 应用内事件 |
| --- | --- | --- |
| 3 | $20 - $30 |  |
| 2 | $10 - $20 | af\_add\_to\_cart |
| 1 | $0 - $10 |  |
| 0 | 不适用 | install |

**示例1**

用户完成了一个价值5美元的购买事件 - 这时CV 1会上升。  
之后，该用户又完成了一个价值20美元的购买事件 - 这时CV 3会上升。  
然后，该用户完成了一个价值为-10美元的购买事件 - 这时CV 1会下降。  
然后，该用户完成了一个add\_too\_cart（加购）事件 - 这时CV 2会上升。

**示例 2**

用户完成了一个价值25美元的购买事件 - 这时CV 3会上升。  
然后该用户触发了af\_add\_to\_cart事件 - 该事件会留在CV 3中。  
然后，该用户完成了一个价值为-20美元的购买事件 - 这时CV 1会下降。

**应用内事件架构示例**

| CV | 应用内事件 |
| --- | --- |
| 3 | af\_purchase |
| 2 | af\_add\_to\_cart |
| 1 | session |
| 0 | install |

**示例**

用户完成了一个session（应用打开） - 这时CV 1会上升  
该用户随后完成了一个购买事件 - 这时CV 3会上升  
然后，该用户又完成了一个session（应用打开） - 这时CV

</Accordion>

<div id="support-anonymized-users" />

<Accordion title="支持匿名用户">

打开**支持匿名用户**的开关后，可在保护<Anchor target="_blank" href="/marketers/zh/docs/apply-privacy-preserving-sdk-methods#用户信息匿名化">匿名用户</Anchor>隐私的同时，确保其SKAN转化值得到准确的更新。

> 🚧 **重要提示！**
>
> 这一功能仅适用于通过<Anchor target="_blank" href="/marketers/zh/docs/apply-privacy-preserving-sdk-methods#用户信息匿名化">用户匿名化方法</Anchor>对所有用户的身份识别信息进行移除和加密的应用。对于这类应用，如需确保SKAN数据的准确性，必须打开**支持匿名用户**开关。

该功能的必要性  
SKAN根据激活后的用户行为，通过标识符来更新转化值。如果某个应用在调用start方法之后调用了**用户匿名化方法**，系统就无法将部分激活后事件关联到初始的激活，导致转化值更新不准确。  
打开**支持匿名用户**开关后，系统就会在应用激活时创建加密的标识符，这样就能让相关应用准确地将用户行为关联到初始激活。即使该用户在后续的某个时间点进行了匿名化，仍能确保数据上报的准确性。

</Accordion>

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 代理 | 代理对<Anchor target="_blank" href="/partners/zh/docs/getting-started-agency-onboarding#skan转化值操作台的访问权限">广告主SKAN转化值操作台的权限有限</Anchor>。 |
| 粗略值 | <ul><li>最多可涵盖10个衡量维度。</li><li>使用多个衡量维度时，如需确保粗略值的编码，所有相关事件都必须发生。</li></ul> |
| 自然应用内事件 | 在SKAN 4的自定义（Custom）和解析（Decode）模式下，应用内事件和总收入的自然量指标不可用。 |
| 模糊数据 | 更改SKAN配置后的48-72个小时内，面板和原始数据报告中的数据是模糊数据。这是由于iOS计时器的限制，AF无法判断用于解析回传的配置是否与之前对其进行编码的配置相匹配。 |
|  |  |

</Accordion>

<div data-zendesk-anchors="skan-conversion-studio-basics=skan%E8%BD%AC%E5%8C%96%E5%80%BC%E6%93%8D%E4%BD%9C%E5%8F%B0%E5%9F%BA%E7%A1%80%E6%93%8D%E4%BD%9C%E6%8C%87%E5%8D%97 01H7Z08MFDASBCBJD18QTXYSXK=skan%E8%BD%AC%E5%8C%96%E5%80%BC%E6%93%8D%E4%BD%9C%E5%8F%B0%E5%9F%BA%E7%A1%80%E6%93%8D%E4%BD%9C%E6%8C%87%E5%8D%97 01H7Z08MFDX3VYJTSWXQ5HQ7BZ=measurement-principles-and-definitions s2s-principles=s2s%E5%8E%9F%E7%90%86 01H7Z08MFDWRGVNXB62Z6CT1G7=s2s%E5%8E%9F%E7%90%86 setting-up-conversion-values-in-skan-conversion-studio=%E5%9C%A8skan%E8%BD%AC%E5%8C%96%E5%80%BC%E6%93%8D%E4%BD%9C%E5%8F%B0%E4%B8%AD%E8%AE%BE%E7%BD%AE%E8%BD%AC%E5%8C%96%E5%80%BC 01H7Z08MFDB76C6Z5SSXHFT71P=%E5%9C%A8skan%E8%BD%AC%E5%8C%96%E5%80%BC%E6%93%8D%E4%BD%9C%E5%8F%B0%E4%B8%AD%E8%AE%BE%E7%BD%AE%E8%BD%AC%E5%8C%96%E5%80%BC 01H7Z08MFDEAYHJAG9XA2TGBWV=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA 01H7Z08MFD7VY1QP85W0YPK8RC=skan-4 01H7Z08MFD3SWVZK68K45NYDP8=custom 01H7Z08MFDZ1EKDQNZWGF7DHK9=fixed-modes h_01J14HX28C9TFDP0MDRYWFV6Q3=%E6%B3%A8%E6%84%8F fixed-mode-measurement=%E5%9B%BA%E5%AE%9A%E8%A1%A1%E9%87%8F%E6%A8%A1%E5%BC%8F 01H7Z08MFDAYVJKJBT08R82N26=%E5%9B%BA%E5%AE%9A%E8%A1%A1%E9%87%8F%E6%A8%A1%E5%BC%8F 01H7Z08MFDCJGZGQR2JR4WQVHR=decode measurement-components=%E8%A1%A1%E9%87%8F%E7%BB%B4%E5%BA%A6 01H7Z08MFDFE345QWHF77RGTD7=%E8%A1%A1%E9%87%8F%E7%BB%B4%E5%BA%A6 01H7Z08MFE5G01NGY5EFTAW93M=single-source-of-truth 01H7Z08MFERDJHSD8NT5KN7DKN=inapp-event-component 01H7Z08MFETMGAE67X499V4092=revenue-component 01H7Z08MFEQG2HRJBWBYFTW3ZK=funnel-component 01H7Z08MFE22J8DDBDNJ18KBEJ=priority-measurement-component 01H7Z08MFES844SS08HS17Y29R=lock-window 01H7Z08MFE61QCC0MZW5RJ910B=activity-window additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H7Z08MFET64PSAVMREQ4HP4S=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H7Z08MFEKP9WNGJD2GBVKB0P=view-cv-mapping csv-mapping-file-columns=cv%E6%98%A0%E5%B0%84%E6%96%87%E4%BB%B6%E5%90%84%E5%88%97%E8%AF%B4%E6%98%8E 01H7Z08MFETCB428W1TXTH2HJ8=cv%E6%98%A0%E5%B0%84%E6%96%87%E4%BB%B6%E5%90%84%E5%88%97%E8%AF%B4%E6%98%8E 01H7Z08MFE5CBQK024CF8FARJ9=conversion-value-capacity-formula 01H7Z08MFETZVQSNWX639E56SK=maximized-custom-cv-examples example-1=%E7%A4%BA%E4%BE%8B-1 01H7Z08MFEXME7RV67XTZRDWJE=%E7%A4%BA%E4%BE%8B-1 example-2=%E7%A4%BA%E4%BE%8B-2 01H7Z08MFEHRF4656X5AR301D8=%E7%A4%BA%E4%BE%8B-2 example-3=%E7%A4%BA%E4%BE%8B3 01H7Z08MFEK0725CN35TP3MPYT=%E7%A4%BA%E4%BE%8B3 example-4=%E7%A4%BA%E4%BE%8B4 01H7Z08MFES7W3EF2JJ8B75K99=%E7%A4%BA%E4%BE%8B4 01H7Z08MFF2JXA0BFNKCW3ZCZ7=priority-measurement-detailed-example measurement-priorities-setting-example=%E4%BC%98%E5%85%88%E7%BA%A7%E8%AE%BE%E7%BD%AE%E7%A4%BA%E4%BE%8B 01H7Z08MFFXAAC37MBV0ES6ADQ=%E4%BC%98%E5%85%88%E7%BA%A7%E8%AE%BE%E7%BD%AE%E7%A4%BA%E4%BE%8B user-journey-scenarios=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E5%9C%BA%E6%99%AF 01H7Z08MFFJ9TQMH0Q93B7N1A8=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E5%9C%BA%E6%99%AF 01H7Z08MFFNBXECB8A5Y0KH9C8=fixed-mode-examples h_01JJH6WZY2QMKAR1C7B5JTMMKE=%E6%B3%A8%E6%84%8F-1 example-a-revenue-measurement=%E7%A4%BA%E4%BE%8Ba%E8%A1%A1%E9%87%8F%E6%94%B6%E7%9B%8A 01H7Z08MFFVKZN3Y2R1ZEVEW4D=%E7%A4%BA%E4%BE%8Ba%E8%A1%A1%E9%87%8F%E6%94%B6%E7%9B%8A example-b-conversion-measurement=%E7%A4%BA%E4%BE%8Bb%E8%A1%A1%E9%87%8F%E8%BD%AC%E5%8C%96 01H7Z08MFFNBA5786R5XZDA5FG=%E7%A4%BA%E4%BE%8Bb%E8%A1%A1%E9%87%8F%E8%BD%AC%E5%8C%96 inapp-events-performed-by-users=%E5%90%84%E7%94%A8%E6%88%B7%E5%AE%8C%E6%88%90%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 01H7Z08MFFA7C6HWQPADZXQQNC=%E5%90%84%E7%94%A8%E6%88%B7%E5%AE%8C%E6%88%90%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 inapp-related-metrics-available=%E4%B8%8E%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9B%B8%E5%85%B3%E7%9A%84%E5%8F%AF%E7%94%A8%E6%8C%87%E6%A0%87 01H7Z08MFF1PEE91J5CJN1GC7V=%E4%B8%8E%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9B%B8%E5%85%B3%E7%9A%84%E5%8F%AF%E7%94%A8%E6%8C%87%E6%A0%87 example-c-engagement-measurement=%E7%A4%BA%E4%BE%8Bc%E8%A1%A1%E9%87%8F%E4%BA%8B%E4%BB%B6 01H7Z08MFF8V718C23PQ2NG3C3=%E7%A4%BA%E4%BE%8Bc%E8%A1%A1%E9%87%8F%E4%BA%8B%E4%BB%B6 app-opens=app-opens%E5%BA%94%E7%94%A8%E6%89%93%E5%BC%80 01H7Z08MFF4PRHSR8NCJ1Q78WM=app-opens%E5%BA%94%E7%94%A8%E6%89%93%E5%BC%80 01H7Z08MFFVS6MYC9EB3KP0H2Y=skan-conversion-studio-api additional-procedures=%E5%85%B6%E4%BB%96%E6%93%8D%E4%BD%9C 01H7Z08MFFPZ4GKM5GFMAE2HDJ=%E5%85%B6%E4%BB%96%E6%93%8D%E4%BD%9C 01H7Z08MFFPKCX5TFQQTMYJEGW=change-skan-measurement-mode 01H7Z08MFF78F9NMWJATYE2YFE=disable-skan-measurement 01H7Z08MFFD4T3D71A6R9K83A3=report-events-by-servertoserver-api 01H7Z08MFFFAEW6NP0YAX773B3=add-ssot-to-fixed-mode-measurements h_01JJH6WZY2R2H1F9ZBGTR0FDNM=%E6%B3%A8%E6%84%8F-2 h_01HKVT9N2KFJQGCWVMGP59YWRH=conversion-value-decrease examples=%E7%A4%BA%E4%BE%8B h_01HM3C8BEG5Z7ZRY12MF3Q4W4K=%E7%A4%BA%E4%BE%8B 01JCWF4HM4KKB0WC8MN00SV4XK=support-anonymized-users 01JCWFY9RZ7JSC63TVBTPRCYHH=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 01H7Z08MFFG9EQFVEKN3AXE9DD=specifications-and-limitations" />
