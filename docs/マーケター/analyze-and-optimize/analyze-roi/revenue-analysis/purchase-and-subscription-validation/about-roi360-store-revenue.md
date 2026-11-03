---
title: ROI360ストア収益について
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T16:34:39Z'
  edited_at: '2026-10-28T08:49:25Z'
  id: 42138855425297
  locale: ja
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ja/articles/42138855425297
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** ROI360ストア収益でアプリ内購入とサブスクリプションを検証し、重複計上を防ぎながら、純収益（税金・ストア手数料を差し引いた収益）を計算します。

> 🚧 **重要**
>
> ROI360ストア収益は、ROI360の有料プランをご契約のお客様のみ利用できます。契約プランの確認やアップグレードについては、担当のカスタマーサクセスマネージャー（CSM）にお問い合わせください。

ROI360ストア収益は、アプリ内購入とサブスクリプションの収益を漏れなく正確に計測するための、AppsFlyerの有料機能です。顧客のライフサイクル全体を把握でき、広告費用対効果（ROAS）を正確に計測できます。

| 機能 | 詳細 |
| --- | --- |
| 収益の計測範囲 | <ul><li>App Store Connect（iOS）とGoogle Play Console（Android）で管理する、すべてのアプリ内購入商品とサブスクリプションの収益</li><li>返金</li><li>支払いが保留中または延期されている取引の収益（Android）</li><li>アプリ内外で発生するサブスクリプション関連イベント</li><li>ストア手数料と税金を差し引いた純収益</li></ul> |
| 収益の検証と正確性の確保 | 同じ取引の重複記録を防ぎます。 iOSでは、ファミリー共有による重複も防ぎます。また、Apple App Storeの取引データを広告主に直接転送することもできます。 |
| データの取得元 | <ul><li>Android・iOS向けのAppsFlyer Purchase SDK Connector</li><li>App Storeのサーバー通知</li><li>Google Playのリアルタイムデベロッパー通知（RTDN）</li></ul> |
| レポートとデータの利用 | 収益データはAppsFlyerのダッシュボードとレポートで利用でき、ポストバックでパートナーに共有することもできます。 |

> ❗️ **警告**
>
> ROI360ストア収益を使用する場合は、アプリ内購入イベントを別途送信しないでください。収益が重複して計上されます。

## ROI360ストア収益の仕組み

1. ユーザーがアプリ内購入を行うか、自動更新サブスクリプションを購入します。
2. アプリがアプリストアで購入処理を行います。
3. AppsFlyer Purchase SDK Connectorが購入を自動的に検出し、検証・記録に必要なデータをAppsFlyerに送信します。
4. AppsFlyerが該当するストアに購入内容を照会し、不正な取引でないことを確認します。
   * 検証に成功すると、AppsFlyerが購入またはサブスクリプションのアプリ内イベントを記録します。
   * レシート検証に失敗した場合、イベントはブロックされたアプリ内イベントのローデータレポート（Protect360の契約者が利用可能）とライブイベントの表示ページに表示され、パラメータ`af_validated`はfalseに設定されます。
5. AppsFlyerが結果をSDK Connectorに返し、SDK Connectorがレシート検証の結果（成功または失敗）をアプリに返します。
6. AppsFlyerは、アプリストアから受信したサーバー通知も、購入・サブスクリプション収益の処理ルールに従って処理します。
   * SDK Connectorからすでに報告されている取引の通知を受信すると、その内容を検証・処理し、購入イベントまたはサブスクリプションの各段階に対応するイベントを内部的に生成します。
   * 不明な取引に関する通知は破棄されます。
   * iOSでは、すべてのサーバー通知を自社サーバーに転送できます。

## ROI360ストア収益の有効化

ROI360ストア収益の計測を有効にするには、次の手順を実行します。

1. AppsFlyerのサイドメニューから<Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.17%" /><strong>［設定］</strong>を開き、<strong>［ROI360］</strong>の<strong>［収益設定］</strong>を選択します。
2. <strong>［購入・サブスクリプション］</strong>タブを開きます。
3. <strong>［1 製品タイプを選択］</strong>で、<strong>［ROI360］</strong>を選択します。
4. <strong>［次へ］</strong>をクリックして進みます。

## ROI360ストア収益の設定

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue">「ROI360ストア収益の設定」</Anchor>を参照してください。

