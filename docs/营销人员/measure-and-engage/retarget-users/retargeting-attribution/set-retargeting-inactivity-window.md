---
title: 再营销中的用户不活跃时长阈值
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2020-05-31T13:56:38Z'
  edited_at: '2026-10-14T10:14:23Z'
  id: 360009305817
  locale: zh-cn
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/zh-cn/articles/360009305817
---
> **概要：** 向不活跃的用户定向投放再营销广告，可有效提升增量效果。您可以分渠道设置用户的不活跃窗口期，精准衡量再营销广告的效果。
>
> ![](https://files.readme.io/c96cda4d05b2724c6f8b30b5ec19f218eb763bd6d9cbf1cb842e0b57ad0902db-51911937664913.png)

## 不活跃时长

广告主可以向不活跃的用户定向投放再营销广告，唤醒沉睡用户。这些广告的转化率通常较高，且能带来可观的ROAS。但如果您未在此类广告中排除活跃用户，其投放效果就会低于正常水平。为了提升再营销广告的增量效果，建议您配置一个**不活跃时长阈值**，排除掉活跃用户。

设置该阈值后，即可将活跃用户排除在再营销归因流程之外。举例来说，假设您将不活跃时长阈值设置为3天，则过去0-3天内的活跃用户不会被纳入归因，而超过4天不活跃的用户会得到归因。不活跃时长阈值同时对再归因和再互动场景生效。在再归因场景中，相关用户的最近一次活跃迹象通过卸载前的最后一次应用打开（session）来体现。

**不活跃用户的归因原理**

* **纳入归因的流量：** 在指定的不活跃时长阈值内未使用相关应用的沉睡用户。AppsFlyer会对再营销广告带来的再互动和重装激活进行归因。
* **不纳入归因的流量**：在指定的不活跃时长阈值内打开过应用的活跃用户会被忽略，且不会被归因到相关的再营销广告。

### 再营销中用户不活跃时长阈值的相关概念

| 时长 | 定义 |
| --- | --- |
| 最大值 | 30天 |
| 默认值 | 0（无）  <br />渠道对接中的**不活跃时长阈值**功能默认关闭。 |
| 用户活跃数据 | 通过SDK或S2S上报的激活或应用打开（session） |
| 设备切换 | 用户切换设备的时间即为最后一次活跃时间。 |

## 使用场景

下文列举了排除活跃用户的再营销投放场景，其中广告主针对相关渠道设置了不活跃时长阈值。

<div id="reattribution" />

<Accordion title="再归因">

此场景中的用户链路如下（详见下方流程图）：用户依次完成以下操作：

* 卸载相关应用，成为流失用户
* 与某渠道投放的再营销广告发生交互
* 重新安装并激活该应用

[![re-attribution_1_en-us.png](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)

| 场景 | 不活跃时长阈值 | 用户沉睡时长 | 归因结果 |
| --- | --- | --- | --- |
| A | 7天 | 8天<br /><br />**用户沉睡**时长超过不活跃时长阈值 | <ul><li>**再归因**（流失用户召回）：再营销广告带来重装激活</li><li>归因到再营销渠道A</li></ul> |
| B | 14天 | 5 天<br /><br />该用户仍处于活跃状态 | <ul><li>**自然重装激活**</li><li>**非自然重装激活**：若该用户与UA渠道发生了广告交互</li><li>根据不活跃时长阈值的界定，该用户仍处于活跃状态，因此不能归因到再营销渠道A。</li></ul> |

</Accordion>

<div id="reengagement" />

<Accordion title="再互动">

此场景中的用户链路如下（详见下方流程图）：用户依次完成以下操作：

* 激活相关应用
* 在数天内处于不活跃状态
* 与某渠道投放的再营销广告发生交互，然后再次打开该应用

[![Re-engagement_scenarios_en-us.png](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)

| 场景 | 渠道A的不活跃时长阈值 | 用户沉睡时长 | 归因结果 |
| --- | --- | --- | --- |
| A | 7天 | 8天<br /><br />**用户沉睡**时长超过不活跃时长阈值 | <ul><li>归因到渠道A的**再互动**</li></ul> |
| B | 7天 | 4天<br /><br />用户在不活跃时长阈值内**使用了该应用**。 | <ul><li>**常规应用打开（session）**</li><li>该流量不归因到再互动渠道A</li></ul> |

</Accordion>

## 渠道对接配置

<div id="zd-srn" />

<Accordion title="SRN">

如果您使用的SRN支持不活跃时长阈值，您会在其渠道对接选项卡中看到该功能的设置控件。

**如需为支持再营销的SRN设置不活跃时长阈值，请按以下方式操作：**

1. 从AppsFlyer后台的左侧菜单栏中选择**协作** > **活跃对接**。
2. 选择相关SRN。
3. 进入**渠道对接**选项卡，向下滚动页面。打开**再营销广告中忽略活跃用户**的开关。
4. 设置**不活跃窗口**。可用范围为1-30天。
5. 点击**保存对接**。

[![Inactivity_window_SRN.png](https://files.readme.io/158a1c56acc330dc8bb25a2199e1ad8b643e4f94a22d55caadae485d4a8a753d-51911937665553.png)](https://files.readme.io/158a1c56acc330dc8bb25a2199e1ad8b643e4f94a22d55caadae485d4a8a753d-51911937665553.png)

</Accordion>

<div id="nonsrn-click-ad-networks" />

<Accordion title="非SRN（广告点击平台）">

**如需为支持再营销的非SRN设置不活跃时长阈值，请按以下方式操作：**

1. 从AppsFlyer后台的左侧菜单栏中选择**协作** > **活跃对接**。
2. 选择相关广告平台。
3. 进入**归因链接**选项卡，向下滚动到**再营销广告中忽略活跃用户**部分，打开该开关。
4. 设置**不活跃窗口**。可用范围为1-30天。  
   该设置会将**不活跃时长阈值**参数`af_inactivity_window`添加到归因链接中，如“&af\_inactivity\_window=7d”。该功能关闭时，归因链接中不会带有这个参数。

[![Inactivity_window_non-SRN.png](https://files.readme.io/10c1921e449c0cfbaed7d0fc07837f8dd9720dc2316d44c966d91b5baddcfbf4-51911937666193.png)](https://files.readme.io/10c1921e449c0cfbaed7d0fc07837f8dd9720dc2316d44c966d91b5baddcfbf4-51911937666193.png)

</Accordion>

<div id="agencies" />

<Accordion title="代理">

#### SRN

代理（需广告主开放权限）

**不活跃时长阈值设置的访问方式如下：**

1. 从AppsFlyer后台的左侧菜单栏中选择**协作** > **活跃对接**。
2. 选择相关SRN。
3. 根据下表信息，在**渠道对接**选项卡中完成所需设置。

| SRN | 代理 |
| --- | --- |
| Doubleclick | <ul><li>启用/关闭再营销功能</li><li>配置不活跃时长阈值</li></ul> |
| Google Ads | <ul><li>无法启用/关闭再营销功能</li><li>代理可以配置不活跃时长阈值，但需要先获得必要权限</li></ul> |
| Meta ads/X Ads/Snapchat | 代理无法访问再营销及**不活跃时长阈值**设置 |

#### 非SRN

合作平台（支持再营销）

**如需为支持再营销的非SRN设置不活跃时长阈值，请按以下方式操作：**

1. 从AppsFlyer后台的左侧菜单栏中选择**协作** > **活跃对接**。
2. 选择相关的非SRN广告平台 > 进入**归因链接**选项卡。

</Accordion>

<div data-zendesk-anchors="inactivity-period=%E4%B8%8D%E6%B4%BB%E8%B7%83%E6%97%B6%E9%95%BF h_01H9JS3QKW5S7VP9YW05CB6STR=%E4%B8%8D%E6%B4%BB%E8%B7%83%E6%97%B6%E9%95%BF retargeting-inactivity-terminology=%E5%86%8D%E8%90%A5%E9%94%80%E4%B8%AD%E7%94%A8%E6%88%B7%E4%B8%8D%E6%B4%BB%E8%B7%83%E6%97%B6%E9%95%BF%E9%98%88%E5%80%BC%E7%9A%84%E7%9B%B8%E5%85%B3%E6%A6%82%E5%BF%B5 h_01H9JS3QKXMBS95RG06A9JXGT0=%E5%86%8D%E8%90%A5%E9%94%80%E4%B8%AD%E7%94%A8%E6%88%B7%E4%B8%8D%E6%B4%BB%E8%B7%83%E6%97%B6%E9%95%BF%E9%98%88%E5%80%BC%E7%9A%84%E7%9B%B8%E5%85%B3%E6%A6%82%E5%BF%B5 scenarios=%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF h_01H9JS3QKXWDX8Y58GX1G5HNYY=%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF h_01H9JS3QKXN0E0MGD35173C9FR=reattribution h_01H9JS3QKXNS77EFYBZP94YQMT=reengagement partner-setup=%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5%E9%85%8D%E7%BD%AE h_01H9JS3QKXGNFM8499G52458B2=%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5%E9%85%8D%E7%BD%AE srn=zd-srn h_01H9JS3QKXCAHG91VS6VSVJTTT=zd-srn h_01H9JS3QKX8R8AXHQWKX7FR9GZ=nonsrn-click-ad-networks h_01H9JS3QKXSDXA5Z7TWN2A7S5K=agencies srn::bd853114=srn h_01H9JS3QKX88HQYJ5881W7VXF2=srn nonsrn=%E9%9D%9Esrn h_01H9JS3QKXRJ8W9H89JBVSZ3R3=%E9%9D%9Esrn" />
