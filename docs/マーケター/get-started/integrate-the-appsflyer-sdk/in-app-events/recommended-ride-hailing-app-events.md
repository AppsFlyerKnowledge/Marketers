---
title: おすすめの配車アプリイベント
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
  created_at: '2021-04-29T08:42:34Z'
  edited_at: '2026-10-14T09:28:27Z'
  id: 360019651957
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/360019651957
---
> **概要：** 概要：配車アプリで推奨されるアプリ内イベントを記録して、ユーザージャーニー全体を通したユーザーの質を計測しましょう。

## <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="100px" /> Ride-hailing

近年、配車サービスが人気を集めています。特に、大半の住民が自動車を所有していない都市部で人気となっています。計測を推奨する一般的なイベントは、配車リクエストと予約です。

これらのイベントを計測することで、次のような判断に役立ちます。

* 乗客とドライバーがどのように交流しているか
* 配車サービスの利用率の高い国
* 価格、乗車回数、乗車距離に関する指標

<div id="important" />

> 🚧 **重要！**
>
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * 実装プロセスを合理化するには、<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ride_hailing">アプリ内イベントジェネレーター</Anchor>を使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、および Unity 開発者向けの <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ride_hailing&view=code">コードサンプル</Anchor> があります。
> * 開発担当者向けの詳細な手順は、**<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyerディベロッパーハブ</Anchor>** を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

[![Flowchart_for_recommended_events_ride_hailing_app_user_journey](https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png)](https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png)

<div id="recommended-structures-for-predefined-events" />

## 規定イベントで推奨される構造

次のセクションでは、配車サービスアプリの一般的なイベント構造の一覧を示しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="complete-registration-af_complete_registration" />

<Accordion title="登録を完了する (af_complete_registration)">

**目的**

このイベントを計測すると、次のことに役立ちます。

* ユーザーがどのような登録方法を好むか
* アプリをダウンロードして、インストールした後に、実際に登録したユーザーの数
* 国ごとの登録トレンドを確認し、ユーザーがアプリを使用する可能性の高い国を判断します

**トリガー**

ユーザーがサインアップ手順を完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_登録方法 | ユーザーがサインアップしたプラットフォームや方法 | Facebook |
| country\_code | 国コード（電話局番） | 66 |

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

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="支払い情報の追加 (af_add_payment_info)">

**目的**

ユーザーを分類するのに役立ちます。これは、次のことに役立ちます。

* ユーザーが支払い情報を追加するのにかかる時間を確認します。
* 最もよく使用される支払い方法 (クレジットカード、e-Wallet) を確認します。
* キャンペーンを設定し、人気のある決済プロバイダーとコラボレーションしましょう

**トリガー**

ユーザーがアカウントに支払い情報を正常に追加したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_成功 | 支払い方法が成功したかどうか | true |
| credit\_card\_type | クレジットカードのタイプ (オプション) | Visa、Mastercard |
| payment\_method\_type | 決済方法の種類 |  |

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="使用したクレジット (af_spent_credits)">

**目的**

このパラメーターは、乗客が各乗車で獲得したクレジットを記録します。乗客はこのクレジットをクーポンや割引と交換することができます。

このイベントを計測すると、次のことに役立ちます。

* クレジットを利用してクーポンを獲得した乗客の数
* 乗客が好むクーポンや割引の種類

**トリガー**

乗客がクレジットを使用したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_content | クーポンや割引のタイプ | 映画のチケット1回分 |
| credits\_used | 使用されたクレジット数 | 1000 |
| credits\_remaining | アカウントのクレジット残高 | 2090 |
| invoice\_id | クレジットの使用で発生した請求書のID | KO215123SD |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## カスタムイベントで推奨される構造

次のセクションでは、カスタムビエント名と推奨されるイベントパラメーターのイベント構造リストを示しています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="ride-booking-requested-ride_booking_requested" />

<Accordion title="配車予約リクエスト（ride_booking_requested）">

**目的**

このイベントを計測すると、次のことに役立ちます。

* 人気のある目的地について知る
* ユーザーの出発地や目的地などのトレンドを理解しましょう
* 平均的な乗車距離を確認します
* 大半のユーザーが居住する都市、地域、国を確認できます

加えて、予約に関するイベントと一緒にこれらのイベントを計測することで、取引が正常に完了したことを記録できます。その後、成功した取引と失敗した取引を比較できます。例えば、リクエストされた乗車予約の数と、完了した乗車予約またはキャンセルされた乗車予約の数を確認できます。

**トリガー**

乗客が配車予約リクエストを作成したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 乗車料金の見積もり | 22.4 |
| af\_currency | 通貨設定 | SGD |
| af\_destination\_a | 出発地 | プラザ・シンガプーラ |
| af\_destination\_b | 到着地 | マリーナベイ・サンズ |
| 距離 | 出発地から到着地までの距離 | 5.2 |
| af\_content\_type | 交通機関の種類 | タクシー |
| payment\_method\_type | 決済方法の種類 |  |
| 都市 | 乗車を予約した都市 | シンガポール |
| af\_地域 | 乗車を予約した地域 | SFA |
| af\_country | 乗車を予約した国 | シンガポール |
| order\_id | 注文ID | 135790 |

</Accordion>

<div id="ride-booking-confirmed-ride_booking_confirmed" />

<Accordion title="配車予約確認済み (ride_booking_confirmed)">

**目的**

このイベントを計測すると、次のことに役立ちます。

