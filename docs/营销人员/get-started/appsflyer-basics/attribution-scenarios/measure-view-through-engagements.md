---
title: 浏览型归因指南
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-20T07:38:24Z'
  edited_at: '2026-10-14T10:11:24Z'
  id: 210084473
  locale: zh-cn
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/zh-cn/articles/210084473
---
> **概要：** 如果用户浏览广告（即发生广告展示）后安装并激活应用，AppsFlyer会通过浏览型归因将这类用户匹配到相应的广告展示。

## 速览

浏览型归因用于衡量已浏览但未点击广告的用户所完成的激活、再归因和再互动。

### 浏览型归因链路

![Retargeting_-_View-through__1_.png](https://files.readme.io/86d32778a8a0966499a0c5c91c1b2d8aed6d5bb24214b1a32fd484779c105a98-4412917609489.png)

### 概念定义

* **展示（impression）：** 每当渠道向用户呈现一条广告时，无论用户是否完成广告点击或其他交互行为，都视为一次展示。
* **转化**：本文中提到的转化包括激活、再归因和再互动。
* **浏览型归因：** 用户看到广告展示后发生转化，AppsFlyer会将该转化归因到展示广告的媒体渠道。

### 浏览型归因的原理

* 同时支持<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#device-id-matching">设备ID匹配</Anchor>以及<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#probabilistic-modeling">概率模型匹配</Anchor>（须<Anchor target="_blank" href="/marketers/zh/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">手动启用</Anchor>）。
* 适用于[浏览型归因渠道列表](/docs/measure-view-through-engagements#view-vta-partner-list)中的渠道。

符合以下条件的广告展示会被纳入浏览型归因链路：

* 广告展示发生在浏览回溯窗口期内（默认为24小时）。
* 如果AppsFlyer发现多个相关的广告展示，则取最近发生的那一次广告展示。
* 广告点击的归因优先级高于广告展示。也就是说，如果点击回溯窗口内发生了点击，则相关转化会归因到最近的一次点击，而最近的一次展示会归因为助攻（assist）。

### 浏览型回溯窗口

* 在设置非SRN的浏览回溯窗口期时，可选的时长范围为1-24小时。SRN的回溯窗口可能会更长。
* 窗口期的设置方式如下：
  * **非SRN：** 请通过展示归因链接中的`af_viewthrough_lookback`参数来设置窗口期时长。如果不设置该参数，AppsFlyer会使用默认的24小时窗口期。
  * **SRN**：取决于您使用的具体SRN。建议您在AppsFlyer中设置的窗口期与SRN侧的窗口期保持一致。

### 浏览型归因的报告和指标

* 汇总数据广告平台向AppsFlyer上报展示数据的方式有两种，一种是通过API上报汇总数据，第二种是在每次展示时上报，然后由AppsFlyer统计出汇总数据。这里需要注意，每个平台统计和上报广告展示的逻辑各不相同，详情请见各大对接渠道对于展示和点击的定义。 您可以通过数据总览面板以及其他数据上报工具查看相关指标，这些指标包括：
  * 展示：在特定时间段内发生的广告展示次数。
  * 浏览型归因通过浏览型归因匹配到的转化数量。
* **原始数据**：
  * AppsFlyer可提供通过浏览型归因匹配到的用户级别数据（即原始数据），数据呈现方式与点击归因产生的用户级别数据相同，但部分渠道会限制这类数据的可用性。
  * AppsFlyer可提供展示数据（呈现方式与点击数据相同）。
  * 以字段值为*impression*的attributed\_touch\_type字段来标记广告展示。

## 浏览型归因的配置方式

<div id="set-impression-links" />

<Accordion title="设置展示链接">

广告平台会向AppsFlyer发送展示链接，并在其中填充广告系列名称等各种相关信息，与点击<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">归因链接</Anchor>中包含的信息类似。

这些链接实时发送到AppsFlyer，因此如果广告展示之后发生了转化，AppsFlyer就能进行准确归因。

在配置展示链接时，请注意以下几点：

* 基础URL是`https://impression.appsflyer.com`，
* 请使用GET请求。
* 请在各类设备ID可用时发送这些信息，比如IDFA、GAID、IDFV等。
* 请在链接中加入<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#适用于广告平台的概率模型归因参数">概率模型</Anchor>参数。
* 您可以使用SHA1对设备ID值进行哈希加密，提升数据安全性。使用这种方式时，请在参数名称的开头加上“sha1\_”前缀，后跟实际参数名以及哈希加密后的参数值，如sha1\_idfa、sha1\_advertising\_id、sha1\_android\_id、sha1\_imei等等。

> 📄
>
>  示例
>
> ```http
> https://impression.appsflyer.com/{app-id}?c={campaign name}&pid={media source}
> &af_viewthrough_lookback=1d&af_prt={agency_name}&af_siteid={site id value}
> &af_sub1={free value}&idfa={idfa value}
> ```

</Accordion>

<div id="set-custom-impression-links" />

<Accordion title="设置自定义展示链接">

广告主在其自有媒体（比如网页横幅）中使用展示归因链接。

广告主<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#创建onelink链接">创建自定义归因链接</Anchor>时，会得到完整的展示链接，当用户与其自有媒体上的广告发生交互时，就会触发这些链接。

自定义展示链接（通过OneLink创建）还可以用于移动端网页访客的浏览型归因。 详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">自定义展示链接的创建方式</Anchor>说明。

</Accordion>

<div id="turn-off-viewthroughattribution" />

<Accordion title="浏览型归因的停用方式">

浏览型归因默认处于启用状态。当AppsFlyer收到有效的展示归因链接时，该链接就会进入归因链路。

由于浏览型归因默认处于启用状态，因此广告主与广告平台合作时需注意相关协议中有关浏览型归因的条款，如果协议中不包含这类转化，必须对相关渠道停用浏览型归因。

您可以分渠道停用浏览型归因。但如果您在AppsFlyer已经接收到展示数据之后停用了浏览型归因，就会出现以下情况：

* 面板中会出现展示指标。
* 但AppsFlyer不会对这些展示进行归因。

**浏览型归因的停用方式如下：**

1. 从AppsFlyer面板左侧的菜单栏中选择**协作** > **活跃对接**。
2. 选择相关的对接渠道。
3. 在渠道对接选项卡中，关闭**浏览型归因**的开关。
4. 点击**保存对接**。

关于SRN的注意事项：在AppsFlyer中关闭浏览型归因后，并不会影响SRN平台侧的自归因。请确保您在AppsFlyer中的浏览型归因设置与SRN平台中的设置保持一致，以避免数据差异。

</Accordion>

<div id="view-vta-partner-list" />

<Accordion title="支持浏览型归因的渠道列表">

您可以在面板中查看支持浏览型归因的广告平台列表。

**该列表的查看方式如下**：

1. 从AppsFlyer面板左侧的菜单栏中选择**协作** > **活跃对接**。
2. **在顶部的筛选条件中，选择**所有合作渠道类型。
3. **在支持的功能**中，选择浏览型。   
   这时界面就会显示支持浏览型归因的渠道列表。

</Accordion>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01HEMT7T1TB9W7ZBRPQW29SRPF=%E9%80%9F%E8%A7%88 viewthrough-attribution-flow=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E9%93%BE%E8%B7%AF h_01HEMT7T1T6ZK4ZH7DKV3162J1=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E9%93%BE%E8%B7%AF terminology=%E6%A6%82%E5%BF%B5%E5%AE%9A%E4%B9%89 h_01HEMT7T1TY46QXBDS6MBF1DZ5=%E6%A6%82%E5%BF%B5%E5%AE%9A%E4%B9%89 viewthrough-attribution-principles=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%9A%84%E5%8E%9F%E7%90%86 h_01HEMT7T1THD8TVKRRJ168HKY2=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%9A%84%E5%8E%9F%E7%90%86 viewthrough-lookback-window=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01HEMT7T1TWHN2AB3Q5X36TKKB=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 viewthrough-attribution-reporting-and-metrics=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%9A%84%E6%8A%A5%E5%91%8A%E5%92%8C%E6%8C%87%E6%A0%87 h_01HEMT7T1TQNKM5GABA7VY6KR1=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%9A%84%E6%8A%A5%E5%91%8A%E5%92%8C%E6%8C%87%E6%A0%87 viewthrough-operations=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%9A%84%E9%85%8D%E7%BD%AE%E6%96%B9%E5%BC%8F h_01HEMT7T1T13JC75ZYY01N8PS6=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%9A%84%E9%85%8D%E7%BD%AE%E6%96%B9%E5%BC%8F h_01HEMT7T1TQ3YNQ2Y0CCGPXWDX=set-impression-links h_01HEMT7T1T75MBS64JE837CJ0E=set-custom-impression-links h_01HEMT7T1T253G1CZNS9KVDFCP=turn-off-viewthroughattribution h_01HEMT7T1T5MQHC3F5EHSGMYQF=view-vta-partner-list" />
