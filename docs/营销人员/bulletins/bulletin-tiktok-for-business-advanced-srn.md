---
title: 公告：TikTok for Business——高级SRN
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-07-26T12:27:56Z'
  edited_at: '2026-10-14T10:15:40Z'
  id: 7925111265041
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/7925111265041
---
<div id="note" />

> 📘 **注意**
>
> 2023年1月30日，我们上线了新的TikTok for Business高级SRN对接**tiktokglobal\_int**，`TikTok for Business的历史对接`**bytedanceglobal\_int**将逐步下线，到2024年3月完全停用。此次变更的过渡将由TikTok负责处理，他们会通知所有相关客户，引导其删除历史对接。**为了避免出现数据丢失问题，请确保新对接和历史对接在过渡期间都处于启用状态**。

| <span id="headline"></span>**内容提要** | AppsFlyer现在支持将TikTok For Business作为高级自归因平台（SRN）来配置对接 |
| --- | --- |
| <span id="effective-date"></span>**生效日期** | <ul><li>1月18日`tiktokglobal_int`</li><li>2024年7月31日</li></ul> |
| <span id="where-is-it-changing"></span>**变更内容** | 活跃对接部分的TikTok For Business对接页面。 |
| <span id="required-actions"></span>**待办事项** | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-advanced-srn-integration-setup">设置新对接</Anchor>。TikTok For Business更新后的PID为`tiktokglobal_int`。</li><li>如果您现在还在使用TikTok For Business的历史对接（`bytedanceglobal_int`），切勿在**过渡日期**之前删除该对接（详见下一行），否则可能会出现数据丢失。</li></ul> |
| <span id="transition-date"></span>**过渡日期** | 启用新对接并经TikTok For Business测试验证可正常生效后，他们会通知您确切的过渡日期，从历史对接`bytedanceglobal_int`过渡到新对接。这一过程**最多可能需要45天**，在此期间面板和报告仍会持续呈现来自历史对接的数据。<br /><br />在过渡日期之后，面板和报告就会显示来自新对接`tiktokglobal_int`的数据。<br /><br />**请注意：** 请注意：如果您不从历史对接过渡，直接使用新对接，则面板和报告会立即呈现来自新对接的数据。 |
| <span id="what-does-this-new-integration-mean"></span>**新对接的作用** | <ul><li>**面板和报告**<ul><li>过渡完毕后，所有由TikTok For Business带来的新增转化都会归因到新的PID（即`tiktokglobal_int`）。</li><li>在启用新对接前记录到的点击和展示仍会归因到`bytedanceglobal_int`。</li></ul></li><li><Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">汇总的点击和展示</Anchor>过渡完毕后，点击和展示信息将从原始数据报告转移到汇总数据报告中（需先启用TikTok的API对接）。<br />**请注意：**<ul><li>设置对接时请务必启用API对接。</li><li>过渡到新对接时，AppsFlyer需要处理大量衡量信息上报的转移工作，因此无法即时呈现新对接的点击和展示数据。</li></ul></li><li>**成本数据**<ul><li>如果您同时启用了<Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">`tiktokglobal_int`</Anchor>和`bytedanceglobal_int`新旧两个<Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">成本对接</Anchor>，**同样的成本数据可能会重复出现**。为了避免此问题，请确保**仅有一个成本对接处于启用状态**。<br />但启用新的成本对接时，新对接会自动收集过渡日前5天的成本数据。也就是说，新对接会重复显示这5天的成本数据。**举例来说**，假设您在1月15日停用了历史成本对接，并在同一天启用了新的成本对接，您就会在新对接中看到1月10日到14日之间的成本数据出现重复。</li><li>**请按以下方式确保仅有一个成本对接处于启用状态：**<ol><li>在**过渡日**当天进入**历史对接**的**成本**选项卡，**关闭**成本对接开关。</li><li>然后进入**新对接**的**成本**选项卡，**打开**成本对接开关。</li></ol></li><li>过渡完毕后，成本数据会关联到新的PID。如需查看历史成本数据，请在相关面板中使用历史PID来筛选数据。</li><li>在过渡期间的数天内，激活数量可能会在新老两个对接之间进行拆分，而成本数据则不会拆分。请注意：在此期间，基于成本和激活数据的KPI（如eCPI和ROI）可能会有偏差。<br />cost integration on.png</li></ul></li></ul><ul><li>**SKAN回传**<br />`SKAN回传`过渡完毕后，所有的SKAN回传都会关联到新对接tiktokglobal\_int。</li><li>**访客找回营销活动**<br />**再营销广告向新对接过渡时，再互动开关默认关闭，无论该开关在历史对接中是否打开。对于<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销广告</Anchor>，为了确保过渡前后的连贯一致，请务必在新对接中打开再互动开关。**</li></ul> |
| <span id="example-illustrating-the-process"></span>**流程说明示例** | <ul><li>确保成本对接开关处于关闭状态。虽然新旧两个对接都处于启用状态，但由于新对接尚未生效，因此不会对其归因。</li><li>数据验证通过后，他们会通知您具体的过渡日期。在本示例中，假设过渡日期为第11天。<br />在此期间，面板和报告都仅呈现历史对接的归因数据。如果新旧两个对接中的成本开关都处于启用状态，则两个对接都会显示重复的成本数据。为了避免出现这样的情况，建议确保新对接中的成本开关保持关闭。</li><li>自过渡日期起的一周内（直到所有旧的点击全都失效），激活归因数据会拆分到新旧两个对接，具体如下：<ul><li>在新对接中，TikTok作为SRN发送数据。</li><li>在历史对接中，AppsFlyer仍会对过渡日期之前发生的旧点击进行归因。</li></ul></li><li>在接下来的60天里，可能仍会持续出现归因到历史对接的应用内事件。因此，为了让AppsFlyer能持续发送这些事件的回传，建议确保历史对接处于启用状态（即渠道对接选项卡中的开关保持打开）。<br />如果新对接中的成本开关之前一直处于关闭状态，您可以在这个阶段将其打开。为了避免成本数据的重复，请关闭历史对接中的成本开关。</li><li>此时，TikTok已完全成为SRN，不再需要应用内事件回传。<br />如果您在此时仍未关闭历史对接中的成本开关，那么即使您已经关闭历史对接，还是会在新对接中看到重复的成本数据。</li></ul> |

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="https://appsflyer.showpad.com/share/XB6r4QA1TN0wN63kqmslA">如何顺利切换到新的TikTok高级SRN对接</Anchor>
> * AppsFlyer产品更新速览

<div data-zendesk-anchors="01H8JZVADPFQ4NTHMCB8PSCV6P=%E6%B3%A8%E6%84%8F h_01HDPFFJ6129APQF5DV3TV0SM2=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
