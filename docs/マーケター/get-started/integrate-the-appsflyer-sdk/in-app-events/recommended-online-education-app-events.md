---
title: おすすめのオンライン教育アプリイベント
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
  created_at: '2021-04-28T12:35:57Z'
  edited_at: '2026-10-14T09:25:19Z'
  id: 360019794378
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/360019794378
---
> **概要：** 概要：オンライン教育アプリで推奨されるアプリ内イベントを記録して、ユーザージャーニー全体のユーザーの質を測定しましょう。


<span id="-online-education"></span><span id="online-education"></span>オンライン教育アプリはユーザーのリモート学習を可能にします。記録を推奨する典型的なイベントには、登録、チュートリアルとコースの完了、受け取った終了証明書などがあります。

これらのイベントを計測することで、次のような判断に役立ちます。

* ユーザーが最も希望するコースはどれかを知り、ターゲティングのヒントを得ることができます
* ユーザーをリターゲティングして、コースを修了するための追加のチュートリアルがあることを思い出させることができます
* 最も需要が高いコースと証明書はどれか

<div id="important" />

> 🚧 **重要！**
>
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * 実装プロセスを合理化するには、<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=online_education">アプリ内イベントジェネレーター</Anchor>を使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、および Unity 開発者向けの <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=online_education&view=code">コードサンプル</Anchor> があります。
> * 開発担当者向けの詳細な手順は、**<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyerディベロッパーハブ</Anchor>** を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

<Image align="center" alt="Flowchart_for_recommended_events_online_education_app_user_journey" src="https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png" />

<div id="recommended-structures-for-predefined-events" />

## 規定イベントで推奨される構造

次のセクションでは、オンライン教育アプリで一般的なイベント構造のリストを示しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

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
| af\_登録方法 | サインアップ方法の種類 | メール、facebook |

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="チュートリアル完了 (af_tutorial_completion)">

**目的**

このイベントを記録すると、次のことを判断できます。

* ユーザーがつまずく可能性のあるトピックは何か
* どのチュートリアルがうまくいかないかを知り、それらを改善できます
* 収益などのディメンション（分析軸）と全体のユーザーアクティビティを関連付けます

**トリガー**

* ユーザーがチュートリアルを完了したとき
* ユーザーがチュートリアルを開始したが、完了せずに中止した場合

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_成功 | ユーザーがチュートリアルを完了したかどうか | yes |
| af\_チュートリアル\_識別子 | チュートリアルID | 3 |
| af\_content | チュートリアル名 | algebra |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="購入 (af_purchase)">

**目的**

ユーザーが実施したアプリ内購入を計測することで次のことに役立ちます。

* アドネットワークと広告代理店間のユーザーのLTV（顧客生涯価値）とキャンペーンのROIを判断します。
* どのようなオファーがユーザーに最も人気があるのかを特定します。
* キャンペーンのターゲティングを最適化するために、購入されたアイテムとキャンペーンを相互参照します。

**トリガー**

購入が正常に完了しユーザーに「ありがとうございました」が表示されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | 購入による収益の予測 | 250.99 |
| af\_currency | Currency code | USD |
| af\_content\_id | アイテムのID | 2024-02-26 |
| order\_id | 注文ID | 9277 |
| af\_領収書ID | レシートID | 9277 |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## カスタムイベントで推奨される構造

次のセクションでは、カスタムビエント名と推奨されるイベントパラメーターのイベント構造リストを示しています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="complete-exercise-complete_excercise" />

<Accordion title="演習の完了 (complete_excercise)">

**目的**

このイベントを記録し、他のデータと比較することでユーザーについて詳しく理解しましょう。例えば、演習を開始したが完了しなかったユーザー数を知ることができます。

**トリガー**

ユーザーが演習を完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| course\_name | コース名 | algebra |
| exercise\_name | 演習名 | 2 |

</Accordion>

<div id="course-completed-course_completed" />

<Accordion title="コースの完了 (course_completed)">

**目的**

このイベントを記録し、他のデータと比較することでユーザーについて詳しく理解しましょう。例えば、コースを開始したが完了しなかったユーザー数を知ることができます。

**トリガー**

ユーザーがコースを完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| course\_name | コース名 | algebra |
| course\_completed | コースが完了したかどうか | yes |

</Accordion>

<div id="certificate-issued-certificate_issued" />

<Accordion title="修了証明書の発行 (certificate_issued)">

**目的**

このイベントを記録し、他のデータと比較することでユーザーについて詳しく理解しましょう。例えば、コースを修了したユーザー数を知り、その後次のコースについてリターゲティングすることができます。

**トリガー**

ユーザーに修了証明書が発行されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| course\_name | コース名 | algebra |
| certificate\_received | 証明書が発行されたかどうか | yes |

</Accordion>

<div data-zendesk-anchors="h_01HGTAYQ9V4Z5YEWTNCZPVMVMF=online-education h_01HGTAYQ9VJ6GS1XVQPG198C8Z=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAYQ9VS0DYFSFNEPDCDVTG=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAYQ9VX44FA5HHBT6DGA2R=login-af_login h_01HGTAYQ9VR78MHTJZFVFCKCV4=complete-registration-af_complete_registration h_01HGTAYQ9VE8ZBF1DJ2AAA1HFF=tutorial-completion-af_tutorial_completion h_01HGTAYQ9VSXMR0J1T0KN6WK2G=purchase-af_purchase recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAYQ9V93HET4AZ7XGE0E3V=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAYQ9VBZZJ5TC1W2S0MK3P=complete-exercise-complete_excercise h_01HGTAYQ9WQJBBEYKDJ8DP9E31=course-completed-course_completed h_01HGTAYQ9WVXX20FNDZWHGDNZ2=certificate-issued-certificate_issued" />
