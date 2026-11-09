---
title: おすすめのホテル予約アプリイベント
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
  created_at: '2021-04-29T14:49:54Z'
  edited_at: '2026-10-14T09:36:12Z'
  id: 360019843558
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/360019843558
---
> **概要：** 概要：ホテル予約アプリで推奨されるアプリ内イベントを記録して、ユーザージャーニー全体を通じてユーザーの質を計測しましょう。

## <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="100px" /> Hotel booking

ホテル予約アプリを使用すると、簡単にホテルを予約できるだけでなく、最も優れた割引価格を選ぶことができます。計測をお勧めする一般的なイベントは、検索、購入、旅行の予約、ウィッシュリストへ追加などです。

これらのイベントを計測することで、次のような判断に役立ちます。

* どのキャンペーンやメディアソースが実際に旅行を予約するユーザーをもたらしているか
* どのキャンペーンやメディアソースが最も多く予約し、収益性の高いユーザーをもたらしているか

ホテルの評価、季節、国、子供の数などの設定を、特定のメディアソースから訪れるユーザーに紐づけることができます。そして、それらのユーザー設定をターゲティングすることでキャンペーンを最適化できます。

<div id="important" />

> 🚧 **重要！**
>
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * 実装プロセスを合理化するには、<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=hotel_booking">アプリ内イベントジェネレーター</Anchor>を使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、Unity開発者向けの <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=hotel_booking&view=code">コードサンプル</Anchor> があります。
> * 開発担当者向けの詳細な手順は、**<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyerディベロッパーハブ</Anchor>** を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

<Image align="center" alt="Flowchart_for_recommended_events_hotel_booking_app_user_journey" src="https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png" />

<div id="recommended-structures-for-predefined-events" />

## 規定イベントで推奨される構造

次のセクションでは、ホテル予約アプリで一般的なイベント構造のリストを示しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="complete-registration-af_complete_registration" />

<Accordion title="登録を完了する (af_complete_registration)">

**目的**

アプリをインストールしてサインアッププロセスを完了したユーザー数、ユーザーが好むサインアップ方法、実際にサインアップするユーザーを引き付けるメディアソースについて理解しましょう。

**トリガー**

ユーザーがサインアップ手順を完了したとき

イベントパラメーター

| フィールド名 | 説明 | 値の例 |
| --- | --- | --- |
| af\_登録方法 | サインアップ方法の種類 | Email、Facebook |

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

<div id="search-af_search" />

<Accordion title="検索 (af_search)">

**目的**

ユーザーが探しているものを知り、どの検索結果が最も関連性が高く購入に繋がったかさらに、特定の地域のユーザーが何を検索しているかを確認し、これに応じて、さまざまなメディアソースでターゲットを定めることができます。

**トリガー**

ユーザーが検索を実行したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_date\_a | チェックイン日 | 2024-02-26 |
| af\_date\_b | チェックアウト日 | 2024-02-26 |
| af\_destination\_a | ユーザーロケーション | ロンドン |
| af\_destination\_b | ホテルの場所 | マドリード |
| af\_num\_adults | 宿泊者数 | 2 |
| af\_num\_children | 子供の数 | 0 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="コンテンツビュー (af_content_view)">

**目的**

このイベントは、次のような判断に役立ちます。

* 検索結果が検索キーワードと関連性があるかを把握します。
* ユーザーが探しているプロパティの種類
* 季節的なトレンド
* 人気のある場所
* 広告やプロモーションでユーザーを引き寄せ、そのユーザーをリターゲティングするメディアソースはどれか

**トリガー**

ユーザーが物件を閲覧しているとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | ホテルの定価 | 674 |
| af\_content\_id | ホテルID |  |
| af\_date\_a | チェックイン日 | 2024-02-26 |
| af\_date\_b | チェックアウト日 | 2024-02-26 |
| af\_destination\_a | ユーザーロケーション | ロンドン |
| af\_destination\_b | ホテルの場所 | マドリード |
| af\_class | 客室タイプ | デラックス |
| af\_num\_adults | 宿泊者数 | 2 |
| af\_num\_children | 子供の数 | 0 |
| af\_hotel\_score | レビューによるホテルスコア | 9.6 |
| af\_推奨星評価 | 希望するホテルの星評価 | 5 |
| af\_preferred\_neighborhoods | ホテルが位置するエリア | 中心部 |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="ウィッシュリストに追加 (af_add_to_wishlist)">

