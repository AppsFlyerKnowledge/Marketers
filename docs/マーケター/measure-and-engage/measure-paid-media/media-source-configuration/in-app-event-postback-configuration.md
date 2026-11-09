---
title: アプリ内イベントポストバック設定
metadata:
  keywords:
    - In-App Events
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-11T08:47:14Z'
  edited_at: '2026-10-14T09:20:45Z'
  id: 208439256
  locale: ja
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ja/articles/208439256
---
> **概要:** アプリエンゲージメントとユーザーの質を測定し、アプリ内イベントデータを利用してキャンペーンを最適化します。

<div id="overview" />

## 概要

アプリ内イベントにより、マーケターはさまざまなソースからアプリエンゲージメントとユーザーの質を測定し、適切なユーザー獲得戦略を構築できます。アドネットワークは、アプリ内イベント情報を利用してキャンペーンを最適化し、CPAまたはイベント単価キャンペーンを実行します。アドネットワークは、ポストバックを介してリアルタイムでアプリ内イベントデータを受信します。<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントに関する詳細はこちら</Anchor>。

<div id="postback-in-app-event-selection" />

## アプリ内イベントポストバックの選択

マーケターは、本記事で説明する設定を用いて、どのアプリ内イベントに対しアドネットワークにポストバックを送信するか選択できます。

<div id="note" />

> 📘 **注記**
>
> * アプリ内イベントには**拒否されたイベント**、つまり、Protect360によってブロックされた、または検証ルールの条件を満たさないイベントが含まれています。
> * **アプリ内イベントポストバック**セクションが**連携**タブに存在しない場合は、パートナーがまだAppsFlyerでのアプリ内イベント記録を予備設定していないことを意味します。パートナーは、<Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">パートナーアシスタントウィジェット</Anchor>を使用してAppsFlyerに連絡し、連携を完了できます。

<div id="in-app-event-postback-window" />

## アプリ内イベントポストバック期間

アプリ内イベントポストバック期間は、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#cpa">CPA (アクション単価)</Anchor> ベースでネットワークと作業するマーケターが、コンバージョン後の期間を設定し、その後はイベントポストバックが送信されないようにすることを可能にします。

例えば、ユーザーがインストールしてから15日以内に発生するイベントに課金される場合、このように期間を設定します。

<Image align="center" alt="15-day_in_app_event_postback_setting.png" src="https://files.readme.io/6ffcd335b85334015f518895b317d3a5e273f4e00c31e3694c0f95a22ba6d4fb-33379700644497.png" width="529px" />

この期間を超えるとポストバックは送信されず、ネットワークにも通知されませんが、イベントはAppsFlyerに記録され続け、ネットワークに帰属します。

ポストバックは常に**現行の**期間設定に基づいて送信されます。次の例を参照してください。

| 1月1日 | 期間は15日です。<br /><br />ユーザーがアプリをインストールします。 |
| --- | --- |
| 1月2日 | 期間は10日に変更されます。 |
| 1月14日 | ユーザーが購入します。<br /><br />イベントが現行の期間(10日) 内に含まれないため、ポストバックはアドネットワークに送信されません。 |
| 1月15日 | 期間は20日に変更されます。 |
| 1月18日 | ユーザーによる再度の購入。<br /><br />今回は、イベントが現在の期間内（20日間）に入っているため、ポストバックが送信されます。 |

<div id="note-1" />