* 最も稼働率の高いドライバーが誰かを知ることができます
* ドライバーがよくリクエストされる目的地
* 各ドライバーの平均や全体の価格

さらに、このイベントに加えて、他の3つの予約関連イベントを計測すると、ドライバーのアクティビティを詳しく確認するために役立ちます。例えば、配車予約リクエストを最も多く確認しているドライバーやロングライドではなくショートライドを選択しているドライバーなどを確認できます。

<div id="trigger" />

#### **トリガー**

ドライバーが予約を承認したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 乗車料金の見積もり | 22.4 |
| af\_currency | 通貨設定 | SGD |
| af\_destination\_a | 出発地 | プラザ・シンガプーラ |
| af\_destination\_b | 到着地 | マリーナベイ・サンズ |
| 距離 | 出発地から到着地までの距離 | 5.2 |
| af\_content\_type | 交通機関の種類 | タクシー |
| driver\_id |  | 1706 |
| payment\_method\_type | 決済方法の種類 |  |
| 都市 | 乗車を予約した都市 | シンガポール |
| af\_地域 | 乗車を予約した地域 | SFA |
| af\_country | 乗車を予約した国 | シンガポール |
| 注文ID | 注文ID | 135790 |

</Accordion>

<div id="ride-booking-canceled-ride_booking_canceled" />

<Accordion title="配車予約のキャンセル (ride_booking_canceled)">

**目的**

このイベントを計測すると、次のことに役立ちます。

* キャンセルの多いドライバーや乗客を記録します
* キャンセルされた回数を把握します
* キャンセル率と価格、目的地、距離、都市などの属性との相関性を把握します
* 乗車予約がキャンセルされた理由を把握します

**トリガー**

予約がキャンセルされたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 乗車料金の見積もり | 22.4 |
| af\_currency | 通貨設定 | SGD |
| af\_destination\_a | 出発地 | プラザ・シンガプーラ |
| af\_destination\_b | 到着地 | マリーナベイ・サンズ |
| 距離 | 出発地から到着地までの距離 | 5.2 |
| af\_content\_type | 交通機関の種類 | タクシー |
| driver\_id |  | 1706 |
| cancelation\_reason | 配車予約がキャンセルされた理由 | 価格が高すぎる、ドライバーが現れなかった、乗客が現れなかった |
| payment\_method\_type | 決済方法の種類 |  |
| 都市 | 乗車を予約した都市 | シンガポール |
| af\_地域 | 乗車を予約した地域 | SFA |
| af\_country | 乗車を予約した国 | シンガポール |
| order\_id | 注文ID | 135790 |
| canceled\_by | 乗車予約が乗客またはドライバーのどちらによってキャンセルされたか | 乗客 |

</Accordion>

<div id="ride-booking-completed-ride_booking_completed" />

<Accordion title="配車予約の完了 (ride_booking_completed)">

**目的**

このイベントを計測すると、次のことに役立ちます。

* 乗客の支出とドライバーの収入の詳細を理解しましょう
* 乗車の完了を、目的地、距離、支払いタイプ、ドライバーIDなどの属性と関連付けます。
* ドライバーと乗客の平均移動距離と全体的な移動距離を確認します
* 完了した乗車と、キャンセルされた乗車を比較します
* ドライバーのスコアを記録し計測します。

**トリガー**

乗車が完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 乗車料金の見積もり | 22.4 |
| af\_currency | 通貨設定 | SGD |
| af\_destination\_a | 出発地 | プラザ・シンガプーラ |
| af\_destination\_b | 到着地 | マリーナベイ・サンズ |
| 距離 | 出発地から到着地までの距離 | 5.2 |
| af\_content\_type | 交通機関の種類 | タクシー |
| driver\_id |  | 1706 |
| payment\_method\_type | 決済方法の種類 |  |
| 都市 | 乗車を予約した都市 | シンガポール |
| af\_地域 | 乗車を予約した地域 | SFA |
| af\_country | 乗車を予約した国 | シンガポール |
| order\_id | 注文ID | 135790 |
| credits\_earned | 乗車を完了したことにより、乗客が獲得したクレジット | 248 |

</Accordion>

<div data-zendesk-anchors="ridehailing=-ride-hailing h_01HGTAZ7J64RZE35JP8XPKMTPZ=-ride-hailing h_01HGTAZ7J6N36EH492QDXCQYB1=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAZ7J6FJ8R9VXKK0F1A1E1=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAZ7J6FQQKV7JB0Z9MG8CD=complete-registration-af_complete_registration h_01HGTAZ7J6YM8DJ96E7Q4M4Y8Q=login-af_login h_01HGTAZ7J67MNJ8T9B9W4NJ5Y9=add-payment-info-af_add_payment_info h_01HGTAZ7J6Z3EX03JTPZFHJJF6=spent-credits-af_spent_credits recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAZ7J6Z6NE8D5A10CRJJH4=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAZ7J6WCY2BQJPSNSTJRQ0=ride-booking-requested-ride_booking_requested h_01HGTAZ7J78J1X3VAYMH8Q3ZBA=ride-booking-confirmed-ride_booking_confirmed trigger=%E3%83%88%E3%83%AA%E3%82%AC%E3%83%BC h_01HGTAZ7J7C4R7A7KT2S95835J=%E3%83%88%E3%83%AA%E3%82%AC%E3%83%BC h_01HGTAZ7J797KA791H1621F9TE=ride-booking-canceled-ride_booking_canceled h_01HGTAZ7J789CJ8P6X8B0V7A64=ride-booking-completed-ride_booking_completed" />
