---
title: Google Ads Web｜Webアプリ向けキャンペーンの作成
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2026-04-07T12:46:10Z'
  edited_at: '2026-10-28T09:15:18Z'
  id: 45498975339537
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/45498975339537
---
> **概要：** WebアプリのGoogle Ads連携を設定し、Offline Conversion API（OCI）を通じてWebコンバージョンのシグナルをGoogleに送信します。

<div id="overview" />

## 概要

AppsFlyerは、WebアプリのキャンペーンにおけるGoogle Ads（`googleads_int`）連携に対応し、GoogleのOffline Conversion API（OCI）を通じてコンバージョンデータをレポートします。

この記事では、Google Adsの広告に接触し、Webサイトでコンバージョンに至るユーザーを対象に、AppsFlyerとGoogle AdsでWebキャンペーンを設定する方法を説明します。

キャンペーンのフローは、ユーザーがGoogleの広告をクリックしてWebサイトにアクセスするところから始まります。ユーザーがWebサイトで購入や会員登録などのイベントを完了すると、AppsFlyerはOCIを通じてコンバージョンのシグナルをGoogle Adsに送信します。 Googleはこのデータを使用して、広告ターゲティングの最適化とキャンペーンのパフォーマンス計測を行います。

<div id="see-also" />

> 📄 **関連記事**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/web-performance-measurement-overview">Web Performance Measurementの概要</Anchor>

<div id="prerequisites" />

### 前提条件

WebアプリのキャンペーンでGoogle Ads連携を有効にする前に、以下を準備してください。

* AppsFlyerに設定済みのWebアプリ
* Webサイトに実装済みのAppsFlyer Web SDK
* 適切なロールまたは権限を持つAppsFlyerアカウント

<div id="how-to-set-up-a-google-ads-web-campaign" />

### Google AdsのWebキャンペーンの設定方法

設定は、次の2つに分かれます。

1. AppsFlyerでGoogle Ads連携を設定（必須）
2. Google Adsでキャンペーンを設定（必須）

<div id="set-up-the-google-ads-integration-in-appsflyer" />

## AppsFlyerでのGoogle Ads連携の設定

まず、Webキャンペーン向けのGoogle Ads連携を有効にし、AppsFlyerからOCIに送信するポストバックを設定します。

<div id="step-1-activate-the-integration" />

<Accordion title="ステップ1：連携の有効化">

1. AppsFlyerのサイドメニューから、［**コラボレーション>Partner Marketplace**］を開きます。
2. **Google Ads Web**を検索して選択します。
3. ［**連携の設定**］をクリックします。［**アクティブな連携**］の設定ページが開きます。
4. アプリのドロップダウンからWebアプリを選択します。
5. ［**連携**］タブで、［**パートナーを有効にする**］をオンにします。

   <div id="note" />

   > 📘 **注意**
   >
   > このパートナーとの連携中は、トグルをオン（有効）のままにしてください。

6. **Advanced Matching Data Sharing：** オンにすると、AppsFlyerに送信するイベント情報に、ハッシュ化されたメールアドレス、電話番号、名、姓などのAdvanced Matchingの項目が含まれている場合、それらの項目がGoogleと共有されます。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor>を参照してください。
7. ［**お客様ID**］を入力します。このIDは、Google Adsの管理画面で取得できます。
   1. <span class="af-ol-a"></span>Google Adsアカウントにログインします。
   2. 右上のGoogleアカウントのアイコンをクリックし、お客様IDが表示される位置までスクロールします。
   3. 次のいずれかを実行します。
      * 同じアプリのキャンペーンを複数のGoogle Adsアカウントで配信している場合、クロスアカウントコンバージョントラッキングにはマネージャー（MCC）アカウントのお客様IDを使用します。個別アカウントのお客様IDではなく、MCC IDを［お客様ID］欄と［MCCのお客様ID］欄の両方に貼り付けます（両方に同じIDを入力）。  詳細は、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">MCCアカウントの設定に関するGoogleの手順</Anchor>を参照してください。
      * 広告配信に使用するGoogle Adsアカウントが1つだけの場合は、そのアカウントのIDを［お客様ID］欄に貼り付け、［MCCのお客様ID］欄は空欄にします。
