---
title: 设置回溯窗口
metadata:
  keywords:
    - Advertisers
    - look back
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-07T09:27:55Z'
  edited_at: '2026-10-14T10:14:50Z'
  id: 208338403
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/208338403
---
> **概要：** 您可以根据您与渠道之间的合作模式来调整点击和浏览的回溯窗口。

<div id="lookback-windows" />

## 回溯窗口

AppsFlyer为广告主提供可以自行配置的归因回溯窗口，便于广告主根据其与渠道的合作模式来调整归因窗口期。

您为每个渠道分别设置对应的归因回溯窗口后，AppsFlyer就能针对不同的渠道按不同的窗口进行归因。

**回溯窗口类型**分为以下几种：

* **点击回溯窗口**从点击到应用激活之间的最长间隔，在此期间发生的激活可以被归因到相关点击。如果用户在该窗口期过后完成激活，该激活会被记录为自然量。
* **深度点击回溯窗口:** 从深度点击（engaged click）到应用激活之间的最长间隔，在此期间发生的激活可以被归因到相关深度点击。 如果用户在该窗口期过后完成激活，该激活会被记录为自然量。
* **深度浏览回溯窗口:** 从深度浏览（engaged view）到应用激活之间的最长间隔，在此期间发生的激活可以被归因到相关深度浏览。 如果用户在该窗口期过后完成激活，该激活会被记录为自然量。
* **浏览型回溯窗口**：从浏览广告到应用激活之间的最长间隔，在此期间发生的激活可以被归因到相关广告。如果用户在该窗口期过后完成激活，该激活会被记录为自然量。

<div id="configurable-lookback-windows-per-attribution-type" />

#### 各归因类型对应的可配置回溯窗口

<table><thead><tr><th rowspan="2"><p><strong>归因类型</strong></p></th><th rowspan="2"><p><strong>归因方法</strong></p></th><th colspan="2"><strong>回溯窗口</strong></th></tr><tr><th><strong>范围</strong></th><th><strong>默认</strong></th></tr></thead><tbody><tr><td rowspan="3"><p>点击型归因</p><p>（所有媒体渠道）</p></td><td>Referrer、ID匹配</td><td>1-30天或<br/>1-23小时</td><td>7天</td></tr><tr><td>概率模型（移动端）</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">自动调整</a></td><td>最多24小时</td></tr><tr><td>概率建模（CTV、PC和主机 - 单一平台链接）</td><td>最长7天（在<code>af_lookback_window</code>链接参数中设置。）</td><td>7天</td></tr><tr><td rowspan="2"><p>深度点击型归因</p><p>(选择的非SRN <a href="./about-enriched-engagement-types#哪些广告平台可以上报深度浏览和深度点击" target="_blank">媒体来源</a>\*)</p></td><td>ID匹配</td><td>1-7天或1-23小时</td><td>2天</td></tr><tr><td>概率模型（移动端）</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">自动调整</a></td><td>最多24小时</td></tr><tr><td rowspan="2"><p>深度浏览型归因</p><p>(选择的非SRN <a href="./about-enriched-engagement-types#哪些广告平台可以上报深度浏览和深度点击" target="_blank">媒体来源</a>\*)</p></td><td>ID匹配</td><td>1-7天或1-23小时</td><td>2天</td></tr><tr><td>概率模型（移动端）</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">自动调整</a></td><td>最多24小时</td></tr><tr><td rowspan="4"><p>浏览型归因</p><p>（部分<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">媒体渠道</a>）</p></td><td>ID匹配</td><td><p>1-24小时</p><p>【2021年12月15日之前，该窗口最长可设置到7天】</p></td><td>24小时</td></tr><tr><td>概率模型（移动端）</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">自动调整</a></td><td>最多24小时</td></tr><tr><td>概率建模（CTV、PC和主机 - 单一平台链接）</td><td>最长7天（在<code>af_lookback_window</code>链接参数中设置。）</td><td>24小时</td></tr><tr><td>概率建模（CTV、PC和主机端 - <a href="./set-up-cross-platform-links-for-multi-device-campaigns#特点与局限性" target="_blank">跨平台OneLink归因链接</a>）</td><td>最长72天（在<code>af_xplatform_vt_lookback</code>链接参数中设置。）</td><td>24小时</td></tr></tbody></table>

<strong>`engaged_click`和`engaged_view`的回溯窗口仅限于SRN平台。对于SRN，`engaged_click`和`engaged_view`的回溯窗口和点击相同，因此需通过</strong>激活点击归因回溯滑块设置。

<div id="probabilistic-modeling-lookback-window" />

### 概率模型回溯窗口

概率模型回溯窗口用于确保归因的准确性，具有以下几个特征：

* 对点击和展示都有效
* 时长会自动调整，最长为24小时
* 无视归因链接中的窗口时长设置
* 比确定性归因模式中的窗口期要短

