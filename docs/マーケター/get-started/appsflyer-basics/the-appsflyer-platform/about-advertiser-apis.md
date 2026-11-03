---
title: 広告主向けAPIについて
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-05-24T15:14:53Z'
  edited_at: '2026-10-21T18:44:40Z'
  id: 360009122638
  locale: ja
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/ja/articles/360009122638
---
> **概要：** 広告主がデータの取得や更新に利用できるAPIについて説明します。

## 広告主向けAPIとインターフェース

<span id="01EEQJERAWW3HY59HVPY3YWA0B"></span>レポート、レポートツール、レポートAPIの詳細については、以下を参照してください。

* <span id="01EEQJERAW2ZTBWBQKBCDSC76Z"></span><span id="01EEQJERAWQ2WCPV0207XM6FR4"></span><span id="01EEQJERAX0W7RCYQWVM2M5S13"></span>ローデータレポートのツール／API
* <span id="01EEQJERAWA09P200SGR985846"></span><span id="01EEQJERAW6AC6WR7E46T5DMHW"></span>集計・分析レポートのツール／API

#### 広告主向けインターフェース

| 分野 | API名 | プレミアム機能 | 説明 | 認証  <br />トークン／キー | インターフェースの種類 |
| --- | --- | --- | --- | --- | --- |
| モバイルアトリビューション | サーバー間（S2S）イベント | いいえ | モバイルアプリ外で発生したアプリ内イベントを記録 | SDK Dev Key | REST API |
| People-based Attribution（PBA） | サーバー間（S2S）Web | いいえ | バックエンドで発生したPBAイベントをレポート | PBAキー | REST API |
| エンゲージメント | OneLink | はい | OneLinkの作成、更新、取得、削除 | SDK Dev Key | REST API |
| リマーケティング | Audiences | はい | ユーザーリストをAudiencesへアップロード | Import Key | REST API |
| プライバシー | openDSRリクエスト | いいえ | データ削除リクエストの送信とステータス確認 | V2.0 | REST API |
| レポート | マスターパフォーマンスKPI | はい | 複数アプリのキャンペーンパフォーマンス指標をCSVファイルで取得 | V2.0 | REST API |
| レポート | 集計レポートの取得 | いいえ | 集計レポートをCSVファイルで取得 | V2.0 | REST API |
| レポート | ローデータの取得 | はい | ローデータレポートをCSVファイルで取得 | V2.0 | REST API |
| レポート | コホート分析 | はい | コホート指標をJSONまたはCSVファイルで取得 | V2.0 | REST API |
| レポート | Data Locker | はい | ローデータおよび集計データのレポート | 該当なし | クラウドストレージ |
| モバイルアトリビューション | Push API | はい | リアルタイムのインストールおよびアプリ内イベントを広告主のサーバーへ送信 | 該当なし | REST API |
| キャンペーンコスト | Cost Import | いいえ | キャンペーンコストをレポート | 該当なし | ファイルアップロード |
| アカウント | アプリ一覧の取得 | いいえ | アカウント内のアプリ一覧を取得 | V2.0 | REST API |
| レポート | ETL Cost | はい | Cost ETLで詳細なキャンペーンコストデータを取得 | 該当なし | クラウドストレージ |
| レポート | SKANレポート | いいえ | SKANの集計レポート | V2.0 | REST API |
| 連携済みパートナー | パートナー連携設定をコピー | いいえ | あるアプリの連携設定パラメーターを別のアプリへコピー | V2.0 | REST API |
| 連携済みパートナー | Install Referrer復号キーを設定 | いいえ | Meta広告から受信したInstall Referrer復号キーを設定 | V2.0 | REST API |

<div data-zendesk-anchors="advertiser-api-list-and-interfaces=%E5%BA%83%E5%91%8A%E4%B8%BB%E5%90%91%E3%81%91api%E3%81%A8%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%BC%E3%83%95%E3%82%A7%E3%83%BC%E3%82%B9 h_01HX9638DX6EHR4ETMSH10K68F=%E5%BA%83%E5%91%8A%E4%B8%BB%E5%90%91%E3%81%91api%E3%81%A8%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%BC%E3%83%95%E3%82%A7%E3%83%BC%E3%82%B9 interfaces-for-advertisers=%E5%BA%83%E5%91%8A%E4%B8%BB%E5%90%91%E3%81%91%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%BC%E3%83%95%E3%82%A7%E3%83%BC%E3%82%B9 h_01HX9638DXNJM3A968A2PSRRKS=%E5%BA%83%E5%91%8A%E4%B8%BB%E5%90%91%E3%81%91%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%BC%E3%83%95%E3%82%A7%E3%83%BC%E3%82%B9" />
