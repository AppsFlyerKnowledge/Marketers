---
title: Google Ads（AdWords）— 再互动
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T09:55:51Z'
  edited_at: '2026-10-14T10:13:39Z'
  id: 4417296925073
  locale: zh-cn
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/zh-cn/articles/4417296925073
---
> **概要：** 衡量Google Ads再营销广告系列

## Google Ads再营销广告系列

您可以使用AppsFlyer衡量**Google Ads App Campaigns for Engagement**（以吸引用户互动为目标的应用广告系列，简称ACE）的投放效果。  
在AppsFlyer中，此类广告系列称为<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销</Anchor>广告系列。 AppsFlyer支持再营销广告的成本、点击和展示数据的拉取。对接该项后，您可以查看和衡量在Google Ads上的广告支出，然后计算Google Ads广告系列的eCPI和ROI。

再营销广告的目标受众是过去安装过应用的用户。

* 如果再营销广告与已安装应用的用户发生互动。则称为**再互动** 。这些通常会需要深度链接用户。
* 未安装应用的用户与再营销广告互动后安装应用，记为一次**重装激活**（Re-install），或称**再归因**（Re-attribution）。

详情请见<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">Google Ads再营销广告支持文档</Anchor> 。

## 设置Google Ads再营销广告系列

在开始配置前，请先查看<Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">与其他Google Ads账户分享链接的指南文档</Anchor>，确保您的再营销广告能通过现有的Link ID正常监测到。

请按以下步骤衡量Google Ads再营销广告的效果：

<div id="enabling-retargeting-in-app-settings" />

<Accordion title="在应用配置中启用再营销">

启用任何媒体渠道的再营销广告系列，都需要在应用层级启用。如果这是您应用的第一个再营销广告系列，请执行以下操作：

1. 从AppsFlyer后台的侧边栏中选择**配置** > **应用配置**。
2. 滚动到页面最下方。
3. 打开**再互动归因**开关。

</Accordion>

<div id="enable-google-ads-retargeting-in-appsflyer" />

<Accordion title="在AppsFlyer中启用Google Ads的再营销衡量">

* 请按<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">配置说明</Anchor>中的第5点说明在AppsFlyer中完成Google Ads的配置。

</Accordion>

<div id="importing-session-start-conversions-in-google-ads" />

<Accordion title="在Google Ads中导入会话开始转化">

要**在Google Ads中**记录再互动广告系列的转化，您需要在Google Ads导入session\_start事件。

在AppsFlyer中为Google Ads开启再营销后，如果至少有一个用户打开该应用，则该事件会显示在Google Ads中。保险起见，打开再营销开关之后，您可以自己打开应用。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">Google Ads中的转化导入说明</Anchor>。

> 📘 **注意事项**
>
> 与所有其他事件不同，即使您未从AppsFlyer将session\_start导入Google Ads，Google Ads API也可以认领session\_start。
> 但是，在那种情况下，这些转换在AppsFlyer仍会被归因。这**会在AppsFlyer和Google Ads中的数据之间造成巨大的差异** 。此外，这会**阻止Google Ads优化**您的广告系列用户定向。

</Accordion>

<div id="setting-up-deep-linking-for-app-campaigns-for-engagement" />

<Accordion title="为再营销广告系列配置深度链接">

Google 再营销广告要求<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6310747?hl=en&ref_topic=3121770">再互动广告系列使用深度链接</Anchor> 。由于域名不匹配，无法使用第三方深度链接解决方案。这包括AppsFlyer的OneLink。使用您自己的<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6046977?hl=en">内部App Links、Universal Links 或者自定义URI Schemes</Anchor> 。

深度链接中无需添加is\_retargeting=true和pid=adwords等其他参数。

</Accordion>

## 动态再营销和购物广告

AppsFlyer支持针对应用和购物广告系列的动态再营销，这类广告在AppsFlyer平台中与再互动广告无异。

* 要了解有关应用动态再营销的信息，请点击<Anchor target="_blank" href="https://support.google.com/adwords/answer/7538938">这里</Anchor>。
* 要了解购物广告系列，请点击<Anchor target="_blank" href="https://support.google.com/google-ads/answer/2454022?hl=en">这里</Anchor>。
* 要了解有关Google再营销广告的更多信息，请点击<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">这里</Anchor> 。

### 对非应用程序活动（需求生成和搜索引擎营销）的支持

AppsFlyer 仅支持 Google 非应用程序活动的重新参与测量，包括：

* 需求生成活动
* 搜索引擎营销（SEM）活动

这些活动与 AppsFlyer **开箱即用**，无需：

* parallel\_tracking.png
* 智能脚本实施

**局限性：**

* 来自需求生成或 SEM 活动的 **安装** 在任何平台上都不被归因。

退出 Google 目前不支持选择加入或退出非应用程序活动的测量（与 TikTok 或 Meta 等平台不同）。

> 📄 **相关文档**
>
> * 请参考<Anchor target="_blank" href="/marketers/zh/docs/get-skan-postback-data-from-google-ads">Google Ads与AppsFlyer的SKAN互动设置</Anchor>，了解iOS 14的相关注意事项。

<div data-zendesk-anchors="google-ads-retargeting-campaigns=google-ads%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 h_01HDP34BWZFG09ABN5NQB6EY32=google-ads%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 setting-up-google-ads-app-campaigns-for-engagement=%E8%AE%BE%E7%BD%AEgoogle-ads%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 h_01HDP34BWZXXNZDE0SR4MXBC9V=%E8%AE%BE%E7%BD%AEgoogle-ads%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 h_01HDP34BWZNHY08NDX6YSE9CXR=enabling-retargeting-in-app-settings h_01HDP34BWZNNNT4HRMXJB2X3S2=enable-google-ads-retargeting-in-appsflyer h_01HDP34BWZ8MGJKEZFC77VYWNG=importing-session-start-conversions-in-google-ads h_01HDP34BWZHWVKKNB7CEHY73R0=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01HDP34BWZ64XG2G0PTH6XCCMG=setting-up-deep-linking-for-app-campaigns-for-engagement dynamic-remarketing-and-shopping-campaigns=%E5%8A%A8%E6%80%81%E5%86%8D%E8%90%A5%E9%94%80%E5%92%8C%E8%B4%AD%E7%89%A9%E5%B9%BF%E5%91%8A h_01HDP34BWZ990SD3B1C5DZRESK=%E5%8A%A8%E6%80%81%E5%86%8D%E8%90%A5%E9%94%80%E5%92%8C%E8%B4%AD%E7%89%A9%E5%B9%BF%E5%91%8A h_google-non-app-campaign-support=%E5%AF%B9%E9%9D%9E%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F%E6%B4%BB%E5%8A%A8%E9%9C%80%E6%B1%82%E7%94%9F%E6%88%90%E5%92%8C%E6%90%9C%E7%B4%A2%E5%BC%95%E6%93%8E%E8%90%A5%E9%94%80%E7%9A%84%E6%94%AF%E6%8C%81 support-for-nonapp-campaigns-demand-gen-and-sem=%E5%AF%B9%E9%9D%9E%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F%E6%B4%BB%E5%8A%A8%E9%9C%80%E6%B1%82%E7%94%9F%E6%88%90%E5%92%8C%E6%90%9C%E7%B4%A2%E5%BC%95%E6%93%8E%E8%90%A5%E9%94%80%E7%9A%84%E6%94%AF%E6%8C%81 h_01HDP2XBSEJVQ5G0MD0V5R05CM=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
