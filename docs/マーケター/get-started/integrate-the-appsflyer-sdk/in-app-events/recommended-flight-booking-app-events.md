---
title: フライト予約アプリの推奨イベント
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
  created_at: '2021-04-29T13:07:29Z'
  edited_at: '2026-10-29T07:44:10Z'
  id: 360019670857
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/360019670857
---
> **概要：** フライト予約アプリで推奨アプリ内イベントを記録し、ユーザーの一連の行動に基づいてユーザーの質を評価します。

<div id="-flight-booking" />

## <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="100px" /> フライト予約

フライト予約アプリでは、旅行者が魅力的なプランや運賃を比較し、簡単に航空券を予約できます。記録を推奨する代表的なイベントは、フライトの予約、フライトの検索、航空券のプランの閲覧です。

イベントを記録すると、次のことができます。

* 人気の目的地の把握
* 季節ごとの傾向の分析
* ユーザーによく選ばれる航空会社の把握

<div id="important" />

> 🚧 **重要**
>
> * アプリ内イベントの実装に関するマーケター向けの<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor>を必ずお読みください。
> * 実装を効率よく進めるには、<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=flight_booking">アプリ内イベント生成ツール</Anchor>を利用してください。このツールには、本記事で紹介する代表的なアプリ内イベントがすべて含まれており、ビジネス上の要件に合わせて変更できます。イベントの設定が完了したら、生成したファイルを開発者に共有してください。
> * 本記事の各推奨イベントには、iOS、Android、Unityの開発者向けの<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=flight_booking&view=code">コードサンプル</Anchor>があります。
> * 開発者向けの詳しい手順は、**<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyerの開発者向けドキュメント</Anchor>で確認できます**。
>
> アプリ内イベントの記録については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">アプリ内イベントガイド</Anchor>を参照してください。

[![Flowchart_for_recommended_events flight_booking_app_user_journey](https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png)](https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png)

<div id="recommended-structures-for-predefined-events" />

## 定義済みイベントの推奨構成

以下に、フライト予約業界で一般的に使用されるイベント構成を示します。各構成には、定義済みのイベント名と、使用を推奨するイベントパラメータが含まれています。アプリ内イベントには、ビジネス上の要件に合う任意のイベントパラメータを含められます。

<div id="complete-registration-af_complete_registration" />

<Accordion title="登録完了（af_complete_registration）">

**目的**

アプリをインストールして登録を完了したユーザー数や、ユーザーに好まれる登録方法を把握します。

**送信タイミング**

ユーザーが登録を完了したとき

イベントパラメータ

| フィールド名 | 説明 | 値の例 |
| --- | --- | --- |
| af\_registration\_method | 登録方法の種類 | email, Facebook |

</Accordion>

<div id="login-af_login" />

<Accordion title="ログイン（af_login）">

**目的**

登録済みユーザーの継続利用状況の把握

**送信タイミング**

ユーザーがログインに成功したとき

**イベントパラメータ**

追加のパラメータなしで送信できます。

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="旅行予約（af_travel_booking）">

**目的**

フライトの予約は、アプリの中心となる機能です。このイベントを使用すると、次のことを把握できます。

* 人気の目的地
* 人気の航空会社
* 季節ごとの傾向

**送信タイミング**

フライトの予約が正常に完了し、ユーザーがサンクスページにアクセスしたとき

**イベントパラメータ**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 予約による収益 | 647.99 |
| af\_currency | 通貨コード | SGD |
| af\_price | 価格 | 674 |
| af\_content\_id | 航空券のプランのID | ODIRNH |
| af\_departing\_departure\_date | 出発日 | 2018-06-21 |
| af\_returning\_departure\_date | 復路の出発日 | 2018-06-26 |
| af\_destination\_a | 出発地 | BKK |
| af\_destination\_b | 到着地（該当する場合） | SYD |
| airline\_code | 航空会社のコード | KLM |
| af\_class | 予約した航空券の搭乗クラス | economy |
| purchase\_method | 購入時の支払い方法 | credit card |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="コンテンツの閲覧（af_content_view）">

**目的**

このイベントを使用すると、次のことを把握できます。

* ユーザーが特に関心を示す航空券のプラン
* 検索結果が検索条件に合っているかどうか

**送信タイミング**

ユーザーが検索結果をクリックしたとき

**イベントパラメータ**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_departing\_departure\_date | 出発日 | 2018-06-21 |
| af\_returning\_departure\_date | 復路の出発日 | 2018-06-26 |
| af\_destination\_a | 出発地 | BKK |
| af\_destination\_b | 到着地（該当する場合） | SYD |

</Accordion>

<div id="search-af_search" />

<Accordion title="検索（af_search）">

**目的**

フライト予約アプリでは、ユーザーがフライトや割引運賃などを検索できます。検索パラメータを記録することで、ユーザーの好みを把握できます。このイベントを使用すると、次のことができます。

* ユーザーが探している内容の把握
* 最も人気のある目的地の把握
* 子どもと一緒に旅行するユーザー数の把握
* ユーザーが旅行先に行きたい時期や、旅行を予定している時期の把握

