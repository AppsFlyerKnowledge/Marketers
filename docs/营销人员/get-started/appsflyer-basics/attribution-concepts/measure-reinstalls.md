---
title: 重装激活
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2022-10-27T07:37:21Z'
  edited_at: '2026-10-14T10:14:32Z'
  id: 10164066030737
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/10164066030737
---
> **概要**：如果用户在激活应用后，将其卸载再重新激活，AppsFlyer就会将该行为视为重装激活。重装激活的归因结果包括以下几种：非自然重装激活、自然重装激活或再归因（再营销）。衡量重装激活可以避免为卸载后再次安装的用户重复买量。

<div id="what-is-a-reinstall" />

## 什么是重装激活

某个应用的用户删除该应用后在<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window#再归因窗口">再归因窗口期</Anchor>内重新安装并激活该应用，即构成一次重装激活。

重装激活的来源包括再营销广告（再归因）、自然流量和非自然流量。

自然和非自然用户在<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window#再归因窗口">再归因窗口期</Anchor>内重新安装并激活已卸载的应用，这类行为统称为重装激活（Reinstall）。

其中，由再营销广告促成的重装激活被称为再归因（Re- attribution）。

具体的归因结果取决于重装激活和应用内事件的归因方式。

如果某次激活发生在<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window#再归因窗口">再归因窗口期</Anchor>之外，则会被记录为<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window#new-install">新增激活</Anchor>。AF会将新增激活归因到相关的媒体渠道（如果没有记录到广告互动，则归为自然量），并触发新一轮的再归因窗口。

下表列出了AppsFlyer对各种重装激活的分类情况

| 重装激活来源 | 是否在再归因窗口内 | 用户在重装激活前是否与再营销广告互动 | 在重装激活之前，用户是否与用户获取广告活动进行了互动？ | 归因结果 |
| --- | --- | --- | --- | --- |
| 再营销广告 | 是 | 是 | 否 | 再归因（reattribution） |
| 自然或非自然流量 | 是 | 否 | 是或否 | Reinstall（重装激活） |
| 自然或非自然流量 | 否 | 否 | 是或否 | 新增激活 |

<div id="why-are-reinstalls-important" />

## 重装激活的意义

对重装激活的准确归因不仅能说明流失用户的召回情况以及广告投放成功与否，还能帮助广告主避免为再归因窗口期内卸载重装的用户重复付费。

<div id="reinstall-flow-and-outcome" />

## 重装激活的归因链路和结果

<div id="reinstall" />

<Accordion title="Reinstall（重装激活）">

用户初次激活应用后将其卸载，并在再归因窗口期完成重新安装并激活该应用，即构成一次重装激活。重装激活可以来自自然流量或拉新广告（参见示例）。

会发生以下情况：

