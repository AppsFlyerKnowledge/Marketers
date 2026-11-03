---
title: お知らせ：エンゲージメントタイプの可視性の強化
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
  created_at: '2024-10-29T15:52:59Z'
  edited_at: '2026-10-14T09:35:56Z'
  id: 29614354758545
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/29614354758545
---
| **更新情報** | 拡張エンゲージメントタイプ（ETT）はすべてのアカウントで確認可能になります。 |
| --- | --- |
| **影響** | <ul><li>はすべてのサポートしているネットワーク（クリックネットワークとSRNの両方）でレポートされます。</li><li>`engagement_type` パラメータがない、または不一致の場合、<Anchor target="_blank" href="/marketers/ja/docs/bulletin-unspecified-engagement-type">デフォルトは `click_unspecified` または `impression_unspecified`</Anchor> になります。</li><li>エンゲージビューとエンゲージクリックは、クリックと同じ<Anchor target="_blank" href="/marketers/ja/docs/about-enriched-engagement-types#attribution-model-with-enriched-engagement-types-beta">アトリビューションの優先順位</Anchor>を持ち、すべての広告ネットワークで一貫性を確保します。</li><li>アトリビューションとインストール数には影響しません。</li><li>（非SRNの<Anchor target="_blank" href="/marketers/ja/docs/about-enriched-engagement-types#networks-that-report-engagement-types">対応媒体</Anchor>のみ）連携タブにエンゲージクリックとエンゲージビューの新しいルックバック期間スライダーを追加します。デフォルトは7日間です。</li><li>SRNの対応媒体の場合、ルックバック期間は、パートナー**連携**タブで設定されたクリックスルールックバック期間から取得されます。</li><li>ダッシュボードで**エンゲージメントタイプ**のディメンションを利用できます。</li><li>選択した場合、`engagement_type` がローデータレポートに含まれます。</li><li>エンゲージビューは `attributed_touch_type=impression` としてレポートされます（Google広告にも適用）。</li><li>2024年11月19日以降、クリックからエンゲージビューへのシフトが起こる可能性があります。<ul><li>`attributed_touch_type=click` の減少</li><li>`attributed_touch_type=impression` の増加</li></ul></li><li>エンゲージビューは、**ビュースルー**計測設定がオフの場合でも計測され、レポートされます。 これらのインプレッションをエンゲージビューとして識別するには、`attributed_touch_type` のみではなく、ダッシュボードやローデータレポートで `engagement_type=engaged_view` の指標を使用します。</li><li>合計インプレッション数は、エンゲージビューと通常のビューの両方を含みます。IPMを計算するには、**総インプレッション数からエンゲージビューを差し引く**必要があります。理由：エンゲージビューはインプレッションのサブセットであり、二重にカウントするとインプレッション数が膨れ上がります。</li><li>インストールは常に最も強いタッチタイプにアトリビューションされます。ビューとエンゲージビューの両方がレポートされている場合、インストールはエンゲージビューにアトリビューションされます。</li></ul> |
| **発効日** | 2024年11月 |
| **対応媒体** | 現在、許可されたネットワークのみがエンゲージメントタイプをAppsFlyerにレポートできます。 |
| **知っておくべきこと** | ETTに関連するすべての情報はナレッジベースに記載されています：<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-enriched-engagement-types">EET - 拡張エンゲージメントタイプ</Anchor></li><li><Anchor target="_blank" href="/partners/ja/docs/enriched-engagement-types-guide-for-ad-networks">パートナー向けの拡張エンゲージメントタイプガイド</Anchor></li></ul> |