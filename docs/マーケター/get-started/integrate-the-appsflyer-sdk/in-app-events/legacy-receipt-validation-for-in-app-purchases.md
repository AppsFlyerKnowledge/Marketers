---
title: ［旧版］アプリ内購入のレシート検証
deprecated: true
metadata:
  keywords:
    - iOS
    - Android
    - Receipt
    - Validation
    - Receipt Validation
    - SDK
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-02-26T10:30:58Z'
  edited_at: '2026-10-29T07:44:12Z'
  id: 207032106
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/207032106
---
> 🚧 **重要**
>
> 本記事では、非推奨となったレシート検証機能について説明します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/bulletin-legacy-receipt-validation-is-deprecated">お知らせ：旧レシート検証機能の非推奨化</Anchor>を参照してください。

> **概要：** レシート検証を実装して、iOSとAndroidのアプリストアにおけるアプリ内購入の不正対策を行い、報告された購入が実際に行われたことを確認します。**注意**：これは旧機能です。改良された新しい完全自動の<Anchor target="_blank" href="/marketers/ja/docs/purchase-and-subscription-validation-overview">アプリ内購入の検証機能</Anchor>については、こちらを参照してください。

## レシート検証の流れ

レシート検証の流れは以下のとおりです。

1. ユーザーがアプリ内購入を行います。
2. アプリストアが、購入の成功をアプリに通知します。
3. アプリ開発者が、SDKのレシート検証関数を呼び出します。

   ```
   validateAndLogInAppPurchase
   ```
4. SDKがAppsFlyerの検証サービスを呼び出します。
5. AppsFlyerが購入を検証し、不正でないことを確認します。
6. 検証に成功すると、AppsFlyerは内部で通常のaf\_purchaseイベントを作成します。検証に失敗すると、作成されたイベントは不正と判定されます（Protect360で確認可能）。
7. AppsFlyerの検証サービスがSDKにレスポンスを返します。
8. SDKが、レシート検証の結果（成功または失敗）をアプリに返します。  
   レシート検証に失敗した場合、イベントは<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports#inapp-level-blocked-reasons">ブロックされたアプリ内イベントのローデータ</Anchor>レポートに表示されます（Protect360契約者が利用可能）。

レシート検証の実装については、開発者向けのSDKドキュメントを参照してください。

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-android#validating-purchases">Android</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-ios#purchase-validation-using-validateandloginapppurchase">iOS</Anchor>

**注意：**

* iOSのサンドボックスアプリ（App Storeで公開されていないアプリ）でレシート検証を行うには、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/validate-and-log-purchase-ios#testing-purchase-validation-in-sandbox-mode">追加のコード</Anchor>が必要です。
* サンドボックス環境での購入は通常のaf\_purchaseイベントとして記録され、その収益はAppsFlyerのダッシュボードとレポートに反映されます。
* AppsFlyerのレシート検証サービスは、すべてのアカウントプランで無料で利用できます。
* Androidでは、購入時にエンドユーザーがインターネットに接続していない場合、レシート検証の結果が`null`となり、検証失敗と判定されることがあります。

> 🚧 **重要**
>
> `validateAndLogInAppPurchase`を呼び出すと、**af\_purchase**アプリ内イベントも生成されます。そのため、検証時にaf\_purchaseイベントを別途生成しないでください。別途生成すると、収益イベントが重複します。

> 📘 **注意**
>
> * *本*記事で説明する旧レシート検証機能は、*StoreKit v2*に対応していません。現行バージョンについては、iOS App Storeとの連携設定を参照してください。
> * アプリ内購入のレシート検証は、サードパーティAndroidアプリストアには対応していません。

<div data-zendesk-anchors="h_01KDJ7QZD8X692EVP1XXGV0KY4=%E9%87%8D%E8%A6%81 receipt-validation-flow=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E6%B5%81%E3%82%8C 01JDSM0JDAQXH8QX8ZAXNB0ZMB=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E6%B5%81%E3%82%8C 01JDSM0JDT6Q3WYW9K484QHY2M=%E9%87%8D%E8%A6%81-1 01JDSM0JD90J3EDMVN6D6Z9J40=%E6%B3%A8%E6%84%8F" />
