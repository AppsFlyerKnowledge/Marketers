---
title: お知らせ：お知らせ：SKANローデータの新しい項目と値 - Data Locker / Push API
metadata:
  keywords:
    - Data Locker
    - Marketers
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2022-12-04T20:34:01Z'
  edited_at: '2026-10-14T09:29:29Z'
  id: 11135475316113
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/11135475316113
---
| **新着情報** | <ul><li>Data LockerとPush APIを介したSKAdNetworkレポートには、SKANバージョン4をサポートするための新しい項目が含まれています：<ul><li>**skad\_postback\_sequence\_index**:値はSKANウィンドウを表す整数で、`0`、`1`、または`2`のいずれかです。SKAN 3の場合：常に0</li><li>**skad\_coarse\_conversion\_value**:値は 、 、 のいずれか。SKAN 3の場合：常に0</li><li>skad\_source\_identifier値は最大4桁の文字列です。SKAN 3の場合：常に0</li><li>skad\_source\_domain値は、アトリビューション可能なWeb広告のソースを表す文字列です。SKAN 3の場合：常に0</li><li>ad\_network\_creative値はアドネットワークから取得したデータの拡充に基づいています。SKAN 3の場合：常に0</li></ul></li><li>メディアソースがMeta広告の場合、すべてのレポートに`Facebook Ads`（Facebookではない）という値が表示されます。</li></ul> |
| --- | --- |
| **発効日** | 2023年1月9日にスキーマの変更が施されます。これらの項目のデータ変更は、AppsFlyer SKANバージョン4リリース（近日リリース予定）の一部として開始されます。 |
| **対象** | 次のレポートに影響があります：<ul><li>SKANバージョン4の新しい項目：<ul><li>skad\_installs （Data LockerおよびPush API経由）</li><li>skad\_redownloads（Data LockerおよびPush API経由）</li><li>skad\_inapps（Data LockerおよびPush API経由）</li><li>**skad\_postbacks**（Data Locker経由）</li><li>skad\_postbacks\_copy （Data Locker経由）（ad\_network\_creative項目は含まれません）</li><li>参照：サンプルレポートスキーマ</li></ul></li><li>Meta広告メディアソース：すべてのレポート</li></ul> |