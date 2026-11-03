---
title: お知らせ：Amazon DSPの新しいEU同意ポリシーへの対応について
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-12T09:11:36Z'
  edited_at: '2026-10-14T09:23:48Z'
  id: 45664244736529
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/45664244736529
---
| セクション | 詳細 |
| --- | --- |
| **概要** | Amazonはデジタル市場法（DMA）の施行に伴い、Amazon AdsにおけるEU同意ポリシーを更新しています。AppsFlyerでは、広告主がAmazon Adsチャネルの価値を最大限に活用できるようにしつつ、同ポリシー要件に対応するための変更を行っています。 |
| **適用開始日** | 2026年6月30日 |
| **更新内容** | **対象となる連携およびユーザー**`amazondsp_int`のSRN連携を通じてAmazon Adsと連携しており、EU（英国およびスイスを含む）で広告配信を行っているすべてのアプリ広告主が対象です。<br /><br />**必要な対応：** EU、英国、またはスイスのユーザーに対するすべてのイベント（アプリ起動およびアプリ内イベント）について、有効なDMA同意シグナルをAppsFlyerへ送信してください。<br /><br />同意シグナルの送信方法：<ol><li>**手動同意：** 手動同意の場合、必須フィールドは manual consent配列内の「`ad_user_data_enabled`」のみです。Google向けDMA同意で必要なその他のフィールドは、Amazonでは不要です。</li><li>**TCF同意：** CMPによって生成されたTCF同意情報をすべて送信してください。その際、同意済みベンダー一覧にAmazon AdsのベンダーID（`793`）が含まれていることを確認してください。</li><li>**GPP同意文字列：** AmazonはGPP同意文字列に対応していますが、現時点ではAppsFlyerではサポートされていません。</li></ol>**<span id="h_01KP0FAZ70YDRQ71TDRYFEG120"></span>参照：**<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance">AppsFlyer SDK経由でDMA同意を送信する方法</Anchor></li><li>AppsFlyerのS2S経由でDMA同意を送信する<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">方法</Anchor>(`consent_data`を検索してください)</li></ul> |