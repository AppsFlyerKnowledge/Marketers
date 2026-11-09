---
title: 从Google Ads拉取SKAN回传数据
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
  created_at: '2021-06-28T19:34:39Z'
  edited_at: '2026-10-14T10:10:17Z'
  id: 4403215779857
  locale: zh-cn
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/zh-cn/articles/4403215779857
---
> **概要：概要：本文介绍了使用Google对接时如何与AppsFlyer共享您iOS应用的SKAN回传数据。**

<div id="get-skan-postback-data-from-google-ads" />

## 从Google Ads拉取SKAN回传数据

如果您与多个广告平台合作，建议您在AppsFlyer后台设置您与这些渠道的SKAN互通，这样您不仅能获得所有平台的SKAN效果指标，还可以利用AppsFlyer平台上的其他可用指标（如成本等）来扩充这些数据。

**Google Ads的SKAN数据上报范围**

* 广告主使用Google Ads投放iOS应用的广告时，Google Ads会与AppsFlyer共享其接收到的iOS SKAN回传汇总数据。
* AppsFlyer会在解析回传数据后更新SKAN面板和报告（包括回传原始数据报告）。
* <Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#ios-145-srn-attribution">iOS 14.5对SRN数据上报的影响</Anchor>

**注意事项**：

接收到iOS回传后，Google会根据广告发布信号来判断末次点击时间。但AppsFlyer将点击时间作为激活时间，因此AppsFlyer和Google面板的数据之间会有差异。

考虑到Google的点击上报方式及其对数据的每日回滚更新，AppsFlyer会拉取前13天的数据，并在激活日期前的末次点击下展示相关激活。 举例来说，假设7月1日发生了点击，则从7月1日到8月15日之间， AppsFlyer会将相关激活展示在Google报告的点击日期下。这会对相关<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#reporting-options">报告</Anchor>产生以下影响：

* 汇总报告和面板会回滚更新。
* <Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports">原始数据报告</Anchor>不会回滚。Data Locker中的文件夹按Google将数据发送到AppsFlyer的日期（即数据接收日期）命名。

<div id="set-up-interoperation" />

## 设置SKAN互通

如需设置Google Ads与AppsFlyer之间的SKAN互通，请完成下列选项卡中的相关步骤。

<div id="set-up-postbacks" />

<Accordion title="设置回传">

**请按以下步骤设置回传发送：**

| 步骤 | 操作 | 说明 |
| --- | --- | --- |
| <span id="1"></span>1 | 检查SKAN设置 | 确认已设置并启用AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">SKAN方案</Anchor>，这样AppsFlyer SDK就能调用SKAN API，从而设置转化值。<br /><br />**SKAN设置的查看方式如下**：<ol><li>从AF后台进入**配置** > **SKAN转化值操作台**。</li><li>点击选项图标（⋮），并确认**SKAN衡量开关**已打开。</li></ol>![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)<ol><li>选择适合您需求的衡量模式。<br />详情请见<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">SKAN转化值操作台</Anchor>。</li><li>记下应用内事件的准确名称，在下一步流程中会用到。**请注意**：事件名称区分大小写。</li></ol> |
| <span id="2"></span>2 | AppsFlyer中的应用内事件映射 | **请按以下步骤查看并设置应用内事件映射**：<ol><li>从AppsFlyer后台进入**协作** > **活跃对接**。</li><li>选择**Google Ads**。</li><li>检查**渠道对接**选项卡中的**启用该渠道**开关是否已打开。若尚未打开，则必须先完成Google Ads对接配置。</li><li>向下滚动到**应用内事件回传**部分：<ol><li>确认**应用内事件回传**开关已打开。</li><li>建议您根据当前所选的衡量模式来设置事件映射。请注意：如果您使用的是收入模式，请确保将af\_skad\_revenue映射到相应的Google收入事件。</li></ol></li><li>向下滚动到页面底部。</li><li>点击**保存对接**。</li></ol> |

</Accordion>

<div id="allow-google-ads-to-share-skan-data-with-appsflyer" />

<Accordion title="让Google Ads将SKAN数据共享给AppsFlyer">

