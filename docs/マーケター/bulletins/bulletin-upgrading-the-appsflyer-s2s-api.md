---
title: お知らせ：
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
  created_at: '2023-11-28T16:26:35Z'
  edited_at: '2026-10-14T09:25:50Z'
  id: 20509378973457
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/20509378973457
---
| **更新情報** | API利用をより安全に提供し、不正行為を減らすために、AppsFlyerはアプリ内イベント用のサーバー間 (S2S) APIをアップグレードしました。<br /><br />AppsFlyerは、お客様に代わってデータを送信するサードパーティのテックパートナー向けのソリューションに取り組んでいます。 |
| --- | --- |
| **発効日** | 2023年12月12日 |
| **前提条件** | 新しいS2S APIをアップデートできるのは管理者（アドミン）のみです。 |
| **必要な対応** | S2Sアプリ内イベントをAppsFlyerに送信する次の項目を更新してください：<ol><li>POST S2Sアプリ内イベントAPIに移動します。</li><li>URL/span><Anchor target="_blank" href="https://api2.appsflyer.com/inappevent">:</Anchor> https://api2.appsflyer.com/inappevent/<br />To <Anchor target="_blank" href="https://api3.appsflyer.com/inappevent">https://api3.appsflyer.com/inappevent</Anchor></li></ol> |
| **推奨アクション** | **すべての本番環境での呼び出しで新しいAPIを更新する前に、次のことを行います：**<br /><br />新しいエンドポイントに多数のテストアプリ内イベントを送信し、 **エラーが返されないようにする**ことを強く推奨します。 |
| **知っておくべきこと** | 新しいAPIのアップデート後に古いエンドポイントに不正イベントが送信されることについて懸念がある場合は、CSMまたはAppsFlyerサポートにお問い合わせください。（その際には関連するアプリIDを必ず含めてください。）<br /><br />本番環境の移行が完了すると、AppsFlyerはこれらのアプリの古いAPIエンドポイントをブロックし、不正な呼び出しをブロックします。 |
| **新しいAPIを更新する必要があるのは誰ですか？** | アプリ内イベント用の新しいS2S APIをアップデートする必要があるのは広告主のみです。 |
| **S2S APIについて** | <Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">S2SトークンとAPIトークンの詳細はこちらをご覧ください。</Anchor> |