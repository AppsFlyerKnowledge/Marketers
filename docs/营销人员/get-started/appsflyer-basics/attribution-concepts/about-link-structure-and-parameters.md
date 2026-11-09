---
title: 链接的结构和参数
metadata:
  keywords:
    - pid
    - Marketers
    - af_
    - af
    - c
    - af_mp
    - clickid
    - af_siteid
    - af_sub_siteid
    - af_c_id
    - af_adset_id
    - af_ad_type
    - af_viewthrough
    - af_cost_model
    - af_cost_value
    - af_web_dp
    - af_ref
    - af_ip
    - af_os_version
    - deep_link_sub
    - deep_link_value
    - af_og_title
    - af_og_description
    - af_og_image
    - af_prt
    - af_adset
    - af_ad
    - af_ad_id
    - af_channel
    - af_keywords
    - af_cost_currency
    - af_sub
    - af_r
    - af_dp
    - af_force_deeplink
    - is_incentivized
    - af_param_forwarding
    - af_partner_account_id
    - af_ua
    - af_os
    - af_model
    - af_media_type
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T11:50:00Z'
  edited_at: '2026-10-14T10:09:48Z'
  id: 207447163
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/207447163
---
> **概要：**  本文重点介绍了AppsFlyer归因链接的结构和参数。

<div id="overview" />

## 速览

广告主可利用归因链接收集用户的广告互动数据。归因链接是广告背后的链接，当用户与广告互动时，该链接就会向AppsFlyer上报该行为。用户点击或浏览广告即形成广告互动， 这时AppsFlyer就会收到一条归因链接的副本。

归因链接可以是**OneLink**链接，也可以是**单平台链接**。

