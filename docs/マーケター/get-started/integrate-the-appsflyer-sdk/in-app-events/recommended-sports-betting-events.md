---
title: おすすめのスポーツベッティングイベント
metadata:
  keywords:
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
  created_at: '2021-11-11T13:24:45Z'
  edited_at: '2026-10-14T09:31:39Z'
  id: 4410672219025
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/4410672219025
---
> **概要：** 概要：スポーツベット（賭け事）アプリで推奨されるアプリ内イベントを記録して、ユーザージャーニー全体を通したユーザーの質を計測しましょう。

## <Image alt="soccer_ball.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="71px" /> Sports betting

スポーツベットアプリを使用すると、参加者はさまざまなスポーツ市場に賭けを実行することができます。記録することを推奨している典型的なイベントは、入金、賭け、引き出しなどです。

これらのイベントを計測することで、次のような判断に役立ちます。

* アプリユーザーの質
* ユーザーはどれだけエンゲージしているか
* 賭け事によって生成された収益
* どのタイプの賭けが最低または最高の収益を生み出しているか

> 🚧 **重要！**
>
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * （近日公開）実装プロセスを合理化するには、<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming">アプリ内イベントジェネレーター</Anchor>を使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、および Unity 開発者向けの <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming&view=code">コードサンプル</Anchor> があります。
> * 開発担当者向けの詳細な手順は、**<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyerディベロッパーハブ</Anchor>** を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