8. AppsFlyerがGoogle Adsにコンバージョンをアップロードできるように、［**Googleでサインイン**］をクリックします。
9. お客様IDを取得したMCCアカウントの管理者アカウントを選択します。
10. ［**許可**］をクリックします。

    <div id="note-1" />

    > 📘 **注意**
    >
    > Googleでサインインし、AppsFlyerによるトークンの取得を許可すると、*Missing token*エラーメッセージは表示されなくなります。サインイン後もエラーが続く場合は、トークンに必要な権限が付与されていることを確認してください。


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="ステップ2：アプリ内イベントポストバックの設定">

WebサイトのイベントをGoogle Adsのコンバージョンアクションにマッピングします。 AppsFlyerは、コンバージョンに基づく最適化を可能にするため、OCIを通じてこれらのイベントをGoogleに送信します。

<div id="note-2" />

> 📘 **注意**
>
> WebアプリではすべてのイベントがWebイベントであり、インストールイベントはありません。 Googleに最適化させたい各イベントを、対応するGoogle AdsのコンバージョンアクションIDにマッピングする必要があります。

1. ［**アプリ内イベントポストバック**］をオンにします。
2. 必要に応じて、［**アプリ内イベントのポストバック期間**］を設定します。この期間は、ユーザーのWebサイトでの最初のコンバージョンイベントの発生時点から始まります。これは、モバイルアプリのインストール日に相当します。
3. ［**イベントを追加**］をクリックします。
4. ［**AppsFlyerイベント**］列で、送信するWebサイトのイベント（`purchase`、`sign_up`など）を選択します。

   <div id="note-4" />

   <div id="note-3" />

   > 📘 **注意**
   >
   > 訪問イベントは対象外です。このドロップダウンでは、カスタムWebイベントのみを選択できます。

5. ［**パートナー側のイベント名**］列に、Google Adsの**コンバージョンアクションID**を入力します。事前にGoogle Adsでコンバージョンアクションを作成する必要があります（後述のパート2のステップ2を参照）。コンバージョンアクションIDを確認するには、次の手順を実行します。
   * Google Adsでコンバージョンアクションのページを開きます。
   * ［**詳細**］タブを開きます。
   * ページのURLから、`ctid=*`クエリパラメータの値をコピーします。たとえば、`ctid=123456789`の場合は、`123456789`を入力します。
6. Google Adsに紐づくイベントのみを送信するには、［**送信対象ユーザー**］列で［**このパートナーのみ**］を選択します。
7. ［**送信するデータ**］列で、ポストバックに収益値を含めるかどうかを選択します。
8. ［**連携を保存**］をクリックします。

</Accordion>

<div id="set-up-a-web-conversion-campaign-in-google-ads" />

## Google AdsでのWebコンバージョンキャンペーンの設定

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="ステップ1：キャンペーンの種類・目的・目標の設定">

1. Google Adsにログインし、キャンペーンを作成します。
2. **キャンペーンの目的**を選択します。
   * モバイルアプリのキャンペーン専用の［**アプリのプロモーション**］を除き、すべての目的を選択できます。
   * Webサイトの特定のコンバージョンイベントに基づいて最適化する場合は、［**販売促進**］または［**見込み顧客の獲得**］を推奨します。
3. **コンバージョン目標**を選択します。デフォルトでは、アカウントレベルの目標が表示されます。そのまま使用することも、関係のない目標を削除することもできます。
   * 最適化したい目標がリストにない場合は、カスタムコンバージョンアクションを作成します（後述のステップ2を参照）。
4. **キャンペーンの種類**を選択します。
   * 商品カタログと確認済みのドメインが必要な［**ショッピング**］を除き、すべての種類を選択できます。

</Accordion>

<div id="step-2-create-conversion-actions" />

<Accordion title="ステップ2：コンバージョンアクションの作成">