如需在AppsFlyer的SKAN面板中查看归因到Google Ads的SKAN激活，必须让Google Ads将SKAN数据共享给AppsFlyer。

**请按以下步骤为Google Ads开通与AppsFlyer的SKAN数据共享：**

1. 以下流程必须由广告主和/或代理完成。
2. 从AppsFlyer后台进入**协作** > **活跃对接**。
3. 搜索并选择**Google Ads**。
4. 进入**SKAN**选项卡。

   <Image align="center" alt="mceclip0.png" src="https://files.readme.io/ba8d881ca8430bfdcf67a37e862ad3e31a9af522f2f877d3fba30bc2e13006a6-4404428381457.png" width="309px" />
5. 如果界面弹出消息显示“**目前暂时不可用**”，一般是因为启用了广告屏蔽插件。发生这种情况时，请关闭广告屏蔽工具，然后刷新页面。如仍不可用，请联系 AppsFlyer 获取支持。

   <Image align="center" alt="mceclip1.png" src="https://files.readme.io/e86b868f71e11ad347ff7557a793090d9d6adb8fe4df4f9010c8d770b373ac6a-4404428420497.png" />
6. 点击**Google Ads登录**。
   * 您必须使用管理员账户登录到Google Ads。
   * 如果Google账户关联了多个应用，只需登录一次即可为所有应用授权，无需分应用逐个授权。
   * 您将相关应用添加到AppsFlyer后台后，AppsFlyer就会拉取与您的Google账户相关联的所有iOS应用的数据，无论您是否为这些应用打开了启用渠道开关。
7. 请按照用户界面的说明进行操作。
8. 某些情况下，界面可能会弹出提示消息，让您为AppsFlyer授权**管理您的AdWords广告投放**， 这时请开放该权限。不用担心，我们不会对您的投放设置做任何更改。

   <Image align="center" alt="GoogleManageAdWords.png" src="https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png" width="182px" />
9. 确认账户状态显示为**waiting for sync**（等待同步）。  
   在AppsFlyer成功从Google Ads拉取到数据前，界面会一直显示该消息（最多需要24小时）。
10. 请在第二天的UTC时间02:00之后检查账户状态是否变为**活跃**。  
    SKAN控制面板中的数据会在每天UTC时间08:00前更新。请注意：请注意：如注意事项部分所述，Google会回滚更新前45天的数据。
