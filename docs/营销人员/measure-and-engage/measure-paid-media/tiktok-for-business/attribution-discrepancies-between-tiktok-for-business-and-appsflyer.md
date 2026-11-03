---
title: TikTok for Business和AppsFlyer之间的归因差异
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-10-30T07:45:29Z'
  edited_at: '2026-10-14T10:07:39Z'
  id: 19733501619473
  locale: zh-cn
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/zh-cn/articles/19733501619473
---
> **概要：** 本文重点解释了TikTok for Business和AppsFlyer之间的归因模式差异。

## 速览

TikTok for Business和AppsFlyer在移动端获客营销生态体系中都扮演着重要的角色，而双方都使用自己特有的归因模型。这会使两者的面板之间产生一些数据差异。虽然我们一直与TikTok for Business保持紧密的合作，以尽可能地减少这样的差异，但广告主仍需了解可能会造成数据差异的各种因素。

## 归因模型的差异

下表列出了可能会导致TikTok Ads Manager与AppsFlyer面板之间产生数据差异的原因：

<table><thead><tr><th>原因</th><th>TikTok Ads Manager</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><p><strong>点击型归因窗口期</strong></p></td><td><p>默认窗口为7天。但安卓应用以及切换到SRN版TikTok的应用可使用不同的配置（TikTok—SRN）。</p></td><td><p>默认窗口期为7天。该窗口期的可用配置范围为1-30天。请确保您在AppsFlyer中设置的窗口期与TikTok侧的归因窗口保持一致。</p></td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><p><strong>浏览型归因窗口期</strong></p></td><td><p>默认窗口期为1天。但安卓应用以及切换到SRN版TikTok的应用可使用不同的配置（TikTok—SRN）。</p></td><td><p>默认窗口期为1天。该窗口期的可用配置范围为1-48小时。请确保您在AppsFlyer中设置的窗口期与TikTok侧的归因窗口保持一致。</p></td></tr><tr><td><span id="multichannel-sourceattribution"></span><p><strong>多源归因</strong></p></td><td><p>TikTok无视其他渠道的广告互动，将激活归因给自己。</p></td><td><p>AppsFlyer使用末次点击归因（详情请见<a href="./appsflyer-attribution-model" target="_blank">AppsFlyer归因模型</a> ）。</p></td></tr><tr><td><span id="crossdevice-attribution"></span><p><strong>跨设备归因</strong></p></td><td><p>Tiktok对用户在不同设备上完成的的互动和激活进行跨端归因，包括iOS、安卓和PC端设备。</p></td><td><p>AppsFlyer对用户在同一个设备上完成的互动和激活进行归因。</p></td></tr><tr><td><span id="different-time-zones"></span><p><strong>不同时区</strong></p></td><td><p>日期范围旁的<a href="https://ads.tiktok.com/help/article/time-zone" target="_blank">TikTok时区</a>无法调整，这是您在创建广告账号时设置的时区。</p></td><td><p>AppsFlyer中默认的应用时区为UTC+0。如需对齐AppsFlyer和TikTok Ads Manager的时区，请在AF后台的<a href="./app-settings#localization-time-zone" target="_blank">应用配置页面</a>中更改相关应用的时区设置。</p></td></tr><tr><td><span id="ios-attribution"></span><p><strong>iOS归因</strong></p></td><td><p>对于iOS应用，TikTok Ads Manager仅显示SKAN的归因结果。</p></td><td><p>对于iOS应用，AppsFlyer在显示SKAN归因结果的同时还会呈现SRN和高级SRN的归因数据，以及去重后的SSOT数据。在两个平台中保持一致的数据仅限SKAN归因结果。 </p></td></tr><tr><td><span id="in-app-event-attribution-periods"></span><p><strong>应用内事件的归因窗口期</strong></p></td><td colspan="2"><p>两个平台上的归因结果可能会由于初次激活后的归因窗口期不同而产生差异，具体如下：</p></td></tr><tr><td><span id="day-1-90"></span><p>第1-90天</p></td><td colspan="2"><p>无归因差异。两个平台都会将应用内事件归因到初次激活。</p></td></tr><tr><td><span id="day-91-180"></span><p>第91-180天</p></td><td rowspan="2"><p>TikTok不上报初次激活的90天以后发生的应用内事件。</p></td><td><div><div><div>AppsFlyer会将事件归因到初始激活。</div></div></div></td></tr><tr><td><span id="day-180"></span><p>第180+天</p></td><td><div><div><div>由于<a href="./user-level-data-retention#渠道的数据保留期限" target="_blank">TikTok的数据保留政策</a>的限制，这些事件会被归因为自然量。</div></div></div></td></tr></tbody></table>

