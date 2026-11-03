---
title: お知らせ： 初回インストールアトリビューション計測
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-06-05T15:04:01Z'
  edited_at: '2026-10-14T09:27:25Z'
  id: 25676426941457
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/25676426941457
---
| **更新情報** | この機能強化アップデートにより、リエンゲージメントまたは<Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls#reattribution">リアトリビューション</Anchor>後のすべての<Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls#再インストール後のアプリ内イベント">アプリ内イベント</Anchor>とセッションは、従来の ‘unattributed’ （非オーガニックに紐づかないセッションとイベント）というラベルではなく、初回インストール時にアトリビューションされたメディアソースに紐づきます。<br /><br />![Screenshot 2023-07-19 at 13.54.21.png](https://files.readme.io/42a96ec533d217ee4dadad71592023d1fd0c977557308638f3553660a95fc7b5-25827620446353.png) |
| --- | --- |
| **発効日** | 2024年7月31日初回インストールモードは、発効日以降にAppsFlyerに追加されたアプリにのみ自動的に適用されます。2024年7月31日以前に追加されたアプリについては、AppsFlyerに連絡して、既存のアプリを初回インストールモードに移行することをお勧めします。 |
| **前提条件** | なし |
| **必要なアクション** | なし |
| **何を知っておく必要がありますか？** | 初回インストールと再インストールの両方でデバイス識別子（IDFAやGAIDなど）をアプリと共有することに同意したユーザーのみが、アプリ内イベントを初回インストール時のメディアソースに紐付けられます。そうでない場合は、 『organic unattributed』（非オーガニックに紐づかないオーガニック）と表示されます。 |
| **影響範囲は？** | <ul><li>**2024年7月31日以降**にAppsFlyerに追加されたアプリの場合：影響なし</li><li>**2024年7月31日以前**に追加されたアプリについては、AppsFlyerに連絡して、既存のアプリを「初回インストール」モードに移行することをお勧めします。移行後、次のことが起こる可能性があります：<ul><li>再インストール後の初回インストールに紐づくアプリ内のイベントやセッションが増加し、「オーガニック」アトリビューションが減少する場合があります。</li><li>オリジナルの広告配信メディアソース（初回インストール時のメディアソース）のMAU数が増加し、オーガニックのMAU数が減少する場合があります。</li><li>アプリが初回インストールモードに切り替わる日に、セッション数は2倍になります。その結果、コホートの1日目のリテンション率が異常に高くなります。</li></ul></li></ul> |