11. 详情请见[衡量数据差异说明](/docs/get-skan-postback-data-from-google-ads#measurement-and-timing-differences-between-appsflyer-and-google-ads)。

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="turning-off-the-skan-integration" />

<Accordion title="关闭SKAN对接">

关闭Google Ads对接时，不仅需要关闭**启用该渠道**按钮，还必须删除SKAN连接，才能停止SKAN数据的记录。

**请按以下步骤关闭SKAN对接：**

1. 从AppsFlyer后台进入**协作** > **活跃对接**。
2. 搜索并选择Google Ads。
3. 进入**SKAN**标签页。
4. 点击相关账户的删除图标。

</Accordion>

<div id="measurement-and-timing-differences-between-appsflyer-and-google-ads" />

<Accordion title="Google与AppsFlyer之间的衡量方式及时间安排差异">

| 注意事项 | 说明 |
| --- | --- |
| <span id="earliest-data-availability"></span>数据可用日期 | 从您启用对接的那天开始（UTC时间）呈现可用数据。由于Google使用点击时间，因此可回滚呈现启用日期前发生的激活。 |
| <span id="install-date"></span>Install date | Google会估算激活前的末次点击时间，以此作为激活时间。点击时间是Google通过广告发送信号来判断的。<br /><br />在对比AppsFlyer面板中的各渠道数据时，请注意以下几点：<ul><li>AppsFlyer不考虑应用或Google Ads账户的时区。</li><li>Google可回滚报告激活日期后45天内的激活数据。</li><li>对于来自其他媒体渠道的激活，AppsFlyer会使用回传接受时间来推算激活时间。</li></ul> |
| <span id="installs"></span>激活假量 | 从Google Ads API V10+开始，AppsFlyer仅展示回传中带有did\_win=TRUE的激活。因此AppsFlyer中呈现的激活数量可能会低于Google Ads面板中的数据。 |

</Accordion>

<div id="troubleshooting-and-faq" />

<Accordion title="故障排查和FAQ">

| 注意事项 | 说明 |
| --- | --- |
| <span id="sending-events-to-google-ads"></span>向Google Ads发送事件 | **问题**：问：对于在转化值衡量方案指定范围之外的其他事件，是否有必要向Google Ads发送其回传？<br /><br />**解答**：答：对于授权广告跟踪的用户，发送所有事件可提升Google Ads的投放优化能力。 |
| <span id="map-multiple-events-to-the-same-google-ads-event"></span>将多个AppsFlyer事件映射到同一个Google Ads事件 | **问题**：问：是否能将多个AppsFlyer事件映射到同一个Google Ads事件？<br /><br />**解答**：答：如果您将多个事件映射到同一个Google Ads标准事件，Google Ads就无法区分这些事件，因而会仅针对Google能够识别的某一个事件优化投放。 |
| <span id="campaign-types-supported"></span>适用的广告系列类型 | **问题： 问：AppsFlyer支持哪些类型的Google Ads广告系列？**<br /><br />**解答**：答：AF的SKAN互通支持网路到应用和应用到应用的iOS广告活动，包括搜索广告、视频广告等等。 |
| <span id="no-data-to-pull"></span>没有可以拉取的数据 | **问题：** 为什么连接状态显示为“No data to pull:<br /><br />**解答**：答：此时可能尚无SKAN数据，或者您需要通过相关账户中的管理员用户角色登入Google Ads。 |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| <span id="engaged-views"></span>深度浏览（Engaged Views） | AF会将深度浏览（Engaged Views）记录为点击，其回传发送方式与点击归因的回传发送方式相同。 |
| <span id="data-freshness"></span>数据时效性 | <ul><li>AppsFlyer每天从UTC时间01:00开始收集来自Google Ads的SKAN数据。</li><li>面板和汇总数据会在7小时后更新。</li></ul> |
| <span id="reports-available"></span>可用报告 | 您可以在SKAN面板以及汇总和原始数据报告中查看Google Ads的数据。详情请见SKAN上报方式。 |
| <span id="agencies"></span>代理 | 如果代理商在广告主的Google Ads账户中具有管理员用户的身份，那么他们可以直接代表广告主完成本文所述的SKAN互通操作，广告主则无需再登录到其Google Ads账号。广告主账户会对代理登录进行标记。 |

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">AppsFlyer的SKAN解决方案指南</Anchor>

<div data-zendesk-anchors="get-skan-postback-data-from-google-ads=%E4%BB%8Egoogle-ads%E6%8B%89%E5%8F%96skan%E5%9B%9E%E4%BC%A0%E6%95%B0%E6%8D%AE h_01HCHYGCVJA3C8WJS8JH7BG0CD=%E4%BB%8Egoogle-ads%E6%8B%89%E5%8F%96skan%E5%9B%9E%E4%BC%A0%E6%95%B0%E6%8D%AE set-up-interoperation=%E8%AE%BE%E7%BD%AEskan%E4%BA%92%E9%80%9A h_01HCHYGCVJY5KT4J6RQS0BJ90G=%E8%AE%BE%E7%BD%AEskan%E4%BA%92%E9%80%9A h_01HCHYGCVJKHF0NFJSAZMMKZ7Z=set-up-postbacks h_01HCHYGCVJEA39W87MWXF7P018=allow-google-ads-to-share-skan-data-with-appsflyer additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HCHYGCVJTS53PCGK21BEZB2T=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HCHYGCVJCSGKYQD3EH0GKZVS=turning-off-the-skan-integration h_01HCHYGCVJE80JX9BKE8NFMA45=measurement-and-timing-differences-between-appsflyer-and-google-ads h_01HCHYGCVJX832CCX87JHGD50W=troubleshooting-and-faq h_01HCHYGCVJ1D32JW8G9YSR27PN=specifications-and-limitations h_01HE7RMSECNDW9VD9XY6H01H55=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
