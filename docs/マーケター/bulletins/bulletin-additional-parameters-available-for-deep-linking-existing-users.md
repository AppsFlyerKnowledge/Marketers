---
title: お知らせ：お知らせ：既存ユーザーのディープリンクに使用できる追加パラメーター
metadata:
  keywords:
    - SDK
    - deep link
    - deep linking
    - Developers
    - Marketers
    - OneLink
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2022-04-27T09:49:22Z'
  edited_at: '2026-10-14T09:36:52Z'
  id: 5733303620113
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/5733303620113
---
> **概要：**

| **新着情報** | AppsFlyer SDK V6.6以降では、UDLメソッドで既存ユーザーをディープリンクするための追加のパラメーターを返すことができます（アプリがインストールされている場合）。 |
| --- | --- |
| **発効日** | 2022年4月27日 |
| **対象** | 既存ユーザーをアプリにディープリンクするためのUDLメソッド |
| 詳細 | **変更前：**<br /><br />**変更後：** 変更後： UDLメソッドは、既存のユーザーをディープリンクするための追加のパラメーターを返します （アプリがインストールされている場合）。<ul><li>`path`</li><li>`scheme`</li><li>`host`</li><li>`af_c_id`</li><li>`af_adset`</li><li>`af_adset_id`</li><li>`af_ad`</li><li>`af_ad_id`</li><li>`af_ad_type`</li><li>`af_channel`</li><li>`af_dp`</li><li>`esp_name`</li><li>`link`</li></ul> |
| **お知らせ事項** | **ベストプラクティス** ：<ul><li>この変更は、ディープリンクに従来の方法（GCD API）を使用している既存のリンクを使用しているお客様のみを対象としています。これらのお客様は、ディープリンク用のUDLメソッドを実装し、これらの追加パラメータを使用して既存のユーザーをディープリンクし、同じリンクを引き続き使用できるようになりました。新しいリンクを作成する必要はありません。</li><li>AppsFlyer SDK V6.6以降の実装が必要</li></ul> |