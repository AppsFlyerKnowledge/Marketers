---
title: お知らせ：Apple AdsがSKANアトリビューションに対応
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2025-04-15T08:21:59Z'
  edited_at: '2026-10-14T09:21:54Z'
  id: 34395758837137
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/34395758837137
---
| **更新情報** | 以前はApple Search Adsと呼ばれていたApple Ads（AA）が、**SKANポストバックコピー**を介してSKANアトリビューションに含めることができるようになりました。アプリは、AppleからAppsFlyerにApple Adsのポストバックを直接転送されるように実装することで、Apple AdsをSKANレポートとアトリビューションロジックに含めることができます。 |
| --- | --- |
| **更新日** | 2025年4月10日 |
| **更新内容** | **Apple Ads SKANデータの入手先**<br /><br />Apple AdsのSKANデータは、<Anchor target="_blank" href="/marketers/ja/docs/skan-raw-data-reports#postback::315d5a62">SKANポストバックコピーのレポート</Anchor>で確認でき、Data Locker、API、管理画面でフルサポートされる予定です。<br /><br />**アトリビューションの変更**：Apple Adsは、以前にSKANで他のネットワークに紐づくインストールのクレジットを受け取ることができます。<br /><br />**データの粒度：** SKANポストバックには、キャンペーンレベルのデータは含まれません。Apple Adsは、キャンペーンIDの項目を使用して、4つのプレースメントのいずれかを反映します：<ul><li>検索結果</li><li>検索タブ</li><li>Todayタブ</li><li>プロダクトページ</li></ul>**対応SKANバージョン：** Apple Adsは **SKAN V1-3**、および**クリックスルー計測**のみに対応しています。SKAN 4は現在対応されていません。<br /><br />**SSOTデータへの影響：** 重複排除ロジックに変更はありません。AppsFlyerの従来の方法で計測されていないApple Adsポストバックが含まれ、残りはSSOTで重複排除されます。 |
| **必要な対応** | AppsFlyerでApple Ads SKANデータを有効にするには、Appleから<Anchor target="_blank" href="/marketers/ja/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">AppsFlyerにSKANポストバック</Anchor>を直接転送するようにアプリ側の実装がされていることを確認してください。<ul><li>すでにアプリで実装されている場合、これ以上の作業は必要ありません。</li></ul>注記：これが機能するには、アプリがiOS 15以降を実行している必要があります。Appleによると、95%以上のユーザーがこの要件を満たしています。 |