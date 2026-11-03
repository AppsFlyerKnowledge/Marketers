---
title: お知らせ：旧レシート検証機能の廃止について
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T11:33:45Z'
  edited_at: '2026-10-14T09:24:11Z'
  id: 42133487071121
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/42133487071121
---
| セクション | 詳細 |
| --- | --- |
| **概要** | <ul><li>アプリ内課金向けの <Anchor target="_blank" href="/marketers/ja/docs/legacy-receipt-validation-for-in-app-purchases">旧レシート検証機能（Legacy Receipt Validation）</Anchor> は、AppsFlyer のすべての SDK において 正式に非推奨となりました。</li><li>以下の SDK バージョン以降、 `validateAndLogInAppPurchase`のメソッドは非推奨（deprecated）として扱われます。<ul><li>Android SDK: v6.17.5</li><li>iOS SDK (native): v6.17.8</li><li>プラグイン（Flutter、Unity、React Nativeなど）：v6.17.8</li></ul></li><li>この非推奨メソッドは、今後の SDK リリースで完全に削除される予定です。</li><li>また、旧レシート検証機能（Legacy Receipt Validation）は、**2026 年 7 月 1 日をもって完全に提供終了となり、それ以降は動作しなくなります。**</li></ul> |
| **適用日** | <ul><li>更新日：2025年12月24日</li><li>提供終了日：2026年7月1日</li></ul> |
| **知っておくべきポイント** | <ul><li>非推奨となった`validateAndLogInAppPurchase`のメソッドは、上記 SDK バージョンでは引き続き存在しますが、将来のアップデートで削除されます。</li><li>メソッドが削除された後は、この方式を利用しているアプリは AppsFlyer 経由でアプリ内課金を検証できなくなります。</li><li>AppsFlyer では、以下 2 つのサポート対象ソリューションを提供しています。<ul><li>**レシート検証**無料で利用可能なソリューションです。新しい `validateAndLog`メソッドを使用し、アプリストアと直接連携して購入を検証します。</li><li>**ROI360 ストア収益**有償のプレミアム収益計測ソリューションです。返金トラッキング、サブスクリプションのライフサイクルの可視化、純収益（ネットレベニュー）の算出などを含みます。</li></ul></li></ul> |
| **必要な対応** | サービス停止や計測への影響を防ぐため、上記 2 つのいずれかのソリューションへ移行してください。<br /><br />詳細については、<Anchor target="_blank" href="/marketers/ja/docs/purchase-and-subscription-validation-overview">購入およびサブスクリプション検証 – 概要</Anchor>を参照してください。 |