[![In_appEvents_UserJourneys_-_Sports_betting__5_.png](https://files.readme.io/7a47ba917ebc5a6e661efb23b078675c16ce43c59c41f9c6fd6fd89d37c242bf-4424606611473.png)](https://files.readme.io/7a47ba917ebc5a6e661efb23b078675c16ce43c59c41f9c6fd6fd89d37c242bf-4424606611473.png)

## 規定イベントで推奨される構造

次のセクションでは、スポーツベットアプリで一般的なイベント構造のリストを示しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

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

ユーザーがサインアッププロセスを完了し、登録がアプリによって (エラーなしで) 確認されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_登録方法 | サインアップ方法の種類 | Email、Facebook |

</Accordion>

## カスタムイベントで推奨される構造

次のセクションでは、カスタムイべント名と推奨されるイベントパラメーターのイベント構造リストを示しています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="first-time-deposit-first_time_deposit" />

<Accordion title="初回デポジット (first_time_deposit)">

**目的**

このイベントを記録すると、次のことを判断できます。

* ユーザーが初回入金を行うタイミング
* 初回入金によって生成された収益

さらに、アドネットワークパートナーは、初回入金を行ったユーザーをターゲットにすることで、広告キャンペーンを最適化することができます。

**トリガー**

ユーザーが初めてベッティングアカウントに入金したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | 入金された金額 | 200 |
| af\_currency | 入金された通貨 | AUD |

</Accordion>

<div id="deposit-deposit" />

<Accordion title="デポジット (deposit)">

**目的**

ユーザーが行う入金額を判断できます

**トリガー**

最初のデポジット後にユーザーが後続的な入金を行ったとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | 入金された金額 | 200 |
| af\_currency | 入金された通貨 | AUD |

</Accordion>

<div id="placed-bet-placed_bet" />

<Accordion title="賭けを実行 (placed_bet)">

**目的**

最少または最多の収益をもたらすイベントを把握します

**トリガー**

ユーザーが賭けを実行したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 実行した賭けの金額 | 100 |
| af\_currency | 実行した賭けの通貨 | AUD |
| event\_number | 実行した賭けのイベントに対する一意の識別子 | 123789 |
| event\_date | 賭けのイベントが実行された日付 | 13122021 |
| event\_time | 賭けのイベントが実行された時間 | 17:30 |
| トランザクションID | 実行された賭けのID | 221 |

</Accordion>

<div id="withdrawal-withdrawal" />

<Accordion title="引き出し／出金 (withdrawal)">

**目的**

ユーザーが以前にベッティングアカウントに入金したお金をいつ引き出すかを把握できます

**トリガー**

ユーザーがベッティングアカウントからお金を引き出したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | 出金の金額。マイナスの収益額として記録されます | -100 |
| af\_currency | 引き出された通貨 | AUD |

</Accordion>

<div id="bonus-bet-bonus_bet" />

<Accordion title="ボーナスベット (bonus_bet)">

**目的**

ボーナスベットは、アプリ所有者がサインアップまたはデポジットに対するインセンティブとして、または特定のベットタイプを促すためのプロモーションとしてユーザーに付与するために使用できる任意のイベントです。

このイベントを記録することで、ユーザーに付与されたボーナス額の合計と、ボーナスベットを実行したユーザー数を把握できます。

**トリガー**

ユーザーが賭けを実行したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 実行した賭けの金額 | 100 |
| af\_currency | 実行した賭けの通貨 | AUD |
| event\_number | 実行した賭けのイベントに対する一意の識別子 | 123789 |
| event\_date | 賭けのイベントが実行された日付 | 13122021 |
| event\_time | 賭けのイベントが実行された時間 | 17:30 |
| bonus\_id | ボーナスベットのID | 221 |

</Accordion>

<div id="cancels-bet-canceled_bet" />

<Accordion title="賭けのキャンセル (canceled_bet)">

**目的**

このイベントを計測すると、次のことに役立ちます。

* キャンセルを頻繁に行うユーザーを記録
* キャンセルされた賭けの数を把握
* キャンセルの理由を把握

**トリガー**

ユーザーが賭けをキャンセルしたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 実行した賭けの金額 | 100 |
| af\_currency | 実行した賭けの通貨 | AUD |
| event\_number | 実行した賭けのイベントに対する一意の識別子 | 123789 |
| event\_date | 賭けのイベントが実行された日付 | 13122021 |
| event\_time | 賭けのイベントが実行された時間 | 17:30 |

</Accordion>

<div id="account-deducted-account_deducted" />

<Accordion title="引き落とされたアカウント (account_deducted)">

**目的**

ユーザーアカウントから金額が引き落とされたとき

**トリガー**

賭けに負けたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 実行した賭けの金額 | 100 |
| af\_currency | 実行した賭けの通貨 | AUD |
| account\_number | ユーザーアカウントの一意の識別子 | 15780 |
| event\_number | 実行した賭けのイベントに対する一意の識別子 | 123789 |
| event\_date | 賭けのイベントが実行された日付 | 13122021 |
| event\_time | 賭けのイベントが実行された時間 | 17:30 |

</Accordion>

<div id="account-credited-account_credited" />

<Accordion title="入金されたアカウント (account_credited)">

**目的**

ユーザーアカウントに金額が入金されたことを記録します

**トリガー**

賭けに勝ったとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_price | 実行した賭けの金額 | 100 |
| af\_currency | 実行した賭けの通貨 | AUD |
| account\_number | ユーザーアカウントの一意の識別子 | 15780 |
| event\_number | 実行した賭けのイベントに対する一意の識別子 | 123789 |
| event\_date | 賭けのイベントが実行された日付 | 13122021 |
| event\_time | 賭けのイベントが実行された時間 | 17:30 |

</Accordion>

<div data-zendesk-anchors="sports-betting=-sports-betting h_01HGTAE0AT9KD9RKX7XPR7A4AT=-sports-betting h_01HGTAE0ATTMEART2R1BD1ZDSB=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAE0ATYW0RDDZZD5EAR7BZ=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAE0ATMBJVKS14SGWGK0DG=login-af_login h_01HGTAE0ATHZWSM0R9A6R9BV96=complete-registration-af_complete_registration recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAE0ATJQDWWBB8D836QRJ5=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAE0AT3ZBH5G16QJW4MGQ1=first-time-deposit-first_time_deposit h_01HGTAE0ATTRCNX1Y4AFJ8VGWC=deposit-deposit h_01HGTAE0ATNW97Y8WJWWXTXX7V=placed-bet-placed_bet h_01HGTAE0ATPB6KHMHHBW7T9B0Q=withdrawal-withdrawal h_01HGTAE0ATGS9VS7QY1974XAPY=bonus-bet-bonus_bet h_01HGTAE0AVKKGGJCB9WWXMWT0D=cancels-bet-canceled_bet h_01HGTAE0AVMB59TDT6AM65DE94=account-deducted-account_deducted h_01HGTAE0AVXMY0J983V9NTYQ2J=account-credited-account_credited" />
