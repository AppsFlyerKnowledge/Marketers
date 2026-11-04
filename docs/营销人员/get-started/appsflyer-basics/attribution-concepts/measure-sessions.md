---
title: Session统计逻辑详解
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-03-14T12:13:13Z'
  edited_at: '2026-10-14T10:09:50Z'
  id: 360000520785
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000520785
---
> **概要**：广告主可以使用session（应用打开）指标衡量指定时间段内的用户互动情况。

<Image alt="DAU_example.jpg" src="https://files.readme.io/97b845b9e04809dc6b670746c81cf1ca59dce11f492194ee7e7895ada01c0b86-360016015278.jpg" width="461px" />

<div id="sessions-counting-principles" />

## session统计的原理

用户完成的session（即应用打开）数量是评估用户与应用的互动情况时需要用到的重要指标。AppsFlyer在多种报告和面板中都提供该指标。session数量还会用于计算下列指标：

* 每日活跃用户（DAU）
* 每月活跃用户（MAU）
* 留存
* 忠实用户数（以完成3次应用打开的默认标准计算）

**请注意：** 自然量的session数据呈现在活跃数据和群组面板中，总览面板不提供该数据。

<div id="sessions-calculation" />

### session的计算方式

我们通过SDK上报的*af\_app\_opened*事件来计算session指标。

在Data Locker的session原始数据中，*af\_app\_opened*事件以*launch*的形式呈现。除了Data Locker以外的其他数据传输工具不提供Session数据。为了便于理解，本文会使用*af\_app\_opened*来指称相关数据。

**Session的上报方式**

发生以下情况时，SDK会上报session：

