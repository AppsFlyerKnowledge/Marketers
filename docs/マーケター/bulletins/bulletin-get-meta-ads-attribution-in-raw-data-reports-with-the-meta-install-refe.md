---
title: お知らせ：Meta Adsインストールリファラーを使用しローデータレポートでMeta Adsのアトリビューションを取得します。
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
  created_at: '2024-02-12T10:47:33Z'
  edited_at: '2026-10-14T09:39:38Z'
  id: 22461635687185
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/22461635687185
---
| **更新情報** | Metaインストールリファラーは、Facebook、Instagram、Audience NetworkでのAndroid広告キャンペーンのアトリビューション測定に役立ちます。これは、Google Play インストールリファラーに追加されるものです。 |
| --- | --- |
| **発効日** | 2024年2月28日 |
| **前提条件** | 以下を確認してください：<ul><li>AppsFlyer SDKのバージョン**V6.12.6**以降が実装されていること</li><li>連携済みパートナー画面で<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup#encrypted-data-from-the-referrer">インストールリファラー復号化キー</Anchor>が入力されていること</li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#prerequisites">ここで説明されている</Anchor>バージョンが、ユーザーのデバイスにインストールされていること</li></ul> |
| **必要なアクション** | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#configure-meta-install-referrer-support">Metaインストールリファラーサポートを設定する</Anchor> |
| **何を知っておく必要がありますか？** | リファラーデータはMeta広告連携を通じて提供されるデータよりも優先され、ローデータレポートで利用できます。また、このソリューションはクリックスルー計測にのみ適用され、ビュースルー計測には適用されません。 |
| **影響範囲は？** | <ul><li>ローデータレポートでMetaへアトリビューションされるインストールの増加が見られる場合があります。</li><li>2つの新しいマッチタイプ項目 `fb_referrer` と `ig_referrer` がローデータレポートに含まれます：<ul><li>`fb_referrer` ：Facebookアプリからのアトリビューション</li><li>`ig_referrer` ：Instagramアプリからのアトリビューション</li><li>`fb_referrer` または `ig_referrer` ：Facebook Audience Networkからのアトリビューション</li></ul></li></ul> |

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup#userlevel-data">Metaインストールリファラー</Anchor>

<div data-zendesk-anchors="h_01H9FHRVKE88CXGH8G7E26ZXT2=%E5%8F%82%E7%85%A7" />
