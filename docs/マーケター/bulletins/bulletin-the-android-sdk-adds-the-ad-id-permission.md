---
title: お知らせ：お知らせ：Android SDKによるAD_IDアクセス許可を追加
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-07-12T08:57:45Z'
  edited_at: '2026-10-14T09:28:21Z'
  id: 7569900844689
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/7569900844689
---
> **概要：** AppsFlyer Android SDK V6.8.0 以降、AD\_IDのアクセス許可がSDKの AndroidManifest.xml で宣言されています。

| **背景** | 2022年初頭、GoogleはGoogle Playサービスの動作の変更とAndroid広告IDの取得に関して新たなアップデートを発表しました。<br /><br /><Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6048248?hl=en">発表</Anchor>によると、Android 13 (API 33) 以上をターゲットとするアプリは、デバイスの広告IDにアクセスするために、マニフェストファイルでGoogle Playサービスの通常のアクセス許可を宣言する必要があります。<br /><br />アクセス許可はインストール時にアプリに付与され、ユーザーの操作はトリガーされません。 |
| --- | --- |
| **変更点** | AppsFlyer Android SDK V6.8.0 以降、AD\_IDのアクセス許可がSDKの AndroidManifest.xml で宣言されています。アプリがビルドされると、SDKのマニフェストが既定でアプリのマニフェストとマージされ、アプリがアクセス許可を明示的に宣言していない場合でもアクセス許可が追加されます。アプリとSDKの両方にアクセス許可が存在する場合、これは正常に動作し、競合はありません。 |
| **お知らせ事項** | <ul><li>SDK V6.8.0 を使用していて、アプリのマニフェストでAD\_IDアクセス許可を持っている場合は、必要に応じてマニフェストから削除し、SDK に追加させることができます。</li><li>V6.8.0 **より前** のバージョンのSDKを使用していて、アプリが Android 13 (API 33) 以上をターゲットにしている場合は、SDK が広告 ID にアクセスできるように、アプリにAD\_IDのアクセス許可を追加する必要があります。</li><li>子ども向けアプリ - FAQキッズアプリ： Googleのポリシー/strong>によると、子供をターゲットにしたアプリは広告 ID を送信してはなりません。子ども向けのアプリを構築していて、SDK V6.8.0 以降を使用している場合は、AD\_IDのアクセス許可を取り消す必要があります。こちらの開発者向けの手順を参照してください。</li></ul> |