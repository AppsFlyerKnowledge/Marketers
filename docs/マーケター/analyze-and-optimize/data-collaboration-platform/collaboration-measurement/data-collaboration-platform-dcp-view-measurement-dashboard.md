---
title: Data Collaboration Platform（DCP）｜計測ダッシュボード
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2025-04-03T11:06:11Z'
  edited_at: '2026-10-14T09:23:49Z'
  id: 34052274677905
  locale: ja
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/ja/articles/34052274677905
---
> **概要：** グラフやテーブルを使って、キャンペーンのパフォーマンスや推移を分析できます。

計測ダッシュボードでは、キャンペーンのパフォーマンスを確認・分析できます。 パフォーマンスKPI、期間ごとの推移、インプレッションやクリック、収益など、さまざまな指標を確認できます。

<div id="the-measurement-dashboard" />

## 計測ダッシュボード

<Image align="center" alt="" src="https://files.readme.io/a69a72f87bbe6290548e52dea810d774ad09618ec1540bfb00db42e62d52f382-44443401136017.png" />

ダッシュボードは、以下の要素で構成されています。

<div id="a-filter-bar" />

<Accordion title="A - 計測パネル">

ダッシュボードパネル（**B**）に表示する計測データを選択します。現在進行中のライブダッシュボード、または過去に設定した履歴ダッシュボードを表示できます。ライブダッシュボードと履歴ダッシュボードについて詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-run-and-manage-measurement#about-measurement-run-modes">計測の実行モードについて</Anchor>を参照してください。

</Accordion>

<div id="h_01KJWV7PG61YPCBMG2X3NGZN96" />

<Accordion title="B - ダッシュボードパネル">

計測パネル（**A**）で選択したダッシュボードが表示されます。このパネルでは、ダッシュボードの編集、複製、再実行のほか、共同作業者への共有も行えます。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-run-and-manage-measurement#計測の管理">［計測の管理］</Anchor>を参照してください。

</Accordion>

<div id="h_01KJWTTFECN74QDZ7GB2JCA9F5" />

<Accordion title="C - フィルタバー">

アトリビューションの対象期間や、表示内容を絞り込むフィルタを設定します。

**アトリビューション期間**

アトリビューションが発生した日付の範囲。

**フィルター**

デフォルトでは、以下の項目で絞り込めます。

* メディアソース
* キャンペーン

</Accordion>

<div id="b-kpi-headline-metrics" />

<Accordion title="D - KPIサマリー">

<table><thead><tr><th>指標</th><th>選択した期間における内容</th></tr></thead><tbody><tr><td colspan="2"><strong>キャンペーンファネル</strong></td></tr><tr><td>インプレッション</td><td>広告がユーザーに表示された回数の合計</td></tr><tr><td>クリック</td><td>広告がクリックされた回数の合計</td></tr><tr><td>非オーガニックコンバージョン</td><td>通常、クリックやインプレッションを経て、非オーガニックのメディアソースにアトリビューションされた新規コンバージョン</td></tr><tr><td>クリック率（CTR）</td><td>クリック数 ÷ インプレッション数</td></tr><tr><td>コンバージョン率</td><td>コンバージョン数 ÷ クリック数</td></tr><tr><td colspan="2"><strong>コンバージョン / アイテム / 収益</strong></td></tr><tr><td>非オーガニックコンバージョン</td><td>通常、クリックやインプレッションを経て、非オーガニックのメディアソースにアトリビューションされた新規コンバージョン</td></tr><tr><td>オーガニックコンバージョン</td><td>事前にメディアソースとの接点がなかったユーザーによる新規コンバージョン</td></tr><tr><td>総コンバージョン数</td><td>選択した期間に発生した、オーガニックと非オーガニックを合わせた新規コンバージョンの総数（総コンバージョン数 = 非オーガニックコンバージョン + オーガニックコンバージョン）</td></tr><tr><td>アイテム</td><td>コンバージョンイベントに紐づくアイテム数の合計。非オーガニック、オーガニック、合計の内訳で表示されます。</td></tr><tr><td>収益</td><td>コンバージョンイベントによって発生したイベント収益の合計。非オーガニック、オーガニック、合計の内訳で表示されます。</td></tr><tr><td colspan="2"><strong>コスト指標</strong></td></tr><tr><td>コスト</td><td>メディアソース、キャンペーン、地域ごとに集計した1日あたりの広告費。通貨単位とあわせて表示されます。</td></tr><tr><td>ROAS</td><td>アトリビューションされた収益をコストで割った値。（アトリビューション収益 ÷ コスト）</td></tr><tr><td>CPC</td><td>クリック1回あたりのコスト。広告費 ÷ クリック数。通貨単位とあわせて表示されます。</td></tr><tr><td>CPM</td><td>1,000インプレッションあたりのコスト。（広告費 ÷ 1,000インプレッション）通貨単位とあわせて表示されます。</td></tr><tr><td>CPA</td><td>アクション1件あたりのコスト。（広告費 ÷ アトリビューションされたコンバージョン数）通貨単位とあわせて表示されます。</td></tr></tbody></table>

