---
title: ［Closed beta機能］Protect360｜不正対策アシスタント「Val」による分析結果の活用
metadata:
  keywords:
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-06-23T14:26:18Z'
  edited_at: '2026-10-28T08:58:25Z'
  id: 36467082193553
  locale: ja
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ja/articles/36467082193553
---
> **概要：** Valは、Protect360に搭載された、不正の予防に役立つアシスタントです。週次で分析結果を提供し、傾向の把握や推奨される対応の確認、不正対策の強化を支援します。 Valは、具体的な対応につながる分析結果を提示することで、不正発生後の対処から、先回りした不正対策への転換を支援します。

<div id="about-val-anti-fraud-assistant" />

## 不正対策アシスタント「Val」とは

Valは、直近のトラフィックの傾向を自動分析し、潜在的な不正リスクを見つけるProtect360の機能です。週次の分析結果を通じて、傾向の把握、推奨される対応の確認、基準値との比較ができます。これにより、不正の削減、セキュリティの強化、パフォーマンスの最適化を支援します。

広告主は、Valを使用して以下の対応ができます。

* アドネットワークを横断して、不正の急増を調査する。
* 古いSDKバージョンや、脆弱性のあるSDKバージョンを検出する。
* 不正対策の検証ルールを改善する。
* 分析済みのデータに基づいて、すぐに対応する。

注意：パートナーは分析結果を利用できません。

<div id="insight-types" />

## 分析結果の種類

Valは、以下の種類の分析結果と対応の選択肢を提供します。分析結果に基づいて、不正検知とセキュリティ全体の改善に直接取り組めます。

| 分析結果の種類 | 説明 | 実行できる対応 |
| --- | --- | --- |
| **不正の急増・急減** | <ul><li>特定のアドネットワークや流入元で、不正が異常に増加または減少している状況を示します。</li><li>アプリ単位で不正の傾向を比較分析し、その変化が想定内のものか、異常なものかを判断するための情報を提供します。</li></ul> | <ul><li>Protect360のダッシュボードで、さらに詳しく調査する。</li><li>分析結果をPNG画像として共有する。</li><li>分析結果を1週間非表示にする。</li></ul> |
| **古いSDKバージョン** | 1年以上前のSDKを使用しているアプリを検出します。こうしたSDKには最新の不正対策が備わっていない可能性があり、不正攻撃を受けやすくなります。 | <ul><li>SDKの更新について詳しく確認する。</li><li>分析結果をPNG画像として共有する。</li><li>分析結果を1週間非表示にする。</li></ul> |
| **不正率の高いSDKバージョン** | 不正率が高いことが確認されているSDKバージョンからのトラフィックを特定し、アプリバージョン別に表示します。 | <ul><li>検証ルールの設定ページを開く。</li><li>分析結果をPNG画像として共有する。</li><li>分析結果を1週間非表示にする。</li></ul> |

<div id="how-val-works" />

## Valの仕組み

Explore Insightsは毎週、過去7～14日間のトラフィックを分析します。特に関連性の高い異常や脆弱性のみを、分析結果として提示します。優先順位を付ける仕組みにより、各分析結果が有用な情報となるようにしています。

注意：分析結果は毎週月曜日に生成され、過去7～14日間のトラフィックデータが対象となります（UTC基準）。

分析結果を適切な期間表示するため、以下のルールに従って表示・削除されます。

| 期間・状態 | 動作 |
| --- | --- |
| 1～7日目 | 非表示にしない限り、分析結果は毎日表示されます。 |
| 8日目 | 分析結果は自動的に削除されます。 |
| 非表示にした場合 | 新たな問題が検出されない限り、分析結果は再表示されません。 |

注意：一度非表示にした分析結果は、その週の間は再表示されません。

<div id="how-to-access-and-use-explore-insights-val" />

## 分析結果を確認する方法とExplore Insights（Val）の使い方

1. 分析結果を確認するには、Protect360ページ右上の<strong>分析結果を確認（Explore Insights）</strong>ボタンをクリックします。
2. <Image align="center" alt="Screenshot 2025-07-27 at 15.51.34.png" src="https://files.readme.io/7fafbd4b22ac860913ff452b81c659cff77170fc400ec8e1f4939e0e2fe1410c-37563710382225.png" width="1962px" />
3. 分析結果に対して対応するには、<strong>対応する（Take action）</strong>ボタンをクリックします。  
   実行できる対応は、[分析結果の種類](/docs/closed-beta-protect360-explore-insights-with-val-anti-fraud-assistant#分析結果の種類)に記載されています。
4. 左右の矢印をクリックすると、前後の対応項目に切り替えられます。
5. 対応項目の下にあるウィジェットには、判断に役立つ情報が表示されます。

<Image align="center" alt="image (11).png" src="https://files.readme.io/0b3d88e18897b7f38c1f70c779e7e5cdcf09565fb5cb7bdc6d9d72309d58e6ad-37563710384529.png" width="1060px" />

<div data-zendesk-anchors="about-val-antifraud-assistant=%E4%B8%8D%E6%AD%A3%E5%AF%BE%E7%AD%96%E3%82%A2%E3%82%B7%E3%82%B9%E3%82%BF%E3%83%B3%E3%83%88val%E3%81%A8%E3%81%AF h_01JYEJW1KXSVXXRA1ZDQQZZ46W=%E4%B8%8D%E6%AD%A3%E5%AF%BE%E7%AD%96%E3%82%A2%E3%82%B7%E3%82%B9%E3%82%BF%E3%83%B3%E3%83%88val%E3%81%A8%E3%81%AF insight-types=%E5%88%86%E6%9E%90%E7%B5%90%E6%9E%9C%E3%81%AE%E7%A8%AE%E9%A1%9E h_01JYEJW1M0DT985B1GARTFBPMQ=%E5%88%86%E6%9E%90%E7%B5%90%E6%9E%9C%E3%81%AE%E7%A8%AE%E9%A1%9E how-val-works=val%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF h_01JYEJW1M8CFEKZBHBE70AQD4G=val%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF how-to-access-and-use-explore-insights-val=%E5%88%86%E6%9E%90%E7%B5%90%E6%9E%9C%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95%E3%81%A8explore-insightsval%E3%81%AE%E4%BD%BF%E3%81%84%E6%96%B9 h_01JYEJW1MGP0FMS24GVBYJ890R=%E5%88%86%E6%9E%90%E7%B5%90%E6%9E%9C%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95%E3%81%A8explore-insightsval%E3%81%AE%E4%BD%BF%E3%81%84%E6%96%B9" />
