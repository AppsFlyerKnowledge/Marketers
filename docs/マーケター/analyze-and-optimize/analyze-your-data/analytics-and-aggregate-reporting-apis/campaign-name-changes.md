---
title: キャンペーン名の変更
metadata:
  keywords:
    - Aggregated Data
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2023-03-26T10:56:19Z'
  edited_at: '2026-10-14T09:39:41Z'
  id: 14038324952465
  locale: ja
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ja/articles/14038324952465
---
> **概要：** 重複したデータ表示を作成せずにキャンペーンの名前を変更します。

## キャンペーン名の変更

キャンペーンの名前を変更すると、管理画面およびレポートでの**集約データ**の表示に影響します。AppsFlyer では、キャンペーン ID をキーとして、キャンペーンを表示します。同じキャンペーン ID に関連付けられた名前が複数ある場合、直近に報告された名前がデータの表示に使用されます。

* この記事では**キャンペーン**の名前の変更を参照していますが、アドセットと広告名の変更にも同じルールが適用されます。
* 名前の変更は、インストール、アプリ内イベント、コスト、収益など、キャンペーンに接続されているすべてのデータの表示に影響します。
* ほとんどのアドネットワークでは、キャンペーン名の変更がサポートされていますが、一部のアドネットワークではサポートされていません。これらのアドネットワークでは、同じデータを持つ重複行が表示される場合があります。
* ローデータは名前の変更の影響を受けません。

次の表には、キャンペーン名の変更をサポートしている管理画面とレポートが示されています。

| 管理画面/レポート | キャンペーン名の変更のサポート |
| --- | --- |
| オーバービュー管理画面 | はい、CTV ビューを除く |
| アクティビティ管理画面 | はい |
| コホートダッシュボード | はい |
| コホートAPI | はい |
| プルAPI | プルAPI V5 以下ではサポートされません |
| ピボット管理画面 | いいえ |
| カスタム管理画面 | いいえ |
| リテンション管理画面 | いいえ |
| アプリ内イベント管理画面 | いいえ |
| Protect360 管理画面 | いいえ |
| コストETL | はい |
| SKAN 概要管理画面 | いいえ |

> 📄 **例**
>
> * 1月1日：**example\_a1** というキャンペーン名で配信開始。
> * 1月2日：キャンペーン名を**example\_a1** から**example\_a2** に変更。
>
> #### キャンペーンのデータ例
>
>
>
> | 日付 | キャンペーン名 | Campaign ID | インストール | 広告費 |
> | --- | --- | --- | --- | --- |
> | 1月1日 | example\_a1 | 123 | 100 | 2024-02-26 |
> | 1月2日 | example\_a2 | 123 | 200 | 2024-02-26 |
>
>
>
> #### 管理画面表示の概要
>
>
>
> <table><tbody><tr><th><p><span>Campaign</span></p></th><th><p><span>Campaign ID</span></p></th><th><p><span>インストール</span></p></th><th><p><span>広告費</span></p></th></tr><tr><td><p><span>example_a2</span></p></td><td><p><span>123</span></p></td><td><p><span>300</span></p></td><td><p>2024-02-26</p></td></tr><tr><td colspan="4"><p>結果:最新のキャンペーン名の下にデータが表示されます。</p></td></tr></tbody></table>

### ベストプラクティス

* ほとんどのアドネットワークでは、キャンペーン名の変更がサポートされていますが、一部のアドネットワークではサポートされていません。これらのアドネットワークでは、同じデータを持つ重複行が表示される場合があります。このような表示の異常を回避するには、キャンペーンに一意のキャンペーンID が割り当てられている必要があります。
* 同じキャンペーン名を異なるキャンペーンID で使用しないでください。
* 同じ広告名を異なる広告 ID で使用しないでください。

<div data-zendesk-anchors="rollout-details=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E5%90%8D%E3%81%AE%E5%A4%89%E6%9B%B4 h_01HW896QQ2T4J0N5PDY6YFTJ49=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E5%90%8D%E3%81%AE%E5%A4%89%E6%9B%B4 h_01HW896QQ34YVGF6P212ZHAQHG=%E4%BE%8B example-campaign-data=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E4%BE%8B h_01HW896QQ3G07XM06HR2CRXA3G=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E4%BE%8B overview-dashboard-display-before-the-behavior-change=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E8%A1%A8%E7%A4%BA%E3%81%AE%E6%A6%82%E8%A6%81 h_01HW896QQ3J9NE9GZRKKAPX46B=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E8%A1%A8%E7%A4%BA%E3%81%AE%E6%A6%82%E8%A6%81 best-practice=%E3%83%99%E3%82%B9%E3%83%88%E3%83%97%E3%83%A9%E3%82%AF%E3%83%86%E3%82%A3%E3%82%B9 h_01HW896QQ4RAQ51GPD17YYZBJF=%E3%83%99%E3%82%B9%E3%83%88%E3%83%97%E3%83%A9%E3%82%AF%E3%83%86%E3%82%A3%E3%82%B9" />
