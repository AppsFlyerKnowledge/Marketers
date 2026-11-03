---
title: レシート検証について
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T14:32:24Z'
  edited_at: '2026-10-28T08:49:21Z'
  id: 42136725767569
  locale: ja
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ja/articles/42136725767569
---
> **At a glance:** レシート検証でアプリ内購入やサブスクリプションの収益を計測し、アプリストアへの照会で取引の正当性を確認する仕組みを説明します。

レシート検証を使うと、Play StoreとApp Storeでのアプリ内購入やサブスクリプションの取引を検証し、収益を計測できます。

レシート検証は、どのプランでも無料で利用できます。

> 📘 **Note**
>
> 純収益の計算、サブスクリプションのライフサイクル全体の計測、返金への対応、購入の自動検出と重複排除が必要な場合は、有料機能のROI360ストア収益をご検討ください。両機能の詳細と比較は、「購入・サブスクリプションの検証に使える2つの機能」を参照してください。

## レシート検証の仕組み

レシート検証は、次の流れで行われます。

1. ユーザーがアプリ内購入を行います。
2. アプリストアが、購入の完了をアプリに通知します。
3. アプリ開発者が、SDKのレシート検証メソッド`validateAndLogInAppPurchase`を呼び出します。
4. SDKがAppsFlyerの検証サービスを呼び出します。
5. AppsFlyerが購入内容を検証し、不正な取引でないことを確認します。
6. 検証に成功すると、AppsFlyerが購入またはサブスクリプションのイベントを記録します。
7. レシート検証に失敗した場合、イベントは<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports#blocked-inapp-events">ブロックされたアプリ内イベントのローデータレポート</Anchor>（Protect360の契約者が利用可能）と<Anchor target="_blank" href="/marketers/ja/docs/testing-the-sdk-integration-for-marketers#view-live-events">ライブイベントの表示ページ</Anchor>に表示され、パラメータ`af_validated`は`false`に設定されます。
8. AppsFlyerの検証サービスが、結果をSDKに返します。
9. SDKが、レシート検証の結果（成功または失敗）をアプリに返します。

## レシート検証の有効化

レシート検証を有効にするには、次の手順を実行します。

1. AppsFlyerのサイドメニューから<strong>［設定］</strong>を開き、<strong>［ROI360］</strong>の<strong>［収益設定］</strong>を選択します。
2. <strong>［購入・サブスクリプション］</strong>タブを開きます。
3. <strong>［1 製品タイプを選択］</strong>で、<strong>［レシート検証］</strong>を選択します。
4. <strong>［保存して次へ］</strong>をクリックし、レシート検証の設定に進みます。

## レシート検証の設定

詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-receipt-validation">「レシート検証の設定」</Anchor>を参照してください<Anchor target="_blank" href="/marketers/ja/docs/set-up-receipt-validation#手順3-sdkの実装の確認">。</Anchor>

## レシート検証のアプリ内購入イベントとパラメータ

定義済みイベントには、次の共通点があります。

* S2Sイベントとして処理されます。
* ダッシュボードとローデータレポートで、オーガニックまたはノンオーガニックのアプリ内イベントとして利用できます。
* ポストバックでパートナーに送信できます。
* SKAN Conversion Studioで使用できます。

**アプリ内購入では、次のイベントが記録されます。**

* `af_purchase`：本番環境
* `af_purchase_sandbox_sdk`：サンドボックス環境

**サブスクリプションのイベント：**

* `af_ars_trial_started`：トライアル期間付きのサブスクリプションの開始。
* `af_ars_subscriptions_started`：有料サブスクリプション（トライアル期間なし）の開始。本番環境用。
* `af_ars_sandbox_sdk`：トライアルまたは有料サブスクリプションの開始。サンドボックス環境用。

**イベントには、次の定義済みパラメータが含まれます。**

* `af_product_id`
* `af_transaction_id`（iOSのみ）
* `af_purchase_token`（Androidのみ）
* `af_revenue`（サンドボックスイベントでは`af_sandbox_revenue`）
* `af_currency`
* `af_store`（app\_store／play\_store）
* `af_environment`（sandbox／production）
* `af_validation_type`（receipt\_validation）

**追加のカスタムパラメータ：**

* SDKの呼び出し時に送信した追加のカスタムパラメータは、ローデータレポートの`custom_data`フィールドに表示されます。

## ROI360ストア収益からレシート検証への切り替え

現在ROI360ストア収益を使用していて、レシート検証に切り替える場合は、次の手順を実行します。

1. AppsFlyerのサイドメニューから<Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.02%" /><strong>［設定］</strong>を開き、<strong>［ROI360］</strong>の<strong>［収益設定］</strong>を選択します。
2. <strong>［購入・サブスクリプション］</strong>タブで、<strong>［製品タイプ］</strong>が現在<strong>［ROI360］</strong>に設定されていることを確認します。
3. <Image alt="Untitled 3.png" src="https://files.readme.io/c27f864253e6749f883047b4529ad292153500db5aebd452568a6aa04407472e-34623601366033.png" width="2.07%" />をクリックします。
4. レシート検証に切り替えると利用できなくなる機能や、データへの影響を説明するメッセージが表示されます。
   * 返金のアトリビューション、サブスクリプション更新の計測、純収益の計算など、ROI360の機能が無効になります。
   * 収益データの正確性が低下する可能性があります。
   * レシート検証では、Purchase Connectorは使用できません。
   * 使用できるSDKメソッドは、`validateAndLogInAppPurchase`のみです。
5. 必要に応じて、<strong>［製品の比較を表示］</strong>をクリックし、比較表を確認します。
6. 切り替えを進める場合は、<strong>［切り替える］</strong>をクリックして確定します。
7. 切り替え後は、<strong>［製品タイプ］</strong>が<strong>［レシート検証］</strong>となり、設定画面も簡略化されます。
8. 次の項目を再確認してください。
   * validateAndLogメソッドの**SDK実装**

## 仕様と制限事項

| 項目 | 補足 |
| --- | --- |
| 対応するストア | • Play Store  <br />• App Store  <br />• その他のストア（サードパーティストア）では、アプリ内購入イベントを手動で送信する必要があります。 |
| iOSのサンドボックスアプリ | iOSのサンドボックスアプリ（App Storeで公開されていないアプリ）では、［キーを検証］の結果は常に「無効」と表示されます。 |

<div data-zendesk-anchors="how-does-receipt-validation-work=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF h_01KD0PBEK0M2NEZJ95QXBA1H3W=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF enable-receipt-validation=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01KD0PBEK0BZNW8YP02EW0DHH4=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 set-up-receipt-validation=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD0PBEK1GZSJQPTP0P2TJMNJ=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E8%A8%AD%E5%AE%9A inapp-purchase-events-and-parameters-for-receipt-validation=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E8%B3%BC%E5%85%A5%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A8%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01KD0PBEK1DVMRXR64EMSWT75W=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E8%B3%BC%E5%85%A5%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A8%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF switch-from-roi360-store-revenue-to-receipt-validation=roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%8B%E3%82%89%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%B8%E3%81%AE%E5%88%87%E3%82%8A%E6%9B%BF%E3%81%88 h_01KD0PBEK1AKE1XM2XVTCNTJ68=roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%8B%E3%82%89%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%B8%E3%81%AE%E5%88%87%E3%82%8A%E6%9B%BF%E3%81%88 traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KD0PBEK1HQKTGM7JP2KYPJAR=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