* 该次激活不会被归因—即该激活不会出现在面板或数据中。
* 没有安装回传会发送至任何媒体渠道。
* 应用内事件的归因方式请参见[应用内事件](/docs/measure-reinstalls#应用内事件)部分

</Accordion>

<div id="reattribution" />

<Accordion title="再归因（reattribution）">

用户初次激活应用后将其卸载，之后与再营销广告互动，并在[再归因窗口期完成重新安装并激活该应用，即构成一次再归因。  

会发生以下情况：

* 此次安装归因至再营销媒体渠道，并呈现在控制面板的再营销和统一视图中
  * 用户获取视图中不包含再归因
* 后续所有的应用内事件都会被归因到再营销渠道（详情请见[应用内事件](/docs/measure-reinstalls#应用内事件)）
* 激活回传会发送到相关的再营销渠道。

如需进一步了解再营销归因，请参考<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">此文档</Anchor>。

</Accordion>

<div id="post-reinstall-in-app-events" />

## 应用内事件

### 速览

[![](https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg)](https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg)

用户在重装激活后完成的应用内事件可分为归因的自然量、归因的非自然量以及未归因的自然量，具体取决于重装激活后的事件归因状态（见下表）。

典型的应用内事件包括用户在重装激活后完成的应用内购买。

#### 应用内事件及其归因方式

<table><tbody><tr><th>重装激活后的事件归因状态</th><th>重装激活后</th><th>再归因后</th></tr><tr><td><strong>归因为自然量</strong></td><td>未归因的自然量</td><td>再营销</td></tr><tr><td> <strong>归因至首次激活</strong><span>(1)</span> </td><td>带来首次激活的渠道</td><td>再营销 <span>(2)</span> </td></tr><tr><td colspan="3"><p><span>(1) 详情请见下文的局限性说明</span></p><p>(2) 主要来源（primary source）字段显示为再营销，次要来源（secondary source）为首次激活渠道（仅在原始数据中可见）。</p></td></tr></tbody></table>

<div id="unattributed-organic-inapps" />

<Accordion title="未归因的应用内事件自然量">

Reinstall（重装激活）

* 所有应用内事件都记录为自然事件或不做记录，具体取决于您使用的面板
* 这些应用内事件的conversion\_type（转化类型）和campaign\_type（广告系列类型）会显示为“unknown”（未知）。
* 用于汇总数据的日期取决于相关的事件：
  * 对于大部分由SDK上报的应用内事件，AppsFlyer会使用应用下载发生的日期来汇总其数据。
  * 对于由SDK连接器发送的广告收入事件（af\_ad\_revenue），AppsFlyer会使用重装激活发生的日期来汇总其数据。

再归因（reattribution）

* 所有应用内事件都会被归因到再营销渠道。

</Accordion>

<div id="attributed-to-the-first-install" />

<Accordion title="归因到首次激活">

> 🚧 **前期准备**
>
> 需要手动启用。建议与您的CSM沟通相关事宜。

#### 作用

让广告主更好地了解用户的获取链路。由于该功能可以将应用内事件归因到初始渠道而非自然量，因此能说明拉新和再营销广告的投放效果。

#### Reinstall（重装激活）

* 由重装激活带来的所有应用内事件都会归因到初始激活(1)

#### 再归因（reattribution）

* 所有应用内事件的主要来源都归因为再营销广告，次要来源都归因到初始激活。(2) (2)

(1) 请参见下文的局限性说明。

(2) 仅在原始数据中可见。

<div id="note-1" />

> 📘 **注意**
>
> 如果您将重装激活后的应用内事件归因设置为**归因到初始激活**，则面板中的自然量KPI数据会变低，这是因为其中的部分流量会被归因到非自然媒体渠道。

</Accordion>

<div id="examples" />

<Accordion title="示例">

<div id="examples-for-first-install-mode-attribution" />

#### 假设您将重装激活后的应用内事件归因设置为**归因到初始激活**。

**示例 1**

用户激活应用（第0天），并完成了金额为10美元的应用内购，之后卸载了该应用。

次日（第1天），该用户重装激活该应用，并完成了金额为5美元的应用内购。

Reinstall\_1.jpg

由于该用户在重装激活之前已经完成了购买，因此不会将其记录为新增的独立用户。

| 媒体渠道 | users | Af\_purchase：<br /><br />独立用户数<br /><br />第0天 | Af\_purchase：<br /><br />独立用户数<br /><br />第1天（累计） | 收入<br /><br />第0天 | 收入<br /><br />第1天（累计） |
| --- | --- | --- | --- | --- | --- |
| Media\_source\_A | 1 | 1 | 1 | $10 | $15 |

| Appsflyer\_id | 设备标识符 | 媒体渠道 | 事件名称 | 事件日期 |
| --- | --- | --- | --- | --- |
| 111 | XXX | media\_source\_A | install | 第0天 |
| 111 | XXX | media\_source\_A | af\_purchase | 第0天 |
| 222 | XXX | organic | reinstall | 第1天 |
| 222 | XXX | media\_source\_A | af\_purchase | 第1天 |

**示例 2**

用户激活应用（第0天）并完成购买，然后卸载了该应用。

次日（第1天），用户与拉新广告互动并重装激活该应用，然后完成购买。

| 媒体渠道 | 事件名称 | 事件日期 | 重装激活归因 | 应用内事件归因 |
| --- | --- | --- | --- | --- |
| media\_source\_A | install | 第0天 | media\_source\_A |  |
| media\_source\_A | af\_purchase | 第0天 |  | media\_source\_A |
| media\_source\_B | reinstall | 第1天 | media\_source\_B |  |
| media\_source\_B | af\_purchase | 第1天 |  | media\_source\_A |

</Accordion>

<div id="limitations" />

<Accordion title="局限性">

* 用户在初次激活和重装激活时都同意与相关应用共享设备标识符（如IDFA或GAID）的情况下，AF才能够将其应用内事件归因到初始激活。
  * 初始激活和重装激活中的设备标识符必须一致
* 重装激活发生的时间必须在上一次激活之后的<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide#reengagement-rules-and-windows">再归因窗口</Anchor>内。
* 每个激活和重装激活都有其专属的appsflyer\_id
* 面板中不区分激活后的应用内事件和重装激活后的应用内事件
  * 可以通过原始数据查看

</Accordion>

<div id="how-does-the-data-appear-in-the-appsflyer-dashboards" />

## 数据在AppsFlyer面板中的呈现方式

<table><tbody><tr><th colspan="2"> </th><th>非自然重装激活</th><th>自然重装激活 </th><th>再归因（reattribution）</th></tr><tr><td colspan="2">重装激活本身</td><td>不显示</td><td>不显示</td><td><span>再营销媒体渠道\*</span></td></tr><tr><td rowspan="2">后续的应用内事件归因</td><td>重装激活后的事件归因设置为<strong>归因为自然应用内事件</strong> </td><td>未归因的自然事件</td><td>未归因的自然事件</td><td><span>再营销媒体渠道</span></td></tr><tr><td>重装激活后的事件归因设置为<strong>归因到初始激活</strong> </td><td>初始媒体渠道</td><td>初始媒体渠道</td><td>再营销广告活动</td></tr><tr><td colspan="5">\*仅在总览面板中可见</td></tr></tbody></table>

<div id="reinstalls-raw-data-reports" />

## 重装激活原始数据报告

<div id="prerequisites" />

> 🚧 **前期准备**
>
> 需要手动启用。详情请咨询您的CSM。

* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQtlerXtCVImurv-JyuG7JMPvLN6p2w79pmbMNBx6WBnLwnYq5bUqXiUuoy2l_UTzEjIr8UkDdclRxf/pub?output=csv">CSV格式的重装激活报告示例</Anchor>

<div id="how-the-install-and-in-app-events-are-attributed" />

#### 激活和应用内事件的归因方式

<table><tbody><tr><th colspan="2"> </th><th>非自然重装激活</th><th>自然重装激活 </th><th>再归因（reattribution）</th><th>非自然激活</th><th>自然激活</th></tr><tr><td colspan="2">归因到  </td><td>拉新广告</td><td>自然量</td><td>再营销广告活动</td><td>拉新广告</td><td>自然量</td></tr><tr><td rowspan="2">后续的事件归因</td><td>重装激活后的事件归因设置为<strong>归因为自然应用内事件</strong> </td><td>自然量</td><td>自然量</td><td>再营销广告活动</td><td>拉新广告</td><td>自然量</td></tr><tr><td>重装激活后的事件归因设置为<strong>归因到初始激活</strong> </td><td>首次安装</td><td>首次安装</td><td>再营销广告活动</td><td>拉新广告</td><td>自然量</td></tr></tbody></table>

<div id="availability-of-reinstall-reports" />

### 重装激活报告的可用性

* 您可以使用下表所列的数据传输工具拉取重装激活原始数据报告。
* 这些报告的结构相同，且字段填充方式与激活报告相似，具体如下：
  * **Media source**（媒体渠道）字段会显示促成重装激活的渠道或自然量（organic）。
  * install\_timeInstall time（激活时间）：显示重装激活时间，即用户重新安装应用后首次打开该应用的时间
  * event\_name Reinstall（重装激活）

| 报告拉取方式 | 非自然重装激活 | 自然重装激活 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">导出数据</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/zh/docs/pull-api-aggregate-data">Pull API</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">Data Locker</Anchor> | ✓ | ✓ |
| Push API | ✓ | ✓ |

<div data-zendesk-anchors="what-is-a-reinstall=%E4%BB%80%E4%B9%88%E6%98%AF%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB 01H7SZVZPGHBQ7VM8TMWRD3CE4=%E4%BB%80%E4%B9%88%E6%98%AF%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB why-are-reinstalls-important=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E7%9A%84%E6%84%8F%E4%B9%89 01H7SZVZPG6T2AW9B3EMT29AQQ=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E7%9A%84%E6%84%8F%E4%B9%89 reinstall-flow-and-outcome=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E7%9A%84%E5%BD%92%E5%9B%A0%E9%93%BE%E8%B7%AF%E5%92%8C%E7%BB%93%E6%9E%9C 01H7SZVZPGVQCNCQ7TCZMYM33T=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E7%9A%84%E5%BD%92%E5%9B%A0%E9%93%BE%E8%B7%AF%E5%92%8C%E7%BB%93%E6%9E%9C 01H7SZVZPGCDP3GRK1BWZ04MR6=reinstall 01H7SZVZPG8WNTK30YXNZ44VTS=reattribution inapp-events=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 01H7SZVZPGBYRWZGAZRT36EFGH=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 overview=%E9%80%9F%E8%A7%88 01H7SZVZPGK7X1NXW467CZP1KJ=%E9%80%9F%E8%A7%88 inapp-events-and-how-they-are-attributed=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%8F%8A%E5%85%B6%E5%BD%92%E5%9B%A0%E6%96%B9%E5%BC%8F 01H7SZVZPHW7E5WV9C643BG6YB=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%8F%8A%E5%85%B6%E5%BD%92%E5%9B%A0%E6%96%B9%E5%BC%8F 01H7SZVZPH4AE1PZK8V5JG6C6X=unattributed-organic-inapps 01H7SZVZPH7KPM7T42GHZ7N69S=attributed-to-the-first-install 01H7SZVZPHBQ7E3R107EB2KXES=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 purpose=%E4%BD%9C%E7%94%A8 01H7SZVZPHXBX6J2APBXS30CPX=%E4%BD%9C%E7%94%A8 reinstall::7f2d499b=reinstall%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB 01H7SZVZPHRJ9WPW3TCYECK50W=reinstall%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB h_01J3FZXYG37R0QFB7BPH9F64GM=%E6%B3%A8%E6%84%8F reattribution::bbb1aabb=%E5%86%8D%E5%BD%92%E5%9B%A0reattribution 01H7SZVZPHZFY9ZDEQYP967C2D=%E5%86%8D%E5%BD%92%E5%9B%A0reattribution 01H7SZVZPH5YGSMPGW7NPKXJAF=%E6%B3%A8%E6%84%8F 01H7SZVZPHF3R44DTHCD9QHPR8=examples with-attributed-to-the-first-install-enabled=%E5%81%87%E8%AE%BE%E6%82%A8%E5%B0%86%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E5%90%8E%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE%E4%B8%BA%E5%BD%92%E5%9B%A0%E5%88%B0%E5%88%9D%E5%A7%8B%E6%BF%80%E6%B4%BB 01H7SZVZPHH3DS9J4VRD70VTX6=%E5%81%87%E8%AE%BE%E6%82%A8%E5%B0%86%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E5%90%8E%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE%E4%B8%BA%E5%BD%92%E5%9B%A0%E5%88%B0%E5%88%9D%E5%A7%8B%E6%BF%80%E6%B4%BB 01H7SZVZPH8MSBQ92XWFK0HWGQ=limitations how-does-the-data-appear-in-the-appsflyer-dashboards=%E6%95%B0%E6%8D%AE%E5%9C%A8appsflyer%E9%9D%A2%E6%9D%BF%E4%B8%AD%E7%9A%84%E5%91%88%E7%8E%B0%E6%96%B9%E5%BC%8F 01H7SZVZPHHQS4NHEDATD7ZP9V=%E6%95%B0%E6%8D%AE%E5%9C%A8appsflyer%E9%9D%A2%E6%9D%BF%E4%B8%AD%E7%9A%84%E5%91%88%E7%8E%B0%E6%96%B9%E5%BC%8F reinstalls-raw-data-reports=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A 01H7SZVZPHPWN8REBQ5CWVFNJT=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A 01H7SZVZPHCVDPDDYD6HHNFMMK=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87-1 how-the-install-and-inapp-events-are-attributed=%E6%BF%80%E6%B4%BB%E5%92%8C%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84%E5%BD%92%E5%9B%A0%E6%96%B9%E5%BC%8F 01H7SZVZPHQT8XS3ZBA4W682GB=%E6%BF%80%E6%B4%BB%E5%92%8C%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84%E5%BD%92%E5%9B%A0%E6%96%B9%E5%BC%8F availability-of-reinstall-reports=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E6%8A%A5%E5%91%8A%E7%9A%84%E5%8F%AF%E7%94%A8%E6%80%A7 01H7SZVZPH6NY7FMG9YHDBB95R=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E6%8A%A5%E5%91%8A%E7%9A%84%E5%8F%AF%E7%94%A8%E6%80%A7" />
