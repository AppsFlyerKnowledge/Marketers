---
title: お知らせ：ローデータレポートにおけるDMA対応
metadata:
  keywords:
    - Marketers
    - Raw Reports
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2024-05-29T16:52:12Z'
  edited_at: '2026-10-14T09:37:28Z'
  id: 25485269115793
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/25485269115793
---
| **新着情報** | 次のDMA同意フィールドがAppsFlyerのローデータツールに追加されました：<ul><li>gdpr\_appliesユーザがDMA管轄に該当するか（true）、否か（false）を示します。</li><li>**ad\_user\_data\_enabled**:ユーザーが、計測およびパーソナライズされた広告にGoogleがユーザーレベルのデータを使用できるようにすることに同意したか（true）、否か（false）を示します。</li><li>**ad\_personalization\_enabled**:ユーザが、Googleがパーソナライズ広告にユーザレベルのデータを使用できるようにすることに同意しているか（true）、否か（false）を示します。</li><li>**raw\_consent\_data**: 広告主からAppsFlyerに送信された完全な未処理の同意データを持つJSON オブジェクトを返します。このオブジェクトで送信された情報は、上記の3つのフィールドに入力するために使用されます。<ul><li>この項目は、ローデータ出力画面およびPull APIでは使用できません。</li></ul></li></ul> |
| --- | --- |
| **発効日** | <ul><li>ローデータ出力画面とPull API - 2024年6月3日</li></ul> |
| **対象** | <ul><li>ローデータ出力画面</li><li>Pull API</li><li>Push API</li><li>Data Locker</li></ul> |
| **誰が知るべきか** | <ul><li>ローデータ出力画面、Push API、Pull API、Data Lockerを使用してローデータ（イベントレベル）を出力している広告主および代理店</li></ul> |
| **影響範囲** | <ul><li>スキームと、データの消費に関連するその他のプロセスを設定してください。</li><li>新しい項目が、Push API およびData Lockerのスキームを壊さないように構築してください。</li></ul> |
| **追加情報** | 詳細：<Anchor target="_blank" href="/marketers/ja/docs/support-google-eu-consent-policy">Google EUの同意ポリシー</Anchor> |