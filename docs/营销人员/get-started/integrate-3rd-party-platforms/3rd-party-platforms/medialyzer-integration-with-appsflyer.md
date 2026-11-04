---
title: AppsFlyer中的Medialyzer对接
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-05-01T11:43:34Z'
  edited_at: '2026-10-14T10:13:09Z'
  id: 14963611180689
  locale: zh-cn
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/zh-cn/articles/14963611180689
---
> **概要：**

<div id="important" />

> 🚧 **重要提示！**
>
> 部分渠道限制第三方的数据共享。

<div id="setting-up-medialyzer" />

## Medialyzer渠道设置

**前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式**：从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**，界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开 （启用） 状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

此时您仅可使用配置窗口中的**对接**选项卡。

如需进一步了合作伙伴配置页面中各选项卡的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">此文档</Anchor>。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

<div id="activate-partner" />

#### 启用渠道

请在首次访问该页面时打开**启用该渠道**开关，然后就可以设置对接了。在您与Medialyzer合作期间，请确保该开关总是处于打开状态。详情请见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">渠道启用说明</Anchor>。

<div id="advanced-privacy" />

#### 高级隐私保护

iOS应用的面板中会显示<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">高级隐私</Anchor>开关，此开关打开时可限制渠道共享用户标识符。请注意：如果您在应用配置中打开了<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">汇总层级的高级隐私</Anchor>开关，AppsFlyer会默认开启并锁定**高级隐私（适用于iOS 14.5及以上版本）**。

<div id="default-postbacks" />

#### 默认回传

用户激活应用后，AppsFlyer会向Medialyzer发送默认回传。详情请参考回传设置说明。

* **关闭开关**：关闭：不向Medialyzer发送激活回传。
* **所有媒体渠道，包括自然流量**：

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

<div id="in-app-event-postbacks" />

#### 应用内事件回传

这部分选项用于设置AppsFlyer事件与渠道之间的映射与回传。

[![app_event_postbacks.JPG](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)

1. 打开**应用内事件回传**开关。
2. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。
3. 请配置以下参数： 

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。<br />**提示**：如果下拉菜单中没有您要查看的事件：<ul><li>请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。</li><li>在**AppsFlyer事件**中输入该事件的名称，然后点击**创建自定义事件**。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">自定义事件映射</Anchor>。</li></ul> |
| **渠道映射事件** | 您可以根据Medialyzer中的定义，输入各个事件对应的名称或ID，也可以按原样发送事件，不映射事件名称。 |
| **事件来源** | 选择**所有媒体渠道，包括自然流量**：发送来自所有渠道以及自然流量的激活回传。 |
| **回传内容** | <ul><li>**不发送值与收入：** 仅发送不带任何参数的事件本身（即没有值或收入）。</li><li>**仅发送值：** 发送**除**收入以外的所有参数。</li><li>**发送值与收入**：发送所有事件参数，**包括**收入（若有）。</li></ul> |

4. 点击**保存对接** 。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

归因链接不适用于Medialyzer。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

Medialyzer的渠道对接不支持成本数据。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

Medialyzer的渠道对接不支持广告收入数据。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

权限设置不适用于Medialyzer。

</Accordion>

<div data-zendesk-anchors="h_01H9FKEAV2225HM5CQAGWS2K99=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA setting-up-spoteffects=medialyzer%E6%B8%A0%E9%81%93%E8%AE%BE%E7%BD%AE h_01H9FKEAV37AT3VTZ5WV1YMWC2=medialyzer%E6%B8%A0%E9%81%93%E8%AE%BE%E7%BD%AE h_01H9FKEAV3YQY124TSZ5Q7VHAY=integration-tab activate-partner=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01H9FKEAV3DW2A6RQ1NS44FT5F=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 advanced-privacy=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 h_01H9FKEAV3T3YCPBYW70QVF540=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9FKEAV3Z1Y09P6E18J8AVX2=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01H9FKEAV3GG6X17X3NCCSWJAS=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01H9FKEAV3ZEF1AHRTQGEGYFSJ=attribution-link-tab h_01H9FKEAV3ERXQ98BJGKBQRGP2=cost-tab h_01H9FKEAV32MB7M2Q1ASDAE6RM=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab" />