|  | OneLink（多平台链接） | 单平台链接 |
| --- | --- | --- |
| 说明及使用场景 | 使用场景：<ul><li>需要使用同一条链接完成多个平台的投放。</li><li>需要深度链接功能。</li><li>您想要使用安卓的App Link或iOS的Universal Link调起应用。</li></ul><Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">进一步了解OneLink</Anchor> | 使用场景：<ul><li>仅在一个平台上投放，如仅投放安卓或iOS。</li><li>仅使用URI scheme吊起应用。</li></ul><Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">进一步了解对接渠道的设置流程</Anchor> |
| 前期准备 | <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">OneLink模板</Anchor> | 无 |
| 需包含的信息 | <ul><li>[媒体渠道](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[广告系列](#c)</li><li>[子渠道ID/次级子渠道ID](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <ul><li>[媒体渠道](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[广告系列](#c)</li><li>[子渠道ID/次级子渠道ID](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> |
| 基础链接 | `{subdomain}`.onelink.me | app.appsflyer.com |
| 独立标识符 | 模板ID | app\_id |
| 链接结构 | `https://{subdomain}.onelink.me/`<br />`{templateid}?pid={media_source}`<br />`&af_siteid={ApplicationID}`<br />`&c={CampaignName}` | `https://app.appsflyer.com/{app_id}?pid={media_source}&af_siteid={ApplicationID}&c={CampaignName}` |
| 示例 | `https://yourbrand.onelink.me/aAB1?pid=greatnetwork_int`<br />`&c=GreatCampaign&af_siteid=A1b1` | `https://app.appsflyer.com/com.greatapp?pid=greatnetwork_int&`<br />`c=GreatCampaign&af_siteid=A1b1` |

<div id="important" />

> 🚧 **重要提示！**
>
> AppsFlyer仅支持通过HTTPS协议传输的互动流量，即点击和展示。

<div id="attribution-link-parameters" />

## 归因链接参数

* 归因链接中的可用参数如下表所列。
* **字段类型**一列说明了参数值的字数限制。详情请见<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">参数值长度限制</Anchor>。

<div id="attribution-link-parametersua-and-retargeting" />

### 归因链接参数——拉新及再营销

您可以[下载下表说明（`.csv`文件）](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZQnoDdFo2NxBuWXBs5gGgvkGU2pr_hn58H9Dtf5uHBAHv4Io89Wd44rRtL24pRsOXHthnBitaOyfp/pub?gid=0&single=true&output=csv)，以供参考。

<div id="attribution-parameters" />

| 参数 | 原始数据中的字段名称 | 说明 | 字段类型和长度： |
| --- | --- | --- | --- |
| <span id="pid"></span>pid | Media Source | AppsFlyer对接渠道的唯一标识符。切勿更改。[更多详情](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)。 | <span id="PID"></span>字符串限长150 |
| <span id="c"></span>c | Campaign | 由广告主或发行商提供。详见[广告系列名称限制](/docs/about-link-structure-and-parameters#what-limits-are-there-on-campaign-names)。 | <span id="Campaign"></span>字符串限长100 |
| <span id="af_prt"></span>af\_prt | Partner | <ul><li>代理帐户名称-可以把激活归因给相应代理</li><li>**注意** ：在启用**授权代理**之前，请勿使用此参数。</li></ul> | 字符串限长50 |
| <span id="af_mp"></span>af\_mp | 不适用 | <ul><li>可向媒体营销渠道发送分激活的回传。</li><li>**请注意**：此参数目前仅适用于Pinterest Marketing Partners。</li></ul> |  |
| <span id="clickid"></span>clickid | 不适用 | 广告平台唯一点击标识符 |  |
| <span id="af_siteid"></span>af\_siteid | Site ID | <ul><li>用于标记广告发行商（展示广告的媒体）的唯一ID。[了解详情](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <span id="Site_id"></span>字符串限长24 |
| <span id="af_sub_siteid"></span>af\_sub\_siteid | Sub Site ID | <ul><li>次级广告平台/媒体ID。</li><li>如果除了主要媒体（子渠道）以外还有次级媒体，或者您想要了解广告样式（如横幅、插屏、视频）等的其他信息，请使用af\_sub\_siteid参数。示例：af\_sub\_siteid =ABCD\_4567</li></ul> | 字符串限长50 |
| <span id="af_c_id"></span>af\_c\_id | Campaign ID | 由广告主/发行商提供 | String 24 |
| <span id="af_adset"></span>af\_adset | Adset | <ul><li>由广告商/发行商提供</li><li>广告组是在广告系列之下、广告之上的一个广告层级。[详情请见此处。](/docs/about-link-structure-and-parameters#数据粒度级别)</li></ul> | String 100 |
| <span id="af_adset_id"></span>af\_adset\_id | Adset ID | 由广告主/发行商提供 | String 24 |
| <span id="af_ad"></span>af\_ad | Ad | 广告名称（[了解详情](/docs/about-link-structure-and-parameters#数据粒度级别)）——由广告主/发行商提供 | String 100 |
| <span id="af_ad_id"></span>af\_ad\_id | Ad ID | 由广告主/发行商提供 | String 24 |
| <span id="af_ad_type"></span>af\_ad\_type | Ad type | 包括以下各种广告类型：<ul><li>**native**（软广）：这种付费广告与媒体平台中的非广告内容完美融合（包括在视觉效果和功能方面），出现在用户的推荐视频中。</li><li>**banner**（横幅）：一种展示广告，一般呈小块长方形，出现在网页或应用界面中的各种位置。</li><li>**interstitial**（插屏）：在发布广告的应用中占据整个界面的全屏广告。这类广告会设计在内容衔接处或在用户链路的过渡环节出现（占据如活动或游戏升级、暂停时）。</li><li>**rewarded\_video**（奖励视频）：一种视频广告，用户看完整个视频就能在应用内得到奖励，如游戏中的生命值、文章的读取权限，或公共场合的Wi-Fi使用权限等。这类奖励型广告能在吸引用户互动的同时为其提供更好的应用内体验。</li><li>**audio**（音频）：在线播客或音乐流媒体平台内以音频格式投放的广告。</li><li>**offerwall**（积分墙）：一种应用内广告单元，开发应用的厂商可通过这种形式进行变现。这种广告类似于应用中的迷你商店，其中列出各种“积分任务”，用户完成任务后即可在应用内获得相应的奖励。</li></ul> | String 24 |
| <span id="af_ad_format"></span>af\_ad\_format | Ad format | 包括以下各种广告类型：<ul><li>**text**（文本）：以简短的文本段落形式出现的文字广告。一般由标题、描述以及链接或CTA按钮组成，用于激发用户兴趣并引导用户点击进入网站或落地页。</li><li>**image**（图片）：通过图像或照片展示某个产品、服务或品牌视觉型广告。通常由引人注意的图片以及精简的文案组成，可能还会带有CTA按钮。</li><li>**video**（视频）：使用视听内容传达营销信息的数字广告。视频长度不一，可作为前、中、后贴片广告穿插在视频内容中，也可在各类平台上单独展示视频广告。</li><li>**playable**（试玩）：一种互动式广告，为用户提供一个迷你版的游戏或应用，让其在正式下载或购买前先行试用，亲身体验游戏玩法或应用功能。</li><li>**interactive**（互动）：一种吸引用户参与或互动的动态广告，可包含小问答、调查问卷或其他互动元素，目的是引起用户注意并引导其积极参与。</li><li>**dynamic\_product**（动态产品）：一种个性化广告，可根据用户行为、偏好设置或浏览历史记录动态填充产品信息和详情，向用户展示高度相关的定制化产品广告。</li><li>**carousel**（轮播）：在一个广告中展示多个幻灯片或卡片，每张卡片可以包含不同的图片、标题和描述，让广告主在单个广告中展示多种产品或功能。</li></ul> |  |
| <span id="af_click_lookback"></span>af\_click\_lookback | Attribution lookback window | <ul><li>点击归因的窗口期，用户点击广告/链接后在此期间激活应用才能被归因到相应渠道，也就是CTIT（点击到安装时间）的最大值。</li><li>点击归因窗口期可在以下范围内自行调整：可用参数值为1d-30d (天) 或 1h-23h (小时)。默认值为7d。</li><li><Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows#回溯窗口的设置方式">OneLink和SRN</Anchor>的归因窗口可自行设置。</li></ul>**请注意**：仅影响点击URL，不影响展示URL。 | 最多3个字符 |
| <span id="af_viewthrough_lookback"></span>af\_viewthrough\_lookback | 不适用 | <ul><li>浏览归因窗口期可在以下范围内自行调整：可用参数值为1h - 24h（小时）。默认值为24h。</li><li><Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows#回溯窗口的设置方式">SRN</Anchor>的归因窗口可自行设置。</li></ul>**请注意**：仅影响展示URL，不影响点击URL。 | 最多3个字符 |
| <span id="af_channel"></span>af\_channel | Channel | 分发广告的媒体渠道流量入口，比如UAC\_Search、UAC\_Display、Instagram、Meta Audience Network等。 | 动态枚举。字符串限长20 |
| <span id="af_engagement_destination"></span>af\_engagement\_destination | Engagement destination | 指示广告链接的目的地的类别，例如 **网页** 登陆页面、**移动** 应用（通过深度链接或应用商店）或其他目的地类型，如 **CTV**、**PC** 或 **控制台**。 | 字符串限长50 |
| <span id="af_keywords"></span>af\_keywords | Keywords | 文本定向型广告的关键词列表 | String 100 |
| <span id="af_cost_model"></span>af\_cost\_model | Cost model | <ul><li>成本模型，通过点击上报成本时仅支持CPI（默认），填充<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">AppsFlyer汇总数据报告中的成本值</Anchor>。</li><li>请尽量通过<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">API</Anchor>上报成本。同时通过链接和API上报成本时，API优先级更高。</li></ul> | 字符串限长20 |
| <span id="af_cost_currency"></span>af\_cost\_currency | Cost currency | <ul><li>符合<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">ISO-4217</Anchor>的3字母货币代码， 如USD、ZAR、EUR。</li><li>【默认】：USD</li></ul> | 3字符枚举 |
| <span id="af_cost_value"></span>af\_cost\_value | Cost value | <ul><li>以成本货币为单位显示的成本值。</li><li>最多精确到小数点后4位。</li><li>只能设置数字（可带小数点）例如：“ 56”，“ 2.85”</li></ul> | 字符串限长20 |
| <span id="af_sub-n-n15-example-af_sub1"></span>af\_sub[n]<br /><br />(n=1-5) 例：af\_sub1 | Sub param [n] | 由广告主自行配置的可选参数。详情请见[特点与局限性](/docs/about-link-structure-and-parameters#特点与局限性)部分，其中说明了这些参数的用法。 | String 100 |
| <span id="af_r"></span>af\_r | 不适用 | 让用户跳转到指定网址，支持**所有平台**（安卓、iOS和PC）。<br /><br />在多平台链接（OneLink）中，该参数：<ul><li>会覆盖模板层级的跳转设置</li><li>会被以下链接层级的参数覆盖：<ul><li>[`af_android_url`](/docs/about-link-structure-and-parameters#af_android_url)</li><li>[`af_ios_url`](/docs/about-link-structure-and-parameters#af_ios_url)</li><li>[`af_web_dp`](/docs/about-link-structure-and-parameters#af_web_dp)</li></ul></li></ul>**请注意：** 参见其他跳转参数[特性与局限性](/docs/about-link-structure-and-parameters#special-characters)。 |  |
| <span id="af_web_dp"></span>af\_web\_dp | 不适用 | 让PC端（例如Windows或Mac）用户跳转到OneLink模板中指定网页以外的URL。此参数用于将PC端用户的归因数据保存到其他平台（如Google Analytics或Omniture）。<br /><br />**请注意：** 参见其他跳转参数[特性与局限性](/docs/about-link-structure-and-parameters#special-characters)。 |  |
| <span id="af_dp"></span>af\_dp | 不适用 | URI scheme作为备用方案，可在Universal Link或Android App Link失效时或用户使用的安卓版本低于6.0时打开应用。建议仅使用该方法进入<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">基本路径</Anchor>，即默认页面。<br /><br />请注意<strong>：</strong>如果你为该参数使用了网页URL（不推荐），请务必查看跳转参数的[特性与局限性](/docs/about-link-structure-and-parameters#special-characters)。 |  |
| <span id="af_force_deeplink"></span>af\_force\_deeplink | 不适用 | 用于强制执行af\_dp中的<Anchor target="_blank" href="/marketers/zh/docs/onelink-troubleshooting-and-faq">深度链接</Anchor> |  |
| <span id="af_ref"></span>af\_ref | 不适用 | 使用S2S点击的广告平台可以通过以下参数发送referrer值：&af\_ref=**ReferrerValue**<br /><br />每个点击的af\_ref值**必须**是唯一的，结构如下：<br /><br />**NetworkName\_UniqueClickValueForEachClick**<br /><br />示例: af\_ref=networkname\_123456789ABCDEF<br /><br />广告平台名称可由任意的有效字符串组成，可以是networkname\_int，或直接使用平台名称。<br /><br />AppsFlyer会使用该参数对安卓设备进行归因，但不会将其用于iOS或Windows设备。 |  |
| <span id="is_incentivized"></span>is\_incentivized | 不适用 | 布尔值：true / false<br /><br />用于标记广告是否带有奖励 |  |
| <span id="af_param_forwarding"></span>af\_param\_forwarding | 不适用 | <ul><li>该参数为“false“时，归因链接里的参数不会传递到跳转后的页面。</li><li>此参数用于精简跳转页面的链接，或预防由归因链接参数造成的跳转问题。</li></ul> |  |
| <span id="af_base_params_forward"></span>af\_base\_params\_forward | 不适用 | <ul><li>该参数为“false“时，归因链接里的AppsFlyer PID和C参数不会传递到跳转后的页面。</li><li>如果用户会从PC端点击相关链接，且您想要保留基本的CRM参数但移除AppsFlyer PID和C参数，这时可以使用这个参数来避免链接中出现多个PID。</li></ul> |  |
| <span id="af_partner_account_id"></span>af\_partner\_account\_id | Network Account ID | 渠道侧的广告主帐户ID | String 100 |
| <span id="af_redirect"></span>redirect | 不适用 | `&redirect=false`时，即可为AppsFlyer标识出S2S点击，并告知AF该点击中渠道负责为用户实现跳转。 |  |
| <span id="af_ua"></span>af\_ua | User-agent | 适用于发送<Anchor target="_blank" href="/partners/zh/docs/redirecting-users-to-the-app-store">S2S</Anchor>点击和展示的广告平台。<br /><br />**重要：** 请勿在客户端与服务器（C2S）链接中使用`af_ua`。在C2S链接中使用`af_ua`可能会影响归属。<br /><br />用户代理（user-agent）字符串以下列形式发送：<ol><li>URL参数（URL-编码）</li><li>HTTP请求头（Request Header，未编码）</li></ol>**URL参数和HTTP请求头中的**User-Agent应完全一致。<br /><br />在安卓平台中，User-Agent有时会被缩减版的Client Hints取代。这种情况下仍应发送该字段。<ul><li>完整的user-agent字符串示例：</li><li>缩减的user-agent字符串示例：</li></ul>**在 iOS 中**，从 iOS 26 开始，版本会被附加。<br />这里是：<ul><li>**附加部分的示例：** `Version/26.0.1 Mobile/15E148 Safari/604.1`</li><li>**完整用户代理的示例：**<br />`Mozilla/5.0 (iPhone; CPU iPhone OS 16_4_1 like Mac OS X) AppleWebKit/8615.1.26.10.24 (KHTML, like Gecko) Mobile/20E252 Version/26.0.1 Mobile/15E148 Safari/604.1`</li></ul> |  |
| <span id="af_ip"></span>af\_ip | IP | 适用于发送<Anchor target="_blank" href="/partners/zh/docs/redirecting-users-to-the-app-store">S2S</Anchor>点击和展示的广告平台。<br /><br />**重要：** 请勿在客户端与服务器（C2S）链接中使用`af_ip`。在C2S链接中使用`af_ip`可能会影响归属。<br /><br />**设备IP地址**<br /><br />**建议**：在af\_ip参数中提供设备IP（若可用）。<br /><br />**次优方案**：AppsFlyer会使用X-Forwarded-For中的IP（若可用）。 |  |
| <span id="deprecated--af_os"></span>【已弃用】af\_os | OS version（操作系统版本） | 【仅适用于iOS】设备的操作系统版本。<br /><br />AppsFlyer已弃用但仍支持该参数。建议：使用af\_os\_version参数代替。 |  |
| <span id="af_os_version"></span>af\_os\_version | OS version（操作系统版本） | <ul><li>适用于发送<Anchor target="_blank" href="/partners/zh/docs/redirecting-users-to-the-app-store">S2S</Anchor>点击和展示的广告平台。</li><li>设备的操作系统版本。<ul><li>安卓：<ul><li>举例来说，12</li><li>对于缩减后的User-Agent（若广告交互发生在PC端浏览器中或使用Chrome 100+引擎的安卓平台中），广告平台必须使用<Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">Client Hints API</Anchor>来拉取该参数值。</li><li>对于**未**缩减的User-Agent，可使用以下正则表达式来攫取User-Agent字符串中的安卓OS版本信息：`(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`。</li></ul></li><li>iOS：<ul><li>举例来说，16.2</li></ul></li></ul></li></ul> |  |
| <span id="af_model"></span>af\_model | Device model | <ul><li>适用于发送<Anchor target="_blank" href="/partners/zh/docs/redirecting-users-to-the-app-store">S2S</Anchor>点击和展示的广告平台。</li><li>用于表示设备型号。<ul><li>安卓：<ul><li>举例来说，Pixel 5</li><li>对于缩减后的User-Agent（若广告交互发生在PC端浏览器中或使用Chrome 100+引擎的安卓平台中），广告平台必须使用<Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">Client Hints API</Anchor>来拉取该参数值。</li><li>对于**未**缩减的User-Agent，可使用以下正则表达式来攫取User-Agent字符串中的安卓设备型号信息：`(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`。</li></ul></li><li>iOS：<ul><li>`iphone`或`ipad`（全部小写）</li><li>包括完整的设备型号标识符以确保准确归属。示例：`iphone15,1`或`ipad14,2`。</li></ul></li></ul></li></ul> |  |
| <span id="af_media_type"></span>af\_media\_type | 媒体类型 | 用于标记广告链接所在的媒体类型。分为以下两种：<ul><li>app：广告链接投放在应用中</li><li>web：广告链接投放在移动端网页中</li></ul> |  |
| <span id="deep_link_sub110"></span>deep\_link\_sub1-10 | 不适用 | 其他的深度链接值。开发人员需要将这些值执行的跳转写入代码中。 |  |
| <span id="deep_link_value"></span>deep\_link\_value | 不适用 | 具体应用内内容的名称，用户点击链接后会跳转到相应页面。开发人员需要把deep\_link\_value执行的跳转写入代码中。 |  |
| <span id="af_og_title"></span>af\_og\_title | 不适用 | 在社交媒体上分享链接时，可使用开放图谱（Open Graph，简称OG）标题来生成标题预览。 | 字符串限长40 |
| <span id="af_og_description"></span>af\_og\_description | 不适用 | 在社交媒体上分享链接时，可使用开放图谱（Open Graph，简称OG）描述来生成描述预览。 | 字符串限长300 |
| <span id="af_og_image"></span>af\_og\_image | 不适用 | 在社交媒体上分享链接时，可使用开放图谱（Open Graph，简称OG）图像来生成图像预览。 |  |

<div id="attribution-link-parametersretargeting-only" />

### 归因链接参数——仅限再营销

| 参数 | 原始数据中的字段名称 | 说明 | 字段类型及长度限制 |
| --- | --- | --- | --- |
| <span id="is_retargeting"></span>is\_retargeting | Is Retargeting (campaign) | 所有再营销广告的点击链接里都应含有`&is_retargeting=true`。  <br />如果不包括该参数或其值为 "false"，则AF会视其为拉新广告。 | 5字符枚举 |
| <span id="af_reengagement_window"></span>af\_reengagement\_window | 再互动窗口期 | 该参数用于调整<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide#reengagement-rules-and-windows">再互动归因窗口期</Anchor>。<br /><br />可在以下范围内调整：<ul><li>1-90天或1-36小时</li><li>全周期：即再互动窗口期无限延长。示例：`&af_reengagement_window=lifetime`</li></ul>默认值：30天<br /><br />示例：`&af_reengagement_window=30d`表示再互动窗口期是30天。 | 不适用 |

<div id="viewability-parameters" />

### 可见性参数

您还可以针对不同的广告类型发送相关的可见性参数，记录用户互动的详细情况。

| 参数 | 参数值格式 | 说明 |
| --- | --- | --- |
| <span id="af_video_total_length"></span>af\_video\_total\_length | 秒数 | 视频总时长 |
| <span id="af_video_played_length"></span>af\_video\_played\_length | 秒数 | 视频播放时长 |
| <span id="af_playable_played_length"></span>af\_playable\_played\_length | 秒数 | 试玩元素完全加载后玩了多长时间 |
| <span id="af_ad_time_viewed"></span>af\_ad\_time\_viewed | 秒数 | 广告展示时长 |
| <span id="af_ad_displayed_percent"></span>af\_ad\_displayed\_percent | % | 广告在设备屏幕上的最大占比 |
| <span id="af_audio_total_length"></span>af\_audio\_total\_length | 秒数 | 音频总时长 |
| <span id="af_audio_played_length"></span>af\_audio\_played\_length | 秒数 | 音频播放时长 |

<div id="android-specific-parameters" />

### 安卓专用参数

| 参数 | 原始数据中的字段名称 | 说明 | 字段类型 |
| --- | --- | --- | --- |
| <span id="advertising_id"></span>advertising\_id | Advertising ID | Google Advertising ID需要广告平台支持 | 最多49个字符 |
| <span id="sha1_advertising_id"></span>sha1\_advertising\_id | 不适用 | 通过SHA1加密的Google Advertising ID——需要广告平台支持 |  |
| <span id="md5_advertising_id"></span>md5\_advertising\_id | 不适用 | 通过MD5加密的Google Advertising ID——需要广告平台支持 | 仅支持激活和再归因 |
| <span id="android_id"></span>android\_id | Android ID | 设备Android\_id需要广告平台支持 | 最多20个字符 |
| <span id="sha1_android_id"></span>sha1\_android\_id | 不适用 | 通过SHA1加密的设备Android\_id——需要广告平台支持 |  |
| <span id="md5_android_id"></span>md5\_android\_id | 不适用 | 通过MD5加密的设备Android\_id——需要广告平台支持 | 仅支持激活和再归因 |
| <span id="imei"></span>imei | IMEI | 设备IMEI ID |  |
| <span id="sha1_imei"></span>sha1\_imei | 不适用 | 通过SHA1加密的设备IMEI ID——需要广告平台支持 |  |
| <span id="md5_imei"></span>md5\_imei | 不适用 | 通过MD5加密的设备IMEI ID——需要广告平台支持 |  |
| <span id="oaid"></span>oaid | OAID | Open Anonymous Device Identifier（匿名设备标识符） | Android SDK 4.10.3及以上版本可用 |
| <span id="sha1_oaid"></span>sha1\_oaid | 不适用 | 通过SHA1加密的匿名设备标识符——需要广告平台支持 | Android SDK 4.10.3及以上版本可用 |
| <span id="md5_oaid"></span>md5\_oaid | 不适用 | 通过MD5加密的匿名设备标识符——需要广告平台支持 | Android SDK 4.10.3及以上版本可用 |
| <span id="af_android_url"></span>af\_android\_url | 不适用 | 让安卓用户跳转到Google Play应用页面以外的链接。适用于<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution#查看多个商店数据单一应用面板-vs-多个应用面板">第三方应用商店</Anchor>。<br /><br />**请注意：** 参见其他跳转参数[特性与局限性](/docs/about-link-structure-and-parameters#special-characters)。 |  |
| <span id="sha1_el"></span>sha1\_el | 不适用 | 用于PC端到移动端的归因，电子邮箱经SHA1加密。需要广告平台支持。 |  |
| <span id="fire_advertising_id"></span>fire\_advertising\_id | 不适用 | Amazon Fire Advertising ID |  |
| <span id="af_android_store_csl"></span>af\_android\_store\_csl | store\_product\_page | Google Console中的自定义商店详情页（Custom Store Listing） | 字符串 |

<div id="ios-specific-parameters" />

### iOS专用参数

| 参数 | 显示名称 | 说明 |
| --- | --- | --- |
| <span id="idfa"></span>idfa | IDFA | 全部大写。需要广告平台支持。<br /><br />字段格式：最多49个字符 |
| <span id="idfv"></span>idfv | IDFV | 全部大写。 |
| <span id="af_ios_url"></span>af\_ios\_url |  | 该参数用于落地页跳转，让iOS设备（iPhone或iPad）的用户跳转到iTunes应用页面以外的链接。<br /><br />**请注意：** 参见其他跳转参数[特性与局限性](/docs/about-link-structure-and-parameters#special-characters)。 |
| <span id="af_ios_store_cpp"></span>af\_ios\_store\_cpp | store\_product\_page | Custom product page ID（自定义产品页面ID，ppid）<br /><br />**请注意：** 在原始数据和汇总数据中，仅针对广告点击记录af\_ios\_store\_cpp（自定义产品页面ID）参数的值，广告展示中不记录该值。 |
| <span id="af_ios_fallback--deprecated"></span>af\_ios\_fallback【已弃用】 | 不适用 | <strong>【已弃用】</strong>通过<Anchor target="_blank" href="/marketers/zh/docs/uri-scheme-fallback-for-ios">iOS URI scheme链路</Anchor>实现跳转。 |
| <span id="sha1_idfa"></span>sha1\_idfa | 不适用 | 通过SHA1加密的IDFA。需要广告平台支持。 |
| <span id="sha1_idfv"></span>sha1\_idfv | 不适用 | 通过SHA1加密的IDFV。 |
| <span id="mac"></span>mac | 不适用 | 设备mac地址。需要广告平台支持。 |
| <span id="md5_idfa"></span>md5\_idfa | 不适用 | 通过MD5加密的IDFV。 |
| <span id="md5_idfv"></span>md5\_idfv | 不适用 | 通过MD5加密的IDFV。 |
| <span id="sha1_mac"></span>sha1\_mac | 不适用 | 通过SHA1加密的设备mac地址。需要广告平台支持。 |

<div id="example" />

> 📄 **示例**
>
> ```http
> https://app.appsflyer.com/{app_id}/?pid=airpush_int&c=RedBanner&
> 	  af_siteid={publisher_id}&af_sub1=1.5&af_sub2=USD&af_sub3=burst_campaign
> ```

这些参数在<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">激活报告</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/analytics-and-aggregate-reporting-apis">分析工具、报告工具、API</Anchor>中都可用。

<div id="custom-parameters" />

### 自定义参数

除了默认的安卓和iOS专用参数外，您还可以使用自定义参数。在归因链接中添加这些自定义参数能帮助您打造定制化的用户体验和内容。

您可以使用`parameter=value`的格式将自定义参数附在归因链接之后。例如：

```http
https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&af_adset=coats&af_ad=cashmere&my_custom_param=my_custom_value
```

使用自定义参数时需注意以下两点：

* 自定义参数不会显示在原始数据中。
* 您可以通过<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">转化数据SDK API</Anchor>来获取自定义参数。

<div id="partner-id-pid-parameter" />

<Accordion title="Partner ID（PID）参数">

在所有可用的归因链接参数中，PID是必须配置的参数。 PID是媒体渠道的唯一标识符，由AppsFlyer设定。 按以下维度 。

每个 <Anchor target="_blank" href="http://appsflyer.com/partners">集成的合作伙伴</Anchor> 具有唯一的 PID 值，后缀为 *\_int* 。 使用时 OneLink链接 您可以将PID设置为您喜欢的任何值，只要它是 次要维度 被集成的合作伙伴保留。

<div id="note" />

> 📘 **注意**
>
> AppsFlyer 阻止使用保留的 <Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#与appsflyer对接的srn">SRN</Anchor> 在自定义媒体源中使用名称作为PID值，例如电子邮件 和短信。 此限制**不适用**于ASRN。

重要集成保留发布者 ID 的示例：有机， googleadwords\_int（Google AdWords），facebook\_int（Meta广告）， 及 twitter\_int（X 广告）。您可以为非集成的使用任何名称 所有媒体渠道都提供 例如电子邮件、SMS 或邮件鸽子。

<div id="avoid-common-pid-issues" />

#### 如何避免常见的PID问题：

* **一定要在归因链接中配置PID，** 在归因链接上没有 PID，用户会自动 归因于 "无" 媒体源，原始安装 源消失了。
* **对于每个集成的源**，仅使用指定的 指定的 PID 以正确归因其安装。
* **如果是自有媒体，请勿使用对接渠道的PID。** 对于任何自定义媒体源，例如电子邮件、短信或 甚至 在Facebook上使用其他非集成的病毒性未付帖子 PID 值，例如 owned\_email。 sms\_push，或其他自定义 `{identifiers}` 不匹配集成合作伙伴名称的。
* <strong>请确保PID中的字符有效。</strong>PID参数： 归因链接中包含以下字符之一 /&lt;>*&?\
  * 点击或安装在仪表板下显示 ***af\_invalid\_param***
  * 归因链接无法得到归因
  * 点击中的深度链接功能无法正常生效

<div id="tip" />

> 👍 **提示**
>
> 避免在PID值中使用空格，或确保 URL 在使用之前对您的归因链接进行编码。

</Accordion>

<div id="site-id-parameter" />

<Accordion title="Site ID（子渠道）参数">

子渠道ID用于标记投放广告的发行商， 下文的 广告即展示广告的网站或应用。Ad 网络 会为其发行商设定唯一的子渠道ID。

此ID包含在传递的`af_siteid`参数中 在归因链接中发送到AppsFlyer，并通过 下文的 各种仪表板、报告选项和回调提供。

请务必通过归因链接将子渠道信息发送给AppsFlyer，因为： 因为 这样才能确保您获取的数据以及数据的格式符合您的实际需求。

* 这能让该媒体的数据更加清晰透明
* AppsFlyer会通过该信息来识别并剔除作弊媒体。 发布者， 和其他流量集群。

子渠道ID参数仅包含投放广告的发行商的ID。 提供广告。

要包含附加信息，例如广告类型、投放， 或 在应用内的两者，例如横幅、插页式或视频， 使用子站点ID参数。

<div id="example-1" />

> 📄 **示例**
>
> 以下归因链接中包含：
>
> * `af_siteid`：子渠道ID
> * `af_sub_siteid`：其他 ID信息（在这种情况下，附属源和广告类型） placement
>
> `https://app.appsflyer.com/com.yourapp?pid=mediaName_int&clickid={clickid}&advertising_id={gaid}&af_siteid=1234&af_sub_siteid=ABCD_4567`
>
> 在示例链接中：
>
> * 1234 = 子渠道ID
> * ABCD = 合作来源（子发布者），出版商 正在合作的
> * 4567 = 应用内的广告类型位置，例如横幅， 插页式或视频

<div id="faq-why-does-traffic-result-in-many-blocked-installs" />

#### **FAQ：为何流量中有很多被屏蔽的激活？**

激活被屏蔽可能是由以下原因导致的：

* **子渠道ID缺失：** 该 点击链接中的参数为空。与发送的参与 一个 空的站点ID表示技术问题或故意的 试图绕过欺诈检测机制。
* **多个子渠道ID：** 同一出版商是 发送 到多个点击网址，使用不同的网站ID。（即您 被视为 掩盖真实出版商活动的欺诈行为 及 通常与以下内容相关联 点击刷量
* **子渠道ID的格式错误：** 发送 错误的 格式，加上其他欺诈迹象，可能导致 （美元或实际使用货币的等价金额） 不仅阻止特定发布者，还可能阻止更高的 集群级别，并可能影响更大数量的合作伙伴 事项

为了避免被封锁的安装，请确保您发送一个单一的网站ID 参数 每个发布者，如示例所示。

</Accordion>

<div id="levels-of-data-granularity" />

## 数据粒度级别

您最多可使用4个链接参数来剖析广告效果。

如果您在所有的活跃归因链接上使用了全部4个参数，就可以实现下列功能：

* 将所有的用户激活和事件都归因到具体的广告
* 您可以在汇总报告中分广告组、广告系列、广告平台来查看和比较所有广告的综合表现，以便在各层级优化投放
* 您可以在原始数据报告和<Anchor target="_blank" href="/marketers/zh/docs/pivot-table-user-metrics">数据透视表</Anchor>里对各广告平台上的所有广告进行对比分析

参数名称如下：

* `Media source (pid=)`
* `campaign name (c=)`
* `Ad set (af_adset=)`
* `Ad name (af_ad=)`

<div id="example-2" />

> 📄 **示例**
>
> 以下归因链接运用了4种颗粒度，记录在“network”平台上投放的“winter”广告系列中”coats“广告组下的“cashmere”广告。
>
> ```http
> https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&
> af_adset=coats&af_ad=cashmere
> ```

<div id="frequently-asked-questions" />

## 常见问题

<div id="should-i-use-lower-or-upper-case-letters-for-parameters" />

<Accordion title="这些参数要用大写格式还是小写格式？">

大写小写都可以，但必须保持一致。如果您用大写字母设置了一个自定义参数，就必须总是使用大写字母来表达该参数，反之亦然。

举例来说，如果您设置了pid=MyMediaSource，请确保您总是按照这样的大小写来使用该参数。如果您在一个归因链接中使用pid=MyMediaSource，而在另一个归因链接中使用pid=mymediasource ，就会产生数据差异，归因链接中的其他参数设置也是同理。

</Accordion>

<div id="is-the-appsflyer-attribution-link-dynamic-or-static" />

<Accordion title="AppsFlyer的归因链接是动态的还是静态的？">

归因链接可以是动态的，也可以是静态的。  
那么要如何判断一个链接是动态还是静态的呢？  
如果**归因链接中包含参数**，就表示这是一个已经定义完毕的归因链接，因此是**静态的**。  
**只有自定义归因链接的短链**（如`yourbrand.onelink.me/HaT8/r5c2b371`）才是**动态**的。  
也就是说，如果您在对接渠道中使用了配置好的归因链接，或在自有媒体中使用了长链，那么就算您之后在AppsFlyer后台更改了该归因链接的值，投出去的链接也不会随之变化。如果要让更改生效，就必须使用更新后的长链。  
相反的，由于自有媒体的短链中不直接包含参数，因此用户与短链互动时，会跳转到AppsFlyer的服务器，这样当前的参数设置就会动态生效。

</Accordion>

<div id="what-is-this-play-store-error-message" />

<Accordion title="Google Play Store的这条报错信息是什么意思？">

如果您在点击一条归因链接后收到以下报错消息：

<Image align="center" alt="TL_error_message.png" src="https://files.readme.io/03e509d3cbe68aa0621bb0f43ab113c25a8427e70826c5af5258f1fc9e3f3d36-360000002485.png" />

这是因为该归因链接中含有“#”这个字符。例如：

```http
https://app.appsflyer.com/com.travelco?pid=globalwide_int&clickid=#reqid#
```

链接中的这类字符通常是宏，会被其他值动态取代。这种情况并不构成问题，您可以直接忽略该消息。

</Accordion>

<div id="what-are-subscriber-parameters-good-for" />

<Accordion title="Subscriber Parameters（自配参数）有什么用处？">

Subscriber Parameters（自配参数），即af\_sub1、af\_sub2…af\_sub\_5，可用于记录任何您关注的KPI。您可以在原始数据报告中查看解析后的自配参数，以便对数据进行汇总或筛选。

<div id="example-3" />

> 📄 **示例**
>
> 一款名为Luber的打车应用有3种颜色的素材模板：蓝色、黄色和红色。Luber的移动营销人员Linda想要测试哪种颜色的模板能带来更多激活。因此她在所有非自归因平台的蓝色广告的归因链接里添加了`&af_sub3=blue`，黄色和红色广告以此类推。然后Linda在原始数据报告里查看解析后的相关信息，就能分析出不同颜色广告的效果并找出转化率最高的那一个。

</Accordion>

<div id="what-limits-are-there-on-campaign-names" />

<Accordion title="广告系列名称有何限制？">

* 归因链接中的广告系列名称长度不能超过100个字符。若超过100个字符，则该广告系列的名称会自动变成`c_name_exceeded_max_length`。
* 广告系列名称的不能以空格开头或结尾，否则会导致面板和报告的数据之间产生差异。

</Accordion>

<div id="traits-and-limitations" />

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| <span id="special-characters"></span>特殊字符 | 在参数键和值中不允许使用以下字符（不适用于跳转和 af\_dp 参数）： ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, % |
| <span id="redirection-parameters"></span>跳转参数： | <ul><li>确保您的跳转URL域名已添加到您的<Anchor target="_blank" href="/marketers/zh/docs/set-up-your-domain-redirect-allowlist">跳转白名单</Anchor>中。</li><li>该参数的值必须是完整的有效网页URL（https://[domain][optional-path]），且符合<Anchor target="_blank" href="https://datatracker.ietf.org/doc/html/rfc1738">RFC 1738标准</Anchor>；该参数中不能使用URI scheme。</li><li>跳转URL**不支持**<Anchor target="_blank" href="https://en.wikipedia.org/wiki/URI_fragment">URI片段标识符</Anchor> （如将用户引导至文章中特定部分的#webpagesection）。</li></ul> |
| <span id="url-characteravailable"></span>链接长度限制 | URL总长度不得超过2000个字符 |
| <span id="agencies"></span>安卓社交应用的Webview深度链接跳转 | 如需进一步了解具体限制，请参考<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection">此文档</Anchor> |
| <span id="deep-linking-is-not-supported-in-the-android-naver-blog-app"></span>安卓版Naver Blog应用不支持深度链接 | 安卓版Naver Blog应用不支持深度链接，用户会跳转到Google Play Store或相关链接指定的网页。 |
| <span id="a-popup-appears-when-clicking-on-a-uri-scheme-link-from-chrome-browser-on-ios"></span>iOS用户在Chrome浏览器中点击带有URI scheme的链接后界面显示弹窗 | iOS版的Chrome发生了更新。更新后，用户在iOS的Chrome中点击URI scheme链接时，界面会跳出弹窗，让用户确认是否要打开相关应用/跳转到App Store。 |
| <span id="uri-scheme-validity-requirements"></span>URI scheme有效性要求 | 建议您使用符合<Anchor target="_blank" href="https://www.rfc-editor.org/rfc/rfc3986#section-3.1">RFC 3986</Anchor>标准的有效URI scheme。不符合该标准的URI scheme无法调起应用，且用户在网页视图（web view）或其他网页环境中点击相关链接后会出现报错。 |
| <span id="telegram-webview-attribution"></span>Telegram WebView归因 | 如需进一步了解具体限制，请参考<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#telegram-webview">此文档</Anchor> |

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 01H8GN1XXC5T2ENFHBK0G4WQ1P=%E9%80%9F%E8%A7%88 01JENAANV4KTRF882JMEM5N91A=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA attribution-link-parameters=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 01H8GN1XXDX1XMQ1GJTHCP425D=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 attribution-link-parameters%E2%80%94ua-and-retargeting=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0%E6%8B%89%E6%96%B0%E5%8F%8A%E5%86%8D%E8%90%A5%E9%94%80 01H8GN1XXDEWPB2MPP3KJVPRJV=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0%E6%8B%89%E6%96%B0%E5%8F%8A%E5%86%8D%E8%90%A5%E9%94%80 af_sub%5Bn%5D%C2%A0%0An15-example-af_sub1=af_sub-n-n15-example-af_sub1 %5Bdeprecated%5D-af_os=deprecated--af_os attribution-link-parameters%E2%80%94retargeting-only=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0%E4%BB%85%E9%99%90%E5%86%8D%E8%90%A5%E9%94%80 01H8GN1XXD9X7CWZJN43PSS94R=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0%E4%BB%85%E9%99%90%E5%86%8D%E8%90%A5%E9%94%80 viewability-parameters=%E5%8F%AF%E8%A7%81%E6%80%A7%E5%8F%82%E6%95%B0 01H8GN1XXETQEYT39F05ZYX4E2=%E5%8F%AF%E8%A7%81%E6%80%A7%E5%8F%82%E6%95%B0 androidspecific-parameters=%E5%AE%89%E5%8D%93%E4%B8%93%E7%94%A8%E5%8F%82%E6%95%B0 01H8GN1XXEE9RGSB1H72H025Z4=%E5%AE%89%E5%8D%93%E4%B8%93%E7%94%A8%E5%8F%82%E6%95%B0 iosspecific-parameters=ios%E4%B8%93%E7%94%A8%E5%8F%82%E6%95%B0 01H8GN1XXESJ9VE3W8CYKRFFYX=ios%E4%B8%93%E7%94%A8%E5%8F%82%E6%95%B0 af_ios_fallback-%5Bdeprecated%5D=af_ios_fallback--deprecated 01H8GN1XXEFRSQSERTB6ARC773=%E7%A4%BA%E4%BE%8B custom-parameters=%E8%87%AA%E5%AE%9A%E4%B9%89%E5%8F%82%E6%95%B0 01H8GN1XXEB58JN4SV9HX1ZV6S=%E8%87%AA%E5%AE%9A%E4%B9%89%E5%8F%82%E6%95%B0 01H8GN1XXE8EXMMKDZMJ2WNNH5=partner-id-pid-parameter h_01JRX48BX8W9V9XWPB1DSG4H8Y=%E6%B3%A8%E6%84%8F avoid-common-pid-issues=%E5%A6%82%E4%BD%95%E9%81%BF%E5%85%8D%E5%B8%B8%E8%A7%81%E7%9A%84pid%E9%97%AE%E9%A2%98 01H8GN1XXEXTGC4M8AMJ256Q9G=%E5%A6%82%E4%BD%95%E9%81%BF%E5%85%8D%E5%B8%B8%E8%A7%81%E7%9A%84pid%E9%97%AE%E9%A2%98 01H8GN1XXEGNVX9GM5JYBMBGCF=%E6%8F%90%E7%A4%BA 01H8GN1XXEVG65YP782CM37RES=site-id-parameter 01H8GN1XXED2MVSNRXN11KZ955=%E7%A4%BA%E4%BE%8B-1 faq-why-does-traffic-result-in-many-blocked-installs=faq%E4%B8%BA%E4%BD%95%E6%B5%81%E9%87%8F%E4%B8%AD%E6%9C%89%E5%BE%88%E5%A4%9A%E8%A2%AB%E5%B1%8F%E8%94%BD%E7%9A%84%E6%BF%80%E6%B4%BB 01H8GN1XXEK0G9TDW8WHWM17HK=faq%E4%B8%BA%E4%BD%95%E6%B5%81%E9%87%8F%E4%B8%AD%E6%9C%89%E5%BE%88%E5%A4%9A%E8%A2%AB%E5%B1%8F%E8%94%BD%E7%9A%84%E6%BF%80%E6%B4%BB levels-of-data-granularity=%E6%95%B0%E6%8D%AE%E7%B2%92%E5%BA%A6%E7%BA%A7%E5%88%AB 01H8GN1XXE4RF9J0APAAKD1WEG=%E6%95%B0%E6%8D%AE%E7%B2%92%E5%BA%A6%E7%BA%A7%E5%88%AB 01H8GN1XXEHPFKX7V0RRW2MH2G=%E7%A4%BA%E4%BE%8B-2 frequently-asked-questions=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98 h_01HN0JW166VHR33T8VVVY47F9P=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98 01H8GN1XXEND9X8YVRQE1YFA5W=should-i-use-lower-or-upper-case-letters-for-parameters 01H8GN1XXER749PH4Z14A7AJ0F=is-the-appsflyer-attribution-link-dynamic-or-static 01H8GN1XXEPQTY0XNW6EZSA9ZN=what-is-this-play-store-error-message 01H8GN1XXFYAFYFX9MNBP6D35B=what-are-subscriber-parameters-good-for 01H8GN1XXFEFA498J22GRF5F8G=%E7%A4%BA%E4%BE%8B-3 01H8GN1XXFS1DFS3HAHVTVG93A=what-limits-are-there-on-campaign-names traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HN0JW166WH76A5SM293PGKX6=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
