---
title: おすすめのエンターテイメントアプリイベント
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
  created_at: '2021-04-25T10:44:33Z'
  edited_at: '2026-10-14T09:34:36Z'
  id: 360019699898
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/360019699898
---
> **概要：** 概要：エンターテイメントアプリで推奨されるアプリ内イベントを記録して、ユーザージャーニー全体のユーザーの質を測定しましょう。

## <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="100px" /> Entertainment

オンデマンドコンテンツに対するユーザーの要求が高まるにつれて、エンターテイメントアプリ市場は非常に競争が激しくなっています。記録が推奨される一般的なイベントには、ユーザーサブスクリプション、コンテンツのストリーミング、コンテンツのダウンロードと保存などがあります。

これらのイベントを計測することで、次のような判断に役立ちます。

* どんなコンテンツをユーザーが視聴するか
* ユーザーが好むコンテンツに応じたキャンペーンのパフォーマンス
* ユーザーエンゲージメントと使用状況

これらのイベントは、次のスマートテレビで動作するエンターテイメントアプリにも関係します。

* Android Smart TV
* Apple TV (tvOS)
* Amazon Fire TV

> 🚧 **重要！**
>
> * アプリ内イベントの実装に関するマーケティング担当者向けの <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">手順</Anchor> を必ずお読みください。
> * 実装プロセスを合理化するには、<Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=entertainment">アプリ内イベントジェネレーター</Anchor>を使用してください。このツールには、この記事で説明している典型的なアプリ内イベントが全て含まれており、これらをビジネスニーズに応じて変更することができます。完了後、ファイルを開発担当者と共有してください。
> * この記事に含まれる推奨イベントごとに、iOS、Android、および Unity 開発者向けの <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=entertainment&view=code">コードサンプル</Anchor> があります。
> * 開発担当者向けの詳細な手順は、**<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyerディベロッパーハブ</Anchor>** を参照してください。
>
> アプリ内イベント計測の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>を参照してください。

[![Flowchart_for_recommended_events entertainment_app_user_journey](https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png)](https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png)

## 規定イベントで推奨される構造

次のセクションでは、エンターテイメントアプリの一般的なイベント構造の一覧を示しています。各構造には、既定のイベント名と推奨されるイベントパラメーターが含まれています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="complete-registration-af_complete_registration" />

<Accordion title="登録を完了する (af_complete_registration)">

**目的**

アプリをインストールし、サインアップを完了したユーザーがどれだけいるか、またユーザーが好むサインアップ方法を確認しましょう

**トリガー**

ユーザーがサインアップ手順を完了したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_登録方法 | ユーザーが選択したサインアップ方法 | Facebook、Google、メール |

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

<div id="start-trial-af_start_trial" />

<Accordion title="トライアル開始 (af_start_trial)">

**目的**

多くのストリーミングサービスでは、ユーザーにプレミアム機能を体験するための試用期間を提供します。このイベントを計測すると、次のことに役立ちます。

* 何人のユーザーが試用期間中にオプトインするかを把握できます。
* トライアルがプロモーションやパートナーとのコラボレーションの一部であるか
* どのプロモーションがトライアル開始のきっかけとなったか

**トリガー**

ユーザーがトライアル期間にオプトインしトライアルを開始した時期

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| trial\_method | トライアルを開始する | 新しい携帯電話で無料、通信料と組み合わせて無料、プロモーション、クーポンコード |
| trial\_method\_identifier | トライアル方法のID | キャリア名（例: **Vodafone**）<br /><br />クーポンコード（例: **TRA123**） |

> 📘 **注意**
>
> このイベントをMeta広告のStartTrialイベントにマッピングして、収益を関連付ける場合は、af\_revenueパラメーターの代わりにaf\_priceパラメーターを使用してください。

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="サブスクリプション (af_subscribe)">

**目的**

サブスクリプションはストリーミングサービスの中核です。このイベントを計測すると、次のことに役立ちます。

* どのキャンペーンがユーザーのサブスクリプションに結び付いたかを確認できます。
* トライアル中のユーザー数をサブクスライブ中のユーザー数と比較しましょう
* サブスクリプションから発生する収益額を決定し、それをキャンペーンやメディアソースに関連付けます

**トリガー**

* ユーザーが正常にサブスクリプションを完了したとき
* サブスクリプションが更新された日時

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| new\_subscription | サブスクリプションが新規購入または更新されたとき | true / false |
| af\_クーポンコード | クーポンコード（サブスクリプション中に使用された場合） | 3MonthsSubscription |
| coupon\_code\_value | 初期価格からのクーポン割引率 | 10% |
| <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">af\_収益</Anchor> | サブスクリプションに紐づく収益 | 5.95 |
| af\_currency | サブスクリプションの支払い通貨 | USD |
| subscription\_method | サブスクリプションに使用された支払い方法 | クレジットカード、E-Wallet、PayPal |
| expiration\_date | サブスクリプションの有効期限 | 2024-02-26 |

</Accordion>

## カスタムイベントで推奨される構造

次のセクションでは、カスタムビエント名と推奨されるイベントパラメーターのイベント構造リストを示しています。アプリ内イベントには、ビジネスニーズを満たす任意のイベントパラメーターを含めることができます。

