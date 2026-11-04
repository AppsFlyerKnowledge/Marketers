---
title: ROI360ガイド｜広告収益のアトリビューション
metadata:
  keywords:
    - ad revenue
    - ad monetization
    - monetization
    - Advertisers
    - adrevenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2016-12-12T10:53:27Z'
  edited_at: '2026-10-28T08:49:58Z'
  id: 217490046
  locale: ja
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ja/articles/217490046
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** 広告収益をユーザーの獲得元に紐づけ、LTV（顧客生涯価値）に基づいてマーケティング施策の成果を把握します。

![Attributes_ad_revenue.png](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)

<div id="ad-revenue-attribution" />

## 広告収益のアトリビューション

* バナー、オファーウォール、インタースティシャルなどの広告がアプリ内に表示されると、広告収益が発生します。
* 広告収益にアプリ内購入やサブスクリプションの収益も合わせると、ユーザーのLTVを漏れなく把握できます。ユーザーのLTVを、獲得のために広告費を投じたキャンペーンに紐づけることで、AppsFlyerでROIを算出・分析できます。

**アトリビューション済み広告収益データ**：

* メディエーションプラットフォームや広告収益化ネットワークから、サーバーAPIまたはアプリに組み込んだ収益報告用SDKを通じて取得します（iOS 14を含む）。
* ユーザー獲得元のメディアソースに紐づけられます。例：
  * ユーザーがネットワークAの広告を見て、自社アプリをダウンロードします。
  * アプリ内に広告が表示されます。
  * アプリ内に表示された広告の掲載元にかかわらず、その広告収益はユーザーを獲得したネットワークAに紐づけられます。
* レポートで確認できるデータの細かさは、広告収益化ネットワークとの連携方式と、広告収益のアトリビューションの種類によって異なります。

<Accordion title="広告収益のアトリビューションの連携方式">

データの正確性と反映の速さは、以下の表に示すとおり、連携方式によって異なります。

**注意**：SDK方式の連携には、開発者による実装が必要です。 S2S方式の連携には、アドネットワークの正しい認証情報が必要です。

