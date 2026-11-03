---
title: お知らせ：プリロードリファラー計測のパラメータ変更に関して
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-15T10:47:47Z'
  edited_at: '2026-10-14T09:29:17Z'
  id: 20161765461009
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/20161765461009
---
| **変更内容** | 適用日以降に記録された新規インストール、およびそれらの新規インストールに紐づくアプリ内イベント・セッションについて、プリロードリファラーのアトリビューションパラメータのレポート方法が変更されます。<br /><br />以下が、プリロードリファラーのアトリビューションパラメータに関する変更点です。<ul><li>**attributed\_touch\_type**：preload または click\_to\_download ではなく、**download** としてレポートされます<ul><li>**engagement\_type**：preload\_rfr のマッチタイプの場合：**preload**、af\_referrer のマッチタイプの場合：**click\_to\_download**としてレポートされます。</li></ul></li></ul>一方、適用日より前にインストールされたユーザーに紐づくアプリ内イベント・セッションについては、従来の挙動が維持されます。<ul><li>**attributed\_touch\_type**：**preload** または **click\_to\_download**<ul><li>**engagement\_type**：**空欄**（値なし）</li></ul></li></ul> |
| --- | --- |
| **適用日** | 2024年1月17日 |
| **影響対象** | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/set-up-appsflyer-preload-referrer-attribution">AppsFlyerのプリロードリファラー計測</Anchor>を利用している 広告主および代理店</li><li>変更箇所：ローデータレポートとダッシュボード</li></ul> |