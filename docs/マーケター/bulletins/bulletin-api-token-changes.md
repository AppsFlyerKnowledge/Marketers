---
title: お知らせ：
metadata:
  keywords:
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2023-01-23T15:35:25Z'
  edited_at: '2026-10-14T09:32:16Z'
  id: 12399683708305
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/12399683708305
---
| **更新情報** | APIの使用に対してより安全で信頼性の高いエクスペリエンスを提供するために、API URLに含まれていた API V1トークンは非推奨になり、bearer authenticationのヘッダーで渡される JWTベースのトークンである API V2トークンが採用されます。 |
| --- | --- |
| **発効日** | 2022年9月 |
| **前提条件** | 管理者のみが AppsFlyer ダッシュボードから <Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens#トークンの取得">API V2 トークンを取得</Anchor>できます。 |
| **APIトークンを更新する必要があるのは誰ですか？** | APIトークンV1を使用している広告主と代理店の両方がトークンを更新する必要があります。 |
| **API V1 トークンを見つける方法** | AppsFlyer管理画面右上メニュー（メールアドレス） > セキュリティセンター >  <Anchor target="_blank" href="/marketers/ja/docs/audit-log">監査ログ</Anchor> 画面から、まだ使用中の API V1 トークンを確認します。ログデータはCSVファイルにダウンロードできます。<ol><li>監査ログ画面に移動します。</li><li>検索バーに "API Token V1" と入力します。</li><li>**サービス** フィルターで **APIコール**のみを選択し、結果をフィルター処理します。</li><li>ページの右上にある [ダウンロード] アイコンをクリックします。<br />CSVファイルがダウンロードされ、アプリID、使用されているサービス、APIリクエストURLが含まれます。</li></ol> |
| **必要な対応** | **API V2 トークンの次のAPIを更新します：**<ol><li><Anchor target="_blank" href="https://hq1.appsflyer.com/account/api-tokens">API トークンページ</Anchor>に移動します。</li><li>「API トークン V2.0」で、**クリップボードにコピー**アイコンをクリックします。</li><li>次の各APIについて：<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/master_api_get">Master API V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">集約データ Pull API V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">ローデータ Pull API V2</Anchor></li></ul><ol><li>API V1のURLを上記のドキュメントのURLに置き換えます。</li><li>コピーしたトークンをbearer authenticationヘッダーに貼り付けます。<br />![token_v2_bearer.png](https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png)</li><li>`'Authorization': 'Bearer %AuthTokenV2%'`</li></ol></li></ol> |
| **API トークンについて** | **API トークンの詳細については、以下を参照してください：**<ul><li>APIトークンの管理<ul><li>Master API</li><li>集計Pull API</li><li><Anchor target="_blank" href="/marketers/ja/docs/pull-api-raw-data">ローデータ</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/send-opendsr-api-requests#gdprリクエストのフォーマット">OpenDSR API</Anchor></li></ul></li></ul> |