| 広告収益のアトリビューションの連携方式 | 説明 |
| --- | --- |
| S2S APIによる[集計データ](#h_01JYRKB8Q3D3W0FM75VH78XQTS) | <ul><li>AppsFlyerは、1日分の収益を国・地域別に取得します。</li><li>収益をトリガーイベントの発生回数で割り、アクションあたりの実効収益（eRPA）を算出します。</li><li>トリガーイベントには、アプリの起動、またはアプリに設定した特定のアプリ内イベントを使用します。</li><li>メディエーションプラットフォームを使用する場合は、そのプラットフォームとの広告収益連携を有効にする前に、配下の広告収益化パートナーとの広告収益連携を無効にしてください。無効にしないと、データが重複します。</li><li>このデータはローデータレポートでは利用できず、ポストバックやUAシグナルでアドネットワークに共有することもできません。</li></ul> |
| S2S APIによる[端末単位データ](#01ECF1PZ36R9W7A0X4WBR95JDS) | <ul><li>メディエーションプラットフォームまたは広告収益化ネットワークが、ユーザーの収益を端末単位で報告します。端末単位のデータに対応していないアドネットワークもあります。</li><li>この収益は、ユーザー獲得元のメディアソースに紐づけられます。広告収益のアトリビューションには、リターゲティングも含め、AppsFlyerのアトリビューションルールが適用されます。</li><li>メディエーションプラットフォームを使用する場合は、そのプラットフォームとの広告収益連携を有効にする前に、配下の広告収益化パートナーとの広告収益連携を無効にしてください。無効にしないと、データが重複します。</li><li>S2S APIによる端末単位の連携は、広告収益の100%を含み、各連携方式の中で最も正確なデータを得られます。</li><li>データはローデータレポートで利用でき、アドネットワークには<Anchor target="_blank" href="/marketers/ja/docs/share-ad-revenue-data-with-partners">UAシグナル経由でのみ共有できます。</Anchor></li><li>Androidでは、一部のメディエーションがAppSet\_idのみを提供する場合があるため、開発者がこのIDの収集を有効にしていることを確認してください。開発者向けの[AppSet IDの収集手順](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id)を参照してください。</li></ul> |
| SDKによる広告表示単位データ | <ul><li>「広告表示単位」は、AppsFlyerが受信するデータの単位を指します。最終的なレポートでは、端末単位など、別の単位に集計される場合があります。</li><li>メディエーションプラットフォームまたは広告収益化ネットワークが、ユーザーの収益を広告表示1回ごとに報告します。広告表示単位のデータに対応していないアドネットワークもあります。</li><li>この収益は、ユーザー獲得元のメディアソースに紐づけられます。広告収益のアトリビューションには、リターゲティングも含め、AppsFlyerのアトリビューションルールが適用されます。</li><li>メディエーションプラットフォームを使用する場合は、そのプラットフォームとの広告収益連携を有効にする前に、配下の広告収益化パートナーとの広告収益連携を無効にしてください。無効にしないと、データが重複します。</li><li>SDKによる広告表示単位の連携は、広告収益の連携方式の中で最も早くデータが反映されます。</li><li>SKAN（SKAdNetwork）に対応しています。</li><li>AppsFlyerの連携済みパートナー一覧にないメディエーションを使用する場合は、SDKによる広告表示単位の連携が必要です。開発者が広告収益SDKのmediation\_networkにcustomMediationを指定する必要があります。</li><li>アドネットワークにデータを共有できるのは、<Anchor target="_blank" href="/marketers/ja/docs/share-ad-revenue-data-with-partners">ポストバック経由のみ</Anchor>です。</li></ul> |
| 広告表示単位（SDK経由）と端末単位（S2S API経由）の併用 | <ul><li>当日（X日）は、SDKで受信した広告表示単位のデータを獲得元に紐づけて報告し、翌日以降に、APIで受信した端末単位のデータに置き換えます。**注意**：Androidでは、SDKで報告されたデータに端末IDがなく、端末を特定できない場合は、APIで受信したデータに置き換えられません。</li><li>速報性と正確性を両立できます。当日（X日）は早く届くデータを使い、翌日（X＋1日）以降は正確性の高いデータを利用できます。</li><li>SKANに対応しています。</li><li><Anchor target="_blank" href="/marketers/ja/docs/share-ad-revenue-data-with-partners">ポストバックとUAシグナルの両方</Anchor>を通じて、アドネットワークにデータを共有できます。</li><li>Androidでは、一部のメディエーションがAppSet\_idのみを提供する場合があるため、開発者がこのIDの収集を有効にしていることを確認してください。開発者向けの[AppSet IDの収集手順](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id)を参照してください。</li></ul> |

</Accordion>

<div id="implementation" />

## 実装

以下では、利用できる広告収益のアトリビューション方式と、実装・管理に必要な作業や手順を説明します。

<Accordion title="広告収益パートナーとの連携">

**事前準備**：

* 広告収益の連携先パートナーに、APIの認証情報の提供を依頼します。

**広告収益パートナーとの連携を有効にするには**：

1. AppsFlyerのサイドメニューから<strong>［設定］</strong>＞**［収益設定］**＞<strong>［広告収益］</strong>を選択します。
2. ［広告収益連携］で、<strong>［新しい広告収益連携］</strong>をクリックします。
3. 広告収益パートナーを選択し、<strong>［次へ］</strong>をクリックします。

   ![ad revenue 3.6(2).png](https://files.readme.io/8ccba7d0909c15e92507bc55c7bf2bf003e1a9431fb6bd1d32a0f41959f7a904-47792643579153.png)

   <div id="note" />

   > 📘 **注意**
   >
   > 使用するメディエーションが対応パートナーの一覧にない場合は、<strong>［カスタムメディエーション］</strong>を選択し、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/gs-ad-revenue">AppsFlyer広告収益SDK API</Anchor>で連携します。

4. 受信する広告収益データの種類を選択します。**注意**：以下のすべての選択肢に対応しているとは限らず、対応状況はアドネットワークによって異なります。
   * アトリビューション済み収益。ユーザー獲得元に基づいて紐づけられた収益です。アトリビューション済み収益は、次の方式で報告できます。
     * S2S APIによる[集計データ](#h_01JYRKB8Q3D3W0FM75VH78XQTS)。
       * 広告収益の配分に使うイベントを選択します。例えばaf\_app\_openedを選択すると、総広告収益をアプリ起動イベントの件数で割り、アプリ起動1回あたりの広告収益を算出します。
     * S2S APIによる端末単位データ。
       * **Android：** 一部のメディエーションが`app_set_id`のみを提供する場合があるため、開発者がこのIDの収集を有効にしていることを確認してください。開発者向けの[AppSet IDの収集手順](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id)を参照してください。
       * **注意**：メディエーションプラットフォームの端末単位の広告収益APIを有効にする場合は、配下の広告収益化ネットワークとの広告収益連携を無効にする必要があります。無効にしないと、データが重複します。
     * SDKによる広告表示単位データ。
       * アプリ開発者に、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/gs-ad-revenue">AppsFlyer広告収益SDK API</Anchor>の実装を依頼します。
     * **推奨：** 広告表示単位（SDK経由）と端末単位（S2S API経由）の併用。
       * アプリ開発者に、[AppsFlyer広告収益SDK API](https://dev.appsflyer.com/hc/docs/gs-ad-revenue)の実装を依頼します。
     * **Android：** 一部のメディエーションが`app_set_id`のみを提供する場合があるため、開発者がこのIDの収集を有効にしていることを確認してください。開発者向けの[AppSet IDの収集手順](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id)を参照してください。
     * **注意**：メディエーションプラットフォームを使用する場合は、そのプラットフォームとの広告収益連携を有効にする前に、配下の広告収益化パートナーとの広告収益連携を無効にしてください。無効にしないと、データが重複します。
5. 連携先パートナーの要件に従って、APIの認証情報を入力するか、ログインします。 SDK連携では、この操作は不要です。
6. ［<strong>保存］</strong>をクリックします。
7. <strong>［接続をテスト］</strong>をクリックします。
   * 接続に成功したことを示すメッセージが表示されれば、設定は完了です。
   * 別のメッセージが表示された場合は、[「広告収益連携のステータスとテスト」](#01ECF1PZ32Z4C20NADJ2SF3EPC)の表で対処方法を確認し、対応後に手順をやり直してください。
8. AppsFlyerは、1日に複数回パートナーからデータを取得します。詳しくは、[データの更新・反映](#01H8V10BKK6N5XJ6GHKC201E3Y)を参照してください。
9. ［任意］AppsFlyerの広告収益データを、メディエーションパートナーやユーザー獲得パートナーのダッシュボードと比較し、正しく計測されているか確認します。<Anchor target="_blank" href="/marketers/ja/docs/compare-roi360-ad-revenue-data-with-partner-data">詳細はこちら</Anchor>
10. ［任意］<Anchor target="_blank" href="/marketers/ja/docs/share-ad-revenue-data-with-partners">UAシグナルと広告収益イベントのポストバック</Anchor>を通じて、ユーザー獲得パートナーに広告収益データを共有します。

**注意**：連携方式を変更すると、UTCの翌日午前0時に反映されます。

</Accordion>

<Accordion title="広告収益パートナー連携の確認・編集・削除">

![delete_edit_adi.png](https://files.readme.io/2d2153ec3248061dab4072e1d981e237f553e32824a68e392ae239778b307610-47792653636113.png)

**広告収益パートナーとの連携を確認・編集・削除するには**：

1. AppsFlyerのサイドメニューから<strong>［設定］</strong>＞**［収益設定］**＞<strong>［広告収益］</strong>を選択し、対象のアプリを選択します。  
   すべてのパートナー連携の一覧とともに、製品、連携方式、連携のステータス、広告収益イベント名が表示されます。
2. 対象の連携にカーソルを合わせ、必要に応じて<strong>［編集］</strong>または<strong>［削除］</strong>をクリックします。

</Accordion>

<Accordion title="複数の連携経由で報告される広告収益の重複排除">

アプリで2つの<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#メディエーションプラットフォーム">メディエーションプラットフォーム</Anchor>とAPI連携（集計データまたは端末単位）し、両方が同じ<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#収益化ネットワーク">広告収益化ネットワーク</Anchor>を扱う場合、広告収益データが一部重複することがあります。それぞれのプラットフォームが、自身を通じて発生した収益だけでなく、接続先の広告収益化ネットワークの収益全体を報告するためです。

**2つのメディエーションプラットフォームが互いの収益を含めて報告する場合に、一部の収益の重複を防ぐには**：

* 利用できる場合は、SDKによる広告表示単位の連携を使用します。この方法で報告された広告表示単位のデータには、重複排除の処理は行われません。 SDKは広告表示1回につき1回だけ報告するため、重複を取り除く必要がありません。
* **API経由**の連携では、広告収益の重複排除を設定します。
  1. AppsFlyerのサイドメニューから<strong>［設定］</strong>＞**［収益設定］**＞<strong>［広告収益］</strong>を選択します。
  2. <strong>［一般設定］</strong>で、<strong>［2つのメディエーションパートナーが互いの収益を含めて報告する場合に広告収益の重複を排除］</strong>にチェックを入れます。**注意**：2つのメディエーションプラットフォームが異なる広告フォーマットを扱う場合は、チェックを入れないでください。例えば、プラットフォーム1でバナーとインタースティシャル、プラットフォーム2でアプリ起動時広告とネイティブ広告を表示する場合です。

     <div id="note-1" />

     > 📘 **注意**
     >
     > 次の連携では、この設定は適用されません。
     >
     > * **広告表示単位（SDK）の連携**：すべてのパートナー。
     > * **端末単位（API）の連携**：AppLovin MAXまたはironSource（Unity LevelPlay）。
     >
     > これらの連携ではデータが重複しないため、重複排除は不要です。


![dedup.png](https://files.readme.io/a739bc7e3557913bf6a67afa74a71dd72673d5b4e4d6bbe1d3ef872e46609422-47792653637265.png)

</Accordion>

<Accordion title="アプリの起動やアプリ内イベントを使った広告収益の集計">

広告収益の集計データ方式は、次のように動作します。

* 連携先のアドネットワークが、1日の総収益を国・地域別に報告します。
* AppsFlyerが、広告収益をトリガーイベントの発生回数で割り、アクションあたりの実効収益（eRPA）を算出します。
* AppsFlyerが、アトリビューション済みの端末ごとに、eRPAの合計を含む\_monetizedイベントを生成します。例：ad\_matched\_monetized。
* eRPAを使って、収益をメディアソースに紐づけます。
* 次のいずれかのイベントを使用できます。
  * **収益化専用のアプリ内イベント**：アプリの変更が必要です。
  * **af\_app\_opened**イベント：デフォルトで利用できます。
* 広告収益連携を利用する場合は、アプリ内イベントで同じ広告収益の金額を別途送信しないでください。 AppsFlyerは連携を通じて広告収益化ネットワークから収益データを取得するため、両方で送信すると、ダッシュボードで広告収益が重複して計上されます。

<div id="aggregate-ad-revenue-using-events" />

#### イベントを使った広告収益の集計

| イベントの方式 | 実装方法 | 確認事項 |
| --- | --- | --- |
| 収益化専用のアプリ内イベント | <ul><li>広告表示時に発生するアプリ内イベントを設定します。</li><li>ユーザーのアクションを個別に数えられるため、eRPAをより正確に計算できます。</li><li>広告収益化ネットワークごとに異なるアプリ内イベントを設定すると、さらに詳しく計測できます。これにより、広告収益化ネットワーク別に収益を確認できます。<br />詳細は、以下の表を参照してください。</li></ul> | <ul><li>開発者によるアプリの変更が必要です。</li><li>ダッシュボードで、広告収益化ネットワーク別の収益を確認できます。</li></ul> |
| af\_app\_openedイベント | <ul><li>af\_app\_openedは、AppsFlyer SDKがデフォルトで送信するイベントです。</li><li>ユーザーのセッションごとに発生します。</li></ul> | <ul><li>アプリの変更は不要です。</li><li>短時間で導入できます。</li><li>1セッションにつき広告を1回だけ表示する場合を除き、eRPAの値に大きなずれが生じます。</li><li>広告収益化ネットワーク別の収益は確認できません。</li><li>アプリを開いたすべてのユーザーが対象となるため、広告を見る意向があったかどうかは分かりません。</li></ul> |

<div id="comparison-of-in-app-event-methods" />

#### アプリ内イベントの方式の比較

| 方式 | メリット | デメリット | 確認事項 |
| --- | --- | --- | --- |
| すべてのアドネットワークで同じイベントを使用します。例：ad\_watched。収益化に関する詳細を含むad\_watched\_monetizedイベントが自動的に生成されます。 | 最も簡単に実装できます。 | アドネットワークごとのクリック数や広告収益など、成果を詳しく比較するための情報は得られません。 | <ul><li>広告をクリックしやすいユーザーを獲得できるメディアソースやキャンペーンを見つけたい場合に適しています。</li><li>広告収益化ネットワークの成果を比較する用途には適していません。</li></ul> |
| <strong>（推奨）</strong>広告視聴用のイベントを、アドネットワークごとに個別に割り当てます。例：ad\_watch\_admob、<br /><br /> ad\_watch\_vungle。 | ローデータだけでなく、ダッシュボードでも各広告収益化ネットワークの成果を把握・比較できます。 | 広告収益は、複数のイベントに分かれて集計されます。アドネットワークごとに別のイベントが必要です。 | ダッシュボードで広告収益化ネットワークを比較できます。アドネットワークごとのアプリ内イベントを使って、収益をネットワーク別に分けられます。 |

</Accordion>

<Accordion title="広告収益連携のステータスとテスト">

広告収益連携の稼働状況は、次の場所で確認できます。

* <Anchor target="_blank" href="/marketers/ja/docs/dashboard-cost-and-ad-revenue-status">広告費・広告収益の連携状況ダッシュボード</Anchor>：アカウント内の1つ以上のアプリで広告収益連携が有効になっているパートナーを、まとめて確認できます。
* **［接続をテスト］ボタン：** 広告収益連携を追加・編集するときに使用できます。連携が正常に動作しているか、その場で確認できます。

連携の動作を確認するには：

1. <strong>［接続をテスト］</strong>をクリックします。
2. 成功した場合は、**［APIキーを検証しました］**（API方式の連携）、または<strong>［認証に成功しました］</strong>（SDK連携）と表示されます。別のメッセージが表示された場合は、以下の表の対処方法に従ってください。

| ステータス | 意味 | 補足／必要な対応 |
| --- | --- | --- |
| APIキーを検証しました | 接続は有効で、データを取得できます。 AppsFlyerは、1日に複数回データを収集します。詳しくは、[データの更新・反映](#01H8V10BKK6N5XJ6GHKC201E3Y)を参照してください。 | なし |
| 認証に成功しました | SDKから有効な広告収益イベントを受信しました。 | なし |
| 認証情報が無効 | 指定した認証情報のうち、1つ以上が正しくありません。 | 広告収益パートナーから正しい認証情報を取得してください。 |
| 設定情報の不足 | 認証情報のフィールドに、未入力の項目があります。 | 広告収益パートナーのダッシュボードで認証情報を取得するか、パートナーに提供を依頼してください。 |
| イベントが見つかりません | 最近、SDKから有効な広告収益イベントを受信していません。 | SDKの実装が完了し、テストイベントが送信されていることを確認してください。<Anchor target="_blank" href="/marketers/ja/docs/testing-the-sdk-integration-for-marketers#view-live-events">ライブイベントビューアー</Anchor>で、イベントの到着をリアルタイムに確認できます。 |

<div id="note-2" />

> 📘 **注意**
>
> SDK連携の場合は、<Anchor target="_blank" href="/marketers/ja/docs/testing-the-sdk-integration-for-marketers#view-live-events">ライブイベントビューアー</Anchor>で広告収益イベントがリアルタイムで記録されることも確認できます。表示されるのは、登録済みのテスト端末から送信されたイベントのみです。

</Accordion>

<div id="ad-revenue-data" />

## 広告収益データ

広告収益データは、AppsFlyerのダッシュボードとローデータレポートで利用できます。

<Accordion title="広告収益の集計データ">

広告収益を計測すると、流入元ごとにユーザーがもたらす価値を継続的に把握できます。ユーザーがアプリを継続的に開き、広告に反応するにつれて、LTVが積み上がっていきます。

**注意**：ダッシュボードやレポートによって、広告収益データに差異が生じる場合があります。

広告収益のアトリビューションは、次の画面・レポートで利用できます。

* LTVベース：
  * ダッシュボード：Overview dashboard、イベント
  * LTVレポート
  * コホートダッシュボードとレポート
  * Master API
* アクティビティベース：
  * ダッシュボード：アクティビティ
  * 広告収益のローデータ

<div id="overview-dashboard---aggregated-performance-report" />

#### **Overview dashboard｜集計パフォーマンスレポート**

![](https://files.readme.io/f3ea2c79ed42c59d26f6f82d7f68e20b319a005e6a3131239b99f13db59b3cff-47792643589393.png)

Overview dashboardでは、次のように表示されます。

* 収益を含む各指標は、LTVベースです。 <Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTVデータとアクティビティデータの違い</Anchor>を参照してください。
* <strong>［収益］</strong>列には、広告収益やアプリ内購入など、すべての収益が含まれます。
* メディアソース、キャンペーン、広告セット、国・地域などの階層でデータを詳しく見ると、レポート内の**monetized**イベントを確認できます。

**イベントダッシュボード**

![](https://files.readme.io/c7c8fddb68f705a7be694afdde6faf387cf34b79abfbc68c39e53823549a385d-47792643591057.png)

アクティビティダッシュボードでは、次のように表示されます。

* 収益を含む各指標は、アクティビティの発生日に基づきます。 <Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTVデータとアクティビティデータの違い</Anchor>を参照してください。
* <strong>［ユーザーあたりの平均アクション数］</strong>は、アプリ内に表示された広告にユーザーが反応する傾向を示します。

<div id="examples" />

#### 例

2017年12月31日に、3人のユーザーがアプリをインストールしたとします。各ユーザーの獲得元は、次のとおりです。

* ユーザーA：ネットワークA
* ユーザーB：ネットワークB
* ユーザーC：オーガニック

アプリは、5つの異なる広告収益化プラットフォームと連携しています。 AppsFlyer SDKを使い、各プラットフォームに対応する次のアプリ内イベントを個別に設定しています。

* Meta Audience Network：fb\_ad\_view
* Chartboost：chartboost\_ad\_view
* Admob：admob\_ad\_view
* Applovin：applovin\_ad\_view
* IronSource：is\_ad\_view

インストール後の4日間に、各ユーザーに次のように広告が表示されました。

| ユーザー | ユーザー獲得元のアドネットワーク | fb\_  <br />ad\_view | chartboost\_  <br />ad\_view | admob\_  <br />ad\_view | applovin\_  <br />ad\_view | is\_ad\_view | 合計 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | ネットワークA<br /><br />2017-12-31 | 2018-01-01<br /><br />$1 | 2018-01-02<br /><br />$1 | 2018-01-03<br /><br />$1 | 2018-01-04<br /><br />$1 |  | $4 |
| B | ネットワークB<br /><br />2017-12-31 | 2018-01-02<br /><br />$1 |  | 2018-01-04<br /><br />$1 |  |  | $2 |
| C | オーガニック<br /><br />2017-12-31 | 2018-01-01<br /><br />$1 |  |  |  | 2018-01-02<br /><br />$1 | $2 |

このデータから、ユーザー別・日別（およびアプリ内イベント別）の収益を、次のように集計できます。

| ユーザー | 2018-01-01 | 2018-01-02 | 2018-01-03 | 2018-01-04 | LTV合計 |
| --- | --- | --- | --- | --- | --- |
| A | $1 | $1 | $1 | $1 | $4 |
| B |  | $1 |  | $1 | $2 |
| C | $1 | $1 |  |  | $2 |
| 合計 | $2 | $3 | $1 | $2 | $8 |

**レポートの見方：**

前述のとおり、広告収益はユーザーのLTVに含まれます。そのため、ダッシュボードでは、選択した期間にインストールしたユーザーが集計対象（コホート）になります。そのユーザーが現在までにもたらした収益が集計されます。異なる2つの日付範囲を選択した場合のレポートを確認します。

集計レポート｜選択期間：2017-12-31～2018-01-05

| アドネットワーク | LTV収益 |
| --- | --- |
| オーガニック | $2 |
| ネットワークA | $4 |
| ネットワークB | $2 |
| ネットワークC | $2 |

この場合のコホートは、2017年12月31日から、この例での当日（2018年1月5日）までにアプリをインストールしたユーザーで構成されます。これらのユーザーがもたらしたすべての収益を獲得元に紐づけ、各ユーザーのLTVに反映します。

</Accordion>

<Accordion title="広告収益のローデータ">

<Image alt="PremiumFeature.jpg" src="https://files.readme.io/674e5d0c9efde9d12008bd705b3ba95f04e133fec3f39d4278612675123d4de4-360007173877.jpg" width="78px" />

広告収益のローデータレポートには、AppsFlyerと端末単位または広告表示単位で連携する、広告収益化ネットワークのデータが含まれます。

**広告収益のローデータの仕組み**

* データは、ユーザーごとのユニークインプレッション数に基づいて集計されます。ユニークインプレッションは、広告収益化ネットワーク、広告ユニット、掲載位置の組み合わせで判定します。
* 広告表示単位のローデータは、次のように利用できます。
  * 端末単位に集計し、端末単位のレポートで提供します。
  * Data Lockerで、広告表示単位のレポートとして提供します。

<table><thead><tr><th>レポート</th><th>データの<br/>エクスポートページ</th><th>Pull API </th><th>Data Locker</th></tr></thead><tbody><tr><td>アトリビューション済み広告収益（ノンオーガニック）</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>オーガニック広告収益</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>リターゲティング広告収益 </td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>広告表示単位のローデータ\*\*</td><td><span>-</span></td><td><span>-</span></td><td><span>✓ </span></td></tr><tr><td colspan="4"><p>\* 1日に複数回更新される、更新版を含むレポートも利用できます。 Data Lockerの更新版を含まないレポートは、1日1回配信されます。詳しくは、<a href="#01H8V10BKK6N5XJ6GHKC201E3Y">データの更新・反映</a>を参照してください。</p><p>\*\* 名前に「広告表示単位」が含まれるレポートを指します。広告表示単位の広告収益連携そのものを指すわけではありません。</p></td></tr></tbody></table>

**データの特徴とフィールド**

広告収益レポートのフィールドには、次の情報が設定されます。

* 広告収益イベント自体から取得する情報。以下の表に記載しています。これらのフィールドは、次の2種類に分かれます。
  * **広告収益固有：** 広告収益に固有のフィールド。例：インプレッション数、掲載位置。**注意**！値が入るフィールドは、広告収益化パートナーによって異なります。このセクションの「アドネットワーク別のフィールド」の表を参照してください。
  * **共通：** 他のローデータレポートでも同じような意味を持つフィールド。例：イベント名、イベント値、通貨。
* イベントをユーザー獲得元のメディアソースに紐づけることで設定される情報。これらのフィールドには、ユーザー獲得時のコンバージョンイベントの情報がコピーされます。例：メディアソース、キャンペーン。これらは、以下の表には記載していません。

<div id="fields-populated-by-ad-revenue" />

#### 広告収益イベントから値を取得するフィールド

| api\_name | フィールド名 | フィールドの種類 | 説明 |
| --- | --- | --- | --- |
| <span id="event_time"></span>event\_time | イベント時刻 | 共通 | 収益が紐づく日付 |
| <span id="event_name"></span>event\_name | イベント名 | 共通 | af\_ad\_revenueを設定 |
| <span id="event_revenue"></span>event\_revenue | イベント収益の通貨 | 共通 | <ul><li>イベントの収益通貨で表した収益額</li><li>0は、収益が発生しないインプレッションを表します。</li></ul> |
| <span id="event_revenue_currency"></span>event\_revenue\_currency | イベントの通貨 | 共通 | イベント収益の通貨 |
| <span id="event_revenue_xxx"></span>event\_revenue\_XXX | イベント収益XXX | 共通 | <ul><li>エクスポートページ：アプリ固有の通貨に換算した収益</li><li>Data Locker：常に米ドル</li><li>Pull API：取得時に指定した通貨</li></ul> |
| <span id="country"></span>country | 国 | 共通 | インストールコンバージョンが発生した国 |
| <span id="ad_unit"></span>ad\_unit | 広告ユニット | 広告収益固有 | このフィールドの値は、アドネットワークによって異なります。サーバー間（S2S）の連携では、次の値を使用します。<ul><li>**MAX：** 広告ユニットID（例：f53328a3c）。</li><li>**IronSource：** banner、rewarded\_video、interstitialなどの広告ユニットの種類。</li></ul>その他のアドネットワークについては、パートナーの連携ガイドや担当者への問い合わせで、必要な形式を確認してください。 |
| <span id="segment"></span>segment | セグメント | 広告収益固有 | 広告の掲載位置名 |
| <span id="monetization_network"></span>monetization\_network | 広告収益化ネットワーク | 広告収益固有 | 広告を配信するアドネットワーク |
| <span id="impressions"></span>impressions | インプレッション数 | 広告収益固有 | ユーザーに広告が表示された回数 |
| <span id="mediation_network"></span>mediation\_network | メディエーションネットワーク | 広告収益固有 | イベントをAppsFlyerに報告するメディエーションプラットフォーム |
| <span id="customer_user_id"></span>customer\_user\_id | カスタマーユーザーID | 共通 | 広告主から取得できる場合に値が入ります。<ul><li>広告表示単位（SDK）の連携：AppsFlyer SDKの`setCustomerUserId()`を使って収集します。</li><li>端末単位（API）の連携：メディエーションAPIから収集します（メディエーションSDKで設定したユーザーIDまたはパブリッシャーユーザーID）。</li><li>OdeeoとAppodealでは非対応です。</li></ul> |

<div id="fields-by-network" />

#### アドネットワーク別のフィールド

<table><thead><tr><th>表示名</th><th>Admob</th><th>ironSource（LevelPlay）</th><th>AppLovin MAX</th><th>Appodeal</th><th>Fyber</th></tr></thead><tbody><tr><td>広告ユニット</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>セグメント</td><td>-</td><td>(1)</td><td>-</td><td>-</td><td>-</td></tr><tr><td>掲載位置</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>広告収益化ネットワーク</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>インプレッション数</td><td><span>-</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td>メディエーションネットワーク</td><td><span>-</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">（1）広告主がironSourceで設定する必要があります。</td></tr></tbody></table>

[広告収益のローデータレポートのサンプル](https://docs.google.com/spreadsheets/d/e/2PACX-1vRm_1tevWFdzdj6JgdxYawLBtYAJj-ubDeY4g1QfbdSkd2-Adi18oemPMdd7m7cM2e3fzm7VH0w6lhD/pub?output=xlsx)

</Accordion>

<Accordion title="データの更新・反映">

データの更新・反映は、連携方式とレポートの提供方法によって異なります。

**S2S API連携**では、最も早い場合、次のタイミングでデータを利用できます。

* ダッシュボードとローデータレポート（Data Locker経由）：X＋1日のUTC正午から、約6時間ごとに1日約4回。その後、2日後、3日後、7日後、14日後に、それぞれ1回。

**広告表示単位のSDK連携**では、最も早い場合、次のタイミングでデータを利用できます。

* ダッシュボード（アクティビティ・コホート指標）：継続的に更新（イベント発生から15～60分後）。
* ダッシュボード（LTV指標）とローデータレポート（Data Locker経由）：最も早い場合、X日のUTC午前5時から、約4時間ごとに1日約6回更新。
* 広告表示単位のローデータレポート（Data Locker経由）：X日のUTC午前1時から、1時間ごとに更新。

**広告表示単位（SDK経由）と端末単位（S2S API経由）の併用**では、当日（X日）の速報性と、翌日（X＋1日）以降の正確性を、次のように両立します。

* SDKで受信する広告表示単位のデータ：

  * ダッシュボード（アクティビティ・コホート指標）：継続的に更新（イベント発生から15～60分後）。
  * ダッシュボード（LTV指標）とローデータレポート（Data Locker経由）：最も早い場合、X日のUTC午前5時から、約4時間ごとに1日約6回更新。
  * 広告表示単位のローデータレポート（Data Locker経由）：X日のUTC午前1時から、1時間ごとに更新。
* S2S APIで受信する端末単位のデータ：

  * ダッシュボードとローデータレポート（Data Locker経由）：X＋1日のUTC正午から、約6時間ごとに1日約4回。その後、2日後、3日後、7日後、14日後に、それぞれ1回。

**ローデータのエクスポートとPull API**では、連携方式やROI360パッケージ（Advanced／Standard）にかかわらず、対象日のデータは翌日（X＋1日）のUTC午後6時から利用できます。これらのツールでは、その時点以降、データは更新されません。

**注意：** ダッシュボードで当日中のデータを利用するには、ROI360 Advancedの契約が必要です。

</Accordion>

<Accordion title="広告収益のData Lockerレポート">

| 名前 | 更新頻度 | レポートに含まれる区分 |
| --- | --- | --- |
| ***日次広告収益（端末単位で集計）*** | 特定の日（X日）の広告収益は、翌日（X＋1日）のUTC午後5時に報告されます。<br /><br />例えば、5月1日の広告収益は5月2日に報告されます。 | アトリビューション済み、オーガニック、リターゲティングの各広告収益が含まれます。 |
| ***日次広告収益レポート（更新版あり、端末単位で集計）*** | 日次レポートは、次のバージョンで構成されます。<ul><li>収益の発生当日（X日）に、4時間ごとに作成される当日版。当日版のデータはSDK APIで収集します。</li><li>S2S APIレポートのデータに基づき、1日後、2日後、3日後、7日後、14日後に作成される、対象日1日分のデータを含むバージョン。</li></ul>つまり、1日分のレポートには、次のバージョンが含まれます。<ul><li>X日の00:00～04:00。</li><li>X日の00:00～08:00［SDK API］</li><li>X日の00:00～12:00［SDK API］</li><li>X日の00:00～24:00［SDK API］</li><li>X＋1日の00:00～24:00［S2S］</li><li>X＋2日の00:00～24:00［S2S］</li><li>X＋3日の00:00～24:00［S2S］</li><li>X＋7日の00:00～24:00［S2S］</li><li>X＋14日の00:00～24:00［S2S］</li></ul> | 各バージョンに、アトリビューション済み、オーガニック、リターゲティングの各広告収益が含まれます。 |
| ***広告表示単位の広告収益レポート（広告表示単位）*** | 広告表示単位の広告収益レコードを、1時間ごとに別ファイルに書き込みます。 |  |

<span id="h_01KRKHJN2G5SER73D3EZB14GDS"></span>**関連情報：**

* <Anchor target="_blank" href="/marketers/ja/docs/revenue-etl-reports">収益ETLレポート</Anchor>

</Accordion>

<div id="additional-information" />

## 補足情報

<Accordion title="集計データ方式から端末単位への移行">

集計データ方式から端末単位へ移行する際は、次の点に注意してください。

* 移行は、過去の広告収益データに影響しません。過去のデータは変わりません。
* 広告収益データは、UTC午前3時から1日に複数回、その時点で選択されている集計単位で取得します。
* 端末単位の連携では、集計データ方式のようにアプリ内イベントを定義する必要はありません。それまでのイベントを引き続き送信しても、AppsFlyerの端末単位のレポートには影響しません。

</Accordion>

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| 制限事項 | 次の画面・ツールでは、広告収益イベントを利用できません。<ul><li>Push API</li><li>リターゲティングダッシュボード</li></ul>端末単位のデータの制限事項：<ul><li>ピボットとMaster APIのコホートでは、af\_ad\_revenueイベントを利用できません。</li><li>コホート分析では、このイベントを利用できます。</li><li><Anchor target="_blank" href="/marketers/ja/docs/applovin-max-ad-revenue-configuration#ベストプラクティス">Meta広告の**アプリ内**入札の収益計測を実装すると、データに差異が生じる場合があります。</Anchor></li></ul>AppsFlyerのダッシュボードでは、af\_ad\_revenueイベントを発生させたユニークユーザー数の集計には対応していません。 |
| 対応する端末ID | 広告収益のアトリビューションでは、次の端末IDに対応しています。<ul><li>AppsFlyer ID</li><li>IDFA</li><li>IDFV</li><li>GAID</li><li>AppSet ID*</li><li>Android ID</li><li>IMEI</li></ul><ul><li>AppSet IDに対応するのは、Applovin MAXとIronSource LevelPlayのメディエーションのみです。開発者向けの[AppSet IDの収集手順](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id)を参照してください。</li></ul> |
| アドネットワークのアクセス権 | コホートレポートにはアクセスできません。 |
| 代理店のアクセス権 | 代理店は、次のように利用できます。<ul><li>広告収益の設定にはアクセスできません。</li><li>自社に関連するダッシュボードとデータをすべて確認できます。</li></ul> |
| 運用媒体の開示設定 | 非対応 |
| タイムゾーン | AppsFlyerのダッシュボードとレポートでは、広告収益はUTCのタイムゾーンでのみ表示されます。例えばUTC＋2で午後2時と報告されたデータは、AppsFlyerではUTC午後2時として表示されます。 1日1回処理されます。<br /><br />さまざまな取得元やパートナーから収集したデータの形式をAppsFlyerで統一する必要があり、その多くがUTCで報告されているためです。 |
| 通貨 | AppsFlyerでは、次のように表示されます。<ul><li>ダッシュボードには、広告主がアプリに設定した通貨で表示されます。</li><li>ローデータレポートには、元の通貨と、広告主がアプリに設定した通貨に換算した金額が表示されます。</li></ul> |
| データの種類 | オーガニックとノンオーガニックの両方に対応しています。 |
| データの更新・反映 | [広告収益](#01H8V10BKK6N5XJ6GHKC201E3Y) |
| 過去のデータ・さかのぼっての更新 | <ul><li>連携を設定した日から、データを取得・利用できます。連携開始日（Day 0）より前の過去データは利用できません。</li><li>S2S APIで受信した特定の日の広告収益データは、1日後、2日後、3日後、7日後、14日後に更新されます。</li><li>Overview dashboard、コホート・アクティビティダッシュボード、Master API、Cohort APIでは、過去の広告収益データも更新されます。ローデータのエクスポートとPull APIでは更新されません。 Advancedの収益パッケージを利用している場合は、Data Lockerのデータも更新されます。</li></ul> |
| アカウントユーザーのアクセス権 | 対応 |
| SKAN | 広告表示単位の広告収益SDK APIで対応しています。 |
| 国・地域 | コホートダッシュボードで国・地域が不明（N/A）の場合、国・地域別に集計するとN/Aのデータは表示されません。 |
| アプリ内イベントのポストバック | <ul><li>パートナーへのポストバックは、［このパートナーのみ］または［オーガニックを含むすべてのメディアソース］を選択できます。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#ポストバック送信のオプション">詳細はこちら</Anchor></li><li>アドネットワークへの広告収益イベントのポストバックに対応するのは、SDKによる広告表示単位の連携と、広告表示単位（SDK経由）・端末単位（S2S API経由）の併用のみです。</li></ul> |
| CTV・PC・ゲーム機のアプリ | <ul><li>Android・iOSアプリに対応しています。</li><li>VungleはWindowsプラットフォーム（UWP）に対応しています。</li><li>その他のプラットフォームには対応していません。</li></ul> |
| カスタマーユーザーID（CUID） | SDK連携と端末単位の連携の両方に対応しています。 |
| ダッシュボードのイベント数 | 当日のデータは、過去のデータよりもイベント数が多くなる傾向があります。過去のデータでは、端末・アドネットワーク・広告ユニット・掲載位置が同じインプレッションをまとめて集計するため、イベント数が少なくなります。 |

</Accordion>

<Accordion title="広告収益の連携済みパートナー一覧">

<table><thead><tr><th rowspan="2">パートナー</th><th colspan="3">利用できる連携方式</th></tr><tr><th>集計データ</th><th>端末単位</th><th>広告表示単位</th></tr></thead><tbody><tr><td>Admost</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./applovin-campaign-configuration#ad-revenue-tab" target="_blank">AppLovin</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./applovin-max-ad-revenue-configuration" target="_blank">AppLovin Max</a></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./appodeal-campaign-configuration" target="_blank">Appodeal</a></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./bytedance-ads-china-campaign-configuration" target="_blank">Bytedance Ads（中国のトラフィック）</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Pangle（TikTok for Business）</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./chartboost-campaign-configuration#ad-revenue-tab" target="_blank">Chartboost</a></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td></tr><tr><td>カスタムメディエーション</td><td>-</td><td>-</td><td><span>✓</span></td></tr><tr><td>Google Ad Manager</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./meta-ads-integration-setup" target="_blank">Meta広告</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./fyber-campaign-configuration#ad-revenue-tab" target="_blank">Fyber</a></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./google-admob-ad-revenue-attribution-configuration" target="_blank">Google Admob</a></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td></tr><tr><td>Inmobi</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td> <a href="./ironsource-campaign-configuration#ad-revenue-tab" target="_blank">ironSource</a>（LevelPlay）</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Mintegral</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Odeeo</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tapjoy</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Topon</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Topon Pte</td><td>-</td><td>-</td><td> <span>✓</span><br/> </td></tr><tr><td>Tradplus</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./unity-ads-campaign-configuration" target="_blank">Unity Ads</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Unity Ads Mediation</td><td>-</td><td>-</td><td><span>✓</span></td></tr><tr><td>Voodoo</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./vungle-campaign-configuration" target="_blank">Vungle</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Yandex</td><td>-</td><td>-</td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div data-zendesk-anchors="ad-revenue-attribution=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 01ECF1PZ2XNCHR4QPATTBV0VMV=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 implementation=%E5%AE%9F%E8%A3%85 01ECF1PZ2Y9ERT5C50ZD4CDJET=%E5%AE%9F%E8%A3%85 h_01_custom_mediation_note=%E6%B3%A8%E6%84%8F h_01M1TXMH5P53PNVW56GHZEXKKK=%E6%B3%A8%E6%84%8F-1 aggregate-ad-revenue-using-events=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E9%9B%86%E8%A8%88 01H8V10BKK06Z3E823G6GNTPKH=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E9%9B%86%E8%A8%88 comparison-of-inapp-event-methods=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E6%96%B9%E5%BC%8F%E3%81%AE%E6%AF%94%E8%BC%83 01H8V10BKKMG2A704NZC2VFSJM=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E6%96%B9%E5%BC%8F%E3%81%AE%E6%AF%94%E8%BC%83 h_01_sdk_live_events_note=%E6%B3%A8%E6%84%8F-2 ad-revenue-data=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%83%87%E3%83%BC%E3%82%BF 01ECF1PZ3315R242DC78HV60YC=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%83%87%E3%83%BC%E3%82%BF overview-dashboard-aggregated-performance-report=overview-dashboard%E9%9B%86%E8%A8%88%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01ECF1PZ348365STFGE3136WEJ=overview-dashboard%E9%9B%86%E8%A8%88%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01ECF1PZ348P0JCBASS4QBD56W=%E4%BE%8B fields-populated-by-ad-revenue=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%8B%E3%82%89%E5%80%A4%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 01H8V10BKK7BHC31W27G22D23K=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%8B%E3%82%89%E5%80%A4%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 fields-by-network=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E5%88%A5%E3%81%AE%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 01H8V10BKKW6NERRYCRD6BVZ54=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E5%88%A5%E3%81%AE%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 01H8V10BKMX7H9H04ZBF3HRJVY=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1" />
