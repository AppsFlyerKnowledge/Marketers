---
title: おすすめのP2Pレンディングアプリイベント
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
  created_at: '2021-04-28T09:01:59Z'
  edited_at: '2026-10-14T09:37:19Z'
  id: 360019614017
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/360019614017
---
> **概要：** 概要：ソーシャル（P2P）レンディングアプリで推奨されるアプリ内イベントを記録して、ユーザージャーニー全体のユーザーの質を測定しましょう。

## <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="100px" /> P2P lending

P2Pレンディングは、個人や企業が互いにお金を貸し借りする方法です。計測を推奨する一般的なイベントには、個々の貸し手と借り手のアクティビティ、貸し手が提供するローンの種類、ローンの受理率と拒否率です。

イベントの計測から収集するデータにより、信頼できる借り手を明確化し、有利な金利を提供することができます。同様に、最も活発な貸し手は誰なのかを確認して、手数料を安く提供することができます。さらに、ユーザーに最も人気のある融資の種類がわかれば、これらユーザーを対象にマーケティングキャンペーンを開始することもできます。

<div id="important" />

> 🚧 **重要！**
>
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * 実装プロセスを合理化するには、<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=p2p_lending">アプリ内イベントジェネレーター</Anchor>を使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、および Unity 開発者向けの <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=p2p_lending&view=code">コードサンプル</Anchor> があります。
> * 開発担当者向けの詳細な手順は、**<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyerディベロッパーハブ</Anchor>** を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

<Image align="center" alt="Flowchart_for_recommended_events P2P_lending_app_user_journey" src="https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png" />

<div id="recommended-structures-for-predefined-events" />

## 規定イベントで推奨される構造

次のセクションでは、P2Pレンディングアプリの一般的なイベント構造の一覧を示しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="complete-registration-af_complete_registration" />

<Accordion title="登録を完了する (af_complete_registration)">

**目的**

登録後、実際に自分の身元を確認するユーザー数を決定します。これらのユーザーをキャンペーンと関連付けし、どのようなキャンペーンがアクティブなユーザーを生み出すかを知ることができます。

**トリガー**

ユーザーの登録が承認されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
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

<div id="recommended-structures-for-custom-events" />

## カスタムイベントで推奨される構造

次のセクションでは、カスタムビエント名と推奨されるイベントパラメーターのイベント構造リストを示しています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="registration-submitted-registration_submitted" />

<Accordion title="登録の提出 (registration_submitted)">

**目的**

P2Pレンディングは悪用されやすいため、ユーザーは最初に本人確認を行う必要があります。この手続きは、登録リクエストの送信によって行います。このイベントを計測すると、次のことに役立ちます。

* ユーザー登録をしたがアカウントを承認しなかったユーザー数を計測できます。
* 登録方法（メール、Facebook、Google）と本人確認の割合の相関性を把握できます。

**トリガー**

ユーザーが登録要求を送信したあと

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_登録方法 | サインアップ方法の種類 | Email、Facebook |

</Accordion>

<div id="fill-loan-form-fill_loan_form_form_name" />

<Accordion title="ローンフォームの入力 (fill_loan_form_&lt;FORM_NAME>)">

**目的**

ドロップ率を決定し、ローン申請を完了していない借り手をリターゲティングします。

このイベントを送信する時は、イベント名にフォーム名を追加してください。

**トリガー**

借り手がフォームを送信したとき

**イベントパラメーター**

パラメーターなしで送信できます

<div id="note" />

> 📘 **注意**
>
> ローンを貸し手と関連付けることをおすすめします。そのためには、カスタマーユーザーIDが設定されていることを確認してください。<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">カスタマーユーザーIDを設定する</Anchor>ことで、貸し手とAppsFlyerに表示されているアプリのユーザーとを照合することができます。カスタマーユーザーIDを設定することで、全てのイベントがカスタマーユーザーID と一緒に送信されることを確認します。

<div id="submit-loan-application-submit_loan_application" />

<Accordion title="ローン申請を送信 (submit_loan_application)">

**目的**

このイベントを計測すると、次のことに役立つでしょう。

* アプリ内で発生したローン申請の総数を決定します。
* ローン申請の最大金額、最小金額、平均金額について把握できます。
* ユーザーが申請するローンの種類を確認できます。

**トリガー**

ユーザーがローン申請を正常に送信したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| loan\_id | ローンのID | 1735102 |
| loan\_amount | ローン申込金額 | 1000 |
| loan\_type | ローン期間 | 3か月 |

</Accordion>

<div id="loan-form-loan_form" />

<Accordion title="ローン申込書 (loan_form)">

**目的**

借り手が提出したローン申請書を確認しましょう。

**トリガー**