详情请见<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#probabilistic-modeling">AppsFlyer的概率模型归因方式</Anchor>。

<div id="lookback-window-setup" />

## 回溯窗口的设置方式

下文分别列出了SRN和归因链接场景中的回溯窗口设置流程。

<Tabs>
<Tab title="SRN回溯窗口">

<div id="attribution-lookback-window-for-srns" />

### SRN的归因回溯窗口

<div id="attribution-lookback-window-with-attribution-links" />

<div id="important" />

> 🚧 **重要提示！**
>
> 每个SRN都有其自己的默认回溯窗口。建议您在AppsFlyer中为相关SRN设置回溯窗口时，将其时长与该SRN自己的默认窗口对齐，这样可以尽量避免数据差异。如果这两个窗口不一致，就很有可能会出现数据差异。详情请见[SRN的数据差异示例](#场景与示例)。

1. 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。
2. 搜索并选择相关的SRN——详见<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#与appsflyer对接的srn">适用SRN列表</Anchor>。
3. 浏览归因默认开启。
4. 进入**渠道对接**选项卡，向下滚动到**点击型归因**和**浏览型归因**的配置部分。
5. 使用滑动条来调节归因窗口的长度。

请参考下表所列的SRN归因窗口：

| SRN | 默认点击回溯窗口（天） | 默认浏览回溯窗口（小时） |
| --- | --- | --- |
| Google | 30 | 24 |
| Meta ads | 7 | 24 |
| Snapchat | 28 | 24 |
| X Ads | 14 | 24 |
| Apple Search Ads | 30 | 24 |
| Oath（YahooGemini） | 7 | 24 |

</Tab>

<Tab title="非SRN回溯窗口">

<div id="non-srn-attribution-lookback-window-for-click-through-and-view-through" />

### 非SRN归因回溯窗口用于点击型和浏览型归因数据

1. 从AppsFlyer面板左侧的菜单栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 浏览归因默认开启。
4. 点击进入**归因链接**选项卡。
5. 选择窗口期的计时单位（天或小时）。
6. 使用**点击型归因**（参数`af_click_lookback`）和**浏览型归因**（参数`af_viewthrough_lookback`）下方的滑动条来设置对应归因窗口的长度。  
   您选定的窗口期时长会自动填充到归因链接中。
7. 选择相关广告系列中需要用到的参数，如广告系列名称、广告组等。
8. 复制并保存该链接备用。后续您需要将该链接提供给广告平台。

<div id="h_01JKWVQB6TTA24VAZ9WVJMGY4X" />

<div id="non-srn-attribution-lookback-window-for-engaged-click-through-and-engaged-view-through" />

### 非SRN归因回溯窗口用于深度点击型和深度浏览型归因数据

1. 从AppsFlyer面板左侧的菜单栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 在对接选项卡中，向下滚动到**深度点击（engaged click）到激活回溯窗口**滑块或**深度浏览（engaged view）到激活回溯窗口**滑块。
4. 使用滑块设置回溯窗口。

<div id="tip" />

> 👍 **提示**
>
> * 如需了解回溯窗口配置方面的技巧和建议，我们在<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">AppsFlyer充电站里为您准备了相关课程</Anchor>，视频虽短，但干货满满！
> * 如需了解归因窗口设置中小时单位的使用场景，请参考[此文档](/docs/set-up-lookback-windows#lookback-in-hours-for-flash-campaigns)。

<div id="lookback-window-in-onelink" />

### OneLink™场景中的回溯窗口

您还可以在OneLink中设置回溯窗口。

1. <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">配置OneLink</Anchor>
2. <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#创建onelink链接">创建一条自定义归因链接</Anchor>
3. 在**其它参数**部分，打开**自定义回溯窗口**开关，然后设置回溯窗口。

</Tab>
</Tabs>

<div id="distribution-of-first-app-launches" />

## 应用首次打开的分布情况

下图展示了用户与广告互动之后的应用激活时间分布情况，

[![](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)

您可以通过上图更好地理解回溯窗口的意义，及其在衡量激活数量时的作用。

在激活应用的用户中，有超过97%的用户在与广告互动后的7天内完成激活。其余2%的用户在广告互动7天后到回溯窗口（30天）结束前完成激活。

实际上，在广告互动后的15分钟内完成激活的用户占到近62%，在1小时内完成激活的用户占到72%。

<div id="scenarios-and-examples" />

## 场景与示例

下文列出了回溯窗口的各种使用场景和示例。

<div id="srn-discrepancy-srn-lookback-longer-than-appsflyer" />

<Accordion title="SRN差异：SRN回溯窗口长于AppsFlyer">

您在X Ads上设置了一个广告系列，并在AppsFlyer后台将其点击回溯窗口设为7天，但X Ads的默认回溯窗口为14天。

[![srn-discrepancy-srn-lookback-larger-than-appsflyer.png](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)

</Accordion>

<div id="srn-lookback-smaller-than-appsflyer" />

<Accordion title="SRN回溯窗口短于AppsFlyer时">

您在X Ads上设置了一个广告系列，并在AppsFlyer后台将其点击回溯窗口设为28天，但X Ads的默认回溯窗口为14天。

[![srn-lookback-smaller-than-appsflyer.png](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)

</Accordion>

<div id="attribution-link-without-a-lookback-window-parameter" />

<Accordion title="不带回溯窗口参数的归因链接">

您也可以配置不带有回溯窗口参数归因链接，这时AppsFlyer会使用默认的点击和展示回溯窗口（分别为7天和1天）。

</Accordion>

<div id="lookback-in-hours-for-flash-campaigns" />

<Accordion title="限时投放场景中的数小时回溯窗口">

限时投放的广告用于在较短的推广窗口内促动用户快速激活应用。

举例来说，假设有一个名为SuperShopping的电商应用需要投放一系列限时广告。在此次推广活动中，如果用户在一小时内激活应用，就可以获得特价优惠。

为此，SuperShopping的市场营销负责人Johnny创建了一条归因链接，并将回溯窗口设置为1小时。这样，Johnny就能了解有多少用户响应了此次推广活动。

此外，应用开发侧还可以识别出由此次限时推广带来的用户，并向其提供广告中所承诺的特价优惠。

</Accordion>

<div id="tip-1" />

> 👍 **提示**
>
> 如需了解回溯窗口和归因方面的技巧和建议，我们在<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">AppsFlyer充电站里为您准备了相关课程</Anchor>，视频虽短，但干货满满！

<div data-zendesk-anchors="lookback-windows=%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01HGFQVP7QZACJ3EGSWEP4HPFV=%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 configurable-lookback-windows-per-attribution-type=%E5%90%84%E5%BD%92%E5%9B%A0%E7%B1%BB%E5%9E%8B%E5%AF%B9%E5%BA%94%E7%9A%84%E5%8F%AF%E9%85%8D%E7%BD%AE%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01HGFQVP7QM0J507CFQ753YS5X=%E5%90%84%E5%BD%92%E5%9B%A0%E7%B1%BB%E5%9E%8B%E5%AF%B9%E5%BA%94%E7%9A%84%E5%8F%AF%E9%85%8D%E7%BD%AE%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 probabilistic-modeling-lookback-window=%E6%A6%82%E7%8E%87%E6%A8%A1%E5%9E%8B%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01JKWV7S7J5B4YA84VGEB478TT=%E6%A6%82%E7%8E%87%E6%A8%A1%E5%9E%8B%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 lookback-window-setup=%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01HGFQVP7QCCN7CHRCAFSNJVHA=%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F attribution-lookback-window-for-srns=srn%E7%9A%84%E5%BD%92%E5%9B%A0%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01HGFQVP7QP61C2K0P7C7YM56Z=srn%E7%9A%84%E5%BD%92%E5%9B%A0%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01HGFQVP7QXTQKGVQJEZ0NEW0M=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA attribution-lookback-window-with-attribution-links=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HGFQVP7QDBFP85A9DJFZE38S=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HGFQVP7Q69H5621GXMYZ441N=%E6%8F%90%E7%A4%BA-1 lookback-window-in-onelink%E2%84%A2=lookback-window-in-onelink h_01HGFQVP7QSJEE8D7TCWZMSXGK=lookback-window-in-onelink distribution-of-first-app-launches=%E5%BA%94%E7%94%A8%E9%A6%96%E6%AC%A1%E6%89%93%E5%BC%80%E7%9A%84%E5%88%86%E5%B8%83%E6%83%85%E5%86%B5 h_01HGFQVP7Q96827N7Q9Q0363SR=%E5%BA%94%E7%94%A8%E9%A6%96%E6%AC%A1%E6%89%93%E5%BC%80%E7%9A%84%E5%88%86%E5%B8%83%E6%83%85%E5%86%B5 scenarios-and-examples=%E5%9C%BA%E6%99%AF%E4%B8%8E%E7%A4%BA%E4%BE%8B h_01HGFQVP7Q02NS8MXF7WKYQ8V1=%E5%9C%BA%E6%99%AF%E4%B8%8E%E7%A4%BA%E4%BE%8B h_01HGFQVP7Q1CYRAHAKY3WK8BK0=srn-discrepancy-srn-lookback-longer-than-appsflyer h_01HGFQVP7QAWDP40H89YBN66GV=srn-lookback-smaller-than-appsflyer h_01HGFQVP7QYE3V2DKW7T4171MX=attribution-link-without-a-lookback-window-parameter h_01HGFQVP7Q7CXSK5G8A0937H5Z=lookback-in-hours-for-flash-campaigns h_01HGFQVP7QM3R973QS99661VPG=%E6%8F%90%E7%A4%BA-1" />
