---
title: おすすめのゲームアプリイベント
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2021-04-06T14:46:54Z'
  edited_at: '2026-10-14T09:27:19Z'
  id: 360018941117
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/360018941117
---
> **概要：** 概要：ゲームアプリで推奨されるアプリ内イベントを記録して、ユーザージャーニー全体を通したユーザーの質を計測しましょう。

## <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="100px" /> Gaming

ゲームアプリには、アーケード、ストラテジー、教育、さらにギャンブルなど色々なゲームジャンルがあります。ゲームアプリで計測を推奨する一般的なイベントには、アプリ内課金、ソーシャルメディアでのシェア、友達の招待などがあります。加えて、ゲームのレベル達成、ゲーム内チュートリアルの完了なども計測できます。

これらのイベントを計測することで、次のような判断に役立ちます。

* ユーザーが最も購入するオファーは何か
* ユーザーはどれだけエンゲージしているか
* ソーシャルメディアにシェアを投稿するユーザー数
* 友達を招待してアプリをインストールを促すユーザー数

また、これらのイベントは、次のプラットフォームのゲームアプリにも関連しています。

* Android Smart TV
* Apple TV (tvOS)
* Amazon Fire TV
* Xbox
* Windowsモバイルデバイス

> 🚧 **重要！**
>
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * 実装プロセスを合理化するには、<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming">アプリ内イベントジェネレーター</Anchor>を使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、および Unity 開発者向けの <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming&view=code">コードサンプル</Anchor> があります。
> * 開発担当者向けの詳細な手順は、**<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyerディベロッパーハブ</Anchor>** を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

[![Flowchart_for_recommended_events gaming_app_user_journey](https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png)](https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png)

## 規定イベントで推奨される構造

次のセクションでは、ゲームアプリの一般的なイベント構造の一覧を示しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

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

<div id="purchase-af_purchase" />

<Accordion title="購入 (af_purchase)">

**目的**

多くのゲームアプリでは、ユーザーがコイン、宝石、武器などのアイテムを購入することができます。これらの購入を記録すると、次のことに役に立ちます。

* アドネットワークと広告代理店間のユーザーのLTV（顧客生涯価値）とキャンペーンのROIを判断します。
* どのようなオファーがユーザーに最も人気があるのかを特定します。
* キャンペーンのターゲティングを最適化するために、購入されたアイテムとキャンペーンを相互参照します。

**トリガー**

購入が正常に完了しユーザーに「ありがとうございました」が表示されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | 購入による収益の予測 | 199.99 |
| af\_currency | Currency code |  |
| af\_数量 | 購入されたアイテムの数 | 2 |
| af\_content\_id | 商品ID | 2024-02-26 |
| 注文ID | 注文ID | 9277 |
| af\_領収書ID | レシートID | 9277 |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="達成したレベル (af_level_achieved)">

**目的**

ゲームでレベルアップすることは、ユーザーの大きな目標の1つです。ゲームでレベルアップすると、新しい機能やステージが解除される場合が多いため、ユーザーはますますプレイを続けたくなります。レベル達成を記録することで、次のことが可能になります。

* どのキャンペーンが最もアクティブなユーザーを生み出すかを特定できます
* 最もアクティブで関心の高いユーザーのタイプを割り出します
* 収益などのディメンション（分析軸）と全体のユーザーアクティビティを関連付けます

**トリガー**

ユーザーがレベル達成ページに到達したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_レベル | ユーザーが達成したレベル | 3 |
| af\_スコア | ユーザーが達成レベルに関するスコア | 500 |

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="チュートリアル完了 (af_tutorial_completion)">

**目的**

チュートリアルでは、アプリの使用方法に関するガイダンスをユーザーに提供します。このイベントを記録すると、次のことを判断できます。

* ユーザーがつまずく可能性のあるトピックは何か
* うまく機能していないチュートリアルはどれか

**トリガー**

* ユーザーがチュートリアルを完了したとき
* ユーザーがチュートリアルを開始したが、完了せずに中止した場合

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_成功 | ユーザーがチュートリアルを完了したかどうか | true |
| af\_チュートリアル\_識別子 | チュートリアルID | 3 |
| af\_content | チュートリアル名 | はじめよう |

</Accordion>

<div id="share-af_share" />

<Accordion title="シェア (af_share)">

**目的**

ユーザーはソーシャルメディアサイトでゲームの成果をシェアすることを好みます。シェアはブランド認知を生み出し、さらに多くのユーザーがアプリをダウンロードしてインストールするよう促進することができます。<Anchor target="_blank" href="/marketers/ja/docs/user-invite-attribution">シェアと招待の計測</Anchor>について詳細を参照してください。

**トリガー**

ユーザーが投稿をソーシャルメディアで共有したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_description | ソーシャルメディアでシェアする理由。例えば、高スコアやレベルアップなど。 | 新記録、レベルアップ、ゲーム勝利 |
| platform | シェアを投稿するのに使用したプラットフォーム | Facebook、Whatsapp、メール |

</Accordion>

<div id="invite-af_invite" />

<Accordion title="招待 (af_invite)">

**目的**

ユーザーが招待を送信するソーシャルメディアサイトと、アプリのダウンロードとインストールを友人に促すために友人を招待したユーザーの数について理解しましょう。

**トリガー**

ユーザーがアプリのダウンロードとインストールをすすめるために正常に友人を招待したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_description | 招待の背景 | このアプリを使ってみてください。 |

</Accordion>

## カスタムイベントで推奨される構造

次のセクションでは、カスタムイべント名と推奨されるイベントパラメーターのイベント構造リストを示しています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="bonus-claimed-bonus_claimed" />

<Accordion title="ボーナス取得 (bonus_claimed)">

**目的**

オファーされたボーナスを取得したユーザー数を把握し、取得されたボーナスをユーザーアクティビティとエンゲージメントに関連付けましょう。

**トリガー**

ユーザーがボーナスを取得し、彼らのアカウントに反映されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| bonus\_type | ユーザーが取得したボーナスの種類 | コイン |

</Accordion>

<div data-zendesk-anchors="gaming=-gaming h_01HGTAVT1XSEY0TS9T2R1H1KXV=-gaming h_01HGTAVT1XTXYHV1MTFR20BR6J=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAVT1X4QQS6GREKC0N0VK6=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAVT1XAAPGHBTXE6DT9927=login-af_login h_01HGTAVT1X4V41YCXBEXTV0KFR=complete-registration-af_complete_registration h_01HGTAVT1X64710WYNZHTHD7R5=purchase-af_purchase h_01HGTAVT1X24N9J3BMDHV3S54M=level-achieved-af_level_achieved h_01HGTAVT1X5RN4A1MAE0BFB3B4=tutorial-completion-af_tutorial_completion h_01HGTAVT1X952BV07KGZHK68P6=share-af_share h_01HGTAVT1X7KSTYXZGAKEPCXZM=invite-af_invite recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAVT1YXGTF0E5YQX1C3CJN=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAVT1YNH0YAFYX4PR7D6DH=bonus-claimed-bonus_claimed" />
