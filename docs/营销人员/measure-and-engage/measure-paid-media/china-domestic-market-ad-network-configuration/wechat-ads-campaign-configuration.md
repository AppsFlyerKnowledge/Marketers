---
title: Amazon Ads的投放配置
metadata:
  keywords:
    - Wechat Ads
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
  created_at: '2017-06-18T06:41:29Z'
  edited_at: '2026-10-14T10:10:43Z'
  id: 115003044106
  locale: zh-cn
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/zh-cn/articles/115003044106
---
> **概要：**

<div id="setting-up-your-campaign-on-wechat" />

<div id="introduction" />

## 简介


2. * 激活
   * 注册
   * Purchase
   * 添加到购物车

<Image align="center" alt="wechat-configuration.png" src="https://files.readme.io/228ee10ef3dc113ae8af8de0f283b144206db1857f6d1f9169355f294155b8f8-50900431174033.png" />

<Image align="center" alt="wechat-keys.png" src="https://files.readme.io/cd7a2406ae9981eaabb4089813c9a1b847f0e6f750b9c0c0a0ac5e726dfe44be-50900431177361.png" />



<span id="setting-up-wechat-on-appsflyer"></span><span id="setting-up-wechat-campaign-as-an-agency"></span>请先进入**Partner Marketplace平台**搜索该渠道，然后前往<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations">活跃对接</Anchor>页面完成其设置操作。

> 📘 **注意**
>
> 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系相关渠道</Anchor>并在其平台上开设账户。

**请按以下步骤激活对接：**

1. 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**， 界面会跳转到对接设置页。
4. 在**渠道对接**选项卡中，打开**启用该渠道**开关。  
   **请注意：在您与该渠道合作期间，请确保该开关总是处于打开（即**启用/strong>）状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

下文分小节介绍了各部分的配置信息。

如需进一步了合作伙伴配置页面中各选项卡的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">此文档</Anchor>。

> 👍 **提示**
>
> * 对接页面中的<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#d-general-settings">通用设置</Anchor>是广告主**必须**为所有合作渠道都配置的内容。
> * 其余步骤都是描述性的或是**可选的**

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

下文说明了对接选项卡中所包含各部分内容。

<div id="activate-partner" />

### 启用渠道

**第一次访问**时，需要打开***激活合作伙伴***开关以开启对接选项卡内的配置参数。只要仍与该合作伙伴合作，这个开关必须为ON。   
有关渠道激活的详细说明请参见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。

<div id="note" />

> 📘 **注意**
>
> 作为“全安装”网络，Liftoff希望获取所有渠道（包括自然渠道）新增安装的数据回传。

<div id="general-settings" />

### 通用设置

**合作伙伴 ID**

<Image align="center" alt="wechat-integration-general-settings.png" src="https://files.readme.io/f1e0675a26116b628629b07616a7b9b86e8413ee36d7504f415207cb1590cb82-50900431178001.png" width="390px" />

<div id="default-postbacks" />

### 默认回传

AppsFlyer可以在用户安装和再互动后自动给AD\_NETWORK发送回传。您可以在这个板块中设置可用回传的**事件来源**。

<Image align="center" alt="wechat-default-postbacks.png" src="https://files.readme.io/1a2703b97a71bf82bcc77f5393459bc94b5443b83a4c4965d2624eda0e9f166f-50900402778129.png" />

若选择**仅该合作渠道**，则仅回传由ironSource带来的用户所完成的事件。  
若选择**所有媒体渠道，包括自然流量**：将所有用户的相关事件数据都上报给ironSource。

<div id="in-app-events-settings" />

### 应用内事件设置

在这里，您可以通过回传来描绘AppsFlyer的Twitter事件。

<Image align="center" alt="wechat_in_app_event_postbacks.png" src="https://files.readme.io/cd6234df4809b27044e361ad8835d4ae92100c491e0aa7c8f003336cdf2ad49d-50900431180561.png" />

4. 将应用内事件回传切换为 "打开"
5. 界定需要发送的SDK事件的来源。  
   选择**仅限来自该渠道的事件**，**仅**回传来自该渠道的用户所产生的事件。  
   选择**来自任何渠道或自然流量的事件**，可将所有用户的事件发送给该渠道。