<div id="media-play-media_play" />

<Accordion title="メディア再生 (media_play)">

**目的**

提供するメディアをユーザーが再生するイベントを記録しましょう。メディアには、例えば動画、音楽、テレビ番組、ラジオなどが含まれます。

このイベントを記録すると、次のことを判断できます。

* タイプおよびコンテンツ別のメディア視聴
* 最も人気のあるストリーミングコンテンツの言語
* ストリーミングコンテンツの最小、最大、および平均持続時間

**トリガー**

ストリームコンテンツ再生後に一定時間（2分など）が経過したあと

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_content\_type | ストリーミングされるコンテンツのタイプ | テレビ番組、音楽 |
| af\_content\_id | ストリーミングされるコンテンツのID | 092, E34 |
| af\_content | コンテンツのタイトル、例えば曲名またはテレビ番組のタイトルとエピソードなど | コンテンツのタイトル |
| media\_duration |  | 5 |
| 言語 | コンテンツの言語 |  |

</Accordion>

<div id="media-minutes-media_minutes" />

<Accordion title="メディア再生時間 (media_minutes)">

**目的**

視聴時間は、特定のコンテンツをユーザーがどれくらい視聴したかを表します。これによりユーザーの使用状況を推測することができるため、ストリーミング業界では、収益の指標に次いで最も重要な指標です。また、サービスの全体的な使用率がどの程度か、最も人気のあるコンテンツが何かを理解することもできます。このイベントを計測すると、次のことに役立ちます。

* どのユーザーがサービスを幅広く利用しているのかを確認できます
* 人気のあるメディアの種類とコンテンツタイプは何かを把握できます

**トリガー**

次のいずれかの場合：

* ユーザーがメディアアイテムのストリーミングを終了したとき
* ユーザーがメディアアイテムのストリーミングを中止したとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| minutes\_consumed |  | 3 |
| af\_content\_type | ストリーミングされるコンテンツのタイプ | テレビ番組、音楽 |
| af\_content\_id | ストリーミングされるコンテンツのID | 092, E34 |
| af\_content | コンテンツのタイトル、例えば曲名またはテレビ番組のタイトルとエピソードなど | コンテンツのタイトル |
| media\_duration |  | 5 |
| 言語 | コンテンツの言語 |  |

</Accordion>

<div id="media-downloaded-media_downloaded" />

<Accordion title="メディアのダウンロード (media_downloaded)">

**目的**

メディア再生とメディアのダウンロードを記録し、この2つを比較することでユーザー設定の好みを知ることができます。ストリーミングが好まれるメディアと、ダウンロードが好まれるメディアを知ることができます。

**トリガー**

ユーザーがメディアのダウンロードを開始した時

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_content\_type | コンテンツタイプ | テレビ番組、音楽 |
| af\_content\_id | コンテンツID | 092, E34 |
| af\_content | コンテンツのタイトル、例えば曲名またはテレビ番組のタイトルとエピソードなど | コンテンツのタイトル |
| media\_duration |  | 5 |
| 言語 | コンテンツの言語 |  |

</Accordion>

<div id="media-saved-media_saved" />

<Accordion title="メディアの保存 (media_saved)">

**目的**

ユーザーの好みを知ることができます

**トリガー**

ユーザーのデバイスにメディアが保存されたとき

**イベントパラメーター**

| 名前 | 説明 | 値の例 |
| --- | --- | --- |
| af\_content\_type | コンテンツタイプ | テレビ番組、音楽 |
| af\_content\_id | コンテンツID | 092, E34 |
| af\_content | コンテンツのタイトル、例えば曲名またはテレビ番組のタイトルとエピソードなど | コンテンツのタイトル |
| media\_duration |  | 5 |
| 言語 | コンテンツの言語 |  |

</Accordion>

<div data-zendesk-anchors="entertainment=-entertainment h_01HGTAX1B0KT8Q6PRE41JCPJ60=-entertainment h_01HGTAX1B0K2RKYGPFFARM0E1B=%E9%87%8D%E8%A6%81 recommended-structures-for-predefined-events=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAX1B05C7G67RJPSG3YF66=%E8%A6%8F%E5%AE%9A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAX1B0CN19DY7PAR27YATD=complete-registration-af_complete_registration h_01HGTAX1B0MG1MTD7QXBCK6JHN=login-af_login h_01HGTAX1B0GTJ6ZWRNW5SEJVE9=start-trial-af_start_trial h_01HGTAX1B1XW0RAV8WPP0HF8HD=%E6%B3%A8%E6%84%8F h_01HGTAX1B1AHHGW6SMXST1KXQE=subscription-af_subscribe recommended-structures-for-custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAX1B1ATFH70K2BJZ7XW13=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E6%A7%8B%E9%80%A0 h_01HGTAX1B1WRQ39H27KPRFZH9W=media-play-media_play h_01HGTAX1B15Z24J8JKKAQH2Z2S=media-minutes-media_minutes h_01HGTAX1B1JPY44SYM59K0M9H2=media-downloaded-media_downloaded h_01HGTAX1B1FXF1DRC91VYRCGMP=media-saved-media_saved" />