</Accordion>

<div id="c-view-charts" />

<Accordion title="E - チャート">

<div id="performance-comparison-charts" />

### **パフォーマンス比較チャート**

<Image align="center" alt="" src="https://files.readme.io/85949b56375db9d94ff749159f25d75cb01deee1c2499cbdc497cdfd42a24976-34052274670097.png" />

**表示設定**

（a）ディメンションと指標

<div id="trend-over-time-comparison" />

### **時系列トレンド比較**

<Image align="center" alt="" src="https://files.readme.io/703f0a9ce0a54399a5d36f29119ab99b5f6b2d975781fb9ec4fbb9558af8d761-34052246603665.png" />

**表示設定**：

（a）ディメンションと指標

（b）表示するディメンション：必要に応じて、フィルタバーから選択します。

</Accordion>

<div id="d-impression-and-clicks-chart" />

<Accordion title="F - インプレッションとクリックのチャート">

クリック数とインプレッション数の推移を時系列で比較できます。

</Accordion>

<div id="e-campaign-performance-table" />

<Accordion title="G - キャンペーンパフォーマンステーブル">

メディアソースごとのKPI指標をテーブルで確認できます。

</Accordion>

<div data-zendesk-anchors="the-measurement-dashboard=%E8%A8%88%E6%B8%AC%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89 h_01JQXNG58SQR32CZXQR5RZK3V9=%E8%A8%88%E6%B8%AC%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89 h_01JQXNG58SRY4FP8EP2F50KK1Q=a-filter-bar h_01JQXNG58SG2JF5J39RDKF8ZM8=b-kpi-headline-metrics h_01JQXNG58S23E1PKFVQEBVFVJ0=c-view-charts performance-comparison-charts=%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E6%AF%94%E8%BC%83%E3%83%81%E3%83%A3%E3%83%BC%E3%83%88 h_01JQXNV0RXS8R5VFGG9VJX547R=%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E6%AF%94%E8%BC%83%E3%83%81%E3%83%A3%E3%83%BC%E3%83%88 trend-over-time-comparison=%E6%99%82%E7%B3%BB%E5%88%97%E3%83%88%E3%83%AC%E3%83%B3%E3%83%89%E6%AF%94%E8%BC%83 h_01JQXNV749GCD6M7TM4CVVDWN7=%E6%99%82%E7%B3%BB%E5%88%97%E3%83%88%E3%83%AC%E3%83%B3%E3%83%89%E6%AF%94%E8%BC%83 h_01JQXNG58SWYQFYQ1EANYXE1XF=d-impression-and-clicks-chart h_01JQXNG58S3J48SQZDQMVJZAPS=e-campaign-performance-table" />
