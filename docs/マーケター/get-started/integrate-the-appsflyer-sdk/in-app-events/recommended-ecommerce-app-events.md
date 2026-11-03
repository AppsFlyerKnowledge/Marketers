---
title: おすすめのEコマースアプリイベント
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
  created_at: '2021-04-19T06:32:18Z'
  edited_at: '2026-10-14T09:29:28Z'
  id: 360019347957
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/360019347957
---
> **概要：** 概要：この記事で提案されているeコマースアプリ向けのイベントを記録して、ユーザージャーニー全体を通してユーザーの質を計測しましょう。

## <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="67px" /> eCommerce

eコマースアプリを使うと、ユーザーは、オンラインで商品を簡単に検索して購入できます。計測をお勧めする一般的なイベントは、検索、購入、カートへ追加、ウィッシュリストへ追加です。

これらのイベントを計測することで、次のような判断に役立ちます。

* 最も人気なカテゴリー
* 購入者が何を検索しているか
* チェックアウトを完了した購入者数
* リピーターと1回のみの購入者の人数

> 🚧 **重要：**
>
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * 実装プロセスを合理化するには、<Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce">アプリ内イベントジェネレーター</Anchor>を使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、および Unity 開発者向けの <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce&view=code">コードサンプル</Anchor> があります。
> * 開発担当者向けの詳細な手順は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">**AppsFlyerディベロッパーハブ**</Anchor>を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

[![Flowchart_for_recommended_events e-Commerce_app_user_journey](https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png)](https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png)

## 規定イベントで推奨される構造

次のセクションでは、eコマースアプリで一般的なイベント構造のリストを示しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="complete-registration-af_complete_registration" />

<Accordion title="登録を完了する (af_complete_registration)">

**目的**

アプリをインストールし、サインアップを完了したユーザーがどれだけいるか、またユーザーが好むサインアップ方法を確認しましょう

**トリガー**

ユーザーがサインアップ手順を完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_登録方法 | サインアップ方法の種類 | メール、メタ広告 |

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

ユーザーが探しているものを知り、どの検索結果が最も関連性が高く購入に繋がったか

**トリガー**

次のいずれかの場合：

* ユーザーが検索ボタンをクリックしたとき
* ユーザーが検索結果ページを開いたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_検索文字列 | 検索規定 | 赤い服、ランニングシューズ |
| af\_content\_list | コンテンツIDのリスト | 2024-02-26 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="コンテンツビュー (af_content_view)">

**目的**

特定商品の表示率を確認できます。このイベントを計測すると、次のことに役立ちます。

* 商品の閲覧と販売を関連付けます
* 商品の閲覧に基づいて、どのカテゴリが最も人気があるかを理解できます
* 購入者の通貨と閲覧した商品の相関性を確認できます

**トリガー**

ユーザーが特定の製品詳細ページを閲覧したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 製品/プロダクト価格 | 2000 |
| af\_content | 国際商品番号 (EAN) (該当する場合)、またはその他の製品またはコンテンツの識別子<br /><br />**Meta ads dynamic ads の必須パラメータ** | ABC123 |
| af\_content\_id | 製品ID<br /><br />**Meta ads dynamic ads の必須パラメータ** | 102 |
| af\_content\_type | 商品カテゴリ<br /><br />**Meta ads dynamic ads の必須パラメータ**  <br />  <br />**注：`af_content_type`をMetaの`fb_content_type`にマッピング**する場合、サポートされている値は`product`または`product_group`のみです。 | 靴 |
| af\_currency | 製品詳細ページの通貨 | THB、USD |

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="リストビュー (af_list_view)">

**目的**

どのリスト（例えば、最新商品、関連商品、おすすめ商品など）が一番閲覧されているかを記録しましょう。

**トリガー**

ユーザーが特定のリストを閲覧したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_content\_type | 商品カテゴリ<br /><br />**Meta ads dynamic ads の必須パラメータ**  <br />  <br />**注：`af_content_type`をMetaの`fb_content_type`にマッピング**する場合、サポートされている値は`product`または`product_group`のみです。 | 関連商品、おすすめ商品、新商品 |
| af\_content\_list | カテゴリのコンテンツIDのリスト | 2024-02-26 |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="ウィッシュリストに追加 (af_add_to_wishlist)">

**目的**

