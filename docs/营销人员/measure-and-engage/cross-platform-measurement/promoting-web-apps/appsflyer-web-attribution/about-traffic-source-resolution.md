---
title: 关于流量来源解析
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T13:46:22Z'
  edited_at: '2026-10-23T12:50:40Z'
  id: 43518064765201
  locale: zh-cn
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/zh-cn/articles/43518064765201
---
> **At a glance:** **内容概要：** 流量来源解析会根据落地页加载时可获取的 URL 参数和引荐来源数据，识别每次网页访问的初始媒体渠道、广告系列和渠道类型。解析结果为后续网页事件的归因提供流量来源信息，包括用户获取事件。

## 什么是流量来源解析？

在网页归因中，落地页加载（**即网页访问**）是用户与网站发生的首次互动。 AppsFlyer 会根据当时可获取的信息（例如 URL 参数和引荐来源数据），识别用户的媒体渠道、广告系列和渠道类型。

这一过程称为**流量来源解析**，用于从 URL 参数中识别并解析媒体渠道和广告系列信息。 AppsFlyer 会捕获并按优先级处理这些参数，以确定此次访问的初始流量来源信息。

流量来源解析属于**归因前的处理流程**。后续执行<Anchor target="_blank" href="/marketers/zh/docs/web-performance-measurement-overview#网页端效果衡量流程">归因流程</Anchor>时，已解析的参数仍可能被覆盖。

流量来源解析的作用并不止于记录访问。解析结果会为后续归因提供流量来源信息，帮助确定后续网页事件（包括用户获取事件）的归属。

了解流量来源解析的工作机制，有助于构建准确的 URL。如需了解如何创建结构清晰的 URL，请参阅<Anchor target="_blank" href="/marketers/zh/docs/choose-attribution-parameters-for-landing-page-urls">为落地页 URL 选择归因参数</Anchor>。

## 流量来源解析流程

流量来源解析分多个步骤进行，逐步完善每次网页访问的归因信息。每个步骤都会补充特定的信息，从记录访问本身，到为报表目的对流量进行分类。流程所需的数据由 Web SDK 或 Web S2S 采集。

流量来源解析包括以下步骤：