## 激活数据的差异

某些情况下，TikTok for Business侧的激活会包含AppsFlyer拦截的流量或不记录为新增激活的流量。

### 再互动广告

再互动广告可引导已安装相关应用的用户打开该应用（即**再互动**）。如果AppsFlyer识别到打开该应用的设备曾经安装过该应用，AppsFlyer就会将这个转化记录为**再归因**。

如果TikTok for Business再互动广告带来的用户完成了相关应用的首次激活，则AppsFlyer会将这些用户记录为**新增的UA用户**。此外，如果用户在初次激活的指定<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口期</Anchor>过期后激活该应用，这些用户也会被记录为新增UA用户。

另一方面，在初次激活的**指定再归因窗口期内**发生的激活则会被AppsFlyer记录为再归因，您可以在AppsFlyer后台的再营销页面中看到这些激活。但TikTok for Business会把这些流量记录为新增激活。

### 使用验证规则和Protect360时被拦截的激活

<Anchor target="_blank" href="/marketers/zh/docs/implement-validation-rules-to-prevent-fraud">验证规则</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide">Protect360</Anchor>是AppsFlyer提供的归因防护功能，用于拦截（屏蔽）特定的激活。使用这些功能时，AppsFlyer可能会拦截某些由TikTok for Business带来的激活，但TikTok for Business仍会将这些激活归因到自己的平台。

> 📄 **示例**
>
> GreatApp的UA经理Jeff创建了一个名为SPNA的广告系列，定向投放到生活在北美的西班牙语用户。为了确保这一点，Jeff定义了一个验证规则，该规则是仅接受来自加拿大和美国的用户。
> 这时，某个位于西班牙的TikTok for Business用户点击了该广告并激活应用，TikTok for Business就会将该次激活归因给自己，而AppsFlyer则会因为该激活不符合验证规则而将其拦截下来。

## 减少数据差异的方式

虽然两个平台的归因模式有所差别，但您仍可在部分情况下减少数据差异。

### 点击型和浏览型归因

AppsFlyer支持点击型归因和浏览型归因。为了减少TikTok for Business和AppsFlyer之间的数据差异，请确保您在AF中设置的点击和展示回溯窗口与TikTok for Business中对应的窗口期保持一致。

> 📄 **示例**
>
> 假设您有一个名为`com.greatapp`的应用，并在AppsFlyer中为该应用设置了1天的点击回溯窗口期，而在TikTok for Business中使用了7天的默认窗口期。如果用户在Tiktok中点击了Greatapp宣传广告后的2-7天才首次打开该应用，AppsFlyer会将这些用户记录为自然量，而这时TikTok for Business则会将这些用户归因到自己的平台。

### 应用内事件归因

TikTok for Business和AppsFlyer的激活后事件（如应用内购）数据中也可能出现差异。下表列出了造成这些差异的常见原因，并提供了相应的建议，帮助您减少相关差异：