AppsFlyerでマッピングしたWebサイトの各イベントに対応するコンバージョンアクションを、Google Adsで作成します。作成後、コンバージョンアクションIDをコピーし、前のセクションのAppsFlyerのイベントマッピングに貼り付けます。

1. Google Adsのサイドメニューから、［**目標>コンバージョン>概要**］を開きます。
2. ［**+新しいコンバージョンアクション**］をクリックします。
3. コンバージョンのデータソースとして［**インポート**］を選択し、次のいずれかを選択します。
   * ［**APIまたはアップロードによる手動インポート>クリック経由のコンバージョンを計測**］、または
   * ［**CRM、ファイル、その他のデータソース>クリック経由のコンバージョンを計測**］を選択し、［データソース］で［*このステップをスキップし、後でデータソースを設定*］を選択します。
4. ［**続行**］をクリックします。
5. ［**コンバージョン目標**］で、コンバージョンアクションのカテゴリを選択します。
6. ［**コンバージョン名**］を入力します。

   <div id="important" />

   > 🚧 **重要！**
   >
   > GCLIDに加えてGBRAID／WBRAIDでもOffline Conversions APIを使用するには、コンバージョンアクションの［**カウント方法**］を［*初回のみ*］ではなく［**全件**］（デフォルト）に設定してください。

7. ［**コンバージョン名**］を入力し、［**追加**］をクリックします。

   <div id="note-5" />

   > 📘 **注意**
   >
   > キャンペーンを1つのアクションのみで最適化する場合は、このカテゴリにそのアクションだけを含めてください。たとえば、購入のコンバージョンアクションに基づいてキャンペーンを最適化する場合は、そのカテゴリに含まれるアクションを購入のみにしてください。キャンペーンの作成時に、このカテゴリをパフォーマンス最適化のコンバージョン目標として選択できるようになります。

8. データソースを設定せずに［**保存して続行**］をクリックし、［**完了**］をクリックします。新しいコンバージョンアクションは、最初は［*無効*］と表示される場合がありますが、実際のデータが送信されると［*有効*］に変わります。
9. 新しいコンバージョンアクションをAppsFlyerのポストバックイベントにマッピングするため、コンバージョンアクションIDを取得します。コンバージョン目標の［**概要**］ページで作成したコンバージョンアクションをクリックし、ページのURLから`ctid=*`クエリパラメータの値をコピーします。
10. AppsFlyerで、Googleに最適化させたいポストバックイベントの［**パートナー側のイベント名**］列に、`ctid`の値を貼り付けます。「アプリ内イベントポストバックの設定」を参照してください。

</Accordion>

<div id="step-3-set-the-campaigns-final-url" />

<Accordion title="ステップ3：キャンペーンの最終ページURLの設定">

Googleは<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">最終ページURL</Anchor>を「ユーザーが広告をクリックした後にアクセスする、自社Webサイト内のWebページのURLアドレス。『ランディングページ』とも呼ばれます」と定義しています。

1. Google Adsで、［**キャンペーン>広告**］ページを開きます。
2. 広告の行で編集アイコンをクリックします。
3. ［**最終ページURL**］欄に、ランディングページのURLを入力します。

   <div id="important-1" />

   > 🚧 **重要！**
   >
   > 最終ページURLにAppsFlyerのURL（OneLinkまたは単一プラットフォーム向けの計測URL）を設定すると、キャンペーンが不承認になる可能性があるため、使用できません。リダイレクトが発生しない、直接アクセスできるWebアドレスのみを使用してください。
   >
   > 最終ページURLにAppsFlyerの計測パラメータを追加し、GoogleのValueTrackパラメータにマッピングできます。例：`af_c_id={campaignid}`。 Googleの広告がクリックされてランディングページが読み込まれると、これらのパラメータをページで利用できます。利用可能なValueTrackパラメータについては、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348">Googleのドキュメント</Anchor>を参照してください。
   >
   > 例：
   >
   > ```http
   > https://example.com?product=1234&af_c_id={campaignid}
   > ```


<div id="note-6" />

