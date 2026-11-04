---
title: PBA网页端归因面板
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2018-12-09T07:49:24Z'
  edited_at: '2026-10-14T10:10:35Z'
  id: 360000654377
  locale: zh-cn
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000654377
---
> **概要：** 概要：该面板可帮助您监测网页端的营销效果，从而有效拉动网页端流量。您可以看到网站访问量和转化事件背后的媒体渠道、广告类型和流量入口，以及深入到广告层级的指标数据。

网页广告归因

<div id="pba-website-attribution" />

## PBA网页端归因

广告主可以使用网页端归因面板深入了解访问量和转化量背后的媒体渠道。

* 广告主可通过面板中的趋势图查看总体趋势以及分渠道和流量入口的拆解数据。
* 该面板提供细致详尽的投放数据，广告主可深入到广告/广告组层级查看每个转化事件的效果指标。

**营销人员可使用该面板获得以下问题的答案：**

| ![icon2.png](https://files.readme.io/77fda01229f4b1b50755bc94f35cc021928ba7af1e3b5b45e61606ab18e8fd7a-360013383917.png) | **投放效果**<br /><br />哪些渠道和广告带来的网站访问量、转化量和价值最高？ |
| --- | --- |
| ![Icon1.png](https://files.readme.io/b20da70a56d881dd2fe31b18df8919db43b47e3e2338b89da7ef5ef6467590d6-360013383937.png) | **投放效率**<br /><br />哪些拉新渠道的投放效果指标（如转化率或ARPU等）最好？ |
| ![s4.png](https://files.readme.io/9a426232668022a9b4d006e685d2384d61efe4814c377aa9295e9b7887f14fef-360013383957.png) | **对比分析** |

<div id="dashboard-reference" />

## 面板使用方式

**您可以通过以下任一方式进入PBA面板：**

* 从AppsFlyer后台的侧边栏中选择**分析** > **基于用户的归因**。
* 从AppsFlyer后台的顶部菜单栏中选**我的应用 >** **查看品牌套件**。 点击PBA面板， 然后进入网页广告归因选项卡。

<Table>
  <thead>
    <tr>
      <th>
        组成部分
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        日期选择器和筛选条件
      </td>
      <td>
        ![WebsiteAttributionFilterPaner_us-en.jpg](https://files.readme.io/1d4cb6145bd0a297d9d358b904968cdffadc4235499ba661048983de8dbc348c-360013057737.jpg)

        * 选择归因的日期范围、<Anchor target="_blank" href="/marketers/zh/docs/using-pba-dashboards">筛选条件和分组维度</Anchor>。
        * 筛选筛选条件包括：媒体渠道、媒体类型、媒体流量入口、国家/地区、转化事件
        * 分组维度分组维度：媒体渠道/广告系列、媒体类型、媒体流量入口、设备类型、操作平台
      </td>
    </tr>
    <tr>
      <td>
        图表
      </td>
      <td>
        **网页端使用情况在一段时间内的变化**

        ![WebsiteAttribution_us-en__1_.jpg](https://files.readme.io/cfa214a82b39db1fdbed128029dd28fdf4b623f2c0c7d7f51e067d5e182431ca-360013057717.jpg)

        * 展示指定时间段内访问流量和转化的来源。
      </td>
    </tr>
    <tr>
      <td>
        数据表
      </td>
      <td>
        **归因表**

        [![WebsiteAttributionTable_us-en.jpg](https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg)](https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg)

        * 网页端的可用指标包括总体指标和分转化事件的细分指标。
        * 查看数据时，您可以从媒体渠道层级切入到广告层级，考察具体的带量渠道和广告。
        * 对比广告在拉动流量和促成转化方面的效果。

        | 总体指标 | 说明 |
        | --- | --- |
        | <span id="visits"></span>访问量 | 访问网站的用户所产生的会话（session）数量 |
        | <span id="unique-visitors"></span>独立访客 | 访问相关网站的独立访客。PBA机制会通过PBA隐私用户图表来判定独立用户数。请务必接入<Anchor target="_blank" href="/marketers/zh/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">CUID</Anchor>，否则无法确保图表的可靠性。同一个用户使用不同浏览器进入网站时，PBA会将其记录为一个独立访客。 |
        | <span id="conversions"></span>转化 | 用户完成的转化事件数量 |
        | <span id="conversion-rate"></span>转化率 | 计算方式为： |
        | <span id="acpu"></span>ACPU | 各独立访客的平均转化量。计算方式为： |
        | <span id="revenue"></span>收入 | 所有事件的收入总和 |
        | <span id="arpu"></span>ARPU | 平均每位用户累计带来的收入计算方式为：收入/独立用户数 |

        | 转化事件指标 | 说明 |
        | --- | --- |
        | <span id="event-count"></span>事件数 | 用户完成事件的次数 |
        | <span id="unique-users"></span>独立用户数 | 完成相关转化事件的独立用户 |
        | <span id="revenue::58195989"></span>收入 |  |
        | <span id="arpe"></span>ARPE | 转化事件的平均收入。计算方式为： |
      </td>
    </tr>
    <tr>
      <td>
        导出CSV文件
      </td>
      <td>
        点击**导出CSV文件**，即可导出该表格。
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="pba-website-attribution=pba%E7%BD%91%E9%A1%B5%E7%AB%AF%E5%BD%92%E5%9B%A0 h_01HJR6ZPF5VWPX9020G0W7NX4X=pba%E7%BD%91%E9%A1%B5%E7%AB%AF%E5%BD%92%E5%9B%A0 dashboard-reference=%E9%9D%A2%E6%9D%BF%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HJR6ZPF58VWA51QWY4BGZN8E=%E9%9D%A2%E6%9D%BF%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F" />
