---
title: おすすめのヘルスケアアプリイベント
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
  created_at: '2021-05-01T10:41:05Z'
  edited_at: '2026-10-14T09:35:21Z'
  id: 360019888518
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/360019888518
---
> **概要：** 概要：ヘルスケアアプリで推奨されるアプリ内イベントを記録して、ユーザージャーニー全体を通じてユーザーの質を計測しましょう。

## <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="100px" /> Healthcare

ヘルスケアアプリでは、ユーザーが健康保険を購入したり、診察を予約したり、医療的なアドバイスを受けたりすることができます。記録をお勧めする一般的なイベントには、ログイン、登録、および個人情報や健康情報のないその他の一般的なイベントが含まれます。

<div id="important" />

> 🚧 **重要！**
>
> * 当事務所の弁護士からの注意：健康データは「制限付きデータ」とみなされ、多くの管轄区域では特別なカテゴリーのデータと見なされます。そのため、お客様はAppsFlyerにそのようなデータを送信することを禁止されています。
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * 実装プロセスを合理化するには、アプリ内イベントジェネレーターを使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、および Unity 開発者向けの <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=healthcare&view=code">コードサンプル</Anchor> があります。
> * 開発者向けの詳細な手順については、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyer公式デベロッパーハブ</Anchor>を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

![In_appEvents_UserJourneys_-_Copy_of_Healthcare__1_.png](https://files.readme.io/54174e697c8dfe2d0d388c19fdd5fa0fbf9703c0155b9c250b40b5d0bcf19698-8232949117073.png)

<div id="recommended-structures-for-predefined-events" />

## 規定イベントで推奨される構造

次のセクションでは、ヘルスケアアプリで一般的なイベント構造のリストを示しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="login-af_login" />

<Accordion title="ログイン (af_login)">

**目的**

登録ユーザーのリテンションを理解しましょう

**トリガー**

ユーザーが正常にログインするたびに記録

**イベントパラメーター**

パラメーターなしで送信できます

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="登録を完了する (af_complete_registration)">

**目的**

アプリをインストールし、サインアップを完了したユーザーがどれだけいるか、またユーザーが好むサインアップ方法を確認しましょう

**トリガー**

ユーザーがサインアップ手順を完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_登録方法 | サインアップ方法の種類 | Email、Facebook |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="カートに追加 (af_add_to_cart)">

**目的**

このイベントは、次のような判断に役立ちます。

* 1回の購入で、ユーザーがカートに追加する商品の平均数
* 2つの違う商品をカートに追加する間に、どれくらいの時間が経過しているか
* 何人の購入者がカートを放棄したか

**トリガー**

ユーザーがカートに商品を追加した日時

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_数量 | 注文数量 | 1 |
| af\_price | 製品の価格 | 10 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="購入 (af_purchase)">

**目的**

ユーザーが実行したアプリ内購入を記録します。このイベントを計測すると次のことに役立ちます：

* アドネットワークと広告代理店間のユーザーのLTV（顧客生涯価値）とキャンペーンのROIを判断します。
* どのようなオファーがユーザーに最も人気があるのかを特定します。
* キャンペーンのターゲティングを最適化するために、購入されたアイテムとキャンペーンを相互参照します。

**トリガー**

購入が正常に完了しユーザーに「ありがとうございました」が表示されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | 購入による収益 | 50.55 |
| af\_currency | Currency code | USD |
| 注文ID | 注文ID | 9277 |
| payment\_method\_type | 使用された支払い方法 | credit card, local |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## カスタムイベントで推奨される構造

次のセクションでは、カスタムイベント名と、使用する推奨イベントパラメーターを含むイベント構造について説明します。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="topup-success-top_up_success" />

<Accordion title="チャージ／トップアップ成功 (af_top_up_success)">

**目的**

料金チャージは、アプリ内で提供されるパッケージやサービスを購入するために使用することができます。このイベントを記録し、他のデータと比較することでユーザーについてより詳しく理解できます。例えば、ユーザーがアカウントに入金する金額を知り、チャージ金額を把握することで、予算内でカスタマイズされたキャンペーンを使用してユーザーをターゲットにすることができます。

**トリガー**

ユーザーがチャージを完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | チャージ金額 | 2000.55 |
| top\_up\_id | チャージのID | 397 |
| payment\_method\_type | 使用された支払い方法 | credit card, local payment |

</Accordion>

<div data-zendesk-anchors="healthcare=-healthcare h_01HGTAFRKKJ22SHB4JHMTGW2TV=-healthcare h_01HGTAFRKKPWC1PQTKF227WWBD=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAFRKKRB8EY8KJ9NXM4Z2T=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAFRKK35Q5W5ADQC2KYHR9=login-af_login h_01HGTAFRKK8E52FRVWQXP4Y3VV=complete-registration-af_complete_registration h_01HGTAFRKN6NJPDB053YYYH202=add-to-cart-af_add_to_cart h_01HGTAFRKNJVFECSFGSWG8B7GN=purchase-af_purchase recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAFRKN29RJRW2V2WCH2AXT=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAFRKNDWHDDR9KDRKJ4H8E=topup-success-top_up_success" />
