---
title: 純収益APIによる税率とストア手数料率の設定
metadata:
  keywords:
    - Revenue
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
  created_at: '2024-11-28T13:57:14Z'
  edited_at: '2026-10-28T08:50:05Z'
  id: 30468586765841
  locale: ja
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ja/articles/30468586765841
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 純収益APIを使い、アプリごとにストア手数料率と税率ルールを設定して、AppsFlyerによるアプリ内購入・サブスクリプションの純収益計算に反映します。標準とは異なる手数料や特定の税率ルールが適用される場合も、実際の収益をレポートに正確に反映できます。

ROI360ストア収益は、総収益からストア手数料と税金を自動的に差し引き、アプリ内購入とサブスクリプションの純収益を計算します。デフォルトの設定には、App StoreとGoogle Playの標準的な手数料率と税率ルールが反映されています。通常と異なるストア手数料率が適用される場合や、特別な税制がある国で事業を行う場合は、純収益APIでデフォルトの設定を変更してください。

純収益APIは2つのREST APIで構成され、アプリごとにストア手数料率と税率ルールを設定できます。

* [ストア手数料率](https://dev.appsflyer.com/hc/reference/post_store-commission-rates)：1つ以上のアプリについて、ストア手数料率を作成・更新・取得・削除します。ストアの各種プログラムに応じて、アプリごとに個別の手数料率を設定できます。
* [税率ルール](https://dev.appsflyer.com/hc/reference/post_tax-rates-app-app-id)：特定のアプリについて、カスタムの税率ルールを作成・取得します。

純収益の計算方法は、<Anchor target="_blank" href="/marketers/ja/docs/about-roi360-store-revenue#true-revenue">「純収益」</Anchor>を参照してください。

> 📘 **注意**
>
> 純収益は、ローデータレポートと、マイダッシュボードの純収益ベースの指標（純収益、純ROI、純ROAS、純ARPU、純利益）に表示されます。

## 税率ルールの更新

ROI360で計測する取引の税金は、デフォルトの税率設定に基づいて報告されます。表示価格に税金が含まれる*税込価格を採用する国*では、税金を差し引いて純収益を計算します。例えば英国では、AppsFlyerは税金とストア手数料の合計額を差し引きます。米国など、表示価格に税金が含まれない*税抜価格を採用する国*では、デフォルトで収益と純収益のパラメータに税金は含まれません。

純収益APIで税率ルールを設定するには、次の手順を実行します。

1. ROI360ストア収益の設定で、次の手順を完了します。

   <div id="ios" />

   <Accordion title="iOS">

   * <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue#手順1iosapp-store-connectのキーの設定">手順1｜ App Store Connectのキーの設定</Anchor>
   * <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue#手順2iosapp-storeのサーバー通知の設定">手順2｜ App Storeのサーバー通知の設定</Anchor>

   </Accordion>

   <div id="android" />

   <Accordion title="Android">

   * <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue#手順1androidサービスアカウントのキーと権限の設定">手順1｜サービスアカウントのキーと権限の設定</Anchor>
   * <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue#手順2androidgoogle-playのサーバー通知の設定">手順2｜ Google Playのサーバー通知の設定</Anchor>

   </Accordion>

2. 開発者に、次の情報を渡します。
   * 認証キーとして使用する<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">API V2トークン</Anchor>。
   * 計算に使用する税金を指定するパラメータと値。以下の表を参照してください。
3. 開発者に、[税率設定REST API](https://dev.appsflyer.com/hc/reference/post_tax-rates-app-app-id)を使って税率ルールを作成するよう依頼します。 POSTリクエストの本文に、JSONファイルを指定します。[このJSONファイル](https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub)には、対応するすべての国と、各国のデフォルトの税率が含まれています。開発者は、このファイルを必要に応じて編集するか、そのままAPIで使用できます。

### 税率設定APIのパラメータ

| パラメータ | 必須 | 補足 |
| --- | --- | --- |
| `tax_name` | はい | <ul><li>顧客の請求書に表示される、税の種類を表す名前。</li><li>例：Sales、VAT、GST</li></ul> |
| `tax_rate` | はい | <ul><li>0より大きい値を指定してください。</li><li>徴収する税率を表す数値。小数点以下4桁まで指定できます。</li><li>例：7.25</li></ul> |
| `tax_exclusive` | いいえ | <ul><li>trueまたはfalseを指定するブール値のパラメータ。</li><li>falseは、収益の総額に税金が含まれることを表します。</li><li>trueは、表示された収益の総額とは別に税金が加算されることを表します。例えば、表示価格に売上税を含めない米国やカナダが該当します。</li><li>デフォルトはfalseです。</li></ul> |
| `country` | いいえ | <ul><li>税が適用される国の[ISO準拠の2文字の国コード](https://www.nationsonline.org/oneworld/country_code_list.htm)。</li><li>例：CA</li><li>**注意：** 英国にはGBではなくUKを使用します。</li></ul> |
| `subdivision` | いいえ | <ul><li>一部の国では、州などの行政区画を追加で指定できます。</li><li>[ISO 3166-2の行政区画コード](https://service.unece.org/trade/locode/2022-2%20SubdivisionCodes.htm)に従って処理されます。</li><li>国コードと行政区画コードの両方を含める必要があります。</li><li>例：US-CA</li></ul> |
| `postal_code` | いいえ | <ul><li>文字、数字、またはその組み合わせからなる文字列。</li><li>例：L4J8E3</li></ul> |
| `deduction_order` | いいえ | <ul><li>**0**、**1**、**2**のいずれかを指定する列挙値：<ul><li>**0**：総収益から先にストア手数料を差し引き、残額から税金を差し引きます。</li><li>**1**：総収益から先に税金を差し引き、残額からストア手数料を差し引きます。</li><li>**2**：税金とストア手数料の両方を、総収益を基準に差し引きます。</li></ul></li></ul> |

## ストア手数料率の設定

AppsFlyerは、デフォルトで標準のストア手数料の計算ルールを適用し、純収益を算出します。 App Storeのデフォルト値は、国・地域によって異なります（各ストアの現在の料率は、<Anchor target="_blank" href="/marketers/ja/docs/about-roi360-store-revenue#true-revenue">「ROI360ストア収益について」</Anchor>を参照）。通常と異なる料率や優遇料率が適用されるアプリでは、純収益APIでアプリごとにストア手数料率を変更します。

例：

* 次のようなストア手数料の優遇制度の対象となる場合：
  * Apple App Store Small Business Program（手数料率15%。中国本土（CN）では12%）
  * Google Playの15%サービス手数料率（年間収益の最初の100万米ドルまで）
* 適用されるストア手数料率が変わった場合。AppsFlyerは変更を自動で把握できないため、純収益APIで手動更新する必要があります。例：
  * 手数料の優遇条件を満たした時点で、低い手数料率を適用する。
  * 優遇条件を満たさなくなった時点で、デフォルトの手数料計算ルールに戻す。

### 純収益APIによるストア手数料の更新

純収益APIを使って、次のようにストア手数料の設定を管理できます。

* GETリクエストで、アカウント内のアプリのストア手数料率を取得し、現在の設定を確認する。
* 必要な手数料率を指定したPOSTリクエストで、カスタムの手数料率を適用する。
* 対象アプリに対するDELETEリクエストで、デフォルトの計算ルールに戻す。

APIを使用する前に：

1. ROI360ストア収益の設定で、次の手順を完了します。

   <div id="ios::f410adfc" />

   <Accordion title="iOS">

   * <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue#手順1iosapp-store-connectのキーの設定">手順1｜ App Store Connectのキーの設定</Anchor>
   * <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue#手順2iosapp-storeのサーバー通知の設定">手順2｜ App Storeのサーバー通知の設定</Anchor>

   </Accordion>

   <div id="android::659c7976" />

   <Accordion title="Android">

   * <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue#手順1androidサービスアカウントのキーと権限の設定">手順1｜サービスアカウントのキーと権限の設定</Anchor>
   * <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue#手順2androidgoogle-playのサーバー通知の設定">手順2｜ Google Playのサーバー通知の設定</Anchor>

   </Accordion>

2. 次の情報を準備します。
   * 認証キーとして使用するAPI V2トークン
   * 適用するストア手数料率（指定できる値：1%～30%）
   * カスタム手数料率を適用するアプリのID
3. 次の設定上の注意点を確認してください。
   * ストア手数料は**アプリごと**に設定します。
   * 指定できる値は**1%～30%** です。
   * 設定が適用されるのは、**新たに受信するイベントのみ**です。
   * カスタムの手数料率を設定していない場合は、**デフォルトのストア手数料計算ルール**が適用されます。

リクエストの構造と例の詳細は、[純収益APIのドキュメント](https://dev.appsflyer.com/hc/reference/overview-7)を参照してください。

<div data-zendesk-anchors="h_01KEFDF4KD0DCMP5DGE7ZJDBGX=%E6%B3%A8%E6%84%8F update-tax-rate-rules=%E7%A8%8E%E7%8E%87%E3%83%AB%E3%83%BC%E3%83%AB%E3%81%AE%E6%9B%B4%E6%96%B0 h_01KEFDF4KDJ5PVS3AW46BS57NC=%E7%A8%8E%E7%8E%87%E3%83%AB%E3%83%BC%E3%83%AB%E3%81%AE%E6%9B%B4%E6%96%B0 h_01KEFDRXY0FWKKK0DK6PS340TC=ios h_01KEFDRXY0RTBH293JQXFWYAM2=android tax-rate-api-parameters=%E7%A8%8E%E7%8E%87%E8%A8%AD%E5%AE%9Aapi%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01KEFDF4KD60SEVBQ8G228PEXD=%E7%A8%8E%E7%8E%87%E8%A8%AD%E5%AE%9Aapi%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF set-up-store-commission-rates=%E3%82%B9%E3%83%88%E3%82%A2%E6%89%8B%E6%95%B0%E6%96%99%E7%8E%87%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KEFDF4KDP4PFKFQ0D9FN8P5D=%E3%82%B9%E3%83%88%E3%82%A2%E6%89%8B%E6%95%B0%E6%96%99%E7%8E%87%E3%81%AE%E8%A8%AD%E5%AE%9A update-store-commission-with-the-net-revenue-api=%E7%B4%94%E5%8F%8E%E7%9B%8Aapi%E3%81%AB%E3%82%88%E3%82%8B%E3%82%B9%E3%83%88%E3%82%A2%E6%89%8B%E6%95%B0%E6%96%99%E3%81%AE%E6%9B%B4%E6%96%B0 h_01KEFDF4KDVTHTGKJ35CQ1GQ1E=%E7%B4%94%E5%8F%8E%E7%9B%8Aapi%E3%81%AB%E3%82%88%E3%82%8B%E3%82%B9%E3%83%88%E3%82%A2%E6%89%8B%E6%95%B0%E6%96%99%E3%81%AE%E6%9B%B4%E6%96%B0 h_01KEFDWVDFBPP7NPSZV0PRGKPZ=ios::f410adfc h_01KEFDWVDFZPHJP6EG0CPNG5A0=android::659c7976" />
