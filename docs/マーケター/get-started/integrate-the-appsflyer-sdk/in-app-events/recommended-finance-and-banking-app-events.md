---
title: おすすめの金融・銀行アプリイベント
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
  created_at: '2021-04-27T12:58:44Z'
  edited_at: '2026-10-14T09:34:23Z'
  id: 360019598337
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/360019598337
---
> **概要：** 概要：この記事で提案されている金融アプリや銀行アプリ向けのイベントを記録して、ユーザージャーニー全体を通してユーザーの質を計測しましょう。


<span id="-finance-and-banking"></span><span id="finance-and-banking"></span>金融アプリと銀行アプリは、新しいクレジットカードへのサインアップやローンの申請など、財務関連のさまざまな目的を実行することができます。計測をお勧めする一般的なアプリ内イベントには、口座開設、クレジットカード申請、ローン申請などがあります。

このイベントを計測することで、次のことを決定することができます。

* ユーザーが最も希望するアカウントはどれかを知り、リターゲティングのアイディアに活用できます
* クレジットカードでユーザーが求めているメリットは何か
* どのようなユーザーに財政援助が必要か、そして必要な金額はどれくらいか

<div id="important" />

> 🚧 **重要！**
>
> * 当事務所の弁護士からの注意：健康データは「制限付きデータ」とみなされ、多くの管轄区域では特別なカテゴリーのデータと見なされます。そのため、お客様はAppsFlyerにそのようなデータを送信することを禁止されています。
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * 実装プロセスを合理化するには、<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=finance_banking">アプリ内イベントジェネレーター</Anchor>を使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、および Unity 開発者向けの <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=finance_banking&view=code">コードサンプル</Anchor> があります。
> * 開発担当者向けの詳細な手順は、**<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyerディベロッパーハブ</Anchor>** を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

<Image align="center" alt="Flowchart_for_recommended_events finance_banking_app_user_journey" src="https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png" />

<div id="recommended-structures-for-predefined-events" />

## 規定イベントで推奨される構造

次のセクションでは、金融と銀行業界で一般的なイベント構造のリストを示しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="login-af_login" />

<Accordion title="ログイン (af_login)">

**目的**

登録ユーザーのリテンションを理解しましょう

**トリガー**

ユーザーが正常にログインしたとき

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

<div id="recommended-structures-for-custom-events" />

## カスタムイベントで推奨される構造

次のセクションでは、カスタムビエント名と推奨されるイベントパラメーターのイベント構造リストを示しています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="registration-verified-registration_verified" />

<Accordion title="登録承認済み (registration_verified)">

**目的**

このイベントを記録し、他のデータと比較することでユーザーについて詳しく理解しましょう。例えば、サインアップしたが承認されなかったユーザーの数を知ることができます。

**トリガー**

登録が承認されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| submit\_registration | 承認されたサインアップ方法のタイプ。個人を特定できる情報（PII）を入力しないでください。 | Email、Facebook |

</Accordion>

<div id="submit-account-application-submit_account_application" />

<Accordion title="アカウント申請の提出 (submit_account_application)">

**目的**

このイベントを記録し、他のデータと比較することでユーザーについて詳しく理解しましょう。例えば、サインアップしたがアカウントを申請しなかったユーザーの数を知ることができます。

**トリガー**

ユーザーがアカウント申請プロセスを完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| account\_type | 申請したアカウントタイプ | savings |
| application\_method | 申請が行われた場所 | アプリ |
| PII\_type | 申請時に使用されたIDタイプ | passport |

</Accordion>

<div id="open-account-success-open_account_success" />

<Accordion title="アカウント開設の成功 (open_account_success)">

**目的**

このイベントを記録し、他のデータと比較することでユーザーについて詳しく理解しましょう。例えば、アカウントを申請したユーザーのうち何人が許可されたかを知ることができます。ファネルを向上したり、これらのユーザーを後日リターゲティングすることも可能です。

**トリガー**

ユーザーの申請が許可されアカウントが開設したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| account\_type | 開設したアカウントのタイプ | savings |
| application\_method | 申請が行われた場所 | アプリ |
| PII\_type | 申請時に使用されたIDタイプ | identification card |

</Accordion>

<div id="open-account-rejected-open_account_rejected" />

<Accordion title="アカウント開設の拒否 (open_account_rejected)">

**目的**

このイベントを記録し、他のデータと比較することでユーザーについて詳しく理解しましょう。例えば、アカウントを申請したが、許可されなかったユーザー数を知ることができます。ファネルを向上したり、これらのユーザーを後日リターゲティングすることも可能です。

**トリガー**

ユーザーがサインアップ手順を完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| account\_type | 申請したアカウントタイプ | savings |

</Accordion>

<div data-zendesk-anchors="h_01HGTAXN8PV7TPNRBWD593BR4K=finance-and-banking h_01HGTAXN8Q652HG7412X583KWX=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAXN8QWEWD86FMF6GEZNZD=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAXN8Q3K0EFGXZ41XZH438=login-af_login h_01HGTAXN8Q6KFDPB8XSVT3F9E8=complete-registration-af_complete_registration recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAXN8Q47F6CXXBEVCDPSBA=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAXN8QB911JMER3EV7RGTM=registration-verified-registration_verified h_01HGTAXN8QCYR0BQ3Q3VN0EQ9X=submit-account-application-submit_account_application h_01HGTAXN8QJ4DKQS2FY9KY0AX4=open-account-success-open_account_success h_01HGTAXN8QK1P5QYEN5SNBQ5ED=open-account-rejected-open_account_rejected" />
