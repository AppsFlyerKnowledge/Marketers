---
title: お知らせ：AppsFlyer SDK バージョン 6.15以降の新しい広告収益SDK API
metadata:
  keywords:
    - Premium Feature
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-07-24T08:59:01Z'
  edited_at: '2026-10-14T09:34:19Z'
  id: 26956998859153
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/26956998859153
---
| **新着情報** | インプレッションレベルの広告収益は、広告収益 SDK コネクタ経由ではなく、AdRevenue SDK API を使用することで利用できるようになりました。 |
| --- | --- |
| **開始** | AppsFlyer SDK バージョン 6.15 |
| **知っておくべきこと** | <ul><li>これまで、インプレッションレベルの広告収益は、AppsFlyer広告収益SDKの**コネクタ**を介して利用可能でした。上記のSDKバージョン以降は、広告収益SDK APIを使用して、AppsFlyer **SDK**自体（コネクタではありません）で実装する必要があります。</li><li>広告収益SDKコネクタは引き続き以下のバージョンで動作します：<ul><li>AppsFlyer Android SDK バージョン 6.14.2以前</li><li>AppsFlyer iOS SDK バージョン 6.14.6以前</li></ul></li></ul> |
| **必要な対応** | <ul><li>現在、広告収益SDKコネクタを使用していて AppsFlyer SDK バージョン 6.15以降にバージョンアップデートする場合、広告収益SDKコネクタを削除して、広告収益SDK APIを実装する必要があります。</li><li>要開発：開発者向けの実装手順は<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">広告収益SDK APIの説明</Anchor>をご覧ください。</li><li><Anchor target="_blank" href="/marketers/ja/docs/integrate-the-roi360-ad-revenue-sdk-api">インプレッションレベルの広告収益SDK API連携</Anchor>について詳しくは、こちらをご覧ください。</li></ul> |