**目的**

ユーザーが予約に関心のあるホテルと目的地を記録します。例えば、ユーザーが探しているホテル、地域、評価が分かれば、このデータを使用してユーザーをリターゲティングできます。

**トリガー**

ユーザーがウィッシュリストにリストを追加したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | ホテルの定価 | 674 |
| af\_content\_id | ホテルID |  |
| af\_date\_a | チェックイン日 | 2024-02-26 |
| af\_date\_b | チェックアウト日 | 2024-02-26 |
| af\_destination\_a | ユーザーロケーション | ロンドン |
| af\_destination\_b | ホテルの場所 | マドリード |
| af\_class | 客室タイプ | デラックス |
| af\_num\_adults | 宿泊者数 | 2 |
| af\_num\_children | 子供の数 | 0 |
| af\_hotel\_score | レビューによるホテルスコア | 9.6 |
| af\_推奨星評価 | 希望するホテルの星評価 | 5 |
| af\_preferred\_neighborhoods | ホテルが位置するエリア | 中心部 |
| purchase\_method | 購入方法 | クレジットカード |
| af\_クーポンコード | プロモーションコードまたはロイヤルティー報酬ポイント |  |
| property\_type | 物件タイプ | ホテル |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="チェックアウト開始 (af_initiated_checkout)">

**目的**

購入者がチェックアウトを開始する際の行動を理解しましょう。このイベントは、次のような判断に役立ちます。

* クレジットカードやeウォレットなど、どのような購入方法が使用されたか
* ユーザーがチェックアウトを完了したかどうか

**トリガー**

ユーザーがクレジットカード情報を追加、またはeウォレットを接続したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | ホテルの定価 | 674 |
| af\_content\_id | ホテルID |  |
| af\_date\_a | チェックイン日 | 2024-02-26 |
| af\_date\_b | チェックアウト日 | 2024-02-26 |
| af\_destination\_a | ユーザーロケーション | ロンドン |
| af\_destination\_b | ホテルの場所 | マドリード |
| af\_class | 客室タイプ | デラックス |
| af\_num\_adults | 宿泊者数 | 2 |
| af\_num\_children | 子供の数 | 0 |
| af\_hotel\_score | レビューによるホテルスコア | 9.6 |
| af\_推奨星評価 | 希望するホテルの星評価 | 5 |
| af\_preferred\_neighborhoods | ホテルが位置するエリア | 中心部 |
| purchase\_method | 購入方法 | クレジットカード |
| af\_クーポンコード | プロモーションコードまたはロイヤルティー報酬ポイント |  |
| property\_type | 物件タイプ | ホテル |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="購入 (af_purchase)">

**目的**

ホテル予約アプリの購入トレンドを理解しましょう。このイベントを計測すると、次のことに役立ちます。

* アドネットワークと広告代理店間のユーザーのLTV（顧客生涯価値）とキャンペーンのROIを判断します。
* どのようなオファーがユーザーに最も人気があるのかを特定します。
* キャンペーンのターゲティングを最適化するために、購入されたアイテムとキャンペーンを相互参照します。

**トリガー**

購入が正常に完了しユーザーに「ありがとうございました」が表示されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | 購入による収益の予測 | 1205.99 |
| af\_price | 全体の購入金額の合計 | 4000 |
| af\_content\_id | 商品ID | 121 |
| af\_content\_type | 商品カテゴリ | hotel |
| af\_currency | Currency code | AUD |
| af\_数量 | カート内の商品の数 | 1 |
| 注文ID | 購入後に生成されるオーダーID | X123ABC |
| af\_領収書ID | CRITEOとGoogle AdWordsのリターゲティング連携に必要なオーダーID | X123ABC |

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="旅行予約 (af_travel_booking)">

