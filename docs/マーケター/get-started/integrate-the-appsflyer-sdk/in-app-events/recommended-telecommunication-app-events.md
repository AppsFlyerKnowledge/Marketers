---
title: おすすめの通信アプリイベント
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
  created_at: '2021-05-02T11:59:16Z'
  edited_at: '2026-10-14T09:11:31Z'
  id: 360019896558
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/360019896558
---
> **概要：概要：** この記事で提案されている通信・テレコミュニケーション向けのイベントを記録して、ユーザージャーニー全体を通してユーザーの質を計測しましょう/strong>。

## <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="100px" /> Telecommunication

通信アプリを使用すると、携帯電話プランやデータプランなどを購入および管理できます。通信アプリで計測が推奨される一般的なアプリ内イベントには、購入、料金チャージ、サブスクリプションなどが含まれます。

このイベントを計測することで、次のことを決定することができます。

* 最も人気のあるゲートウェイプランはどれか
* ユーザーが購入できる手頃な製品やパッケージはどれか
* どのプランが長期契約に最もつながりやすいか

<div id="important" />

> 🚧 **重要！**
>
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * 実装プロセスを合理化するには、<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=telecommunication">アプリ内イベントジェネレーター</Anchor>を使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、および Unity 開発者向けの <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=telecommunication&view=code">コードサンプル</Anchor> があります。
> * 開発担当者向けの詳細な手順は、**<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyerディベロッパーハブ</Anchor>** を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

[![Flowchart_for_recommended_events_telecommunication_app_user_journey](https://files.readme.io/ae4c696208b49aa546ffc0a15f76b148b35af43984a76e699d1df7c54507352c-4404604045457.png)](https://files.readme.io/ae4c696208b49aa546ffc0a15f76b148b35af43984a76e699d1df7c54507352c-4404604045457.png)

<div id="recommended-structures-for-predefined-events" />

## 規定イベントで推奨される構造

次のセクションでは、通信・テレコミュニケーションアプリで一般的なイベント構造のリストを示しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たすどんなイベントパラメーターを含めることができます。

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

<div id="content-view-af_content_view" />

<Accordion title="コンテンツビュー (af_content_view)">

**目的**

特定の製品の表示率を決定し、

* 商品の閲覧と販売を関連付けます
* 商品の閲覧に基づいて、どのカテゴリが最も人気があるかを理解できます
* 購入者の通貨と閲覧している商品との相関性を確認します

**トリガー**

ユーザーが特定の製品詳細ページを閲覧したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 製品/プロダクト価格 | 200 |
| af\_content\_id | 製品ID | 102 |
| af\_content\_type | 製品カテゴリー | インターネットパッケージ |
| af\_currency | 製品詳細ページの通貨 |  |

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
| af\_content\_type | リストのタイプ | 関連商品、おすすめ商品、新商品 |
| af\_content\_list | カテゴリのコンテンツIDのリスト | 2024-02-26 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="購入 (af_purchase)">

**目的**

通信アプリの多くでは、ユーザーが追加データプランなどを購入することができます。このイベントを計測することで、次のことが可能になります。

* アドネットワークと広告代理店間のユーザーのLTV（顧客生涯価値）とキャンペーンのROIを判断します。
* どのようなオファーがユーザーに最も人気があるのかを特定します。
* キャンペーンのターゲティングを最適化するために、購入されたアイテムとキャンペーンを相互参照します。

**トリガー**

購入が正常に完了しユーザーに「ありがとうございました」が表示されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | 購入による収益の予測 | 2024-02-26 |
| af\_currency | Currency code | THB |
| af\_content\_type | 購入されたパッケージ名 | 5G |
| 注文ID | 注文ID | 9277 |
| payment\_method\_type | 決済方法の種類 | credit card, local payment |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## カスタムイベントで推奨される構造

次のセクションでは、カスタムイべント名と推奨されるイベントパラメーターのイベント構造リストを示しています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="select-package-select_package" />

<Accordion title="パッケージの選択 (select_package)">

**目的**

**トリガー**

ユーザーがパッケージを選択したがまだ決済を完了していないとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| 価格 | サブスクリプションの価格 | 50000 |
| af\_content\_type | ユーザーが選択したコンテンツの内容 | Data 5 GB |

</Accordion>

<div id="topup-success-top_up_success" />

<Accordion title="チャージ／トップアップ成功 (af_top_up_success)">

**目的**

料金チャージは、パッケージやアプリ内で提供されているその他のサービスを購入するために使用されます。このイベントを記録し、他のデータと比較することでユーザーについて詳しく理解しましょう。例えば、ユーザーがアカウントに入金する金額を知り、チャージ金額を使用して、予算内でカスタマイズされたキャンペーンをターゲットにすることができます。

**トリガー**

ユーザーがチャージを完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | チャージ金額 | 2024-02-26 |
| top\_up\_id | チャージのID | 397 |
| payment\_method\_type | 決済方法の種類 | credit card, local payment |

</Accordion>

<div id="topup-unsuccessful-top_up_unsuccessful" />

<Accordion title="チャージ／トップアップ失敗 (af_top_up_unsuccessful)">

**目的**

このイベントを記録し、他のデータと比較することでユーザーについて詳しく理解しましょう。例えば、チャージしようとしたが失敗したユーザー数を知ることができます。

**トリガー**

ユーザーがチャージしようとしたが、アクションが失敗したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| error\_reason | チャージ失敗の理由 | exceeded\_daily\_limit |

</Accordion>

<div id="subscription-complete-subscription_complete" />

<Accordion title="サブスクリプション完了 (af_subscription_complete)">

**目的**

このイベントを計測することで、次のことが可能になります。

* どのキャンペーンがユーザーのサブスクリプションに結び付いたかを確認できます。
* サブスクライブしたユーザーの数を、サブスクリプションを停止したユーザー数と比較します。
* サブスクリプションから発生した収益を計測し、キャンペーンやメディアソースに関連付けます。

**トリガー**

* ユーザーが正常にサブスクリプションを完了したとき
* サブスクリプションが更新された日時

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| subscription\_type | サブスクリプションの種類 | Monthly 30 GB |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | サブスクリプションの金額 | 555.50 |

</Accordion>

<div data-zendesk-anchors="telecommunication=-telecommunication h_01HGTAGFNFWKWYHPG6F5EK17YD=-telecommunication h_01HGTAGFNG1Z8NAFJ71DP0YSYD=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAGFNG99PQC03F13WQ4CVK=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAGFNGQ56C8CN7A325SQ7M=login-af_login h_01HGTAGFNG1W5QWGN1D969JHGY=complete-registration-af_complete_registration h_01HGTAGFNGRJHD89332473DZFE=content-view-af_content_view h_01HGTAGFNG10GNZVMDNXRJSYJ9=list-view-af_list_view h_01HGTAGFNGV82NQSZ29B96YJCQ=purchase-af_purchase recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAGFNG3A2A6KCX8GGQAJBX=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAGFNGE3MKZEDKDZ0B9XDD=select-package-select_package h_01HGTAGFNGFSE2DAYRGG039GT9=topup-success-top_up_success h_01HGTAGFNGXBBYWJEMBVMN1YQS=topup-unsuccessful-top_up_unsuccessful h_01HGTAGFNGT3CJFRS2YC7R57KG=subscription-complete-subscription_complete" />
