---
title: お知らせ：Meta AdsとGoogle Adsにおける、Web・アプリの統合レポート
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-10-05T12:17:10Z'
  edited_at: '2026-10-14T09:24:32Z'
  id: 39686956300433
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/39686956300433
---
| セクション | 詳細 |
| --- | --- |
| **更新内容** | <ul><li>`metaweb_int`の全ての計測データが、`Facebook Ads`のデータとして報告されます。</li><li>`googleads_int`の全ての計測データが、`googleadwords_int`のデータとして報告されます。</li><li>この変更は、適用日以降に発生した新しいデータのみに影響します。既存の成果の紐づけに対しては遡及的に適用されません。</li><li>この変更は、管理画面上やローデータレポートなど、すべてのレポートツールに適用されます。</li><li>オフィシャルのメディアソース（例：Facebook Ads、googleadwords\_int）への移行は、自動的に**バックエンドで**行われます。</li><li>Meta WebとGoogle Webの完全なWebキャンペーンのコストは、管理画面上とコストETLでそれぞれメインのPID ： `facebook_int` / `googleadwords_int`の下に計測されます。</li></ul> |
| **適用開始日** | 2025年11月2日 |
| **変更理由** | 今回の統合により、特定のネットワーク（例：Meta や Google）のすべてのキャンペーンをまとめて管理し、モバイルと Web のコストを含む包括的なレポーティングを提供します。 |
| **必要な対応** | <ul><li><strong>キャンペーン設定のプロセスに変更はありません。</strong>元々のPID（`metaweb_int` / `googleads_int`）を引き続き使用してください。従来の連携設定を使用することで、該当する Webの連携を通じてAppsFlyerからポストバックを正しく送信できるようになります。</li><li>**ローデータツール**<ul><li>`original_url`の項目には、広告で使用された元々のPIDが表示されます。</li><li>成果の紐づけ先であるメディアソースの項目には、更新後の名称が反映されます。</li></ul></li><li>**Meta WebとGoogle Webのキャンペーンコストを取得**するには、計測リンクにキャンペーンIDを含める必要があります。</li></ul> |
| **ベストプラクティス** | <ul><li>分類を簡単にするため、キャンペーン名にキャンペーンタイプを含めておきましょう。（\_web, \_appなど）</li><li>Webキャンペーンの完全なコストレポートを有効にするには、それぞれのメインの連携（Facebook Ads、googleadwords\_int）の「コスト」タブ内で、アカウントを接続してください。</li></ul> |
| **今後のサポート予定** | <ul><li>AppsFlyerでは、キャンペーンタイプ（アプリまたはWeb）を示す、新しいディメンション（`engagement_platform_group`）を導入する予定です。</li><li>今後、コンバージョンAPIの統合を予定しているPIDは以下です：</li></ul><ul><li>`snapweb_int` → **snapchat\_int**へ統合</li><li>`tiktokweb_int` → **tiktokglobal\_int**へ統合</li><li>`twitterweb_int` → **Twitter**へ統合</li></ul>**<span id="h_01K6T5WZKJ2XP34V3T64TWG153"></span>注意**<br />これらのマッピングはすでに有効化されており、上記のPIDを使った計測は、完全な連携サポート前でも自動的に主要な SRNのPIDへ変換されます。 |