> 📘 **注**
>
> [「オーガニックを含むすべてのメディアソース」](#ポストバック送信のオプション)が選択されている場合、このルールは適用されません。この場合、この設定を行ったパートナーは、**たとえそのコンバージョンイベントの帰属先が別のパートナーであったとしても**、**設定を行ったパートナーに対して**定義されたポストバック期間内にイベントが発生した限り、広告主が受信するすべてのコンバージョンイベントについてポストバックを受け取ります。

<div id="default-postback-window" />

### デフォルトのポストバック期間

アプリ内イベントのポストバック設定を始める際、デフォルトの期間は自動で6か月に設定されます。

<div id="note-2" />

> 📘 **注記**
>
> 2019年7月30日より前に、パートナーのアプリ内イベントポストバックを利用し始めた場合、デフォルトの期間設定はライフタイム（制限なし）です。つまり、アプリ内イベントのポストバックは常に送信されます。

<div id="who-can-configure-postback-windows" />

### ポストバック期間を設定できるのは誰か

* マーケター
* 代理店（**アプリ内イベントのポストバック設定を許可する** <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#代理店の許可">権限</Anchor>がある場合）。  
  **注:** 同じアドネットワークを利用するマーケターと代理店は、それぞれ独自にポストバック期間を設定できます。これはネットワークとの契約に基づきます。
* パートナー（**アプリ内イベントのポストバック設定を許可する** <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">権限</Anchor>がある場合）。

<div id="event-mapping" />

## イベントマッピング

各マーケターは同じタイプのイベントに異なる名前を付けられます。これらのイベント名はパートナーの名義と異なることもあります。

例えば、ユーザーがアプリ内で購入をすると、あるマーケターはそれを `purchase` や `event5` など、情報量の少ないIDで命名し、パートナーは `purchase_event` と名付けるかもしれません。

マーケターのイベントがパートナーのイベントと一致するようにするには、イベント名をマッピングする必要があります。

<div id="note-3" />

> 📘 **注**
>
> 特定のパートナーの連携タブでマッピングされたイベントは、標準のポストバックおよび <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAN ポストバック</Anchor> の両方に適用されます。

<div id="mapping-methods" />

### マッピング方法

各パートナーは、以下の方法のいずれかを選んでアプリ内イベントをマッピングします。

* [パートナーイベントIDを入力してください](/docs/in-app-event-postback-configuration#h_c513e6d4-d46f-4070-a98d-1888a5ea939d)
* [リストからイベントIDを選択](/docs/in-app-event-postback-configuration#select-an-event-id-from-the-list)
* [イベントをそのまま送信（マッピングなし）](/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped)

<div id="note-4" />

> 📘 **注記**
>
> * 全てのパートナーに全てのマッピング方法があるわけではありません。
> * マッピングをパートナー自らが行える [権限](/docs/in-app-event-postback-configuration#アドネットワークによるイベントマッピング)を与えることが可能です。

<div id="h_c513e6d4-d46f-4070-a98d-1888a5ea939d" />

<Accordion title="パートナーイベントIDを入力してください。">

* **AppsFlyerイベント**: アプリイベントのリストからイベントを選んでください。
* **パートナーイベントにマッピング済み**:テキストフィールドに、パートナーから受け取った、アプリイベント（AppsFlyerイベント）に対応するイベントIDを入力してください。

<div id="note-5" />

> 📘 **注記**
>
> * イベント名では大文字と小文字が区別されます。不一致を避けるために、すべてのメディアソースとアプリバージョンで正しいイベント名を使用するようにしましょう。
> * イベント名を入力する際、イベント名の前後にアンダースコア（低いダッシュ）を使用できます。AppsFlyerから送信されるイベント名が正確に同じアンダースコアを持っている場合にのみ、アンダースコアを使用してください。

<Image align="center" alt="enter_event_name.png" src="https://files.readme.io/b9d65d3a6b4c1ab4d3f7e83cc2226af5c5a83e1e83cfbfa3df36d295ae568a45-33379700646545.png" />

</Accordion>

<div id="select-an-event-id-from-the-list" />

<Accordion title="リストからイベントIDを選択してください。">

* **AppsFlyerイベント**: アプリイベントのリストからイベントを選択します。
* **パートナーイベントにマッピング済み**:定義済みのパートナーイベントのリストから、アプリイベント（AppsFlyerイベント）に対応するイベントを選択します。

<Image align="center" alt="In-app_event_postbacks_en-us.png" src="https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png" />

</Accordion>

<div id="send-events-as-they-are-unmapped" />

<Accordion title="イベント名をそのまま送信する（マッピングなし）">

一部のパートナーは、マッピングされていないアプリ内イベントポストバックを好みます。つまり、イベント名はアプリでの名前どおりに送信されます。イベント名が `購入`、`獲得`、`イベント5` であっても構いません。

パートナーに送信する未マッピングのイベントを選択できます。

* **手動で追加:** 特定のイベントを選択してください。
* **すべてのイベントを送信（アンインストールとセッションは除外）**:すべてのイベントを送信します。これには、アンインストール、セッション（アプリの起動）、`af_app_opened`イベントは含まれません。

<div id="note-6" />

> 📘 **注記**
>
> 広告主が意図せず第三者のアナリティクスプラットフォームと情報を共有しすぎないようにするため、2019年3月以降、アナリティクスプラットフォームに対して、[**Send All Events (excludes uninstalls and sessions)**]（すべてのイベントを送信 - アンインストールとセッションを除く）オプションを削除しました。この日付以前に設定された分析プラットフォームでは、このオプションがそのまま保持されています。

**イベントを手動で追加するには:**

1. **イベントを追加**をクリックしてください。
2. ポストバックオプションを選択してください:
   * **AppsFlyerイベント**: アプリイベントのリストからイベントを選択します。
   * **ユーザー向け**:イベントの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#for-users-from">送信オプション</Anchor>を選択します。
   * **含む**:ポストバックに含める[データ](/docs/in-app-event-postback-configuration#ポストバックに含めるデータ)を選択します。
3. さらにイベントに対してこの手順を繰り返してください。

<Image align="center" alt="send_postbacks_as_is_en-us.png" src="https://files.readme.io/cc6b2bb1a381d88add035b9f369b0ba68dee8744aa3c2ee2f8f6f054b365a0dd-33379684962705.png" />

**すべてのイベントを送信するには:**

1. 「**すべてのイベントを送信（アンインストールとセッションを除く）**」を選択します。
2. ポストバックオプションを選択してください:  
   * **ユーザー向け**:すべてのイベントの[送信オプション](/docs/in-app-event-postback-configuration#ポストバック送信のオプション)を選択します。
   * **含む**:ポストバックに含めるすべてのイベントの[データを選択します。](/docs/in-app-event-postback-configuration#ポストバックに含めるデータ)

<Image align="center" alt="send_postbacsk_as_is_no_mapping.png" src="https://files.readme.io/458ca832d4176ccd306236cf10f211499e841dc9f550558987dff3ee683bd2d1-33379700651665.png" />

</Accordion>

イベントマッピングの詳細については、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">アプリ内イベントポストバック</Anchor>をご覧ください。

<div id="options-for-sending-postbacks" />

### ポストバック送信のオプション

各イベントで、どのような場合にポストバックを送信するかを選択できます（ポストバック期間内）。

* **このパートナーのみ：** イベントがこのパートナーに起因する場合、つまり、イベントを実行したユーザーがこのパートナーから来た場合にのみ、ポストバックを送信します。
* **オーガニックを含む全メディアソース：** 任意のパートナーに起因するイベントやオーガニックイベント、つまりイベントを実行したユーザーがどのメディアソースから来た場合でも、すべてのメディアソースにポストバックを送信します。　**注：** オーガニックを含むすべてのメディアソースを選択した場合、他のパートナーのポストバックにはアトリビューションデータは含まれません。

<div id="data-to-include-in-the-postbacks" />

### ポストバックに含めるデータ

ポストバックでアドネットワークと共有するイベントデータの種類を選択することができます。次のいずれかのオプションを選択します。

* **値も収益もなし**:パラメーター（値または収益）なしでイベント自体のみを送信します。
* **値有りで収益なし**:収益値**以外**のすべてのパラメーターを送信します。
* **Values & revenue（値も収益も送信する）**：収益値を含む全てのイベントパラメーターを送信します（存在する場合）。
* 価値 / 収益 / 純収益イベントに含まれる収益値および純収益値（イベントに存在する場合）を含む、すべてのイベントパラメーターを送信してください。

<div id="note-7" />

> 📘 **注**
>
> 「**値、収益、純収益**」オプションをご利用いただくには<strong>、ROI360 Advanced</strong>のサブスクリプションが必要です。また、このオプションは および`af_ars_*` イベントでのみ`af_purchase*`ご利用いただけます。

広告ネットワークがキャンペーンを最適化し、結果を改善するためには収益の共有をお勧めします。ただし、収益の共有は必須ではありません。イベントの価値に`af_revenue`が定義されている場合のみ、収益共有を有効にしてください。それ以外の場合、広告ネットワークは収益値が空のイベントを受け取ります。

<div id="share-revenue" />

#### シェア収益

ポストバックでは、`af_revenue`および`af_currency`はJSON`event_value`の外側に<strong>「monetary</strong>」および「**currency**」として記述され、個別に送信することができます。ポストバック構造の例:

```http
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&content_id=(af_content_id)
```

「**値、収益、net revenue**」オプションが選択されている場合、`af_net_revenue`JSONの`event_value`外部に<strong>「net-monetary」</strong>として記述し、別途送信することも可能です。ポストバック構造の例:

```http
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&net-monetary=(net-monetary)&content_id=(af_content_id)
```

<div id="note-8" />

> 📘 **注**
>
> 」または「<strong>値あり・収益なし」</strong>を選択した場合、それぞれのパラメーターは「N/A」で表示されます。

<div id="tip" />

> 📘 **ヒント**
>
> アプリ内イベントポストバック設定では、標準の**マネタリーパラメータ**（）にグロス収益の代わりとしてネット収益を送信することも可能です。この設定を利用するには、Customer Success Manager（CSM）へお問い合わせください。

<div id="h_01HBZCRNKGBEDSBZEY87KYQ60G" />

> 📄 **例**
>
> マーケティング担当者は、次の event\_value と共に購入イベントを送信します：`event_value`event\_value
>
> ```json
> {"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_content_type":"category_a"}
> ```
>
> 以下の表は、パラメーターがどのように送信されるかを示しています。
>
>
>
> | フィールド名 | イベント価値 | 金銭的 | 通貨 | net-monetary |
> | --- | --- | --- | --- | --- |
> | **価値なし & 収益なし** | 該当なし | 該当なし | 該当なし | 該当なし |
> | **価値あり & 収益なし** | `{"af_currency":"N/A","af_content_id":"1234567","af_revenue":"N/A","af_content_type":"category_a"}&monetary=N/A&content_id=1234567` | 該当なし | 該当なし | 該当なし |
> | **価値あり & 収益あり** | `{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_content_type":"category_a"}&monetary=50.87&content_id=1234567` | 50.87 | 米ドル | 該当なし |
> | **価値 / 収益 / 純収益** | `{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_net_revenue":35.61,"af_content_type":"category_a"}&monetary=50.87&net-monetary=35.61&content_id=1234567` | 50.87 | 米ドル | 35.61 |

<div id="conditional-in-app-event-postbacks" />

### 条件付きアプリ内イベントポストバック

異なるイベントにマッピングできる複数の条件を使用してアプリ内イベントのポストバックをフィルタリングします。フィルター条件を満たすイベントのみがSRNやAnalyticsパートナーなどのパートナーに送信されます。この機能は次の用途に利用します:

* ユーザーのセグメンテーション、パーソナライゼーション、リテンションの最適化
* データの最小化
* ユーザーブライバシーの保護

<div id="h_01HBZCRNKHRTMHP3JPFVCS8D6N" />

> 📄 **例**
>
> ゲームアプリのマーケティング担当者は、アドネットワークを通じて行っているキャンペーンを最適化しようとしていますが、その対象はレベル10またはレベル50に到達したユーザーや、アプリ購入に3ドルを使うユーザーのみです。
>
> <Image align="center" alt="in_app_event_condition__1_.png" src="https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png" />
>
> **このイベントの条件は次のように設定されています:**
>
> * レベル が<strong><em>10</em></strong>に等しいとき、<em>`fb_mobile_level_acheived`</em>にマップします。
>   それ以外の場合（**または**）、
> * レベル が<strong><em>50</em></strong>に等しいとき、<em>`fb_mobile_level_acheived`</em>にマップします。
>   それ以外の場合（**または**）、
> * コスト が<strong><em>3</em></strong>に等しいとき、<em>`fb_mobile_purchase`</em>にマップします。

**イベントの条件を設定するには:**

1. パートナー連携ページで、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">定義しマッピング</Anchor>する必要のあるアプリ内イベントをパートナーに送信します。
2. 必要なイベントのアイコン![image.png](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png)をクリックして条件を追加します。
3. <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview#event-values">イベント価値</Anchor>で表示される条件フィールドを入力します。
   * プロパティ名
   * 価値
   * 条件をマッピングするパートナーイベント（これらの[マッピングオプション](/docs/in-app-event-postback-configuration#マッピング方法)のいずれかを使用）
4. さらに条件を追加できますが、まず既存の条件の全てのフィールドを入力してください。
5. **統合を保存**をクリックします。

<div id="considerations" />

#### 考慮事項

条件を構成する際に、パートナーに送信されるイベントについて次の考慮事項が満たされていることを確認してください。

<div id="condition-structure" />

<Accordion title="条件の構造">

* 条件のプロパティと値がイベントのデータと一致している必要があります。
* 現在、条件は「等しい」のみ設定可能です。
* 配列などの複雑な構造はサポートしていません。

</Accordion>

<div id="multiple-conditions-for-an-event" />

<Accordion title="イベントに対する複数の条件">

* 1つのイベントに設定できる条件は最大5つです。
* ポストバックを送信するには、少なくとも1つの条件を満たす必要がありますが、実行されるのは1つのみです。
* 条件は出現順にチェックし、最初に満たされた条件を実行します。
* 各条件は個別にマッピングされます。パートナーイベント名が「**条件に基づく**」に変更されます。
* 複数の条件が同じプロパティまたは同じ値を持つことは可能ですが、2つの条件が同時に同じプロパティと値を持つことはできません。
* 複数の条件を同一のイベントにマッピングすることが可能です。

</Accordion>

<div id="note-9" />

> 📘 **注記**
>
> * この機能は、キャンペーンの最適化に与える影響を把握するために、テストアプリやマイナーなイベントなどでテストすることをお勧めします。
> * <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ポストバックコンテンツ</Anchor>を確認するには、ローデータポストバックレポートをダウンロードしてください。

<div id="editing-multiple-events" />

### 複数のイベントを編集する

イベントをマッピングする際、ユーザーに関するフィールドの値は、と（含む）で複数のイベントに対して1回の操作で編集できます。

**複数のイベントを編集するには:**

1. 更新するイベントを選択します。
2. **一括操作**をクリックします。
3. 選択したすべてのイベントに適用する新しい設定を選択してください。
   * **ユーザーの選択**（1オプションのみ選択可能）
     * このパートナーのみ
     * オーガニックを含む全てのメディアソース
   * **含む**（1オプションのみ選択可能）
     * データなし（デフォルト）
     * 収益のない価値
     * 価値と収益

<Image align="center" alt="In-app_event_postbacks_en-us.png" src="https://files.readme.io/559265d0e12e9e2ef62e0a19c5833465ee758821654877cffa4e75f6ff3f99b9-33379700657169.png" />

<div id="custom-events" />

### カスタムイベント

マッピング可能なイベントのリストには、SDKにより既に報告されたイベント、またはAppsFlyerに送信されたサーバー間イベントのみが表示されます。マップしたいイベントがドロップダウンリストに表示されない場合、次の理由が考えられます。

* まだイベントを実行したユーザーがいません
* このイベントが最後に発生したのは2週間以上前です
* アクティブなイベントのリストが多すぎます

**いずれの場合も、イベントをパートナーIDにマッピングするためには、以下の手順に従ってください。**

1. ドロップダウンリストから[**+ アイテムを追加**]をクリックします。
2. テキストボックスに、追加したいイベントの名前を入力してください。
3. 確認するには、Vマークをクリックしてください。追加したイベントがリストに表示され、選択できるようになります。 ![add-custom-event-name.jpg](https://files.readme.io/cab91e281e863e7bbe0e3a96392552a149f7ccccd41695f2e4579089256e8dd1-33379684971793.jpg)
4. イベントをパートナーの識別子にマッピングします。
5. **連携を保存**をクリックしてマッピングを保存してください。

<div id="note-10" />

> 📘 **注意**
>
> * ポストバックページにカスタムイベントを追加しても、アプリから自動的に取得されるわけではありません。適切な機能を確保するには、SDKまたはS2Sでイベントを設定する必要があります。詳細はAppsFlyerにイベントを送信する方法をご覧ください。
> * 特定のパートナーでカスタムイベントが追加されると、このイベントは全てのパートナーのリストに追加されます。つまり、このイベントはどのパートナーのドロップダウンリストでも確認できます。
> * イベント名とパラメーターの定義に関する <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#tips">ヒント</Anchor> と <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#limitations">制限事項</Anchor> を参照してください。

**代理店と広告ネットワーク:**

* カスタムイベントを追加することはできません。
* マーケターがイベントを追加し、必要な<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">権限</Anchor>を許可した後にのみ、イベントを表示またはマッピングできます。

<div id="event-mapping-by-ad-networks" />

## アドネットワークによるイベントマッピング

マーケティング担当者は、アドネットワークが独自にイベントをマッピングすることを許可できます。そのためには、マーケターがアドネットワークに必要な権限を与える必要があります。

1. **アクティブ統合**ページで、権限を付与したいパートナーを見つけます。
2. [権限]タブで、[**アプリ内イベントのポストバック構成を許可**]トグルを[**オン**]に切り替えます。

<Image align="center" alt="広告ネットワーク権限ポストバック.png" src="https://files.readme.io/f8369f6a0a60d3c48ef66b51f61b3c81f00f6c88511f5f69b2c927788a64f018-33379700661265.png" />

アドネットワークが権限を取得すると、「[イベントIDをテキストフィールドに入力](/docs/in-app-event-postback-configuration#マッピング方法)」の指示に従ってイベントをマッピングできます。

<div id="event-mapping-by-agencies" />

## 代理店によるイベントマッピング

マーケティング担当者は代理店にアプリ内イベントポストバックの設定を許可することができます。

<div id="note-11" />

> 📘 **注意**
>
> 広告主と代理店の両方が同じアドネットワークに対して同じアプリ内イベントのポストバックを有効にしている場合、AppsFlyerはポストバックを1回のみ送信します。これにより、イベントの重複が防止されます。

**代理店にアプリ内イベントポストバックを設定する権限を付与する方法：**

1. **アクティブ統合**ページから代理店を見つけます。
2. 代理店が全てのイベントを共有できるか、特定のアドネットワークに関連するイベントのみを共有できるかを選択します。
3. 代理店がイベントの収益を送信できるかを選択します。
4. 代理店が共有できる特定のイベントを選択します。

<Image align="center" alt="代理店イベント.png" src="https://files.readme.io/194b9a18f7721d4cc159f6385140cbb989108b70110e2e0d0f29f90d6115b10a-33379684973969.png" />

<div id="h_01HDP3XHBPA5GZEVERMBN43JH0" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベント—概要</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure">リッチアプリ内イベント—イベント構造</Anchor>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HE0FQ1AB6NQCTKFTDW22SRYC=%E6%A6%82%E8%A6%81 postback-inapp-event-selection=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E9%81%B8%E6%8A%9E h_01HBZCRNKGH1PAK8RC846PPRTS=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E9%81%B8%E6%8A%9E h_01HBZCRNKGQTJ4VJ00TVTS14N2=%E6%B3%A8%E8%A8%98 inapp-event-postback-window=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HBZCRNKGS71QGK5506N07K84=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01K9MBNYC6PPHXSZ3KNVNSDASJ=%E6%B3%A8 default-postback-window=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HBZCRNKGV5CREN5K0RBDMBH6=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HBZCRNKGVXN233AFFHG42NW9=%E6%B3%A8%E8%A8%98-1 who-can-configure-postback-windows=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%A7%E3%81%8D%E3%82%8B%E3%81%AE%E3%81%AF%E8%AA%B0%E3%81%8B h_01HBZCRNKG7AECFSBXV2WDD9AR=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%A7%E3%81%8D%E3%82%8B%E3%81%AE%E3%81%AF%E8%AA%B0%E3%81%8B event-mapping=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01HBZCRNKG7SZ4T41BY60BAJZN=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01HBZCRNKGT64TE2XYK9VS4ATD=%E6%B3%A8-1 mapping-methods=%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E6%96%B9%E6%B3%95 h_01HBZCRNKG4EF9MSY696SD5VQ9=%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E6%96%B9%E6%B3%95 h_01HBZCVAGPSNDJMWRWENEP45N7=%E6%B3%A8%E8%A8%98-2 enter-the-partner-event-id=h_c513e6d4-d46f-4070-a98d-1888a5ea939d h_01HBZCRNKG1E63DZRSDWTB8CJN=%E6%B3%A8%E8%A8%98-3 h_01HBZCRNKGWQBNY8RP4MTW3DXV=select-an-event-id-from-the-list h_01HBZCRNKG4981T00N70X2GP0J=send-events-as-they-are-unmapped h_01HBZCRNKGXJ683VHFTE277ER9=%E6%B3%A8%E8%A8%98-4 options-for-sending-postbacks=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E9%80%81%E4%BF%A1%E3%81%AE%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 h_01HBZCRNKG1VN7E6TVCPDW7M73=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E9%80%81%E4%BF%A1%E3%81%AE%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 data-to-include-in-the-postbacks=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AB%E5%90%AB%E3%82%81%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF h_01HBZCRNKGESY50NSZGTVPT25M=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AB%E5%90%AB%E3%82%81%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF h_01KRKDVVV246YZYGM5G2ZJR63W=%E6%B3%A8-2 sharing-revenue=%E3%82%B7%E3%82%A7%E3%82%A2%E5%8F%8E%E7%9B%8A 01J9Y0T400M5Z62Q9CKF8M75WR=%E3%82%B7%E3%82%A7%E3%82%A2%E5%8F%8E%E7%9B%8A h_01KRKDVVV2YF4XMKNCVEG1FFSG=%E6%B3%A8-3 h_01KRKDVVV242YPHP2W8EWTBSMD=%E3%83%92%E3%83%B3%E3%83%88 h_01HBZCRNKGBEDSBZEY87KYQ60G=%E4%BE%8B conditional-inapp-event-postbacks=%E6%9D%A1%E4%BB%B6%E4%BB%98%E3%81%8D%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HBZCRNKG5X3B2NJZZP6ER2CX=%E6%9D%A1%E4%BB%B6%E4%BB%98%E3%81%8D%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HBZCRNKHRTMHP3JPFVCS8D6N=%E4%BE%8B-1 considerations=%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 h_01HBZCRNKHBR57YVHZQP7NJBAP=%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 h_01HBZCRNKHJGBYNP9JN24CQ3CC=condition-structure h_01HBZCRNKH1R0FR61C6TA0MCTN=multiple-conditions-for-an-event h_01HBZCRNKHF6TFP0N302D7DCMD=%E6%B3%A8%E8%A8%98-5 editing-multiple-events=%E8%A4%87%E6%95%B0%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B h_01HBZCRNKHHD3WC4GTJT9NSJ4C=%E8%A4%87%E6%95%B0%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B custom-events=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HBZCRNKH754PANWSZ4FMXJVQ=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HBZCRNKH4PVR3FEMTMERW3M1=%E6%B3%A8%E6%84%8F event-mapping-by-ad-networks=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AB%E3%82%88%E3%82%8B%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01HBZCRNKH1GCZY17R04WTZ0MQ=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AB%E3%82%88%E3%82%8B%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 event-mapping-by-agencies=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AB%E3%82%88%E3%82%8B%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01HBZCRNKHHF3E6CZNQQG0Q4VS=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AB%E3%82%88%E3%82%8B%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01K5B6QS6YXKMJSEWE2WFT5AQC=%E6%B3%A8%E6%84%8F-1 h_01HDP3XHBPA5GZEVERMBN43JH0=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
