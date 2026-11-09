---
title: ROI360ガイド｜広告費・収益データ
metadata:
  keywords:
    - cost
    - Advertisers
    - Premium
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-11-10T13:52:03Z'
  edited_at: '2026-10-28T08:47:59Z'
  id: 10515748254609
  locale: ja
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/ja/articles/10515748254609
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要**：広告費と収益のデータを取得し、ROIとROASの全体像を把握します。

<Image align="center" alt="M_emptyState.png" src="https://files.readme.io/5eec5be77bf0b72afdd95b1957642cc67ba509000bc756ac68d87da5e96ed08e-11832563913489.png" />

<div id="overview" />

## 概要

ROI360は、広告費と収益のレポートに特化したツール群で、高精度のデータを可能な限り迅速に提供します。

広告費と収益の両方のデータから、広告費用対効果（ROAS）と投資利益率（ROI）の全体像を把握できます。

<div id="cost-tools" />

### 広告費関連ツール

ROI360の広告費関連ツール（旧称：Xpend）は、広告費データの集計とレポート作成を行います。以下の表に、利用できる広告費関連のツールと機能をまとめています。各機能の詳細は、リンクをクリックして確認してください。

<table><thead><tr><th>ツール</th><th>説明</th></tr></thead><tbody><tr><td><a href="./roi360-cost-aggregation-overview" target="_blank">アトリビューションに紐づく広告費</a></td><td><p><span>アトリビューション、クリック、インプレッションに紐づく広告費データを、取得できる最も詳細な単位で提供します。</span></p><p><span>80を超えるAPI連携に対応しており、グローバルに展開するアドネットワークや、地域に特化したアドネットワークと簡単に連携できます。</span></p></td></tr><tr><td><a href="./import-cost-data" target="_blank">ファイルのインポート</a></td><td><span>コストインポートを使用して、API経由で取得していない広告費データを記録します。</span></td></tr><tr><td><a href="./incorporate-agency-fees-into-campaign-costs" target="_blank">代理店手数料</a></td><td><span>代理店手数料を計算し、広告費に含めます。</span></td></tr><tr><td><a href="./set-up-and-use-roi360-cost-etl-reports" target="_blank">コストETL\*</a></td><td>1日4回更新されるキャンペーンの広告費データを、広告主のBIシステムに取り込める形式で、AWS S3またはGCSのバケットに配信します。</td></tr><tr><td colspan="2">\* ROI360 Advancedプランで利用可能</td></tr></tbody></table>

**注意**：ROI360を利用していない場合も、<Anchor target="_blank" href="/marketers/ja/docs/view-aggregated-cost-data-for-attribution-links">アトリビューションリンクで送信される広告費データ</Anchor>を集計できます。ただし、この方法はCPIの課金モデルのみに対応しており、CPA、CPC、CPMなどのモデルには対応していません。

<div id="revenue-tools" />

### 収益関連ツール

ROI360の収益関連ツールは、アプリ内課金、サブスクリプション、広告収益のデータを集計し、レポートを作成します。税金やアプリストアの手数料も収益指標に反映されます。 以下の表に、利用できる収益関連のツールと機能をまとめています。各機能の詳細は、リンクをクリックして確認してください。

<table><thead><tr><th>ツール</th><th>説明</th></tr></thead><tbody><tr><td><a href="./purchase-and-subscription-validation-overview" target="_blank">アプリ内課金</a></td><td><span>検証済みのアプリ内課金を自動的にレポートします。返金やキャンセルなど、購入後に発生する取引のデータも含まれます。</span></td></tr><tr><td><a href="./purchase-and-subscription-validation-overview" target="_blank">サブスクリプション収益</a></td><td><span>変更、キャンセル、ファミリー共有を含む、サブスクリプションの情報を自動的にレポートします。</span></td></tr><tr><td><a href="./roi360-guide-ad-revenue-attribution" target="_blank">広告収益</a></td><td>APIまたはSDK経由で連携する20を超える広告収益パートナーに対応し、正確かつ最新のデータを取得できます。</td></tr><tr><td> <a href="./revenue-etl-reports" target="_blank">収益ETL</a>\*</td><td>収益データを、広告主のBIシステムに取り込める形式で、AWS S3またはGCSのバケットに配信します。</td></tr><tr><td colspan="2">\* ROI360 Advancedプランで利用可能</td></tr></tbody></table>

**注意**：ROI360に含まれない、基本的な収益計測ツールもあります。これらのツールは、ROI360に含まれるツールと異なり、開発者による多くの設定作業が必要です。

* <Anchor target="_blank" href="/marketers/ja/docs/about-receipt-validation">アプリ内課金のレシート検証</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/purchase-and-subscription-validation-overview">サブスクリプション収益の計測</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/roi360-revenue-attribution-overview">独自のアプリ内イベントによる収益の記録</Anchor>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HKHGX9JJQQCKF9SDZRSCM1XJ=%E6%A6%82%E8%A6%81 cost-tools=%E5%BA%83%E5%91%8A%E8%B2%BB%E9%96%A2%E9%80%A3%E3%83%84%E3%83%BC%E3%83%AB h_01HKHGX9JJRWDP9PMYP9CFA7MQ=%E5%BA%83%E5%91%8A%E8%B2%BB%E9%96%A2%E9%80%A3%E3%83%84%E3%83%BC%E3%83%AB revenue-tools=%E5%8F%8E%E7%9B%8A%E9%96%A2%E9%80%A3%E3%83%84%E3%83%BC%E3%83%AB h_01HKHGX9JJFQ9ZM6J3B2D5G6C5=%E5%8F%8E%E7%9B%8A%E9%96%A2%E9%80%A3%E3%83%84%E3%83%BC%E3%83%AB" />
