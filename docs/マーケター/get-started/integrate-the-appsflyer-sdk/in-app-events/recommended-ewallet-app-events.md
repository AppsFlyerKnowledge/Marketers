---
title: おすすめのeWalletアプリイベント
metadata:
  keywords:
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
  created_at: '2021-06-10T11:36:07Z'
  edited_at: '2026-10-14T09:21:08Z'
  id: 4402425586065
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/4402425586065
---
> **概要：** 概要：この記事で提案されている電子マネーアプリ向けのアプリ内イベントを記録して、ユーザージャーニー全体を通してユーザーの質を計測しましょう。

## <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="67px" /> eWallet

電子マネーアプリを使用すると、ユーザーはデバイスを介してデジタル決済または購入を行うことができます。推奨される一般的な計測イベントには、資金の追加、コンテンツの表示、販売業者の選択、プロモーションの表示、決済完了などがあります。

このイベントを計測することで、次のことを決定することができます。

* どのようなコンテンツやプロモーションがユーザーに人気かを把握し、その後類似または関連する表示を提供することができます。
* 電子マネーを使用して請求書の支払いをする最も人気のあるサービスの種類は何かを把握できます。
* どの販売業者が最も人気が高いかを分析できます。

<div id="important" />

> 🚧 **重要！**
>
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * 実装プロセスを合理化するには、<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ewallet">アプリ内イベントジェネレーター</Anchor>を使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、および Unity 開発者向けの <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ewallet&view=code">コードサンプル</Anchor> があります。
> * 開発担当者向けの詳細な手順は、**<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyerディベロッパーハブ</Anchor>** を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

<Image align="center" alt="Flowchart_for_recommended_events e-Wallet_app_user_journey" src="https://files.readme.io/cf1f91f9c89d1f45448a6172e48b7f59fdce767f00c893d91b12a5f2d043945f-4404610923409.png" />

<div id="recommended-structures-for-predefined-events" />

## 規定イベントで推奨される構造

以下のセクションでは、電子マネー分野で一般的なイベント構造のリストを提供しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="complete-registration-af_complete_registration" />

<Accordion title="登録を完了する (af_complete_registration)">

**目的**

アプリをインストールし、サインアップを完了したユーザーがどれだけいるか、またユーザーが好むサインアップ方法を確認しましょう。

**トリガー**

ユーザーがサインアップ手順を完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_登録方法 | サインアップ方法の種類 | Email、Facebook、Google |

</Accordion>

<div id="login-af_login" />

<Accordion title="ログイン (af_login)">

**目的**

登録ユーザーのリテンションを理解しましょう

**トリガー**

ユーザーが正常にログインしたとき

**イベントパラメーター**

パラメーターなしで送信できます

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="コンテンツビュー (af_content_view)">

**目的**

特定のコンテンツの表示率を決定します。このイベントを計測すると、次のことに役立ちます。

* ユーザー向けにどのようなコンテンツが最も人気かを把握し、マーケティングキャンペーンを最適化することができます。
* アイテム表示と販売業者を関連付けることができます。

**トリガー**

ユーザーが特定のアイテムやカテゴリーコンテンツを表示したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| item | アイテムの種類 | cinema ticket |
| merchant\_name | 販売業者の名前 | cineplex |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## カスタムイベントで推奨される構造

次のセクションでは、カスタムビエント名と推奨されるイベントパラメーターのイベント構造リストを示しています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="wallet-complete-topup-wallet_complete_topup" />

<Accordion title="電子マネーの料金チャージ完了(wallet_complete_topup)">

**目的**

料金チャージは、パッケージやアプリ内で提供されているその他のサービスを購入するために使用されます。このイベントを記録し、他のデータと比較することでユーザーについて詳しく理解しましょう。例えば、ユーザーがアカウントに入金する金額を知り、チャージ金額を使用して、予算内でカスタマイズされたキャンペーンをターゲットにすることができます。

**トリガー**

ユーザーが銀行口座またはクレジットカードから電子マネーアプリに資金を追加したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| top\_up\_amount | 決済額 | 100 |
| top\_up\_method | 決済方法の種類 | bank transfer |

</Accordion>

<div id="payment-transaction-completed-payment_transaction_completed" />

<Accordion title="決済完了 ( payment_transaction_completed )">

**目的**

このイベントを計測すると、次のことに役立ちます。

* トランザクションで支払いを完了したユーザーを把握できます。
* 大規模なトランザクションを特定し、多額の資金をアプリに追加したユーザーをリターゲットします。