| 原因 | 说明 | AppsFlyer的建议 |
| --- | --- | --- |
| <span id="selfattribution"></span>**自归因** | TikTok会将激活和事件归因到TT广告，而AppsFlyer会将这些流量归因到促成相关转化的获客渠道。这时，在AppsFlyer的归因结果中，TikTok会显示为助攻渠道。 | 您可以结合TikTok获得归因的转化数据与TikTok作为助攻的转化数据一起查看，以减少数据差异。 |
| <span id="unmapped-events"></span>**未映射的事件** | AppsFlyer通过SDK获取事件信息，如果您未将相关事件映射到TikTok for Business，则AF不会向其发送这些事件。 | 请确保将所有代表用户质量的应用内事件都<Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-advanced-srn-integration-setup#应用内事件回传">映射到TikTok for Business</Anchor>。 |
| <span id="unsent-revenue"></span>**未发送的收入** | AppsFlyer通过SDK获取收入信息，如果您未选择发送收入，则AF不会将其发送给TikTok for Business。 | 配置<Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-advanced-srn-integration-setup#应用内事件回传">TikTok for Business的渠道映射事件</Anchor>时，请务必选择发送收入。 |
| <span id="missing-event-values-on-tiktok"></span>**TikTok for Business侧缺失事件值** | 如果参数和值的结构正确，AppsFlyer就会将其作为映射事件的一部分发送给TikTok for Business。 | 请按照<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure">AppsFlyer推荐的结构</Anchor>配置您的SDK应用内事件，确保完整映射TikTok for Business事件值。 |

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01HFXTVVZNJQJFAAR1F3HW1D5M=%E9%80%9F%E8%A7%88 differences-in-attribution-models=%E5%BD%92%E5%9B%A0%E6%A8%A1%E5%9E%8B%E7%9A%84%E5%B7%AE%E5%BC%82 h_01HFXTVVZN79JX9E5PTXMPB8BS=%E5%BD%92%E5%9B%A0%E6%A8%A1%E5%9E%8B%E7%9A%84%E5%B7%AE%E5%BC%82 differences-in-installs=%E6%BF%80%E6%B4%BB%E6%95%B0%E6%8D%AE%E7%9A%84%E5%B7%AE%E5%BC%82 h_01HFXTVVZNDQKNW85BBWR0PE2Z=%E6%BF%80%E6%B4%BB%E6%95%B0%E6%8D%AE%E7%9A%84%E5%B7%AE%E5%BC%82 reengagement-campaigns=%E5%86%8D%E4%BA%92%E5%8A%A8%E5%B9%BF%E5%91%8A h_01HFXTVVZNA1R59KCA41H2YSBJ=%E5%86%8D%E4%BA%92%E5%8A%A8%E5%B9%BF%E5%91%8A rejected-installs-when-using-validation-rules-and-protect360=%E4%BD%BF%E7%94%A8%E9%AA%8C%E8%AF%81%E8%A7%84%E5%88%99%E5%92%8Cprotect360%E6%97%B6%E8%A2%AB%E6%8B%A6%E6%88%AA%E7%9A%84%E6%BF%80%E6%B4%BB h_01HFXTVVZNJVFHE0W5DTP5PDCG=%E4%BD%BF%E7%94%A8%E9%AA%8C%E8%AF%81%E8%A7%84%E5%88%99%E5%92%8Cprotect360%E6%97%B6%E8%A2%AB%E6%8B%A6%E6%88%AA%E7%9A%84%E6%BF%80%E6%B4%BB 01H890CZSYCTQZCAYAZP9TCBBF=%E7%A4%BA%E4%BE%8B minimizing-discrepancies=%E5%87%8F%E5%B0%91%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82%E7%9A%84%E6%96%B9%E5%BC%8F h_01HFXTVVZNW9GZB8QYMR1KTNMN=%E5%87%8F%E5%B0%91%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82%E7%9A%84%E6%96%B9%E5%BC%8F clickthrough-and-viewthrough-attribution=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%92%8C%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01HFXTVVZNN45WY997DK9K8WA4=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%92%8C%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01HFRQMF6HTT84J4EDFXZMK7CP=%E7%A4%BA%E4%BE%8B-1 inapp-event-attribution=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%BD%92%E5%9B%A0 h_01HFXTVVZNG7TKQVY1229X594G=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%BD%92%E5%9B%A0" />