借り手がローン申請書を正常に提出したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| loan\_id | ローンのID | 1735102 |
| loan\_amount | ローン申込金額 | 1000 |
| loan\_type | ローン期間 | 3か月 |

</Accordion>

<div id="submit-credit-check-submit_credit_check" />

<Accordion title="クレジットチェックの提出 (submit_credit_check)">

**目的**

借り手の財務履歴（過去のクレジット、支払習慣、ローンの種類など）を確認し、リスクレベルを評価します。

**トリガー**

貸し手がローンの申請を受け取ったあと

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| loan\_id | ローンのID | 1735102 |
| loan\_amount | ローン申込金額 | 1000 |
| loan\_type | ローン期間 | 3か月 |

</Accordion>

<div id="loan-accepted-loan_accepted" />

<Accordion title="ローンの許可 (loan_accepted)">

**目的**

ローンの傾向やその他の指標について確認しましょう。このイベントは、次のような判断に役立ちます。

* どのような種類のローンが許可されているか
* 承認されたローンで申請された金額

**トリガー**

ローンが承認されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| loan\_id | ローンのID | 1735102 |
| loan\_amount | ローン申込金額 | 1000 |
| loan\_type | ローン期間 | 3か月 |

</Accordion>

<div id="loan-rejected-loan_rejected" />

<Accordion title="ローンの却下 (loan_rejected)">

**目的**

ローンが却下される理由を理解しましょう。ローン金額、ローン期間、および拒否率の相関を確認できます。ローンを拒否されたユーザーをリターゲティングして、小額のローンを選ぶよう提案することもできます。

**トリガー**

貸し手がローンを却下したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| loan\_id | ローンのID | 1735102 |

</Accordion>

<div id="payment-payment" />

<Accordion title="支払い (payment)">

**目的**

信頼できる借り手をマークするのに役立ちます。信頼できる借り手とは、ローンの返済を怠らないように努力する借り手を指します。信頼できる借り手がどのキャンペーンから生み出されているかを知ることができます。加えて、このイベントの計測は、支払いの最小額、最大額、平均額に関するデータを収集するためにも役立つでしょう。

**トリガー**

借り手がローンの支払いを行うとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| loan\_id | ローンのID | 1735102 |
| payment\_amount | 支払額 | 100 |
| payment\_id | 支払いID | AE12SF |

</Accordion>

<div id="payment-completed-payment_completed" />

<Accordion title="支払い完了 (payment_completed)">

**目的**

ローンの返済義務に従う借り手をハイライトします。また、このような借り手をリターゲティングし、利子の削減や他のプロモーションを提供することもできます。

**トリガー**

ローンが全額返済されたとき

**イベントパラメーター**

| フィールド名 | 説明 | 値の例 |
| --- | --- | --- |
| loan\_id | ローンのID | 1735102 |

</Accordion>

<div id="payment-received-payment_received" />

<Accordion title="支払いの受取り (payment_received)">

**目的**

借り手がローン契約の条件に従ってローン支払いを完了することを確認します。

**トリガー**

借り手がローンの支払いを行うとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| loan\_id | ローンのID | 1735102 |
| payment\_amount | 支払額 | 100 |
| payment\_id | 支払いID | AE12SF |

</Accordion>

</Accordion>

<div data-zendesk-anchors="p2p-lending=-p2p-lending h_01HGTAY6DHKXCTP52P2EPHXN5H=-p2p-lending h_01HGTAY6DHDDG3MVCXEM705MTK=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAY6DH1V6S5NKJEFCVW1PF=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAY6DHHGW3M6NQ0K3J6HTC=complete-registration-af_complete_registration h_01HGTAY6DHZTKJR94T8B6WEYZ6=login-af_login recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAY6DH00660DSP5RX3PA9C=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAY6DHETK285KPGW54YV5Z=registration-submitted-registration_submitted h_01HGTAY6DHCQKWMG4YRZDHBMZT=fill-loan-form-fill_loan_form_form_name h_01HGTAY6DHHNJ9EKV3FQ6BKKBF=%E6%B3%A8%E6%84%8F h_01HGTAY6DH4D6NV1NHV5717CDH=submit-loan-application-submit_loan_application h_01HGTAY6DHVWFEFJYB4TGK1B9W=loan-form-loan_form h_01HGTAY6DH7V1JSPCDHDTFR4YA=submit-credit-check-submit_credit_check h_01HGTAY6DH22HRQQJ5NQ2T71QM=loan-accepted-loan_accepted h_01HGTAY6DHTMJ22KQSXHNBJ8B3=loan-rejected-loan_rejected h_01HGTAY6DHD8A2H61XKFPXW589=payment-payment h_01HGTAY6DJWJDQBW52RPG7W7P4=payment-completed-payment_completed h_01HGTAY6DJE0K3VC0YNVWAXT29=payment-received-payment_received" />
