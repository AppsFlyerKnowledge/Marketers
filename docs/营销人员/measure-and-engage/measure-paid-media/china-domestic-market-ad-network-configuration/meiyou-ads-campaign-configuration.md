---
title: Amazon Ads的投放配置
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - China
    - meiyou
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-01T03:26:18Z'
  edited_at: '2026-10-14T10:08:59Z'
  id: 360002141597
  locale: zh-cn
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/zh-cn/articles/360002141597
---
> **概要：**


<span id="setting-up-meiyou-ads"></span>请先进入**Partner Marketplace平台**搜索该渠道，然后前往<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations">活跃对接</Anchor>页面完成其设置操作。

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

<div id="activate-partner" />

### 渠道激活

**第一次访问**时，需要打开***激活合作伙伴***开关以开启对接选项卡内的配置参数。只要仍与该合作伙伴合作，这个开关必须为ON。   
有关渠道激活的详细说明请参见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。

<div id="general-settings" />

### 通用设置

![mceclip3.png](https://files.readme.io/451f74c0a6b45926f89a3f2a5d04b6ef240184c4862b576bee0d0a2b7a832f30-50900150950417.png)

**启用展示归因**

如果希望获取该AD\_NETWORK的浏览型归因，要把这里设置为开启。您可以使用归因链接选项卡中对应的滑块来调整浏览回溯窗口。

<div id="default-postbacks" />

### 默认回传

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="548px" />

<div id="in-app-events-settings" />

### 应用内事件设置

可以在这里通过回传把AppsFlyer事件映射给AD\_NETWORK。

**键**

<Image alt="mceclip1.png" src="https://files.readme.io/32b1c68531c7aa752514f9b1c13c4438cddef2e93d2ca04ab287d46acecda15e-50900150956305.png" width="661px" />

2. 将应用内事件回传切换为 "打开"
3. 点击**添加事件**将 SDK 事件添加到列表中
4. 填写以下参数:

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | AppsFlyer接收到的来自SDK或S2S事件的事件名称。  <br />**提示**：如果列表中没有您要找的事件，请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。 |
| **渠道映射事件** | 从Apple获取相应的事件ID，并在文字段中进行设置。 |
| **回传内容** | **未勾选时**-AppsFlyer会把收入参数以外的所有详细应用内事件发送给合作伙伴，收入参数是另外包含在**af\_revenue**中的。  <br />**勾选时**-AppsFlyer会把包括收入值（如果某事件有收入的话）在内的所有参数发送给合作伙伴。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接页面">

请注意, AppsFlyer 不会保存生成的合作伙伴归因链接。

![mceclip2.png](https://files.readme.io/3a9b086aa1a76dc64289a512eec56885d108dce5c2778580fc0b2962f00c8a95-50900150957201.png)

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

![attribution-link-parameters.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

只需在新参数框中输入, 即可将任何其他参数添加到归因链接中。更多详情, 请参阅 **<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">AppsFlyer 归因链接结构和参数</Anchor>。**

<div id="click-through-attribution" />

### 点击型归因

可以拖曳这个滑块来设置**点击到安装时间的最长时间**。只有发生在归因窗口期内的安装（首次启动）才有可能会被归因给Twitter。

**归因链接参数:** af\_click\_lookback

点击查看更多关于<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">点击归因窗口</Anchor>的信息。

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

<div id="click-attribution-link" />

### 点击归因链接

这就是包含了所有设置信息的归因链接。将其发送给AD\_NETWORK\_NAME，以便在潜在客户点击相应广告时激活。

<div id="view-through-attribution-lookback-window" />

### 浏览型归因窗口期

可以拖曳这个滑块来设置**最大展示至安装时间**。用户浏览Snapchat广告后，只有在该窗口期内激活（首次打开）应用时（且期间没有点击其他相关广告），AppsFlyer才会将该激活归因到Snapchat。

您可以将这个值自定义为1-23小时或1-7天。

**归因链接参数:** af\_viewthrough\_lookback

更多关于<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">展示归因的信息在这里</Anchor>。

[![](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)

<div id="impressions-attribution-link" />

### 展示归因链接

展示归因链接里含有与点击归因链接相似的归因数据（除了窗口期不同之外）。将该链接发送给合作伙伴, 以便在相应广告被观看1秒或更长时间时激活该链接。


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

![rtb_house-permissions-new.png](https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png)

<div id="ad-network-permissions" />

### 广告平台权限

您可以使用权限开关向广告平台授权，让其处理与自己相关的配置：

* ***允许配置对接***-允许合作伙伴设置对接选项卡 (应用内事件回传除外)
* ***允许配置应用内事件回传***-允许合作伙伴在集成选项卡上设置映射给其自身的应用内事件回传
* ***允许访问留存报告***-仅允许访问该合作伙伴自己的留存数据
* ***允许访问Protect360控制面板***-仅访问该合作伙伴自己的Protect360数据，前提是广告主有开通该功能

如需进一步了解广告平台权限的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">此文档</Anchor>。

</Accordion>

<div data-zendesk-anchors="h_01HKW6VQGVGFA45SQK1KANQ10Q=setting-up-meiyou-ads h_01HKW6VQGV5CD2FD0PSEBMQQ6D=%E6%B3%A8%E6%84%8F h_01HKW6VQGVJ07SMFPZVS0VQ3D2=%E6%8F%90%E7%A4%BA h_01HKW6VQGV71MM2T401TGHEMHA=integration-tab activate-partner=%E6%B8%A0%E9%81%93%E6%BF%80%E6%B4%BB h_01HKW6VQGV3HG1ZTR41BD43ZTC=%E6%B8%A0%E9%81%93%E6%BF%80%E6%B4%BB general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01HKW6VQGVNG13KARWZBSD59KX=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HKW6VQGV32R49RCEKCYK1G18=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-events-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01HKW6VQGVHCVWR4KDHTH24D17=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01HKW6VQGVV9X64XHW48VGW6E6=attribution-link-tab attribution-link-parameters=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 h_01HKW6VQGVZJ36JVCZ3SW7Z3YD=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 clickthrough-attribution=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01HKW6VQGWZQQZWT476QT496YF=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 click-attribution-link=%E7%82%B9%E5%87%BB%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HKW6VQGWG7BH11EK5HQACKVY=%E7%82%B9%E5%87%BB%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 viewthrough-attribution-lookback-window=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F h_01HKW6VQGWFJEJYD9KG8BH9EX0=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F impressions-attribution-link=%E5%B1%95%E7%A4%BA%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HKW6VQGWXCB2W13TM4WAGWE1=%E5%B1%95%E7%A4%BA%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HKW6VQGWY3AFFTN0DP8BCV7S=cost-tab h_01HKW6VQGWARB4409DWKVDY45W=ad-revenue-tab h_01HKW6VQGW20F6TTCBPGDH57JW=permissions-tab ad-network-permissions=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90 h_01HKW6VQGWXBME473RXA5K1217=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90" />