1. [记录访问](#步骤-1记录识别访问)：捕获用户到达网站的行为，并记录一次访问事件，即便此时流量来源尚未被识别。这样可以确保在应用归因逻辑之前，所有符合条件的访问都得到衡量。
2. [媒体渠道解析](#第-2-步媒体渠道解析)：分析 URL 参数和引荐来源数据，识别出带来此次访问的平台或合作方，或判定该次访问为自然流量。
3. [广告系列解析](#步骤-3广告系列解析)：解析出与已识别媒体渠道相关联的更精细颗粒度的广告系列信息，以支持精细化的效果分析。
4. [渠道分类](#步骤-4渠道分类)：根据已解析的媒体渠道，将每次访问归入某个高层级渠道，为报告和分析提供标准化视图。

## 步骤 1：记录/识别访问

记录访问是网页效果衡量（Web Performance Measurement）流程的第一步。这一步发生在媒体渠道解析和归因之前，作为预处理阶段，负责采集用户的原始访问行为，为后续处理做好准备。

该逻辑分为两个阶段进行。首先，会对**引荐来源**进行分类（即用户到达您网站之前所在的域名）。然后，根据引荐来源的类型，检查用户的应用打开状态及是否存在媒体渠道信息，以决定是否记录此次访问。

#### 第 1 阶段：引荐来源分类

AppsFlyer 会将引荐来源分为以下三类：

* **排除的外部来源**：例如支付处理平台，或您已设置为排除项的任何域名。
* **排除的内部来源**：例如，您自己的子域名或登录流程。
* **其他来源**：不属于上述两类的所有其他引荐来源。

#### 第 2 阶段：检查应用打开状态并记录访问

AppsFlyer 会根据引荐来源的类型检查应用打开状态，并决定是否记录访问：

* **排除的外部来源：** 不记录访问。
* **排除的内部来源：** 不使用引荐来源进行归因，因为此类引荐来源并非真实的用户获取来源。
  * 如果应用打开状态为活跃（连续 30 分钟没有操作后视为非活跃，否则视为活跃），则不会记录此次访问。
  * 如果应用打开状态不活跃，则记录此次访问，但会将引荐来源视为自引荐并忽略。除非 URL 中包含归因参数（例如 UTM、PID、点击 ID），否则此次访问将归类为自然流量。
* **其他来源：**
  * 如果应用打开状态不活跃，则记录此次访问。新的应用打开都会被视为一次新的访问，不受其他条件影响。
  * 如果应用打开状态为活跃，且 URL 中包含非直接流量来源信息（例如 UTM、PID、点击 ID），则记录此次访问。此次再次访问可能触发再营销转化（重新互动），用于归因后续事件。
  * 如果应用打开状态为活跃，但没有媒体渠道信息，则本次应用打开期间不会记录新的访问。

<Image alt="流量来源解析流程图" src="https://files.readme.io/d5f807d5ced5ed9a90a41cda0f38fe7ffef0b81c321bae90ad410076b484c810-47195479783953.png" width="1494px" />

## 第 2 步：媒体渠道解析

媒体渠道解析流程会判断一次访问是否属于：

* **非自然流量：** 识别出了某个具体的归因来源。
* **自然流量：** 未识别到归因来源（例如，用户直接输入 URL 或使用书签）。

在媒体渠道解析过程中，AppsFlyer 会通过评估从落地页 URL 路径和查询字符串中提取的参数，确定一次网页访问的来源。

为获得最佳结果，请使用 AppsFlyer 专用参数，例如 `pid` 和 `af_campaign`，以提供最高级别的颗粒度和控制。 AppsFlyer 也可识别行业标准参数，例如 UTM 标签和点击 ID，这样您无需更改现有的广告测量配置即可直接开始使用。

AppsFlyer 会按优先级顺序解析媒体渠道。一旦成功识别出某个来源，流程就会停止。媒体渠道解析包括以下步骤：

<Accordion title="1. 排除域名">

首先，AppsFlyer 会检查这次访问是否来自您的**排除列表**中的某个域名。如果该域名已被排除（例如您的内部域名，或 PayPal 等支付处理商），该访问会被自动忽略，或归类为**自然流量**。

如需详细了解在将 Web 应用添加到 AppsFlyer 时如何指定要排除的域名，请参阅<Anchor target="_blank" href="/marketers/zh/docs/configure-web-performance-measurement-settings#排除域名">排除的域名</Anchor>。

</Accordion>

<Accordion title="2. AppsFlyer PID（合作伙伴 ID）">

如果该域名未被排除，AppsFlyer 会在 URL 中查找 `pid=` 参数。

* 如果找到了，媒体渠道会直接取自这个参数。
* <span id="social-media-partners"></span>以下媒体平台会使用特定的名称，而不是原始 URL 参数值。

| URL 参数（PID） | 媒体渠道显示名称 |
| --- | --- |
| `pid=iossearchads_int` | Apple Search Ads |
| `pid=facebook_int` | Facebook Ads |
| `pid=metweb_int` | Facebook Ads |
| `pid=twitter_int` | Twitter |
| `pid=twitterweb_int` | Twitter |
| `pid=googleads_int` | googleadwords\_int |
| `pid=tiktokweb_int` | tiktokglobal\_int |
| `pid=snapweb_int` | snapchat\_int |

</Accordion>

<Accordion title="3. UTM 参数">

如果在 URL 中找不到 PID，AppsFlyer 会评估 `utm_source` 和 `utm_medium` 参数，以识别媒体渠道。最终的解析结果由这两个字段的组合决定。

#### **UTM 逻辑的工作原理**

* 在大多数情况下，AppsFlyer 会提取 `utm_source` 的原始值，并直接将其用作媒体渠道。
* 如果 `utm_medium` 为 `email`、`mail` 或 `e-mail`，媒体渠道会自动解析为 `e-mail`。
* 如果存在 `utm_medium` 且该值不属于邮件（email）类型，AppsFlyer 会根据特定的自定义映射规则检查该值（请参阅下方映射表）。
* 如果缺少 `utm_medium`，或者没有匹配到任何自定义规则，AppsFlyer 会回退为使用 `utm_source` 作为媒体渠道。

#### **UTM 映射规则**

| utm\_source | utm\_medium | 媒体渠道 |
| --- | --- | --- |
| Google | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | googleadwords\_int |
| Google | cpm / display / banner / video / listing | dv360\_int |
| dfa / dbm / dcm / doubleclick | cpm | dv360\_int |
| Facebook / FB / Meta | cpc / ppc / cpm / cpa / paidsocial / paid-social / paid\_social / paid | Facebook Ads |
| Bing / microsoft / ms | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | bingsearch\_int |
| Yahoo / Gemini | cpm / display / listing | yahoogemini\_int |
| twitter | cpc / ppc / paid / paidsocial / paid-social / paid\_social | Twitter |
| Snapchat / snap | swipe / cpc / ppc / paid / paidsocial / paid-social / paid\_social | snapchat\_int |
| pinterest | cpc / ppc / paid / paidsocial / paid-social / paid\_social | pinterest\_int |
| tiktok | cpc / ppc / paid / paidsocial / paid-social / paid\_social | tiktokglobal\_int |

</Accordion>

<Accordion title="4. 点击 ID">

如果 URL 中既没有 PID，也没有 UTM 参数，AppsFlyer 会尝试使用 **点击 ID** 来识别媒体渠道。这些是由特定广告平台自动追加到 URL 的唯一标识符。

AppsFlyer 使用以下点击 ID 映射对访问进行归因：

| 点击 ID 参数 | 解析后的媒体渠道 |
| --- | --- |
| `gclid`、`wbraid` 或 `gbraid` | googleadwords\_int |
| `msclkid` | bingsearch\_int |
| `twclid` | Twitter |
| `vmcid` | yahoogemini\_int |
| `sccid` | snapchat\_int |
| `li_fat_id` | linkedin\_int |
| `ttclid` | tiktokglobal\_int |
| `tbclid` | taboola\_int |
| `ob_click_id` | outbrain\_int |
| `dicbo` | outbrain\_int |
| `yclid` | yandex\_int |
| `rdt_cid` | reddit\_int |
| `epik` | pinterest\_int |
| `oppref` | openai\_int |

> 📘 **Note**
>
> * AppsFlyer 不会使用 `fbclid` 进行流量来源解析，因为 Meta 会将该参数同时附加到付费和自然的 Facebook 点击上。如需将流量归因到 Meta，请使用 `pid=facebook_int`，或将 `utm_source` 设置为相应的 Meta 渠道值。
> * `dclid` 参数不会用于解析媒体渠道。 `dclid` 是 Campaign Manager 360（CM360）的标识符，在使用 CM360 时，可能会与其他点击 ID（例如 Facebook 的 `fbclid`，或 TikTok 的 `ttclid`）同时出现。仅凭 `dclid` 进行解析，可能会得到错误的结果。

</Accordion>

<Accordion title="5. HTTP 引荐来源">

如果在 URL 中未找到查询参数（PID、UTM 或点击 ID），AppsFlyer 会使用 `http_referrer` 来识别流量来源。这依赖于一种内部解析机制，该机制会提取域名host并将其映射到媒体渠道。

#### **解析机制**

为识别流量来源，AppsFlyer 会对引荐来源字符串进行如下清理：

1. 将 URL 精简为仅保留**主机**
2. 移除**域名后缀**（如 `.com`、`.org` 等顶级域名，或 `.co.uk` 等扩展名）
3. 移除**域名前缀**（例如 `www.`，`m.`，`l.`，或 `lm.`)

*示例：引荐来源为*`www.mywebsite.com?param=example` *时，会被解析为媒体渠道* `mywebsite`。

#### **引荐来源映射规则**

| 如果域名主机包含… | 解析后的媒体渠道 |
| --- | --- |
| `mail.` 或 `outlook.` | 邮件 |
| `t.co` | twitter |
| `googleads.g.doubleclick.net` | googleadwords\_int |
| `tpc.googlesyndication.com` | dv360\_int |

#### **搜索引擎映射**

| 如果域名主机包含… | 解析后的媒体渠道 |
| --- | --- |
| `google。` | Google 搜索 |
| `search.yahoo` | Yahoo 搜索 |
| `bing.com` | Bing 搜索 |

#### **Android 应用引荐来源**

如果访问来源于 Android 应用，则引荐来源主机按如下方式映射：

| 应用引荐来源字符串 | 解析后的媒体渠道 |
| --- | --- |
| `com.google.android.googlequicksearchbox` | Google 搜索 |
| `com.google.android.gm` | 邮件 |
| `com.linkedin.android` | linkedin |
| `com.twitter.android` | twitter |
| `org.telegram.messenger` | telegram |

</Accordion>

## 步骤 3：广告系列解析

在第 2 步确认媒体渠道后，AppsFlyer 会继续尝试识别具体的广告系列详情。

AppsFlyer 按优先级顺序从以下 URL 参数中提取广告系列信息：

| URL 参数（多个） | 映射到 | 优先级顺序 |
| --- | --- | --- |
| `c`、`af_campaign`、`utm_campaign` | 广告系列名称 | <ol><li>`c`</li><li>`af_campaign`</li><li>`utm_campaign`</li></ol> |
| `af_c_id`, `af_campaign_id` | 广告系列 ID | <ol><li>`af_c_id`</li><li>`af_campaign_id`</li></ol> |
| `af_adset` | 广告组名称 | — |
| `af_adset_id` | 广告组ID | — |
| `af_ad` | 广告名称 | — |
| `af_ad_id` | 广告 ID | — |
| `af_keywords` | 关键词 | — |

## 步骤 4：渠道分类

除了识别媒体渠道外，AppsFlyer 还会将每次访问归入相应的渠道。这一分类可在原始数据报告和数据面板中，为流量类型提供统一的高层级视图。

### 使用 af\_channel 覆盖渠道

如需指定自定义渠道值，请在落地页 URL 中添加 `af_channel` 参数。例如，`af_channel=ig` 会将渠道设置为 `ig`，从而让您按标准类别无法体现的颗粒度（例如具体广告位）来细分流量。

`af_channel` 仅在该次访问同时识别出媒体渠道时才会被解析。如果该次访问为自然流量（未识别到媒体渠道），无论是否存在 `af_channel`，都会始终解析为 `Direct`。

### 默认渠道分类

如果不存在 `af_channel`，或该次访问不满足上述条件，AppsFlyer 会回退至根据已识别的媒体渠道进行自动分类：

* **直接访问：** 用户直接输入了网址，或通过书签访问。未识别到归因来源。
* **自然搜索：** 来自 Google、Yahoo、Bing 等搜索引擎的免费流量。
* **社交媒体：** 来自各社交平台的流量。
* **邮件：** 来自邮件营销活动或邮件服务商的流量。
* **广告：** 由付费广告带来的流量。
* **引荐：** 通过引荐来源识别出的、来自其他网站的流量。
* **其他：** 不属于以上任何类别的流量。

**注意：** 每次访问都会分配到一个渠道。该分类基于已识别的媒体渠道和归因方式自动完成，结果具有确定性，但可通过 `af_channel` 覆盖。

<div data-zendesk-anchors="what-is-traffic-source-resolution=%E4%BB%80%E4%B9%88%E6%98%AF%E6%B5%81%E9%87%8F%E6%9D%A5%E6%BA%90%E8%A7%A3%E6%9E%90 h_01KGMEER6DX8W3ECBEBYP4DQV1=%E4%BB%80%E4%B9%88%E6%98%AF%E6%B5%81%E9%87%8F%E6%9D%A5%E6%BA%90%E8%A7%A3%E6%9E%90 the-traffic-source-resolution-flow=%E6%B5%81%E9%87%8F%E6%9D%A5%E6%BA%90%E8%A7%A3%E6%9E%90%E6%B5%81%E7%A8%8B h_01KGMEER6DA4HMSZ3TVEAG84WZ=%E6%B5%81%E9%87%8F%E6%9D%A5%E6%BA%90%E8%A7%A3%E6%9E%90%E6%B5%81%E7%A8%8B step-1-visit-recording=%E6%AD%A5%E9%AA%A4-1%E8%AE%B0%E5%BD%95%E8%AF%86%E5%88%AB%E8%AE%BF%E9%97%AE h_01KGMEER6DV02F44C5ZPSBEQEX=%E6%AD%A5%E9%AA%A4-1%E8%AE%B0%E5%BD%95%E8%AF%86%E5%88%AB%E8%AE%BF%E9%97%AE stage-1-referrer-classification=%E7%AC%AC-1-%E9%98%B6%E6%AE%B5%E5%BC%95%E8%8D%90%E6%9D%A5%E6%BA%90%E5%88%86%E7%B1%BB h_01KSSEM5P8RX29CD6C6ZD2DVAT=%E7%AC%AC-1-%E9%98%B6%E6%AE%B5%E5%BC%95%E8%8D%90%E6%9D%A5%E6%BA%90%E5%88%86%E7%B1%BB stage-2-session-evaluation-and-visit-recording=%E7%AC%AC-2-%E9%98%B6%E6%AE%B5%E6%A3%80%E6%9F%A5%E5%BA%94%E7%94%A8%E6%89%93%E5%BC%80%E7%8A%B6%E6%80%81%E5%B9%B6%E8%AE%B0%E5%BD%95%E8%AE%BF%E9%97%AE h_01KSSEM5P8KBYDBCB7PAPGPX5M=%E7%AC%AC-2-%E9%98%B6%E6%AE%B5%E6%A3%80%E6%9F%A5%E5%BA%94%E7%94%A8%E6%89%93%E5%BC%80%E7%8A%B6%E6%80%81%E5%B9%B6%E8%AE%B0%E5%BD%95%E8%AE%BF%E9%97%AE step-2-media-source-resolution=%E7%AC%AC-2-%E6%AD%A5%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E8%A7%A3%E6%9E%90 h_01KGMEER6D082QTZGZYEXT6726=%E7%AC%AC-2-%E6%AD%A5%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E8%A7%A3%E6%9E%90 how-utm-logic-works=utm-%E9%80%BB%E8%BE%91%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 h_01KGMF0E1XBSJCVDWGC4R8XMPX=utm-%E9%80%BB%E8%BE%91%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 utm-mapping-rules=utm-%E6%98%A0%E5%B0%84%E8%A7%84%E5%88%99 h_01KGMF0JSBZ3WYM65R55BCDAMN=utm-%E6%98%A0%E5%B0%84%E8%A7%84%E5%88%99 the-parsing-mechanism=%E8%A7%A3%E6%9E%90%E6%9C%BA%E5%88%B6 h_01KGMEZA9ETGK6Z89GM111E64Z=%E8%A7%A3%E6%9E%90%E6%9C%BA%E5%88%B6 referrer-mapping-rules=%E5%BC%95%E8%8D%90%E6%9D%A5%E6%BA%90%E6%98%A0%E5%B0%84%E8%A7%84%E5%88%99 h_01KGMEZESC451HVJT139BSXEA5=%E5%BC%95%E8%8D%90%E6%9D%A5%E6%BA%90%E6%98%A0%E5%B0%84%E8%A7%84%E5%88%99 search-engine-mapping=%E6%90%9C%E7%B4%A2%E5%BC%95%E6%93%8E%E6%98%A0%E5%B0%84 h_01KGMEZKCTASMNXZG13VTVECVH=%E6%90%9C%E7%B4%A2%E5%BC%95%E6%93%8E%E6%98%A0%E5%B0%84 android-app-referrers=android-%E5%BA%94%E7%94%A8%E5%BC%95%E8%8D%90%E6%9D%A5%E6%BA%90 h_01KGMEZQYCDS23MVW3MQH9Q5JQ=android-%E5%BA%94%E7%94%A8%E5%BC%95%E8%8D%90%E6%9D%A5%E6%BA%90 step-3-campaign-resolution=%E6%AD%A5%E9%AA%A4-3%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E8%A7%A3%E6%9E%90 h_01KGMEER6ES1AYT24MC4HZCX9X=%E6%AD%A5%E9%AA%A4-3%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E8%A7%A3%E6%9E%90 step-4-channel-classification=%E6%AD%A5%E9%AA%A4-4%E6%B8%A0%E9%81%93%E5%88%86%E7%B1%BB h_01KGMEER6ETWGFFM3E17KHMDAF=%E6%AD%A5%E9%AA%A4-4%E6%B8%A0%E9%81%93%E5%88%86%E7%B1%BB h_01_overriding-the-channel-with-af-channel=%E4%BD%BF%E7%94%A8-af_channel-%E8%A6%86%E7%9B%96%E6%B8%A0%E9%81%93 overriding-the-channel-with-af_channel=%E4%BD%BF%E7%94%A8-af_channel-%E8%A6%86%E7%9B%96%E6%B8%A0%E9%81%93 h_01_default-channel-classification=%E9%BB%98%E8%AE%A4%E6%B8%A0%E9%81%93%E5%88%86%E7%B1%BB default-channel-classification=%E9%BB%98%E8%AE%A4%E6%B8%A0%E9%81%93%E5%88%86%E7%B1%BB" />
