---
title: お知らせ：OneLinkのショートURLの有効期限の自動延長
metadata:
  keywords:
    - OneLink
    - User invite
    - OneLink API
    - Developers
    - Marketers
    - bulk upload
    - Link Management
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2022-03-10T11:17:11Z'
  edited_at: '2026-10-14T09:29:04Z'
  id: 4667188714001
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/4667188714001
---
| **変更点** | 一括アップロード、SDKユーザー招待API もしくはOneLink APIで作成されたOneLinkショートURLのデフォルトのTTL（Time To Live）は、リンクがクリックされるたびに延長されます。<ul><li>365日間</li><li>SDKユーザー招待計測：60日間</li><li>OneLink API：31日間</li></ul> |
| --- | --- |
| **発効日** | 2024年1月14日 |
| **対象：** | <ul><li>OneLink一括アップロード</li><li>ユーザー招待リンク（SDKから生成されたOneLink URL）</li><li>OneLink API</li></ul> |
| **変更点** | 変更前：一括アップロード、SDKユーザー招待API、OneLink APIで作成されたOneLinkショートURLには、TTL（Time To Live）- 動作する有効期限が設定されていました。TTLが切れた後、リンクは意図したとおりに機能しなくなり、アトリビューションデータも提供されなくなりました。<br /><br />**変更後：** 一括アップロード、SDKユーザー招待API、OneLink APIで作成されたOneLinkショートURLのTTLが延長されました。ただし、リンクがクリックされるたびにTTLが延長されます。<ul><li>365日間</li><li>SDKユーザー招待計測：60日間</li><li>OneLink API：31日間</li></ul> |
| **お知らせ事項** | <ul><li>この変更は、TTLを持つ新規および既存のOneLinkショートURLに影響します。</li><li>OneLink APIの場合：<ul><li>パラメータ `ttl={value}` を追加し、何日、何時間、何分と指定することで、デフォルトのTTLを変更することができます。　例：`ttl=7d`, `ttl=12h`, or `ttl=10m`.</li></ul></li><li>OneLink API & 一括アップロードの場合：<ul><li>リンクのTTLを自動的に延長させたくない場合は、パラメータ `renew_ttl=false` をリンクに追加してください。<br />**注：**<ul><li>パラメータ `renew_ttl` は、実際のURLには表示されません。</li><li>OneLink APIの場合、値はbooleanであり、true（デフォルト）またはfalseのいずれかです。</li></ul></li></ul></li></ul> |