購入者がどの製品やカテゴリーをウィッシュリストに追加したかを記録しましょう。ウィッシュリストに頻繁に追加される商品がわかっている場合は、これらの商品をセールまたは割引価格で購入者に提示して、購入を促すことができます。また、ユーザーがウィッシュリストに追加した商品に応じて、これらのユーザーをリターゲティングすることもできます。

**トリガー**

ユーザーがアイテムをウィッシュリストに追加したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 製品の価格 | 600 |
| af\_content\_id | 製品ID | 300 |
| af\_content\_type | 商品カテゴリ<br /><br />**Meta ads dynamic ads の必須パラメータ**  <br />  <br />**注：`af_content_type`をMetaの`fb_content_type`にマッピング**する場合、サポートされている値は`product`または`product_group`のみです。 | 靴、エレクトロニクス |
| af\_currency | 製品詳細ページに表示された通貨 | 英ポンド |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="カートに追加 (af_add_to_cart)">

**目的**

ユーザーがカートに商品を追加したときに計測します。このイベントは、次のような判断に役立ちます。

* 1回の購入で、ユーザーがカートに追加する商品の平均数
* 2つの違う商品をカートに追加する間に、どれくらいの時間が経過しているか
* 何人の購入者がカートを放棄したか

**トリガー**

ユーザーがカートに商品を追加した日時

**イベントパラメーター**

| フィールド名 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 製品/プロダクト価格 | 2024-02-26 |
| af\_content | 国際商品番号 (EAN) (該当する場合)、またはその他の製品またはコンテンツの識別子<br /><br />**Meta ads dynamic ads の必須パラメータ** | ABC123 |
| af\_content\_id | 製品ID<br /><br />**Meta ads dynamic ads の必須パラメータ** | 2024-02-26 |
| af\_content\_type | 商品カテゴリ<br /><br />**Meta ads dynamic ads の必須パラメータ**  <br />  <br />**注：`af_content_type`をMetaの`fb_content_type`にマッピング**する場合、サポートされている値は`product`または`product_group`のみです。 | シャツ、靴 |
| af\_currency | 商品の通貨 | THB、USD |
| af\_数量 | カートに追加された同じ商品の数 | 2024-02-26 |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="チェックアウト開始 (af_initiated_checkout)">

**目的**

購入者がチェックアウトを開始する際の行動を理解しましょう。このイベントは、次のような判断に役立ちます。

* 購入者がチェックアウトしたときの平均価格と購入イベントの平均価格
* チェックアウトへ進んだ後にユーザーが商品を追加または削除するかどうか

**トリガー**

ユーザーがチェックアウトを開始したが、まだチェックアウトを完了していないとき

**イベントパラメーター**

| フィールド名 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | カート内の合計金額 | 4000 |
| af\_content\_id | カート内の商品ID | 2024-02-26 |
| af\_content\_type | 商品カテゴリ<br /><br />**Meta ads dynamic ads の必須パラメータ**  <br />  <br />**注：`af_content_type`をMetaの`fb_content_type`にマッピング**する場合、サポートされている値は`product`または`product_group`のみです。 | シャツ、パンツ |
| af\_currency | チェックアウト時の通貨 | THB |
| af\_数量 | カート内のアイテム総数 | 2024-02-26 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="購入 (af_purchase)">

**目的**

アプリ内の購入に関する傾向を理解しましょう。このイベントを計測すると、次のことに役立ちます。

* アドネットワークと広告代理店間のユーザーのLTV（顧客生涯価値）とキャンペーンのROIを判断します。
* どのようなオファーがユーザーに最も人気があるのかを特定します
* キャンペーンのターゲティングを最適化するために、購入されたアイテムとキャンペーンを相互参照します。

**トリガー**

購入が正常に完了しユーザーに「ありがとうございました」が表示されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 購入による収益の予測 | 1205.99 |
| af\_price | 全体の購入金額の合計 | 4000 |
| af\_content | 国際商品番号 (EAN) (該当する場合)、またはその他の製品またはコンテンツの識別子<br /><br />**Meta ads** **dynamic ads の必須パラメータ** | ABC123 |
| af\_content\_id | 商品ID<br /><br />**Meta ads dynamic ads の必須パラメータ** | 2024-02-26 |
| af\_content\_type | 商品カテゴリ<br /><br />**Meta ads dynamic ads の必須パラメータ**  <br />  <br />**注：`af_content_type`をMetaの`fb_content_type`にマッピング**する場合、サポートされている値は`product`または`product_group`のみです。 | 靴、パンツ |
| af\_currency | Currency code | AUD |
| af\_数量 | カート内の商品の数 | 2024-02-26 |
| 注文ID | 購入後に生成されるオーダーID | X123ABC |
| af\_領収書ID | 注文ID<br /><br />**購入検証のための CRITEO および Google 広告ワードの必須パラメータ** | X123ABC |