> 📘 **注意**
>
> GoogleのWeb広告キャンペーンでは、広告接触ごとに最終ページURLとトラッキングテンプレートURLの2つのURLを使用できます。ただし、広告の遷移先がWebサイトであるWebアプリのキャンペーンでは、トラッキングテンプレートURLは不要です。キャンペーンの目標がWebからモバイルアプリへの誘導である場合にのみ、トラッキングテンプレートURLが必要になることがあります。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-create-web-based-campaigns">Google AdsのWeb to Appキャンペーンの記事</Anchor>を参照してください。

</Accordion>

<div id="view-web-performance-measurement-data" />

## Web Performance Measurementのデータの確認

Google AdsキャンペーンのWebの計測データは、クロスプラットフォームダッシュボードとローデータのエクスポートで確認できます。

* **ダッシュボード：** <Anchor target="_blank" href="/marketers/ja/docs/my-dashboards#crossplatform-dashboard">クロスプラットフォームダッシュボード</Anchor>では、Webとアプリのデータが並べて表示され、プラットフォームを横断したキャンペーンのパフォーマンスをまとめて確認できます。
* **ローデータのエクスポート：** Webの計測データは、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-export-page">ローデータのエクスポートページ</Anchor>でも確認できます。
  * Google Adsに成果が紐づくWebイベントの`media_source`フィールドには、`googleadwords_int`が表示されます。

<div id="note-7" />

> 📘 **注意**
>
> この統合されたレポート表示により、モバイルとWebのすべてのコストレポートを含め、Webキャンペーンとアプリキャンペーンのパフォーマンスを1か所で分析できます。

<div id="measure-web-performance-data-with-web-cost" />

## Webコストを利用したWeb Performance Measurementのデータ分析

ダッシュボードと<Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">Cost ETLレポート</Anchor>で、Google AdsのWeb計測データとWebコストデータを合わせてパフォーマンスの全体像を把握するには、<Anchor target="_blank" href="/marketers/ja/docs/roi360-onboarding-guide#roi360について">ROI360パッケージ</Anchor>を契約し、以下の設定を完了してください。

1. ［**コスト**］タブまたは［**コスト設定**］ページから、`googleads_int`ではなく`googleadwords_int`を通じて、Webアプリにコストを連携します。コスト連携の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiの有効化">コストデータを計測するためのROI360コストAPIの設定</Anchor>を参照してください。
2. ランディングページのURLにキャンペーンID（`af_c_id`）を含めます。 Webの計測結果に紐づくコスト、クリック、インプレッションを最も細かい粒度で確認できるよう、URLにキャンペーン階層の情報をすべて含めてください。

<div id="troubleshooting-in-app-event-postbacks" />

## アプリ内イベントポストバックのトラブルシューティング

Google Adsにイベントデータが表示されない場合は、サポートに問い合わせる前に以下を確認してください。

<div id="set-token-permissions" />

<Accordion title="トークンの権限の設定">

Google Adsで、アクセストークンにオフラインコンバージョンをアップロードするために必要な権限があることを確認してください。

1. Google Developers Consoleを開きます。
2. `uploadClickConversions`に次のOAuthスコープがあることを確認してください：`https://www.googleapis.com/auth/adwords`
3. AppsFlyerの［連携］タブで、［**Googleでサインイン**］をクリックします。
4. MCCアカウントの管理者アカウントを選択します。
5. ［**許可**］をクリックします。

</Accordion>

<div id="mcc-customer-id" />

<Accordion title="MCCのお客様ID">

同じアプリのキャンペーンを複数のGoogle Adsアカウントで配信している場合は、MCCアカウントのお客様IDを使用する必要があります。 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186">MCCアカウントの設定に関するGoogleの手順</Anchor>を参照してください。

</Accordion>

<div id="conversion-action-id" />

<Accordion title="コンバージョンアクションID">

