---
title: Amazon Ads与AppsFlyer之间的归因差异
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-09-18T04:28:03Z'
  edited_at: '2026-10-14T10:09:18Z'
  id: 28461159218449
  locale: zh-cn
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/zh-cn/articles/28461159218449
---
> **概要：** 本文重点解释了Amazon Ads和AppsFlyer之间的归因模式差异。

## 速览

Amazon Ads和AppsFlyer在移动端获客营销生态体系中都扮演着重要的角色，而双方都使用自己特有的归因模型，因此两者的面板之间可能会有一些数据差异。虽然我们一直与Amazon Ads保持紧密的合作，以尽可能地减少这样的差异，但广告主仍需了解可能会造成数据差异的各种因素。

## 归因模型的差异

下表列出了可能会导致Amazon Ads与AppsFlyer面板之间产生数据差异的原因：

| 原因 | Amazon Ads Manager | AppsFlyer |
| --- | --- | --- |
| <span id="clickthrough-attribution-lookback-window"></span>浏览型归因窗口期 | 默认窗口期为14天。此窗口期目前不可自行调整。 | 默认窗口期为7天。该窗口期的可用配置范围为1-30天。请确保您在AppsFlyer中设置的窗口期与Amazon Ads的归因窗口保持一致。 |
| <span id="viewthrough-attribution-lookback-window"></span>浏览型归因窗口期 | 默认窗口期为14天。此窗口期目前不可自行调整。 | 默认窗口期为1天。该窗口期的可用配置范围为1-30天。请确保您在AppsFlyer中设置的窗口期与Amazon Ads的归因窗口保持一致。 |
| <span id="multichannel-source-attribution"></span>多源归因 | Amazon Ads无视其他渠道的广告互动，将激活归因给自己。 | AppsFlyer使用末次点击归因原则。  <br />进一步了解<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">AppsFlyer的归因模型</Anchor>。 |
| <span id="different-timezones"></span>时区不同 | 日期范围旁的Amazon Ads时区无法调整，这是您在创建广告账号时设置的时区。 | AppsFlyer中默认的应用时区为UTC+0。如需对齐AppsFlyer和Amazon Ads的时区，请在AF后台的<Anchor target="_blank" href="/marketers/zh/docs/app-settings#localization-time-zone">应用配置页面</Anchor>中更改相关应用的时区设置。 |

## 减少数据差异的方式

虽然两个平台的归因模式有所差别，但您仍可在部分情况下减少数据差异。

### 点击型和浏览型归因

AppsFlyer支持点击型归因和浏览型归因。为了减少Amazon Ads和AppsFlyer之间的数据差异，请确保您在AF中设置的点击和展示回溯窗口与Amazon Ads中对应的窗口期保持一致。

> 📄 **示例**
>
> 假设您有一个名为com.greatapp的应用，并在AppsFlyer后台将其Amazon Ads点击回溯窗口期设为1天，而在Amazon Ads中使用了7天的默认窗口7天。如果用户在Amazon Ads中点击了Greatapp宣传广告后的2-7天才首次打开该应用，AppsFlyer会将这些用户记录为自然量，而这时Amazon Ads则会将这些用户归因到自己的平台。

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01J81NN4J4A1KWBXJQD9SM2AWH=%E9%80%9F%E8%A7%88 differences-in-attribution-models=%E5%BD%92%E5%9B%A0%E6%A8%A1%E5%9E%8B%E7%9A%84%E5%B7%AE%E5%BC%82 h_01J81NN4J4WSJBFHBARKTQ9JG5=%E5%BD%92%E5%9B%A0%E6%A8%A1%E5%9E%8B%E7%9A%84%E5%B7%AE%E5%BC%82 reducing-discrepancies=%E5%87%8F%E5%B0%91%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82%E7%9A%84%E6%96%B9%E5%BC%8F h_01J81NN4J4EJQH47YJF0H5M97G=%E5%87%8F%E5%B0%91%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82%E7%9A%84%E6%96%B9%E5%BC%8F clickthrough-and-viewthrough-attribution=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%92%8C%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01J81NN4J4X6V3XWRZWNDJ14PV=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%92%8C%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01J81NN4J4NC0SK4QRTQZRJS0F=%E7%A4%BA%E4%BE%8B" />