**目的**

アプリの全体的な予約率を決定します。このイベントを計測すると、次のことに役立ちます。

* 予約から発生した収益を記録
* 子供と一緒にホテルを予約するユーザー数を把握
* 季節的なトレンドを理解
* 人気のあるホテルを決定

**トリガー**

ユーザーがホテルを予約した後で予約完了ページが表示されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | 予約による収益 | 647.95 |
| af\_currency | Currency code | 英ポンド |
| af\_price | ホテルの定価 | 674 |
| af\_content\_id | ホテルID |  |
| af\_date\_a | 2024-02-26 | チェックイン日 |
| af\_date\_b | チェックアウト日 | 2024-02-26 |
| af\_destination\_a | ユーザーロケーション | ロンドン |
| af\_destination\_b | ホテルの場所 | マドリード |
| af\_class | 客室タイプ | デラックス |
| af\_num\_adults | 宿泊者数 | 2 |
| af\_num\_children | 子供の数 | 0 |
| af\_hotel\_score | レビューによるホテルスコア | 9.6 |
| af\_推奨星評価 | 希望するホテルの星評価 | 5 |
| af\_preferred\_neighborhoods | ホテルが位置するエリア | 中心部 |
| purchase\_method | 購入方法 | クレジットカード |
| af\_クーポンコード | プロモーションコードまたはロイヤルティー報酬ポイント |  |
| property\_type | 物件タイプ | ホテル |
|  | ユーザーの初回予約 | true |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## カスタムイベントで推奨される構造

次のセクションでは、カスタムビエント名と推奨されるイベントパラメーターのイベント構造リストを示しています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="first-purchase-first_purchase" />

<Accordion title="初回購入 (first_purchase)">

**目的**

[購入](/docs/recommended-hotel-booking-app-events#purchase-af_purchase)イベントと同じです。さらに、このイベントは次のことを判断するのに役立ちます。

* 新規購入者が購入するまでにどれくらいの時間がかかるのか
* どの商品が初回購入時に購入されやすいか
* 初回購入の平均的な価格と収益

**トリガー**

ユーザーが最初の購入を完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | 購入からの収益 | 1205.95 |
| af\_price | 全体の購入金額の合計 | 4000 |
| af\_content\_id | 商品ID | 2024-02-26 |
| af\_content\_type | 商品カテゴリ | hotel |
| af\_currency | 通貨設定 | AUD |
| af\_数量 | カート内の商品の数 | 1 |
| 注文ID | 購入後に生成されるオーダーID | X123ABC |
| af\_領収書ID | CRITEOとGoogle AdWordsのリターゲティング連携に必要なオーダーID | X123ABC |

</Accordion>

<div data-zendesk-anchors="hotel-booking=-hotel-booking h_01HGTB0APWWTRER6GAWJ7TJ05S=-hotel-booking h_01HGTB0APWQDX7VN96GM7520ZH=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTB0APW933179Q90HFASW1V=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTB0APWRKRGCJ5TFKTPHH33=complete-registration-af_complete_registration h_01HGTB0APW1XY5R69CJ8PSQV6C=login-af_login h_01HGTB0APW5YF2DASC0HYDPTA9=search-af_search h_01HGTB0APXTQWBS4EXJ8D724G0=content-view-af_content_view h_01HGTB0APXS95QGK17RE8B3Y1E=add-to-wishlist-af_add_to_wishlist h_01HGTB0APX1XX2W3YX85W75F6B=initiated-checkout-af_initiated_checkout h_01HGTB0APXGPW16FRY3C7VSMDM=purchase-af_purchase h_01HGTB0APXJFHMPGYC63ZTV4R9=travel-booking-af_travel_booking recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTB0APXP6WVM1AVEMEY6KVS=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTB0APX4ND0NGVTK9FA38QR=first-purchase-first_purchase" />