**トリガー**

特定の購入取引が完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| item | 支払われたアイテム | prepaid card reload |
| 量 | 支払額 | 1 |
| transaction\_amount | トランザクションの金額 | 50 |

</Accordion>

<div id="bill-payment-success-bill_payment_success" />

<Accordion title="請求書支払いの成功 (bill_payment_success)">

**目的**

このイベントは、ユーザーが請求書の支払い時に電子マネーアプリを使用する最も一般的なサービスの種類（水道代、電気代、クレジットカード残高など）を判断するのに役立ちます。

**トリガー**

ユーザーが電子マネーアプリを使用して請求書、クレジットカードの明細書、映画館のチケットなどの支払いを行ったとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| merchant\_name | 販売業者の名前 | Electricity provider |
| payment\_amount | 支払額 | 100 |
| カテゴリ | サービスの種類 | Electricity |

</Accordion>

<div id="promo-promo" />

<Accordion title="プロモーション (promo)">

**目的**

このイベントは、次のような判断に役立ちます。

* 提供されているプロモーションがユーザーに人気があるかどうか
* プロモーションがユーザーへの追加製品のクロスセルに役立つかどうか

**トリガー**

ユーザーがアプリ内で利用可能なプロモーションを選択したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| promo\_type | 提供されたプロモーションの種類 | 30% off |

</Accordion>

<div id="voucher-redeem-voucher_redeem" />

<Accordion title="クーポン使用 (voucher_redeem)">

**目的**

このイベントは、次のような判断に役立ちます。

* プロモーションコードを使用するユーザーの数
* ユーザーが好むクーポンや割引の種類

**トリガー**

ユーザーがクーポンコードを使用したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| voucher\_ID | クーポンのID | 1735103 |
| merchant\_name | 販売業者の名前 | cineplex |

</Accordion>

<div id="select-merchant-select_merchant" />

<Accordion title="販売業者の選択 ( select_merchant )">

**目的**

このイベントは、どの販売業者が最も人気があるかを判断し、このデータを使用して、類似のマーチャントに電子マネーサービスへの参加を試みるのに役立ちます。

**トリガー**

ユーザーが利用可能な販売業者のリストから選択したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| merchant\_name | 販売業者の名前 | cineplex |
| type | ビジネスの種類 | cinema |
| 金額 | 広告主が使用する通貨 | USD |
| merchant\_ID | トランザクションに関与する支払処理システムに、どの資金をどこに送金するかを指示するビジネスに添付された特定の ID | 123456 |

</Accordion>

<div id="scan-barcode-success-scan_barcode_success" />

<Accordion title="バーコードスキャンの成功 ( scan_barcode_success )">

**目的**

このイベントを計測すると、次のことに役立ちます。

* ユーザーが販売業者との特定の取引をいつ完了したかを理解できます。
* どの販売業者が最も人気が高いかを分析できます。

**トリガー**

ユーザーが電子マネーアプリを使用して訪問した各加盟店のQRコードをスキャンしたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| merchant\_name | 販売業者の名前 | cineplex |
| merchant\_ID | トランザクションに関与する支払処理システムに、どの資金をどこに送金するかを指示するビジネスに添付された特定の ID | 123456 |

</Accordion>

<div data-zendesk-anchors="ewallet=-ewallet h_01HGTAEVWFZXCA7AV0P35W992F=-ewallet h_01HGTAEVWFR4QS6XAT1T28N1R5=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAEVWF8SVYTQMQ12219HX0=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAEVWFBA3CD7ZA40VCER95=complete-registration-af_complete_registration h_01HGTAEVWGDBN8B3P2YHQJ5RYF=login-af_login h_01HGTAEVWGYFYEZBD3ZED7GGFG=content-view-af_content_view recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAEVWG39P9A84P926BG3VE=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAEVWGNYC5Z0ACHV8CFVNQ=wallet-complete-topup-wallet_complete_topup h_01HGTAEVWG36K4V4Z0NN8QYDNV=payment-transaction-completed-payment_transaction_completed h_01HGTAEVWG136M86GM1JPV74RH=bill-payment-success-bill_payment_success h_01HGTAEVWG34EXM28GW2ZN0NRC=promo-promo h_01HGTAEVWG0EHESWPQHCX4P3SH=voucher-redeem-voucher_redeem h_01HGTAEVWGKGC7N8ZB0MMQJ4YE=select-merchant-select_merchant h_01HGTAEVWG20101JC5VVK29Y0E=scan-barcode-success-scan_barcode_success" />