</Accordion>

## カスタムイベントで推奨される構造

次のセクションでは、カスタムビエント名と推奨されるイベントパラメーターのイベント構造リストを示しています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="first-purchase-first_purchase" />

<Accordion title="初回購入 (first_purchase)">

**目的**

[購入](/docs/recommended-ecommerce-app-events#purchase-af_purchase)イベントと同じです。さらに、このイベントは次のことを判断するのに役立ちます。

* 新規購入者が購入するまでにどれくらいの時間がかかるのか
* どの商品が初回購入時に購入されやすいか
* 初回購入の平均的な価格と収益

**トリガー**

ユーザーが最初の購入を完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 購入からの収益 | 1205.99 |
| af\_price | 全体の購入金額の合計 | 4000 |
| af\_content | 国際商品番号 (EAN) (該当する場合)、またはその他の製品またはコンテンツの識別子<br /><br />**Meta ads dynamic ads の必須パラメータ** | ABC123 |
| af\_content\_id | 商品ID<br /><br />**Meta ads dynamic ads の必須パラメータ** | 2024-02-26 |
| af\_content\_type | 商品カテゴリ<br /><br />**Meta ads dynamic ads の必須パラメータ**  <br />  <br />**注：`af_content_type`をMetaの`fb_content_type`にマッピング**する場合、サポートされている値は`product`または`product_group`のみです。 | 靴、パンツ |
| af\_currency | 通貨設定 | AUD |
| af\_数量 | カート内の商品の数 | 2024-02-26 |
| 注文ID | 購入後に生成されるオーダーID | X123ABC |
| af\_領収書ID | 注文ID<br /><br />**CRITEOとGoogle AdWords広告のリターゲティング連携に必要なパラメータ** | X123ABC |

</Accordion>

<div id="remove-from-cart-remove_from_cart" />

<Accordion title="カートから削除 (remove_from_cart)">

**目的**

このイベントを計測することで、次のことが可能になります。

* 購入者がどの商品をカートから削除したかを決定します
* 購入者がカートから削除した商品のカテゴリを確認できます
* [カートに追加](/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart)イベントのデータと比較して、チェックアウトされない商品に関するインサイトを得ることができます

**トリガー**

ユーザーがカートから商品を削除したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_content\_id | 商品またはアイテムのID | 521 |
| af\_content\_type | 商品カテゴリ<br /><br />**Meta ads dynamic ads の必須パラメータ**  <br />  <br />**注：`af_content_type`をMetaの`fb_content_type`にマッピング**する場合、サポートされている値は`product`または`product_group`のみです。 | 靴 |

</Accordion>

<div data-zendesk-anchors="ecommerce=-ecommerce h_01HGTAWG2166CZYKJE9166G12J=-ecommerce h_01HGTAWG21Z0C9SR2G54W68G8Q=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAWG2115VB3A8J2WG3DJKK=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAWG21EQ0FE40WGFJRDJY5=complete-registration-af_complete_registration h_01HGTAWG22HFZ24V2BDCH3RFN8=login-af_login h_01HGTAWG22B5Z9AXENDATKR67T=search-af_search h_01HGTAWG22PSKS80ZQNAC0K24M=content-view-af_content_view h_01HGTAWG2219SVQ86PT1K3TVV9=list-view-af_list_view h_01HGTAWG22EQMVWXJCXC2KQDX8=add-to-wishlist-af_add_to_wishlist h_01HGTAWG23T81SPFJEA6BY5F2W=add-to-cart-af_add_to_cart h_01HGTAWG23FPKQ6RHJ9VYET63Y=initiated-checkout-af_initiated_checkout h_01HGTAWG2385E9Q0FXZXEW38YK=purchase-af_purchase recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAWG235EXE17EJ5DWQYERM=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAWG23NTG0Q70B9A3685AD=first-purchase-first_purchase h_01HGTAWG239TQ51Z7FQW4FC1TZ=remove-from-cart-remove_from_cart" />