## 参考情報

以下では、ROI360によるアプリ内購入（IAP）とサブスクリプションの収益計測を詳しく説明します。 IAP・サブスクリプションのイベントとパラメータ、総収益から純収益を計算する仕組み、収益計測の仕様と制限事項を取り上げます。

> 📘 **注意**
>
> アプリ内イベントに追加のカスタムパラメータを含めるには、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-connector">Purchase SDK Connector</Anchor>で**カスタムデータソース**を設定します。これにより、自社の業務ルールに応じたデータやメタデータを、購入・サブスクリプションのイベントに追加できます。
> これらのパラメータは、ローデータレポートの`custom_data`フィールドで確認できます。

<div id="iaprelated-events-and-parameters" />

<Accordion title="IAPのイベントとパラメータ">

AppsFlyerで計測するIAPイベントと、各イベントに含まれるパラメータを以下に示します。各パラメータの説明は、[イベントパラメータの一覧](#parameter-dictionary)を参照してください。

**生成されるイベントには、次の共通点があります。**

* サーバー間（S2S）イベントとして扱われます。
* ローデータレポートでオーガニックまたはノンオーガニックのアプリ内イベントとして利用でき、収益ETLのストア収益レポートにも含まれます。
* ポストバックでパートナーに送信されます。
* SKAN Conversion Studioに対応しています。

<div id="purchase-af_purchase" />

<Accordion title="購入（af_purchase）">

**説明**

ユーザーが購入したときに記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-af_purchase_free" />

<Accordion title="無料での購入（af_purchase_free）">

**説明**

ユーザーが無料で購入したときに記録されます。収益に関するすべてのパラメータに0が表示されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-canceled-af_purchase_canceled" />

<Accordion title="購入のキャンセル（af_purchase_canceled）">

**説明**

ユーザーが購入をキャンセルしたときに記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="purchase-pending-af_purchase_pending" />

<Accordion title="購入の保留（af_purchase_pending）">

**説明**

ユーザーが購入したものの、支払いがまだ処理されていないときに記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="refund-af_purchase_refund" />

<Accordion title="返金（af_purchase_refund）">

**説明**

購入に対して返金が行われたときに記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue（収益が0を超える場合にイベントに含まれます）
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="test-purchase-af_purchase_sandbox_sdk" />

<Accordion title="テスト購入（af_purchase_sandbox_sdk）">

**説明**

サンドボックス環境でSDK経由の購入をテストすると記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_purchase_sandbox_s2s" />

<Accordion title="テスト購入（af_purchase_sandbox_s2s）">

**説明**

サンドボックス環境でS2S経由の購入をテストすると記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="subscriptionrelated-events-and-parameters" />

<Accordion title="サブスクリプションのイベントとパラメータ">

AppsFlyerで計測するサブスクリプション関連イベントと、各イベントに含まれるパラメータを以下に示します。各パラメータの説明は、[イベントパラメータの一覧](#parameter-dictionary)を参照してください。

生成されるイベントには、次の共通点があります。

* S2Sイベントとして扱われます。
* ローデータレポートで、オーガニックまたはノンオーガニックのアプリ内イベントとして利用できます。
* ポストバックでパートナーに送信できます。
* SKAN Conversion Studioで使用できます。

**注意：** ユーザーの端末のプラットフォームによっては、アプリ内イベントの一部のパラメータに値が入らない場合があります。

<div id="trial-started-af_ars_trial_started" />

<Accordion title="トライアルの開始（af_ars_trial_started）">

**説明**

ユーザーがトライアルを開始したときに記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-canceled-af_ars_trial_canceled" />

<Accordion title="トライアルの自動更新停止（af_ars_trial_canceled）">

**説明**

トライアル期間中に、ユーザーがサブスクリプションの自動更新を停止したときに記録されます。トライアル期間中に自動更新を再開しなかった場合は、期間終了後に終了（離脱）イベントが発生します。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-churned-af_ars_trial_churned" />

<Accordion title="トライアルの終了（離脱）（af_ars_trial_churned）">

**説明**

トライアル期間が終わり、ユーザーが離脱したときに記録されます。自動更新を停止し、トライアル期間が終了した場合に発生します。支払いや技術上の問題で更新できず、離脱に至った場合にも発生します。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_reason

</Accordion>

<div id="trial-converted-af_ars_trial_converted" />

<Accordion title="トライアルから有料契約への移行（af_ars_trial_converted）">

**説明**

トライアル期間が終わり、通常料金での更新に移行したときに記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* store\_commission
* af\_revenue（収益が0を超える場合にのみイベントに含まれます）
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-started-af_ars_subscription_started" />

<Accordion title="サブスクリプションの開始（af_ars_subscription_started）">

**説明**

割引料金または通常料金のサブスクリプションが始まったときに記録されます。

**注意**：

* 新規サブスクリプションは、SDK Connector経由でのみ記録できます。
* iOSでは、ユーザーがすでに保有しているサブスクリプションを再購入した場合、SDK Connectorはレシート検証の成功をアプリに返しますが、AppsFlyerには新たな取引を記録しません。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue（収益が0を超える場合にイベントに含まれます）
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-canceled-af_ars_subscription_canceled" />

<Accordion title="サブスクリプションの自動更新停止（af_ars_subscription_canceled）">

**説明**

請求期間の途中で、サブスクリプションの自動更新が停止されたときに記録されます。同じ請求期間内に自動更新を再開しなかった場合は、期間終了後に終了（離脱）イベントが発生します。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-paused-af_ars_subscription_paused-android-only" />

<Accordion title="サブスクリプションの一時停止（af_ars_subscription_paused）｜Androidのみ">

**説明**

ユーザーが有効なサブスクリプションを一時停止したときに記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-resumed-af_ars_subscription_resumed" />

<Accordion title="サブスクリプションの再開（af_ars_subscription_resumed）">

**説明**

終了または返金されたサブスクリプションが、通常料金で再開されたときに記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* af\_reason
* event\_revenue（イベント収益が0を超える場合にイベントに含まれます）
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-churned-af_ars_subscription_churned" />

<Accordion title="サブスクリプションの終了（離脱）（af_ars_subscription_churned）">

**説明**

サブスクリプションのユーザーが離脱したときに記録されます。通常は、自動更新の停止や請求期間の終了後に発生します。支払いや技術上の問題で更新できず、離脱に至った場合にも発生します。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_reason

</Accordion>

<div id="subscription-refunded-af_ars_subscription_refunded" />

<Accordion title="サブスクリプションの返金（af_ars_subscription_refunded）">

**説明**

サブスクリプションのユーザーに返金が行われたときに記録されます。

**注意：**

* 通常、このイベントにはマイナスの値が記録されます。返金対象の取引を特定できない場合や、通知に返金の詳細が含まれない場合は、返金イベントに金額が表示されません。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_reason
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_refunded\_transaction\_ids
* event\_revenue\_usd
* event\_revenue（収益が0を超える場合にイベントに含まれます）
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_store
* af\_environment
* af\_period\_type
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-billing-grace-af_ars_subscription_billing_grace" />

<Accordion title="サブスクリプションの支払い猶予（af_ars_subscription_billing_grace）">

**説明**

支払いの問題でサブスクリプションを更新できず、支払い猶予期間に入ったときに記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-renewed-af_ars_subscription_renewed" />

<Accordion title="サブスクリプションの更新（af_ars_subscription_renewed）">

**説明**

サブスクリプションが自動更新されたときに記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue（収益が0を超える場合にイベントに含まれます）
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-changed-af_ars_subscription_xgraded" />

<Accordion title="サブスクリプションの変更（af_ars_subscription_xgraded）">

**説明**

ユーザーがサブスクリプションをアップグレード、ダウングレード、または別の商品に切り替えたときに記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue（収益が0を超える場合にイベントに含まれます）
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="existing-subscriber-af_ars_existing_subscriber" />

<Accordion title="既存のサブスクリプションユーザー（af_ars_existing_subscriber）">

**説明**

請求期間の途中で、SDK Connectorが既存の契約者に関する通知を受け取ったときに記録されます。後続のサーバー通知で次の段階に移る前の、サブスクリプションの状態を表します。通常、導入時やSDK Connectorへの移行中に発生します。

**パラメータ**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated

</Accordion>

<div id="test-purchase-af_ars_sandbox_sdk" />

<Accordion title="テスト購入（af_ars_sandbox_sdk）">

**説明**

サンドボックス環境でSDK経由の購入をテストすると記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_ars_sandbox_s2s" />

<Accordion title="テスト購入（af_ars_sandbox_s2s）">

**説明**

サンドボックス環境でS2S経由の購入をテストすると記録されます。

**パラメータ**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="parameter-dictionary" />

<Accordion title="パラメータ一覧">

IAPとサブスクリプションのイベントのパラメータは、ローデータレポートで個別の列に表示されるか、**Event value**に含めて格納されます。

個別の列に表示されるパラメータは、次のとおりです。

* app\_id
* customer\_user\_id
* country\_code
* af\_currency
* event\_revenue\_usd
* af\_revenue
* android\_id
* ip
* idfa
* appsflyer\_id

これらのパラメータについて詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">データフィールドの一覧</Anchor>を参照してください。

次の表は、ARSイベントとVIAPイベントで利用できるローデータのパラメータを説明しています。

| パラメータ | 補足 | 製品 |
| --- | --- | --- |
| af\_cancelation\_date\_ms | キャンセル日 | IAP |
| af\_cuids | <ul><li>ARSでは、このパラメータにすべてのCUIDを含む配列が格納されます。</li><li>CUIDの配列は、端末IDにかかわらず表示されます。このため、異なる端末IDに同じCUIDが表示されることがあります。</li></ul> | サブスクリプション |
| af\_discount\_id | 初回購入時にユーザーに提示されたオファーのID。割引コードがある場合にのみ値が入ります。 | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_discount\_type | ユーザーが適用した割引の種類。設定される値：<ul><li>iOS<ul><li>introductory</li><li>promotional</li><li>offer\_codes</li><li>win\_back</li></ul></li><li>Android<ul><li>intro price（初回割引料金）</li><li>one\_time\_code</li><li>vanity\_code</li></ul></li></ul> | サブスクリプション |
| af\_environment | データを受信した環境。productionまたはsandbox。 | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_expires\_date\_ms | 現在のサブスクリプションの請求期間が終了する日時 | サブスクリプション |
| af\_net\_revenue | 適用されるすべての控除を反映した純収益。 af\_net\_revenue\_factorsを参照してください。 | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_net\_revenue\_country | <ul><li>税が適用される国の<Anchor target="_blank" href="https://www.nationsonline.org/oneworld/country_code_list.htm">ISO準拠の2文字の国コード</Anchor>。</li><li>例：CA</li><li>注意：英国にはGBではなくUKを使用します。</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_net\_revenue\_factors | <ul><li>報告されるaf\_net\_revenueの計算に使用した、すべての控除項目を表す配列。</li><li>値の例：store\_commission</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_net\_revenue\_postal\_code | <ul><li>文字、数字、またはその組み合わせからなる文字列</li><li>例：L4J8E3</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_net\_revenue\_subdivision | <ul><li>一部の国では、州などの行政区画を追加で指定できます。 <Anchor target="_blank" href="https://service.unece.org/trade/locode/2023-1%20SubdivisionCodes.htm">ISO 3166-2の行政区画コード</Anchor>に従って処理されます。</li><li>国コードと行政区画コードを含みます。</li><li>例：US-CA</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_net\_revenue\_tax\_exclusive | <ul><li>trueまたはfalseを指定するブール値のパラメータ。</li><li>falseは、収益の総額に税金が含まれることを表します。</li><li>trueは、表示された収益の総額とは別に税金が加算されることを表します。</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_net\_revenue\_tax\_name | <ul><li>顧客の請求書に表示される、税の種類を表す名前。</li><li>例：Sales、VAT、GST</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_net\_revenue\_tax\_rate | <ul><li>徴収する税率を表す数値。小数点以下4桁まで指定できます。</li><li>例：7.25</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_offer\_id | <ul><li>該当する場合に、その取引に適用されたオファーのID（割引やプロモーションのオファーなど）。</li><li>Androidのみ</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_order\_id | <ul><li>取引の注文ID</li><li>Androidのみ</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_original\_transaction\_id | <ul><li>元の取引ID</li><li>iOSのみ</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_original\_transaction\_id | <ul><li>元の取引ID</li><li>iOSのみ</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_period\_type | <ul><li>サブスクリプションまたはトライアル期間の種類。</li><li>設定される値：<ul><li>trial</li><li>intro</li><li>normal</li></ul></li></ul> | サブスクリプション |
| af\_product\_id | サブスクリプションの商品ID | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_purchase\_date\_ms | 報告対象の商品IDに対応するアプリ内購入イベントの発生日時 | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_purchase\_option\_id | <ul><li>取引に紐づく購入オプションのID。</li><li>Androidのみ</li></ul> | IAP |
| af\_purchase\_option\_type | 取引の購入オプションの種類。設定される値（Android）：<ul><li>buy</li><li>rent</li></ul> | IAP |
| af\_purchase\_state | 設定される値：<ul><li>Purchased（購入済み）</li><li>Canceled（キャンセル済み）</li><li>Pending（保留中）</li></ul> | IAP |
| af\_purchase\_token | <ul><li>取引の購入トークン</li><li>Androidのみ</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_reason | ［内容に変更なし］ | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_refunded\_transaction\_ids | <ul><li>返金されたすべての取引IDを含む配列</li><li>iOSのみ</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_store | サブスクリプション商品を購入したアプリストア | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| af\_subscription\_ownership\_type | FAMILY\_SHAREDは、ファミリー共有を通じて利用権を持つユーザーであることを表します。 PURCHASEDは、支払いを行うユーザー本人が購入したことを表します。 | サブスクリプション |
| af\_transaction\_id | <ul><li>取引のID</li><li>iOSのみ</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |
| store\_commission | <ul><li>購入した商品からストアに支払う手数料の割合（計算値）。</li><li>小数で表示されます。</li><li>例：30</li></ul> | <ul><li>IAP</li><li>サブスクリプション</li></ul> |

</Accordion>

<div id="true-revenue" />

<Accordion title="純収益">

純収益機能は、ROI360ストア収益で取引ごとの純収益を算出する仕組みです。取引を受信するたびに純収益をリアルタイムで自動計算し、レポートに反映します。

> 📘 **注意**
>
> 純収益はローデータレポートに表示され、アプリ内イベントのポストバックでリアルタイムに送信することもできます。また、<Anchor target="_blank" href="/marketers/ja/docs/my-dashboards">マイダッシュボード</Anchor>の純収益ベースの指標（純収益、純ROI、純ROAS、純ARPU、純利益）でも確認できます。
>
> ポストバックで純収益を送信するには、アプリ内イベントで<strong>［値、収益、純収益］</strong>を選択します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#ポストバックに含めるデータ">アプリ内イベントのポストバック設定</Anchor>を参照してください。

> 📘 **ヒント**
>
> アプリ内イベントのポストバックで、通常は総収益を送信する収益（金額）パラメータに、純収益を設定することもできます。この設定を利用するには、担当のカスタマーサクセスマネージャー（CSM）にお問い合わせください。

総収益から純収益を計算する際は、次の項目を考慮します。

* **ストア手数料**：
  * 自動的に計算・報告されます。お客様側での操作は不要です。
  * アプリ内購入（IAP）のデフォルトのストア手数料は、ストアの国・地域によって異なります。
    * App Store：日本とEU諸国は26%。中国本土（CN）：25%。その他の国・地域：30%。
    * Play Store：30%。
  * サブスクリプションの手数料は、各ユーザーの契約継続期間に応じて自動的に計算されます。
    * App Storeの最初の12か月：日本とEU諸国は26%、中国本土（CN）は25%、その他の国・地域は30%。 13か月目以降：日本は15%、中国本土（CN）は12%、その他の国・地域は15%。
    * Play Store：初日から15%。
  * 純収益の計算に関するパラメータは、ローデータレポートで確認できます。
  * デフォルトとは異なるストア手数料率を設定するには、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">純収益API</Anchor>を使用します。例えば、手数料率が15%（中国本土（CN）では12%）となるAppleのSmall Business Programに参加しているアプリで役立ちます。
* **税金**：
  * ROI360で計測する取引の税金は、デフォルトの税率設定に基づいて報告されます。
  * これは、表示価格に税金が含まれる国に適用されます。例えば英国では、AppsFlyerは税金とストア手数料の合計額を差し引きます。米国など、表示価格に税金が含まれない国では、デフォルトで収益と純収益のパラメータに税金は含まれません。
  * この設定は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">純収益API</Anchor>で変更できます。対応する国とデフォルトの税率は、<Anchor target="_blank" href="https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub">このJSONファイル</Anchor>で確認できます。開発者は、このファイルを必要に応じて編集するか、そのままAPIで使用できます。

レポートでは、次のパラメータに純収益のデータが格納されます。詳しくは、[パラメータ一覧](#parameter-dictionary)を参照してください。

| パラメータ | 純収益の計算で差し引く項目 |
| --- | --- |
| `store_commission` | ストア手数料 |
| `af_net_revenue_tax_name` | 税金 |
| `af_net_revenue_tax_rate` | 税金 |
| `af_net_revenue_tax_exclusive` | 税金 |
| `af_net_revenue_postal_code` | 税金 |
| `af_net_revenue_country` | 税金 |
| `af_net_revenue_subdivision` | 税金 |
| `af_net_revenue` | <ul><li>ストア手数料</li><li>税金</li></ul> |
| `af_net_revenue_factors` | <ul><li>ストア手数料</li><li>税金</li></ul> |

</Accordion>

<div id="troubleshooting-and-disprepancies" />

<Accordion title="トラブルシューティングとデータの差異">

| 現象 | 説明／解決方法 |
| --- | --- |
| AppsFlyerで表示されるアプリ内購入・サブスクリプションのイベント数が、実際のアプリストアの件数より少ない。 | AppsFlyerでイベントが生成されるのは、SDK Connectorを組み込んだバージョンにアプリを更新したユーザーのみです。一方、アプリストアでは、ユーザーが使用するアプリのバージョンにかかわらず、すべてのイベントが記録されます。そのため、更新版のアプリがすべてのユーザーに行き渡るまでは、アプリの収益データとストアのデータに差異が生じます。 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 仕様 | 製品 | 補足 |
| --- | --- | --- |
| 分割払いのサブスクリプション（Android） | サブスクリプション収益 | 非対応 |
| サブスクリプションの支払い保留中の  <br />取引（Android） | サブスクリプション収益 | 非対応 |
| 新規サブスクリプション | サブスクリプション収益 | AppsFlyerの購入SDK経由でのみ記録されます。 |
| 価格変更 | サブスクリプション収益 | サブスクリプション収益の計測で、変更後の商品価格を含むSDK通知をまだ受信していない場合は、変更前の価格を収益として報告し続けます。購入SDKから変更後の商品価格を受信すると、新しい価格が反映されます。 |
| 総収益 | <ul><li>IAP</li><li>サブスクリプション収益</li></ul> | 対応 |
| 純収益 | <ul><li>IAP</li><li>サブスクリプション収益</li></ul> | ローデータとマイダッシュボード（純収益ベースの指標）で利用できます。 |
| 返金 | IAP | 元の購入から180日後まで報告できます。 |
| 重複排除 | <ul><li>IAP</li><li>サブスクリプション収益</li></ul> | イベントの発生日から180日後までに報告された取引に対応しています。 |
| SDKの厳格モード | <ul><li>IAP</li><li>サブスクリプション収益</li></ul> | ROI360のサブスクリプションとIAPは、次のバージョン以降でSDKの厳格モードに対応しています。<ul><li>AppsFlyer iOS Purchase SDK Connector V6.13.0</li><li>Unity Purchase SDK Connector V2.0.1</li></ul> |
| 通貨 | <ul><li>IAP</li><li>サブスクリプション収益</li></ul> | 収益は元の通貨（event\_revenueパラメータ）と米ドル（event\_revenue\_usdパラメータ）で報告されます。 |
| データの更新・反映 | <ul><li>IAP</li><li>サブスクリプション収益</li></ul> | <ul><li>取引単位のストア収益レポート：1時間ごと</li><li>端末単位のストア収益レポート：8時間ごと</li></ul> |
| StoreKit 2 | <ul><li>IAP</li><li>サブスクリプション収益</li></ul> | <ul><li>StoreKit 2には、Purchase SDK Connectorのバージョン6.16.2以降で対応しています。</li><li><Anchor target="_blank" href="/marketers/ja/docs/bulletin-update-app-store-credentials-for-ios-roi360-receipt-validation">こちら</Anchor>で説明している、更新されたApp Storeの認証情報を使用していることを確認してください。</li></ul> |
| Googleの1回限りの購入商品 | IAP | <ul><li>対応する購入オプション：購入、レンタル</li><li>予約購入：非対応</li></ul> |

</Accordion>

<div data-zendesk-anchors="h_01KSAJW61CZZBWBQ112VR5095C=%E9%87%8D%E8%A6%81 h_01KD0W3J6105033NV6FYKGQ8BQ=%E8%AD%A6%E5%91%8A how-does-roi360-store-revenue-work=roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF h_01KD2JZQ0JYVF8S1E2W3N91KYV=roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF enable-roi360-store-revenue=roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01KD2JZQ0JS9YQ2SPNN6NHAJEH=roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 set-up-roi360-store-revenue=roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD2JZQ0JD53598CES8ECAHR3=roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%AE%E8%A8%AD%E5%AE%9A reference=%E5%8F%82%E8%80%83%E6%83%85%E5%A0%B1 h_01JKWGTJQY938NV6VCJ7KKS23E=%E5%8F%82%E8%80%83%E6%83%85%E5%A0%B1 h_01KD6B3KC75RFDV08G9RT1BX1M=%E6%B3%A8%E6%84%8F h_01HDEPSK8DFQ24EZ5T0EPBSVS4=iaprelated-events-and-parameters 01H8VJJP1ER9N6BPAES8H8CK4T=purchase-af_purchase h_01J50N58GYF2BYC57HA7THSWW6=purchase-af_purchase_free 01H8VJJP1EXYE1EQS08CK8BG02=purchase-canceled-af_purchase_canceled 01H8VJJP1ET5TAAQ17EMK6TVRE=purchase-pending-af_purchase_pending 01H8VJJP1E8JKPGT2V9CCB1XW8=refund-af_purchase_refund 01H8VJJP1ECQMS49M8Z1X1FT4B=test-purchase-af_purchase_sandbox_sdk 01H8VJJP1E3X7YZNYT5D8REVEW=test-purchase-af_purchase_sandbox_s2s h_01HDEQBACTTPZ04YYD1KV49SEZ=subscriptionrelated-events-and-parameters 01H8VJJP1EHAZBGT82WRWB00JT=trial-started-af_ars_trial_started 01H8VJJP1ETCHTK6JMK9ERS5A5=trial-canceled-af_ars_trial_canceled 01H8VJJP1EC45X8PJVPWT3G7S3=trial-churned-af_ars_trial_churned 01H8VJJP1EYPQM50JVX1KPZXAZ=trial-converted-af_ars_trial_converted 01H8VJJP1EA4WTCEJWBB1HPRJF=subscription-started-af_ars_subscription_started 01H8VJJP1EF744NE425Y30VG0M=subscription-canceled-af_ars_subscription_canceled 01H8VJJP1EMKBP27070NRR9CZ5=subscription-paused-af_ars_subscription_paused-android-only 01H8VJJP1EGHNQ35JM1TWV4ND0=subscription-resumed-af_ars_subscription_resumed 01H8VJJP1EM2GJ28VBE6V76SBG=subscription-churned-af_ars_subscription_churned 01H8VJJP1E28XXAQSGZ9PYDT08=subscription-refunded-af_ars_subscription_refunded 01H8VJJP1E399B2AVWP9VKZ0D4=subscription-billing-grace-af_ars_subscription_billing_grace 01H8VJJP1EEZZ0DE75VXAZQP3E=subscription-renewed-af_ars_subscription_renewed 01H8VJJP1FGXHRK3J0XB2G4PCQ=subscription-changed-af_ars_subscription_xgraded 01H8VJJP1FKC8KZ2HKJVGZEV23=existing-subscriber-af_ars_existing_subscriber 01H8VJJP1F720QT97Q0TW4SEM2=test-purchase-af_ars_sandbox_sdk 01H8VJJP1FSRHG26EXMEG3325P=test-purchase-af_ars_sandbox_s2s 01H8VJJP1F0ZV2PX39D9JCG6B4=parameter-dictionary 01H8VJJP1FF219YN3XHRCGW7Z3=true-revenue h_01KBFWTM4XJ417930YVDD36ASK=%E6%B3%A8%E6%84%8F-1 h_01KRKEP613DR8RZ5Q2A5H7KZAH=%E3%83%92%E3%83%B3%E3%83%88 01JHZG8FFHTYE2PMRWWS8WNR6X=troubleshooting-and-disprepancies 01H8VJJP1FP2MPRF8AN77REXD0=traits-and-limitations" />