* 用户打开相关应用。
* 相关应用从后台切换到前台。开发人员可以调用[setMinTimeBetweenSessions](/docs/measure-sessions#session-reporting-by-the-app-sdk)来更改此处的数据上报行为。
* 在安卓应用中，开发人员可手动设置session上报。比如总是在后台运行的工具类应用会使用这种方式上报session。

**Session指标**

<div id="minimum-time-between-sessions-mechanism" />

## Session之间的最短间隔机制

该机制会影响session数量的统计。**请注意：** 如果您设置的最短间隔较长（比如超过一小时的间隔），且用户在一天之内打开相关应用的次数较少，这时DAU和留存等的session相关指标会受到影响。特别是对于一般情况下用户每天打开一次的应用来说，影响尤为突出。

<div id="description-and-example" />

<Accordion title="说明和示例">

Session统计的流程如下：统计到一个session → 开始倒计时 → 倒计时期间上报的session会被忽略。

**示例**

前提假设：

| 场景示例 | session上报时间（从00:00起的分钟数） | 统计的session数量 | 被忽略的session |
| --- | --- | --- | --- |
| A | 0, 10, 20, 30 | 4 | 无 |
| B | 0, 1, 9, 11 | 2 | 21 |
| C | iOS回传延时：[24 + 48 ] / 2 = 36. | 3 | 15 |

</Accordion>

<div id="timer-setting" />

<Accordion title="计时器的设置">

* 默认值：10分钟
* 可以设置的范围：

  * 1-60分钟
  * 1-24小时

**请按以下方式设置session之间的最短间隔：**

1. 从AppsFlyer后台的侧边栏中选择**配置** > **应用配置**。
2. 设置**session之间的最短间隔**。
3. 点击**保存配置**。   
   新的配置会在一小时内生效。

</Accordion>

<div id="sessions-related-topics" />

## 与session相关的事项

<div id="retargeting-sessions" />

<Accordion title="再营销session">

* AppsFlyer自2020年7月12日起提供再营销的session数据。
* 您可以通过以下方式查看再营销的session数据：
  * 数据总览面板的“再营销”和“统一”视图。
  * 相关群组的“再营销”和“统一”视图。
    * 在“统一”视图中，如果相关session被同时匹配到UA和再营销渠道，则再营销渠道会获得最终的归因，且面板不会显示UA渠道。
    * 数据时效性：每天在UTC时间13:00更新。
  * Data Locker：可启用再营销session报告，其中包含再互动和再归因的session。
    * 数据时效性：有6小时的延迟。
* 再互动窗口期内发生的session会同时被归因到UA渠道和再营销渠道。同理，其他的再互动应用内事件也会受到<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">双重归因</Anchor>。
* 对于Google Ads和X Ads，*af\_app\_opened*事件只发送一次，以避免重复回传。

</Accordion>

<div id="sessions-postbacks-to-partners" />

<Accordion title="向渠道发送session回传">

您可以针对AppsFlyer统计到的每一个session，向渠道发送session<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#映射方式">回传</Anchor>。

* 如需发送session回传，请将*af\_app\_opened*手动映射到渠道侧的对应事件。请注意：在Data Locker的AppsFlyer原始数据报告中，该事件以*launch*的形式呈现。
* 请注意：这是一个量级较大的事件，很多渠道不希望接收这类事件。

<div id="note" />

> 📘 **注意**
>
> 只有启用了**Send Sessions**的渠道才能支持`af_app_opened`的映射。

</Accordion>

<div id="session-reporting-by-the-app-sdk" />

<Accordion title="分应用（SDK）的session上报">

**应用侧：** 每当用户打开相关应用或将其调到前台运行时，SDK会根据*setMinTimeBetweenSessions*设置，发送*af\_app\_opened*事件。

**服务器侧：然后按照与其他应用内事件相同的<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">归因规则</Anchor>，对统计到的session进行归因。**

<div id="explicit-sessions-reporting-by-the-developer-android-apps-only" />

#### **开发人员手动设置的session上报（仅适用于安卓）**

您可以在安卓应用中使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#logsession">logSession</Anchor>来手动上报session。iOS中没有等效的调用方式。

* 如果相关应用长时间时间在后台运行，您可能需要让开发人员在其中部署session上报逻辑。常见的此类应用包括电池管理、桌面启动、锁屏、杀毒等工具类软件。对于这类应用，可以考虑在每天午夜上报一个session，或按适合相关应用的频率来上报session。
* 除了上述方式，您也可以在用户完成特定应用内操作时记录session，比如点击*清除内存*按钮等等。

<div id="setting-minimum-time-between-app-launches" />

#### **设置应用打开之间的最短间隔**

您可以在SDK中设置两个session之间的最短间隔。也就是说，两个session之间的时间必须超过这个最短间隔，才能算作两个独立的session。

请使用***setMinTimeBetweenSessions***（即af\_app\_opened事件）来调控session之间的最短间隔，以便判定并统计独立session。

* 【默认】5秒。也就是说，一个session发生后，必须等待5秒才能上报下一个session。
* 该API支持session之间最短间隔的设置。

**具体设置方式请见`setMinTimeBetweenSessions`的SDK参考信息：**

<Tabs>
<Tab title="安卓">

请参考安卓SDK对接说明中的[`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setmintimebetweensessions)

</Tab>

<Tab title="iOS">

请参考iOS SDK对接说明中的[`minTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#mintimebetweensessions)

</Tab>

<Tab title="Unity">

请参考Unity SDK对接说明中的[`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/api#setmintimebetweensessions)

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="sessions-counting-principles=session%E7%BB%9F%E8%AE%A1%E7%9A%84%E5%8E%9F%E7%90%86 h_01HB8NDPNKERK1RR1Y09V2R2CC=session%E7%BB%9F%E8%AE%A1%E7%9A%84%E5%8E%9F%E7%90%86 sessions-calculation=session%E7%9A%84%E8%AE%A1%E7%AE%97%E6%96%B9%E5%BC%8F h_01HB8NDPNKFW6S28A3TC7W5J3C=session%E7%9A%84%E8%AE%A1%E7%AE%97%E6%96%B9%E5%BC%8F minimum-time-between-sessions-mechanism=session%E4%B9%8B%E9%97%B4%E7%9A%84%E6%9C%80%E7%9F%AD%E9%97%B4%E9%9A%94%E6%9C%BA%E5%88%B6 h_01HB8NDPNKF32E34M3CBJ6GMP8=session%E4%B9%8B%E9%97%B4%E7%9A%84%E6%9C%80%E7%9F%AD%E9%97%B4%E9%9A%94%E6%9C%BA%E5%88%B6 h_01HB8NDPNKERP5YVEXMPKP620B=description-and-example h_01HB8NDPNK6R2P682EPSPQ8MGH=timer-setting sessions-related-topics=%E4%B8%8Esession%E7%9B%B8%E5%85%B3%E7%9A%84%E4%BA%8B%E9%A1%B9 h_01HB8NDPNKPTJX56Q2SVAB6V6T=%E4%B8%8Esession%E7%9B%B8%E5%85%B3%E7%9A%84%E4%BA%8B%E9%A1%B9 h_01HB8NDPNMX2JTFHVTN14MVCCW=retargeting-sessions h_01HB8NDPNM5Z9ZHADD32EG66BJ=sessions-postbacks-to-partners h_01HYARHNQCWEHAFQ6B3FHZ0KTK=%E6%B3%A8%E6%84%8F h_01HB8NDPNM0Z7D1ZS7G952SSKK=session-reporting-by-the-app-sdk explicit-sessions-reporting-by-the-developer-android-apps-only=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E6%89%8B%E5%8A%A8%E8%AE%BE%E7%BD%AE%E7%9A%84session%E4%B8%8A%E6%8A%A5%E4%BB%85%E9%80%82%E7%94%A8%E4%BA%8E%E5%AE%89%E5%8D%93 h_01HB8NTFMR3Y9GHFP3EWMAATHY=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E6%89%8B%E5%8A%A8%E8%AE%BE%E7%BD%AE%E7%9A%84session%E4%B8%8A%E6%8A%A5%E4%BB%85%E9%80%82%E7%94%A8%E4%BA%8E%E5%AE%89%E5%8D%93 setting-minimum-time-between-app-launches=%E8%AE%BE%E7%BD%AE%E5%BA%94%E7%94%A8%E6%89%93%E5%BC%80%E4%B9%8B%E9%97%B4%E7%9A%84%E6%9C%80%E7%9F%AD%E9%97%B4%E9%9A%94 h_01HB8NTMC1JYPDWYG9YC8RNSEQ=%E8%AE%BE%E7%BD%AE%E5%BA%94%E7%94%A8%E6%89%93%E5%BC%80%E4%B9%8B%E9%97%B4%E7%9A%84%E6%9C%80%E7%9F%AD%E9%97%B4%E9%9A%94" />