ポストバックするアプリ内イベントが、正しいコンバージョンアクションIDにマッピングされていることを確認してください。 Google AdsでコンバージョンアクションIDを確認するには、[ステップ2：コンバージョンアクションの作成](#step-2-create-conversion-actions)を参照してください。

</Accordion>

<div id="traits-and-limitations" />

## 機能と制限事項

| 項目 | 補足 |
| --- | --- |
| クリックとインプレッション | Webキャンペーンのクリックとインプレッションの取得には、<Anchor target="_blank" href="/marketers/ja/docs/roi360-onboarding-guide">ROI360の契約</Anchor>が必要です。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01KNM00RR7V9BAA2BSPDECHC9F=%E6%A6%82%E8%A6%81 h_01KQC2B644Y44631ZQKC1HPEF4=%E9%96%A2%E9%80%A3%E8%A8%98%E4%BA%8B prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01KNM00RR7H7A9CE06APEZSXKR=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 how-to-set-up-a-google-ads-web-campaign=google-ads%E3%81%AEweb%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 h_01KNM00RR77P8VD2YJ2R7DZBVX=google-ads%E3%81%AEweb%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 set-up-the-google-ads-integration-in-appsflyer=appsflyer%E3%81%A7%E3%81%AEgoogle-ads%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KNM00RR7E8MFSTGYKFEJDS1C=appsflyer%E3%81%A7%E3%81%AEgoogle-ads%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KNM00RR71ZXB72H8X1YXWKED=step-1-activate-the-integration h_01KNM00RR84CCGBR3T5WG7C5VW=%E6%B3%A8%E6%84%8F h_01KNM00RR86C5VKBVTA9X6QRAS=%E6%B3%A8%E6%84%8F-1 h_01KNM00RR8BCJTMPZ29C841BY1=step-2-set-inapp-event-postbacks h_01KNM00RR8PSJ7FEAP7MMEJ1XG=%E6%B3%A8%E6%84%8F-2 h_01KNM00RR89XJ0BZKFDXVC4860=%E6%B3%A8%E6%84%8F-3 set-up-a-web-conversion-campaign-in-google-ads=google-ads%E3%81%A7%E3%81%AEweb%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KNM00RR8SAS3TM1NG5DC58TF=google-ads%E3%81%A7%E3%81%AEweb%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KNM00RR8S24AG7FMN6067PZ2=step-1-set-the-campaign-type-objective-and-goals h_01KNM00RR8H1ZFSHFT0DVB11GN=step-2-create-conversion-actions h_01KNM00RR8EV8XY02YJFV5XSX8=%E9%87%8D%E8%A6%81 h_01KNM00RR8N96SNP1YK0CTN6YZ=%E6%B3%A8%E6%84%8F-4 h_01KNM00RR82NZSKB7K06HCP1VE=step-3-set-the-campaigns-final-url h_01KNM00RR8EP6J43G29Q8VVA5B=%E9%87%8D%E8%A6%81-1 h_01KNM00RR8A704MKGVVC6MQ2KN=%E6%B3%A8%E6%84%8F-5 view-web-attribution-data=web-performance-measurement%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D h_01KNM00RR8EYJAX2KRGCM65E9M=web-performance-measurement%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D h_01KNM00RR86Q2GTHVNC505KCXZ=%E6%B3%A8%E6%84%8F-6 measure-web-attribution-data-with-web-cost=web%E3%82%B3%E3%82%B9%E3%83%88%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%9Fweb-performance-measurement%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E5%88%86%E6%9E%90 h_01KNM00RR9TF8JRTJXWN23MF1S=web%E3%82%B3%E3%82%B9%E3%83%88%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%9Fweb-performance-measurement%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E5%88%86%E6%9E%90 troubleshooting-in-app-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01KNM00RR9Z0BM5EE62M17EE0F=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01KNM00RR9CJJQAP4GAXZ9KK8N=set-token-permissions h_01KNM00RR9215H3KB024BBFZX2=mcc-customer-id h_01KNM00RR9DBR5979GA0FVD5AK=conversion-action-id traits-and-limitations=%E6%A9%9F%E8%83%BD%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KQAE3JKMQ6ZEATDAEXBC4PT6=%E6%A9%9F%E8%83%BD%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
