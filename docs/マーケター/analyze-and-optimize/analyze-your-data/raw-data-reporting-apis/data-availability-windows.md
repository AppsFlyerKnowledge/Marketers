---
title: データの利用可能期間
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2022-01-04T03:33:13Z'
  edited_at: '2026-10-14T09:29:02Z'
  id: 4415473374865
  locale: ja
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/ja/articles/4415473374865
---
> **概要：** データの利用可能期間は、レポートの種類と、それぞれに定められた利用可能期間によって異なります。

<div id="data-availability-windows" />

## データの利用可能期間

* 「**利用可能期間**」と「**データ保持期間**」は、それぞれ異なる意味を持ちます。<Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">データ保持期間</Anchor>とは、AppsFlyerのサーバー上でローデータを保持する期間を指し、利用可能期間よりも長く設定されています。
* 利用可能期間の長さは、ご契約のサブスクリプションパッケージによって異なります。
* なお、本記事の内容は<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">Data Locker</Anchor>には適用されません。

<div id="raw-data-availability-window" />

### ローデータの利用可能期間

利用可能期間により、Pull APIおよびローデータのエクスポートページから取得できるローデータの範囲が制限されます。利用可能期間はレポートの種類によって異なります。詳細は以下の表を参照してください。

| レポートのイベントタイプ | レポートタイプの例 | デフォルトの利用可能期間 |
| --- | --- | --- |
| アトリビューション | オーガニックインストール、非オーガニックインストール、リターゲティングコンバージョン、アンインストール | 過去90日間のうち60日分 |
| アプリ内イベント | オーガニックアプリ内イベント、非オーガニックアプリ内イベント、リターゲティングアプリ内イベント | 過去90日間のうち31日分 |

<div id="aggregated-data-availability-window" />

### 集計データの利用可能期間

利用可能期間により、Pull APIおよび集計データのエクスポートページから取得できるデータの範囲が制限されます。利用可能期間はレポートの種類によって異なります。詳細は以下の表を参照してください。

| レポート | 利用可能期間 |
| --- | --- |
| 集計レポート | <Anchor target="_blank" href="/marketers/ja/docs/bulletin-aggregated-ltv-data-availability">最初のアプリインストールを起点として25</Anchor>か月間（2年＋1か月） |

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/report-generation-quotas-rate-limitations">レポート生成の上限</Anchor>

<div data-zendesk-anchors="data-availability-windows=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E6%9C%9F%E9%96%93 h_01HE0FT9CNECNKYMVX9ZJJ9DNV=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E6%9C%9F%E9%96%93 raw-data-availability-window=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E6%9C%9F%E9%96%93 h_01HE0FT9CNS4N1GD1AYRBSRWPF=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E6%9C%9F%E9%96%93 aggregated-data-availability-window=%E9%9B%86%E8%A8%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E6%9C%9F%E9%96%93 h_01HE0FT9CPW91ASDH9MEW083ZH=%E9%9B%86%E8%A8%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E6%9C%9F%E9%96%93 h_01HE7S7VH4PC6FQAYKP6A0G4YY=%E5%8F%82%E7%85%A7" />
