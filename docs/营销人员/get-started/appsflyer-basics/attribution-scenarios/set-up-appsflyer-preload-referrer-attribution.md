---
title: AppsFlyer预装referrer归因
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2022-03-02T09:54:10Z'
  edited_at: '2026-10-14T10:14:49Z'
  id: 4543811207313
  locale: zh-cn
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/zh-cn/articles/4543811207313
---
> **概要：** 概要：AppsFlyer可以通过预装referrer将激活归因到预装推广。预装推广是指营销人员与设备生产商（OEM）、移动运营商和应用推广平台合作，在设备出厂或首次启动时将其应用预装到设备中。

<div id="overview" />

## 速览

在预装推广场景中，设备生产商（OEM）、移动运营商和应用推广平台会在触达用户之前就将相关应用预先安装到设备上。预装有两种实现方式，可以由OEM在设备出厂时完成，也可以由服务商在设备首次激活时完成。

预装推广能让广告主在无需进行线上投放的情况下就触达更广泛的用户群体。

预装referrer归因是三种<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#preload-campaigns">预装归因方式</Anchor>之一，能让营销人员在确保用户隐私的前提下准确衡量预装推广的效果。这种归因方式能为营销人员提供确定性的归因结果，同时又能保护用户隐私。这是因为其归因原理是对referrer进行匹配，进而完成归因，而referrer与设备和用户标识符无关，是独立生成的信息。

该解决方案能够：

* 支持应用更新和重新下载（redownload）数据的呈现
* 显示并衡量设备初次激活以及应用首次打开，这样您就可以了解具体渠道的预装设备激活数量，以及相关应用的首次打开时间。

<div id="partners-supporting-preload-referrer-campaigns" />

## 支持预装referrer投放的渠道

<table><thead><tr><th rowspan="2">Partner</th><th rowspan="2">PID</th><th colspan="2">预装referrer投放选项<a href="./set-up-appsflyer-preload-referrer-attribution#预装referrer选项"><span>了解详情</span> </a> </th></tr><tr><th>预装推广</th><th>点击下载</th></tr></thead><tbody><tr><td><a href="#特点与局限性">Samsung</a></td><td>samsung_int</td><td><span>✓</span></td><td> </td></tr><tr><td>Digital Turbine On Device</td><td>digitalturbine_int</td><td><span>✓</span></td><td>即将更新</td></tr><tr><td>Aura from Unity</td><td>aura_int</td><td><span>✓</span></td><td>即将更新</td></tr><tr><td>Appnext</td><td>appnext_int</td><td><span>✓</span></td><td>即将更新</td></tr><tr><td>Glance<br/> </td><td>glance_int</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

<div id="preload-referrer-options" />

## 预装referrer选项

Referrer可以用来对预装激活和点击下载进行归因。详情请见下文表格。

在AppsFlyer平台中，预装归因的优先级最高。也就是说，即使用户在首次打开应用前与其他类型的广告进行了互动，其激活仍会归因到相关的预装推广，其他的广告互动则会获得助攻激活归因。**请注意**：

| Referrer选项 | 说明 | UA激活原始数据匹配类型 |
| --- | --- | --- |
| 预装推广 | <ul><li>在设备出厂或设备首次激活时完成应用预装，也可以在设备首次激活时通过向导对话框引导用户下载相关应用。</li><li>预装事件与点击具有相同的归因优先级，在设备首次启动时上报给AppsFlyer。</li><li>当用户首次打开相关应用时进行归因。</li><li>预装事件的归因优先级最高（除非您打开了“具有同等归因优先级”的开关）。</li></ul> | `preload_rfr` |
| 点击下载 | <ul><li>用户通过推送通知、第三方应用商店等在设备激活后较长的一段时间内安装应用。</li><li>如果用户与广告或推送通知进行了互动，会自动下载并安装相关应用，无需跳转到应用商店。</li><li>根据AppsFlyer的末次点击规则进行归因。</li></ul> | `af_referrer` |


<span id="view-preload-attribution-data"></span>预装/点击下载推广的效果数据可用性如下：

* 数据总览面板 并按预装渠道和广告系列汇总。
* **原始数据**原始数据：仅可通过Data Locker获取点击报告中的互动数据。可在初始URL字段查看该数据，并通过af\_engagement\_type参数识别预装（preload）或点击下载（click\_to\_download）。有关激活数据的说明请见上一节中的表格，其中解释了原始数据中呈现匹配类型的方式。

<div id="set-up-preload-referrer-attribution" />

## 设置预装referrer归因

**前期准备：**

* 在相关应用中接入AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-android-sdk-release-notes">Android SDK 6.10.1+</Anchor>。
* 联系AppsFlyer预装渠道。

**预装referrer归因的设置方式如下**：

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 选择一个预装渠道。
3. 在**渠道对接**选项卡中打开**预装归因**开关。  
   [<Image alt="" src="https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png" width="538px" />](https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png)
4. 设置**预装回溯窗口**的时长，范围：60天。
5. 【可选】打开**预装具有同等归因优先级**的开关。  
   该开关打开后，确定性点击与预装具有相同的归因优先级。也就是说，如果AppsFlyer在预装Referrer互动与应用激活之间记录到一次确定性点击，会根据末次触达的归因逻辑将该次激活归因到点击而非预装referrer。
6. 点击**保存对接** 。
7. 通知预装渠道已开通其预装投放的归因。



<div id="traits-and-limitations" />

<div id="set-up-samsung-preload-referrer-attribution" />

<div id="samsung-preload-referrer" />

### 特点与局限性

| 特点 | 说明 |
| --- | --- |
|  | samsung\_int |
| SDK version | v6.16.0 |
| Match type | `preload_rfr` |
| 数据总览面板 | 并按预装渠道和广告系列汇总。 |
| 原始数据报告 |  |

<div data-zendesk-anchors="appsflyer-preload-referrer-attribution=%E9%80%9F%E8%A7%88 h_01HEKAF7K41PH189PSCKBRF070=%E9%80%9F%E8%A7%88 partners-supporting-preload-referrer-campaigns=%E6%94%AF%E6%8C%81%E9%A2%84%E8%A3%85referrer%E6%8A%95%E6%94%BE%E7%9A%84%E6%B8%A0%E9%81%93 h_01HEKAF7K5CWX2P9TY8M0MTQAM=%E6%94%AF%E6%8C%81%E9%A2%84%E8%A3%85referrer%E6%8A%95%E6%94%BE%E7%9A%84%E6%B8%A0%E9%81%93 preload-referrer-options=%E9%A2%84%E8%A3%85referrer%E9%80%89%E9%A1%B9 h_01HEKAF7K4H3HNAMEYM6C58Y29=%E9%A2%84%E8%A3%85referrer%E9%80%89%E9%A1%B9 h_01HEKAF7K4GJDDPHCFTTC75YBS=view-preload-attribution-data set-up-preload-referrer-attribution=%E8%AE%BE%E7%BD%AE%E9%A2%84%E8%A3%85referrer%E5%BD%92%E5%9B%A0 h_01HEKAF7K41RBRVXC6GF6PCN3Y=%E8%AE%BE%E7%BD%AE%E9%A2%84%E8%A3%85referrer%E5%BD%92%E5%9B%A0 samsung-preload-referrer=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 set-up-samsung-preload-referrer-attribution=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 traits-and-limitation=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01JCB6K81QRK2NM983SJBYD9M3=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01JDPYAV86PT14C91ZQ2D9XTZ2=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
