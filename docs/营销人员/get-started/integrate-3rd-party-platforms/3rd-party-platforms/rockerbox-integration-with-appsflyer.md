---
title: AppsFlyer中的Xbox对接
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2020-11-23T14:55:00Z'
  edited_at: '2026-10-14T10:03:39Z'
  id: 360015760757
  locale: zh-cn
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/zh-cn/articles/360015760757
---
> **概要：**

<Image align="center" alt="rockerbox-logo_en-us.png" src="https://cdn.appsflyer.com/marketplace/static/logo/rockerbox.png" />

<div id="important" />

> 🚧 **重要提示！**
>
> 部分渠道限制第三方的数据共享。


**<span id="setting-up-rockerbox"></span>前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式**：从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**，界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开 （启用） 状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

下文说明了对接选项卡中所包含各部分内容。

<div id="activate-partner" />

### 启用渠道

详情请见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation#渠道对接的启用方式">渠道启用说明</Anchor>。

<div id="general-settings" />

### 通用设置

<div id="default-postbacks" />

### 默认回传

<div id="in-app-events-settings" />

### 应用内事件设置

<Image align="center" alt="rockerbox-in-app-events_en-us.png" src="https://files.readme.io/3fc74bb16d6a1222d1d244bbb1083ff247e3315d0fc7060e0ec3e8ad30a07233-360013891517.png" />

详情请见应用内事件回传说明文档。

请按以下步骤配置应用内事件回传：

2. 启用应用内事件回传。
3. 点击添加事件，将SDK事件添加到列表中。
5. * **不发送值与收入：** 仅发送事件本身，不发送事件值。
   * **含事件值不含收入值：** 发送除收入值以外的所有参数。
   * **发送值与收入：** 发送所有事件参数，包括收入值（若有）。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

</Accordion>

<div data-zendesk-anchors="h_01H9HWJW82HZ9FR31VHHRBZ3EM=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01H9HWJW83BKP8DSYTV6YGPHK7=setting-up-rockerbox h_01H9HWJW83WDGQKKMM942NPA1S=integration-tab activate-partner=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01H9HWJW83Z4NGT000091AHX0Z=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01H9HWJW832NQBPK2VS6TS1QK7=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9HWJW83CGMBADDBP7EJTR9N=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-events-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01H9HWJW84H4SDVRNZAG1D6N0D=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01H9HWJW84G6GXMBTGMHTDPM6R=attribution-link-tab h_01H9HWJW84BZNHN4DRKA33WCVK=cost-tab h_01H9HWJW848DRTKBF3AKR5KYC5=ad-revenue-tab h_01H9HWJW84NTZWKP2FP2WK4FZD=permissions-tab" />
