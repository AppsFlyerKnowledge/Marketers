---
title: Unity Ads投放配置
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
  created_at: '2019-08-29T08:24:47Z'
  edited_at: '2026-10-14T10:13:33Z'
  id: 360002358897
  locale: zh-cn
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/zh-cn/articles/360002358897
---
>


<span id="setting-up-vivo-ads"></span>请先进入**Partner Marketplace平台**搜索该渠道，然后前往<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations">活跃对接</Anchor>页面完成其设置操作。

> 📘 **注意**
>
> 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系相关渠道</Anchor>并在其平台上开设账户。

**请按以下步骤激活对接：**

1. 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**，
4. 界面会跳转到对接设置页。
5. 在**对接**选项卡中，打开**启用该渠道**开关。

点击以下内容阅读有关选项卡设置的信息。

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

<div id="enable-view-through-attribution" />

### 启用展示归因

如果希望获取该AD\_NETWORK的浏览型归因，要把这里设置为开启。您可以使用归因链接选项卡中对应的滑块来调整浏览回溯窗口。

<div id="default-postbacks" />

### 默认回传

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="456px" />

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接页面">

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

<Image alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" width="479px" />

只需在新参数框中输入, 即可将任何其他参数添加到归因链接中。更多详情, 请参阅 **<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">AppsFlyer 归因链接结构和参数</Anchor>。**

<div id="click-through-attribution" />

### 点击型归因

可以拖曳这个滑块来设置**点击到安装时间的最长时间**。只有发生在归因窗口期内的安装（首次启动）才有可能会被归因给Twitter。

**归因链接参数:** af\_click\_lookback

点击查看更多关于<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">点击归因窗口</Anchor>的信息。

![viewthrough_en-us.png](https://files.readme.io/47ff5d900d8edfdc30f2d2c0588f5e06fc3b44e71aeab630d1b5df2ea8c2db47-50900334036625.png)

<div id="attribution-link" />

### 归因链接

这就是包含了所有设置信息的归因链接。把这个归因链接发给Liftoff，当潜在客户点击相应广告时，该链接会被激活。

<div id="view-through-attribution-lookback-window" />

### 浏览型归因窗口期

可以拖曳这个滑块来设置**最大展示至安装时间**。界定用户从浏览广告到激活（即下载后首次启动）应用之间的最长时限（期间无广告点击），仅在该窗口期内发生的激活才会被归因到Twitter。

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

</Accordion>

<div data-zendesk-anchors="h_01HKW6Y9CJED5RV97WWSYQNBDG=setting-up-vivo-ads h_01HKW6Y9CJ747R6F84H6XEVHRC=%E6%B3%A8%E6%84%8F h_01HKW6Y9CJXAR3YQ1RM3VTE0CF=%E6%8F%90%E7%A4%BA h_01HKW6Y9CJZ1YPFBQH1W0QV21G=integration-tab activate-partner=%E6%B8%A0%E9%81%93%E6%BF%80%E6%B4%BB h_01HKW6Y9CJC0EWH84B7GW29VJM=%E6%B8%A0%E9%81%93%E6%BF%80%E6%B4%BB enable-viewthrough-attribution=%E5%90%AF%E7%94%A8%E5%B1%95%E7%A4%BA%E5%BD%92%E5%9B%A0 h_01HKW6Y9CJ8PNMN2ANR3E3WK1H=%E5%90%AF%E7%94%A8%E5%B1%95%E7%A4%BA%E5%BD%92%E5%9B%A0 default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HKW6Y9CJDY5XHWXN3CK0YGK8=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HKW6Y9CKQXSWXNK1VEXQFEPA=attribution-link-tab attribution-link-parameters=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 h_01HKW6Y9CKSHBWNBH0RY3X3RR3=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E5%8F%82%E6%95%B0 clickthrough-attribution=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01HKW6Y9CKE86Z1Z4QZH0M665T=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 attribution-link=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HKW6Y9CKNB685ZYXB8RM1P41=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 viewthrough-attribution-lookback-window=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F h_01HKW6Y9CKV48NRWSXD0ZKY3M0=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F impressions-attribution-link=%E5%B1%95%E7%A4%BA%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HKW6Y9CKV6XY1BCD9XX42XZ7=%E5%B1%95%E7%A4%BA%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HKW6Y9CKZ0TMJ1F3H8X2W733=cost-tab h_01HKW6Y9CKB65QFDTKX4AW3P23=ad-revenue-tab h_01HKW6Y9CKV3KJ5X5ECEF2JJ8N=permissions-tab" />
