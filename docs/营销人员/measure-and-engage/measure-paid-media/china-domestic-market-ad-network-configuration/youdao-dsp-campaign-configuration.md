---
title: Amazon DSP投放配置
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - youdao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-07-30T09:13:02Z'
  edited_at: '2026-10-14T10:13:01Z'
  id: 360002133558
  locale: zh-cn
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/zh-cn/articles/360002133558
---
> **概要：**


<span id="setting-up-youdao-dsp"></span>请先进入**Partner Marketplace平台**搜索该渠道，然后前往<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations">活跃对接</Anchor>页面完成其设置操作。

> 📘 **注意**
>
> 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系相关渠道</Anchor>并在其平台上开设账户。

**请按以下步骤激活对接：**

1. 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**，
4. 界面会跳转到对接设置页。
5. 在**对接**选项卡中，打开**启用该渠道**开关。

下文分小节介绍了各部分的配置信息。

如需进一步了合作伙伴配置页面中各选项卡的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">此文档</Anchor>。

> 👍 **提示**
>
> * 对接页面中的<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#d-general-settings">通用设置</Anchor>是广告主**必须**为所有合作渠道都配置的内容。
> * 其余步骤都是描述性的或是**可选的**

<div id="integration-tab" />

<Accordion title="对接页面">

与AD\_NETWORK的对接仅支持默认回传中的安装事件。

<div id="activate-partner" />

### 渠道激活

**第一次访问**时，需要打开***激活合作伙伴***开关以开启对接选项卡内的配置参数。只要仍与该合作伙伴合作，这个开关必须为ON。   
有关渠道激活的详细说明请参见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。

<div id="default-postbacks" />

### 默认回传

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="583px" />

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接页面">

请注意, AppsFlyer 不会保存生成的合作伙伴归因链接。

该选项卡可分成几个不同部分：

<div id="attribution-link-parameters" />

### 归因链接参数

在本节中, 选择要添加到归因链接中的参数。

在归因链接里添加更多参数可以便于日后进行进一步的深入分析。归因链接中预定义的参数，可以通过添加参数和定义新值的方式进行编辑。

* **Campaign** - 添加该参数以比较AD\_NETWORK\_NAME的不同广告活动。  
  **归因链接参数:** c
* **广告集**-设置广告集名称以比较AD\_NETWORK\_NAME某具体广告系列活动的不同广告集之间的表现。  
  **归因链接参数:** af\_adset
* **广告名称**-设置广告名称可以比较该自有媒体渠道某具体广告集中不同广告的表现。  
  **归因链接参数**: af\_ad
* **Site ID** 和**Sub Site ID** - 设置子渠道ID参数可以把安装归因给具体的发布平台。如果有许多发布平台, 我们建议限制所使用的site ID数量, 并使用sub site ID 参数, 以避免超出site ID 限制。  
  **归因链接参数:** af\_siteid and af\_sub\_siteid
* **订阅者参数**-使用5个订阅者参数中的任何一个来插入有用的值。请注意，这些参数会被解析并出现在原始数据报告中，便于汇总或筛选数据。  
  **归因链接参数:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" width="511px" />

只需在新参数框中输入, 即可将任何其他参数添加到归因链接中。更多详情, 请参阅 **<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">AppsFlyer 归因链接结构和参数</Anchor>。**

<div id="click-through-attribution" />

### 点击型归因

可以拖曳这个滑块来设置**点击到安装时间的最长时间**。只有发生在归因窗口期内的安装（首次启动）才有可能会被归因给Twitter。

**归因链接参数:** af\_click\_lookback

点击查看更多关于<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">点击归因窗口</Anchor>的信息。

<Image align="center" alt="netease-click-through.png" src="https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png" />

<div id="attribution-link" />

### 归因链接

这就是包含了所有设置信息的归因链接。将其发送给AD\_NETWORK\_NAME，以便在潜在客户点击相应广告时激活。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

该合作伙伴不支持成本数据对接。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入页面">

该渠道不支持广告收入对接。

</Accordion>

<div id="permissions-tab" />

<Accordion title="权限页面">

您可以在这个选项卡中为Twitter开放各种权限。请注意：即使您停用了ironSource归因，仍可以使用授权选项卡向ironSource开放各类权限。

<Image align="center" alt="rtb_house-permissions-new.png" src="https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png" />

<div id="ad-network-permissions" />

### 广告平台权限

您可以使用权限开关向广告平台授权，让其处理与自己相关的配置：

* ***允许配置对接***-允许合作伙伴设置对接选项卡 (应用内事件回传除外)
* ***允许配置应用内事件回传***-允许合作伙伴在集成选项卡上设置映射给其自身的应用内事件回传
* ***允许访问留存报告***-仅允许访问该合作伙伴自己的留存数据
* ***允许访问Protect360控制面板***-仅访问该合作伙伴自己的Protect360数据，前提是广告主有开通该功能

如需进一步了解广告平台权限的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">此文档</Anchor>。

</Accordion>

<div data-zendesk-anchors="h_01HKW6ZN60XK9DSCEVQ216P1G9=setting-up-youdao-dsp h_01HKW6ZN60DM5PFX946S76DVGW=%E6%B3%A8%E6%84%8F h_01HKW6ZN60J946AYXMKJPSW91T=%E6%8F%90%E7%A4%BA h_01HKW6ZN60TAMV09SSD8JM29GS=integration-tab activate-partner=%E6%B8%A0%E9%81%93%E6%BF%80%E6%B4%BB h_01HKW6ZN60PGGR7RDWKP5S2HJ9=%E6%B8%A0%E9%81%93%E6%BF%80%E6%B4%BB default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HKW6ZN61B4KY1BEA76MYX4BC=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HKW6ZN61WPTBRKNTG3BXHYRP=attribution-link-tab attribution-link-parameters=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 h_01HKW6ZN6172ASA82J51CM13NW=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 clickthrough-attribution=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01HKW6ZN614J1A71A9B38QRN7E=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 attribution-link=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HKW6ZN61EZP9ES6GK09C68DH=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HKW6ZN61AWQFR8VD489ZEC6J=cost-tab h_01HKW6ZN68J89ZY3QCJZARYSTP=ad-revenue-tab h_01HKW6ZN68EQS2MB9MK7TV7TB1=permissions-tab ad-network-permissions=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90 h_01HKW6ZN68HZECRSMR3GPTAG4R=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90" />