**送信タイミング**

ユーザーが検索フォームに入力し、検索ボタンをクリックした後

**イベントパラメータ**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_num\_children | 旅行する子どもの人数 | 0 |
| af\_destination\_a | 出発地 | BKK |
| af\_destination\_b | 到着地（該当する場合） | SYD |
| af\_departing\_departure\_date | 出発日 | 2018-06-21 |
| af\_returning\_departure\_date | 復路の出発日 | 2018-06-26 |
| af\_num\_infants | 旅行する乳児の人数 | 0 |
| af\_num\_adults | 旅行する大人の人数 | 1 |

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="支払い情報の追加（af_add_payment_info）">

**目的**

フライト予約時の支払い情報の追加について、成功した操作と失敗した操作の両方を記録します。

**送信タイミング**

ユーザーがフライト予約ボタンをクリックしたとき

**イベントパラメータ**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_success | 支払い方法の追加に成功したかどうか | true |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="購入（af_purchase）">

**目的**

フライト予約アプリでの購入傾向を把握します。このイベントを使用すると、次のことができます。

* アドネットワーク別・広告代理店別のユーザーLTVとキャンペーンROIの把握
* ユーザーに最も人気のある航空券のプランの把握
* キャンペーンと購入内容を照合し、キャンペーンのターゲティングを最適化

**送信タイミング**

購入が正常に完了し、ユーザーがサンクスページにアクセスしたとき

**イベントパラメータ**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 購入による推定収益 | 1205.99 |
| af\_price | 購入の合計金額 | 4000 |
| af\_content\_id | アイテムID | 121 |
| af\_content\_type | アイテムのカテゴリ | flight |
| af\_currency | 通貨コード | AUD |
| af\_quantity | カート内のアイテム数 | 1 |
| af\_order\_id | 購入後に生成される注文のID | X123ABC |
| af\_receipt\_id | 注文ID。CriteoとGoogle Adsのリターゲティング連携で必須です。 | X123ABC |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## カスタムイベントの推奨構成

以下に、カスタムイベント名と使用を推奨するイベントパラメータを含むイベント構成を示します。アプリ内イベントには、ビジネス上の要件に合う任意のイベントパラメータを含められます。

<div id="first-purchase-first_purchase" />

<Accordion title="初回購入（first_purchase）">

**目的**

[購入](/docs/recommended-flight-booking-app-events#purchase-af_purchase)イベントと同じです。さらに、このイベントを使用すると、次のことを把握できます。

* 新規購入者が購入に至るまでの時間
* 初回購入者に人気のフライト
* 初回購入の平均価格と平均収益

**送信タイミング**

ユーザーが初回購入を完了したとき

**イベントパラメータ**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 購入による収益 | 1205.99 |
| af\_price | 購入の合計金額 | 4000 |
| af\_content\_id | アイテムID | 121, 262 |
| af\_content\_type | アイテムのカテゴリ | flight |
| af\_currency | 通貨 | AUD |
| af\_quantity | カート内のアイテム数 | 1 |
| af\_order\_id | 購入後に生成される注文のID | X123ABC |
| af\_receipt\_id | 注文ID。CriteoとGoogle Adsのリターゲティング連携で必須です。 | X123ABC |

</Accordion>

<div data-zendesk-anchors="flight-booking=-%E3%83%95%E3%83%A9%E3%82%A4%E3%83%88%E4%BA%88%E7%B4%84 h_01HGTAZRKG0SQ66XK7VN9KVGEY=-%E3%83%95%E3%83%A9%E3%82%A4%E3%83%88%E4%BA%88%E7%B4%84 h_01HGTAZRKGGQBBAM4XJHR4B45P=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E6%8E%A8%E5%A5%A8%E6%A7%8B%E6%88%90 h_01HGTAZRKHK1427YX16HWRDRPN=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E6%8E%A8%E5%A5%A8%E6%A7%8B%E6%88%90 h_01HGTAZRKHACHNSNX9DSZ3ZZ51=complete-registration-af_complete_registration h_01HGTAZRKHTC9TNWNPACRZW31Y=login-af_login h_01HGTAZRKHZGW442XTZF99VGV9=travel-booking-af_travel_booking h_01HGTAZRKHGY0Z83ETZWAFNSWP=content-view-af_content_view h_01HGTAZRKH8JYE8Q6NDPF1PQC7=search-af_search h_01HGTAZRKH78CR2GH0960MS8R0=add-payment-info-af_add_payment_info h_01HGTAZRKHXE8VF78ZE0KF9AF6=purchase-af_purchase recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E6%8E%A8%E5%A5%A8%E6%A7%8B%E6%88%90 h_01HGTAZRKH4ZZEK5JGXZ7G5QDJ=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E6%8E%A8%E5%A5%A8%E6%A7%8B%E6%88%90 h_01HGTAZRKHG7GE4BKFDRHZC163=first-purchase-first_purchase" />