6. 点击**添加事件**将 SDK 事件添加到列表中
7. 请配置以下参数：

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | AppsFlyer接收到的来自SDK或S2S事件的事件名称。  <br />**提示**：如果列表中没有您要找的事件，请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。 |
| **渠道映射事件** | Apple方面定义的每个事件的唯一名称或ID。  <br />从Apple获取相应的事件ID，并在文字段中进行设置。 |
| **回传内容** | **未勾选时**-AppsFlyer会把收入参数以外的所有详细应用内事件发送给合作伙伴，收入参数是另外包含在**af\_revenue**中的。  <br />**勾选时**-AppsFlyer会把包括收入值（如果某事件有收入的话）在内的所有参数发送给合作伙伴。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

可以在这个标签页创建要发送给Liftoff的归因链接，以归因Liftoff的广告系列、广告组或者广告。请注意, AppsFlyer 不会保存生成的合作伙伴归因链接。

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

<Image align="center" alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" />

只需在新参数框中输入, 即可将任何其他参数添加到归因链接中。更多详情, 请参阅 **<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">AppsFlyer 归因链接结构和参数</Anchor>。**

<div id="click-through-attribution" />

### 点击型归因

可以拖曳这个滑块来设置**点击到安装时间的最长时间**。只有发生在归因窗口期内的安装（首次启动）才有可能会被归因给Twitter。

**归因链接参数:** af\_click\_lookback

点击查看更多关于<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">点击归因窗口</Anchor>的信息。

<Image align="center" alt="" src="https://files.readme.io/86114a765dea30da658a676d1a7506c6ba385bdf8ebcf7241a1ce85f8c413077-50900402782737.png" />

<div id="click-attribution-link" />

### 点击归因链接

这就是包含了所有设置信息的归因链接。把这个归因链接发给Liftoff，当潜在客户点击相应广告时，该链接会被激活。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

广告收入配置不适用于该合作伙伴。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

</Accordion>

<div data-zendesk-anchors="introduction=%E7%AE%80%E4%BB%8B h_01HKW6Z36NGCWC0R6EQX49S34J=%E7%AE%80%E4%BB%8B setting-up-your-campaign-on-wechat=%E7%AE%80%E4%BB%8B h_01HKW6Z36NTSGCDQM553YMHHDH=%E7%AE%80%E4%BB%8B setting-up-wechat-on-appsflyer=setting-up-wechat-campaign-as-an-agency h_01HKW6Z36N8S8KSBNMR8A54RRN=setting-up-wechat-campaign-as-an-agency h_01HKW6Z36N3JSYEWJZH74M5WWJ=setting-up-wechat-campaign-as-an-agency h_01HKW6Z36NPKQGH2E3ZZJFVTHH=%E6%B3%A8%E6%84%8F h_01HKW6Z36NHHDW13B7K24D18H6=%E6%8F%90%E7%A4%BA h_01HKW6Z36PDGTT3EERY8F4VA79=integration-tab activate-partner=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01HKW6Z36P0EQF829NW3GDXKEN=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01HKW6Z36P806MHV6N3D1N9HW3=%E6%B3%A8%E6%84%8F-1 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01HKW6Z36P51EG4BW7WA3JGSKN=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HKW6Z36P3D4EPKC6ZZK94YVF=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-events-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01HKW6Z36PA90WEJMFH7BZMD72=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01HKW6Z36PRBT2X6F5BHYW06E1=attribution-link-tab attribution-link-parameters=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 h_01HKW6Z36P73H79MVFXQ29K2M6=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 clickthrough-attribution=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01HKW6Z36P95C7CT1J6YS5CQN8=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 click-attribution-link=%E7%82%B9%E5%87%BB%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HKW6Z36PEAPM8RAKB0RM9RES=%E7%82%B9%E5%87%BB%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HKW6Z36PEG0T9WQQRNY19EVG=cost-tab h_01HKW6Z36WE1SDC7KZHCMTPA0T=ad-revenue-tab h_01HKW6Z36W6QKR583X4Q4BNBZ4=permissions-tab" />
