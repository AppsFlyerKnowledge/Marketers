---
title: Meta広告｜連携設定
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Facebook
    - App Install
    - View-Through
    - integrated partner
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2013-01-24T20:13:58Z'
  edited_at: '2026-10-28T09:16:51Z'
  id: 207033826
  locale: ja
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ja/articles/207033826
---
> **概要：** Meta広告とAppsFlyerの連携について説明します。

<div id="meta-ads-setup-guide" />

## Meta広告の設定ガイド

AppsFlyerでMeta広告のモバイルアプリ広告のアトリビューションを開始するには、どのくらいかかるでしょうか。

すでに<Anchor target="_blank" href="/marketers/ja/docs/integrate-the-appsflyer-sdk">アプリにAppsFlyer SDKを実装</Anchor>し、Meta広告でもアプリを登録済みであれば、1分もかかりません。

モバイルアプリのアトリビューションのために、FacebookログインやFacebook SDKをアプリに実装する必要はありません。以下の[基本設定の手順](#meta広告アトリビューションの基本設定)に従ってください。その後、Meta広告の[詳細な設定オプション](#meta広告アトリビューションの詳細設定)も確認してください。

<div id="basic-meta-ads-attribution-setup" />

## Meta広告アトリビューションの基本設定

<div id="create-and-retreive-facebook-app-id" />

<Accordion title="FacebookアプリIDの作成と取得">

Meta広告とAppsFlyerを連携するには、まず<Anchor target="_blank" href="https://developers.facebook.com/docs/apps/register">FacebookアプリID</Anchor>を作成し、取得します。

**FacebookアプリIDの作成手順**：

1. **Meta広告**の<Anchor target="_blank" href="https://developers.facebook.com/apps">アプリダッシュボード</Anchor>に移動します。
2. <strong>［アプリ］</strong>で、<strong>［新しいアプリを作成］</strong>をクリックします。
3. アプリ名を入力し、一意の名前空間を指定します。アプリの正しいプラットフォームを必ず追加してください。正しく設定されていないと、インストールが適切にアトリビューションされない可能性があります。

**FacebookアプリIDの取得手順**：

1. **Meta広告**の<Anchor target="_blank" href="https://developers.facebook.com/apps">アプリダッシュボード</Anchor>に移動します。
2. 対象のアプリをクリックします。
3. 画面左上のアプリIDをクリックしてコピーします。

   [![](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)

AppsFlyerは、アプリIDごとにデータをアトリビューションします。同じFacebookアプリIDを、[AndroidアプリとiOSアプリの両方](https://developers.facebook.com/docs/app-ads/app-setup/)に使用できます。 iOS 14以降では、Meta広告の広告アカウント数は、アプリごとに9アカウントまでに制限されています。

</Accordion>

<div id="enable-meta-ads-device-level-data" />

<Accordion title="Meta広告のデバイスレベルのデータの有効化">

Metaは、2025年6月17日から<strong>Advanced Mobile Measurement（AMM）</strong>のレポート提供を再開しています。利用に同意すると、以下を利用できます。

* デバイスレベルのモバイル分析
* Metaキャンペーンのイベントレベルのアトリビューション指標
* 既存のAppsFlyerダッシュボードとエクスポートへの完全な連携

**AMMを有効にするには、以下の手順に従ってください。**

1. <Anchor target="_blank" href="https://business.facebook.com/business/loginpage/?next=https%3A%2F%2Fdevelopers.facebook.com%2Fadvanced_mobile_measurement%2Fterms">Meta広告</Anchor>にアクセスします。
2. 対象のアプリIDを選択します（複数選択可）。
3. MetaのAdvanced Mobile Measurement利用規約に同意します。

<div id="important" />

> 🚧 **重要！**
>
> * MetaのAMM利用規約への同意は、Meta開発者アプリの管理者が行う必要があります。
> * アトリビューション情報をすべて確認できるデバイスレベルのデータは、AMM利用規約への同意後、新たにアトリビューションされたデバイスについてのみ利用できます。
> * アプリ内イベントは、紐づくコンバージョンの制限状況を引き継ぎます。具体的には、以下のとおりです。
>   * Advanced Mobile Measurement（AMM）への同意前に発生したコンバージョンにアプリ内イベントが紐づく場合、そのイベントには引き続き制限が適用されます。
>   * AMMへの同意後に発生したコンバージョンにアプリ内イベントが紐づく場合、そのイベントはローデータレポートで利用できます。

</Accordion>

<div id="set-the-meta-ads-active-integration" />

<Accordion title="Meta広告の連携設定">

1. AppsFlyerで、<strong>［連携］>［パートナー連携］>［マーケットプレイス］</strong>タブに移動します。
2. Meta広告を検索し、選択します。
3. <strong>［連携する］</strong>をクリックします。連携設定ページが表示されます。
4. <strong>［連携］</strong>タブで、<strong>［パートナーを有効にする］</strong>をオンにします。  
   **注意：** このパートナーとの連携を継続する間は、トグルをオン（<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">有効</Anchor>）のままにしてください。
5. <strong>［一般設定］</strong>で、以下を行います。

   [![](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)

   * <strong>［FacebookアプリID］</strong>欄に、[FacebookアプリID](#create-and-retreive-facebook-app-id)を貼り付けます。
   * インストールリファラの[復号キーをMeta広告から取得](/docs/meta-ads-integration-setup#google-play-referrer-apiまたはmetaインストールリファラの暗号化データ)し、貼り付けます。
6. <strong>［拡張データ共有］をオンまたはオフにします。</strong>後述の[拡張データ共有](#advanced_data_sharing)を参照してください。 （2024年10月14日までに、すべてのアカウントへ順次提供。）
7. <strong>［詳細マッチングデータの共有］をオンまたはオフにします。</strong>後述の[詳細マッチングデータの共有](#advanced_matching_data_sharing)を参照してください。
8. <strong>［連携を保存］</strong>をクリックします。

</Accordion>

<div id="optional--configure-recommended-settings" />

<Accordion title="［任意］推奨設定">

[![](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)

* Meta広告のクリックスルールックバック期間に合わせて、7日間に設定します。  
  （[一部のケースではデフォルト値が異なります](https://www.facebook.com/business/help/395050428485124?id=428636648170202)。）
* Meta広告のビュースルールックバック期間に合わせて、1日に設定します。
* 新しい連携では、デフォルトで<strong>［再インストールアトリビューション］</strong>がオンになっています。再インストールアトリビューションでは、リアトリビューション期間中にアプリを再インストールしたユーザーを計測できます。インストールアトリビューション設定の値を使用するため、ルックバック期間を別途設定する必要はありません。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls">再インストールの計測</Anchor>を参照してください。

</Accordion>

<div id="advanced-meta-ads-attribution-setup" />

## Meta広告アトリビューションの詳細設定

Meta広告アトリビューションの基本設定が完了したら、続いて詳細設定を行います。

<div id="getting-userlevel-data-for-android-installs" />

<Accordion title="Androidインストールのデバイスレベルのデータの取得">

#### Google Play Install Referrer API

Meta広告は、Google Playストアにユーザーを誘導するAndroidアプリ広告について、キャンペーンのメタデータを広告主と共有します。広告主は、Google Play Install Referrer APIを通じてアトリビューション項目を取得できます。このAPIは<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">アプリへの実装が必要です</Anchor>。 Google Play Install Referrer APIから取得した項目は、マッチタイプが`gp_referrer`としてAppsFlyerのローデータレポートに反映されます。これは、復号キーを登録し、インストールがMeta広告にアトリビューションされた場合にのみ利用できます。これにより、AppsFlyerは広告IDのないユーザー（LATが有効なユーザー）もアトリビューションできます。

<div id="meta-install-referrer" />

#### **Metaインストールリファラ**

<div id="note" />

> 📘 **注意**
>
> Metaインストールリファラを使用すると、AppsFlyerはデバイスのローカルストレージから広告キャンペーンのメタデータを取得できます。 SDKからMetaインストールリファラにアクセスできるようにする方法は、[Dev Hub](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer)を参照してください。

Google Play Install Referrer APIに加えて、Metaインストールリファラを使用することでも、AppsFlyerはデバイスのローカルストレージから広告キャンペーンのメタデータを取得できます。このデータは、アトリビューション計測に使用します。 Google Play Install Referrer APIとMetaインストールリファラの主な違いは、以下のとおりです。

* Metaインストールリファラにはインプレッションとクリックのデータを含められますが、Google Play Install Referrer APIはクリックデータに限られます。
* Metaインストールリファラには複数のセッションのデータが含まれる場合がありますが、Google Play Install Referrer APIは最後のセッションのデータに限られます（クリックが発生したセッションと同じセッション内で、アプリをインストールする必要があります）。

そのため、ローデータレポートでMeta広告にアトリビューションされるインストール数が増える場合があります。 Google Play Install Referrer APIまたはMetaインストールリファラでインストールがアトリビューションされると、そのデータはローデータレポートで利用できます。 Metaインストールリファラ経由で取得できるアトリビューション項目は、Facebookアプリ経由では`fb_referrer`、Instagramアプリ経由では`ig_referrer`のマッチタイプで、AppsFlyerのローデータレポートに反映されます。これは、復号キーを登録し、インストールがMeta広告にアトリビューションされた場合にのみ利用できます。 Metaインストールリファラの復号キーは、Google Playインストールリファラに使用するキーと同じです。AppsFlyerに再度登録する必要はありません。

<div id="campaign-attribution-fields-available-via-the-referrer" />

#### **リファラから取得できるキャンペーンのアトリビューション項目：**

* 広告ID
* 広告名
* 広告セットID
* 広告セット名
* キャンペーンID
* キャンペーン名
* アカウントID
* チャネル

<div id="note-1" />

> 📘 **注意**
>
> * **Google Play Install Referrer APIについて：**
>   * リファラデータを正しく引き渡すには、AppsFlyer SDKの**V5.4.0以降**が必要です。リファラデータはAPI経由のデータよりも優先され、制限の対象にはなりません。この方法は、クリックスルーアトリビューションに適用されます。ビュースルーアトリビューションには適用されません。
>   * Channelフィールドは、Google Play Referrer APIから受信したチャネルの値（MetaからGoogle Playに送信された値）に基づいて決まります。空文字列を受信した場合、Channelフィールドには「None」と表示されます。
>
> * **Metaインストールリファラについて：** お知らせに記載された<Anchor target="_blank" href="/marketers/ja/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">前提条件と必要な対応</Anchor>を参照してください。

<div id="meta-install-referrerfaq" />

#### Metaインストールリファラ｜よくある質問

**Metaインストールリファラは、どのような場合にアトリビューションに使用できますか？**

* インストールアトリビューションでは、以下に対応しています。
  * すべてのキャンペーンでのクリックスルーアトリビューション。
  * ビュースルーアトリビューションは、ブロードターゲティング（年齢と性別がデフォルト設定の場合など）を使用する、すべてのAdvantage+アプリキャンペーンと手動のアプリの宣伝キャンペーンでサポートされます。

* 対応ストア：Google Playストアと、Google Play以外のAndroidアプリストア。
* 対象外：ランディングページにリダイレクトするキャンペーンは含まれません。

**Meta広告の「ブロードターゲティング」とは何ですか？**

ビュースルーのインストールデータを受信するには、ブロードターゲティングが必要です。対応するキャンペーン設定は、以下のとおりです。

* 年齢：デフォルト設定（18歳～65歳以上）を適用します。
* 性別：デフォルト設定（すべての性別）を適用します。
* 地域：国グループおよび国単位の指定に対応しています。 **注意：** 市区町村や郵便番号など、より細かい地域を配信対象に指定する場合は、指定条件を厳密な制限としない設定にする必要があります。
* 詳細ターゲット設定：興味・関心、行動、詳細な利用者層について、指定条件を厳密な制限としない設定にします。
* カスタムオーディエンス：指定条件を厳密な制限としない設定にします。
* 指定条件を厳密な制限としない設定にするには、広告キャンペーンで［Advantage詳細ターゲット設定］のチェックボックスをオンにする必要があります。[![](https://files.readme.io/58ad1f360c324a4e53290f2aa6bc18e30efea0a08f37012342f2811bbb022c6a-30354145604369.png)](https://files.readme.io/58ad1f360c324a4e53290f2aa6bc18e30efea0a08f37012342f2811bbb022c6a-30354145604369.png)

<div id="encrypted-data-from-google-play-referrer-api-or-meta-install-referrer" />

#### Google Play Referrer APIまたはMetaインストールリファラの暗号化データ

Google Play Referrer APIとMetaインストールリファラのデータは、どちらもMetaによって暗号化されています。 Meta開発者アカウントで取得できるキーを使用して、このデータを復号できます。必要な対応の欄で説明する復号キーを、AppsFlyerに登録する必要があります。復号キーは、アプリごとに一度登録するだけで構いません。

キーを登録していない場合や削除した場合でも、前述のキャンペーンのアトリビューション項目がない状態で、リファラに基づいてインストールがMeta広告にアトリビューションされる場合があります。以下の条件を満たす場合に発生します。

* Meta広告がインストールのアトリビューションを申告していない。
* Google Play Install Referrer APIからデータを受信したが、復号していない。
* そのリファラが示すクリックが、最後のクリックである。

**Metaから復号キーを取得するには、以下の手順に従ってください。**

1. Metaの開発者ポータルにログインします。
2. 右上の<strong>［マイアプリ］</strong>に移動します。
3. 復号キーを取得するアプリを選択します。
4. ページ左側の<strong>［設定］</strong>><strong>［ベーシック］</strong>に移動します。 [![](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)
5. Androidセクションまでスクロールすると、［パッケージ名］欄の下に［Install Referrer decryption key］というラベルで復号キーが表示されます。注意：パッケージ名とGoogle Playストアを設定したセクションと同じ場所です。

**AppsFlyerで復号キーを設定するには、以下の手順に従ってください。**

1. ［必須］アプリにAppsFlyer SDK V5.4以降が実装されていることを確認します。それ以前のバージョンは使用しないでください。
2. AppsFlyerのサイドメニューから、**［連携］**><strong>［連携済みパートナー］</strong>を選択します。
3. <strong>［Meta広告］</strong>を選択します。 [![](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)
4. <strong>［連携］</strong>タブの<strong>［インストールリファラ復号キー］</strong>欄にキーを貼り付けます。この操作は、アプリごとに一度行うだけで構いません。
5. <strong>［連携を保存］</strong>をクリックします。

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="コスト、クリック、インプレッション">

[![meta_cost_tab.png](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)

この連携では、キャンペーン、広告セット、広告、地域・国別のコスト、クリック、インプレッションの集計データを取得できます。対応するディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークのコスト連携一覧</Anchor>を参照してください。

**注意：** クリックとインプレッションのデータは、この連携に含まれます。ただし、**コストデータには**<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview?query=xpend">**ROI360**</Anchor>**の契約が必要です**。

**Cost APIを有効にするには、以下の手順に従ってください**。

1. Meta広告のキャンペーンを管理できるユーザーアカウントにログインしていることを確認します。ログインするユーザーには、Metaビジネスマネージャのすべてのキャンペーンを運用する権限が必要です。
2. <strong>［コスト］</strong>タブに移動します。
3. <strong>［コスト、クリック、インプレッションのデータを取得］</strong>をオンにします。
4. <strong>［f login］</strong>ボタンをクリックします。 Meta広告のビジネスアカウントまたは管理者アカウントでログインできます。
5. アクセス許可を求められたら、AppsFlyerによるMeta広告のキャンペーンデータへのアクセスを許可します。  
   **注意**：連携後の初回同期と、それ以降の同期では、AppsFlyerは最大7日前までさかのぼってMeta広告のコストデータを取得します。

**接続済みのMeta広告アカウントを削除するには：** 操作列で対象アカウントにカーソルを合わせ、<strong>［接続を削除］</strong>をクリックします。

<div id="notes" />

> 📘 **注意**
>
> * すでにMeta広告にログインしている場合、<strong>［f login］</strong>ボタンをクリックすると、ウィンドウが開いてすぐに閉じます。これは正常な動作です。
> * Meta広告への権限を持つユーザーが複数いる場合は、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-faq#why-doesnt-cost-data-include-data-from-all-campaigns">一部のデータが取得できない事態を避ける</Anchor>ため、全員がログインすることを推奨します。

<div id="cost-data-sync-status" />

#### コストデータの同期状況

コスト・広告収益の連携状況ダッシュボード、または個々のアドネットワークのダッシュボードで、<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">Cost APIのステータス</Anchor>と、AppsFlyerが対応するコストデータを最後に取得できた日時を確認できます。 

複数のアカウントを同期して、コストデータを取得できます。同期したアカウントごとに、コスト連携のステータスと、AppsFlyerが対応するコストデータを最後に取得できた日時が表示されます。

<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-faq#meta広告のコストに関するよくある質問">コスト、クリック、インプレッションのデータ</Anchor>を活用して分析データを充実させる方法については、こちらを参照してください。

</Accordion>

<div id="inapp-event-mapping" />

<Accordion title="アプリ内イベントのマッピング">

[![meta_iae_postbacks.png](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)

**アプリ内イベントをマッピングするには、以下の手順に従ってください。**

1. <strong>［アプリ内イベントポストバック］</strong>をオンにします。  
   アプリでMeta広告へのアプリ内イベントのマッピングを**初めて**有効にすると、**af\_app\_open**が自動的に**fb\_mobile\_activate\_app**にマッピングされます。
2. 以下の項目を設定します。

| パラメータ名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | アプリに実装されたSDK、またはサーバー間イベントからAppsFlyerが受信したイベント名です。<br />**ヒント**：目的のイベントが表示されない場合は、以下を試してください。<ul><li>非オーガニックインストールのデバイスでイベントを発生させ、再度確認します。</li><li><strong>［AppsFlyerイベント］</strong>にイベント名を入力し、<strong>［カスタムイベントを作成］</strong>をクリックします。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントのマッピング</Anchor>を参照してください。</li></ul> |
| **マッピング先のパートナーイベント** | Meta広告側で定義されている、各イベントの一意の名前またはIDです。以下の方法でマッピングできます。<ul><li>**テキスト欄：** 対応するイベントIDをMeta広告から取得します。</li><li>**ドロップダウン：** 最適なAppsFlyerの定義済みイベントを選択します。</li><li>**そのまま送信**：名前をマッピングせず、イベントをそのまま送信します。</li></ul> |
| **送信対象ユーザー** | イベントの送信対象を選択します。<ul><li>**このパートナーのみ**：このイベントがMeta広告にアトリビューションされた場合にのみ、ポストバックを送信します。</li><li>**オーガニックを含むすべてのメディアソース**：いずれかのパートナーにアトリビューションされたイベントと、オーガニックのイベントについてポストバックを送信します。</li></ul> |
| **送信データ** | <ul><li>**データなし（デフォルト）**：イベント値を含めず、イベント自体のみを送信します。</li><li>**イベント値と収益**：収益値がイベントに含まれる場合、その収益値も**含めて**、すべてのイベントパラメータを送信します。</li><li>**収益を除くイベント値**：収益値を**除く**、すべてのパラメータを送信します。</li></ul> |

3. SDKまたはサーバー間のイベントをリストに追加するには、<strong>［イベントを追加］</strong>をクリックします。

**イベント名の制限事項：**

* イベント名の長さ：2～40文字。
* 以下の文字は使用できません。
  * コロン（:）
  * ピリオド（.）
  * ラテン文字（英字）以外の文字：2020年1月12日時点で、Meta広告は中国語の文字を拒否します。 AppsFlyerでは他の文字種をテストしていません。使用する場合は、ポストバックでの対応可否をMeta広告に確認してください。
* イベント名は大文字と小文字を区別します。乖離を避けるため、すべてのメディアソースとアプリバージョンで、イベント名の大文字と小文字を正しく使い分けてください。

<div id="note-2" />

> 📘 **注意**
>
> Meta広告は、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-in-app-event-mapping#キャンペーン最適化のための広告収益データのマッピング">af\_ad\_revenueイベントを適切なMeta広告イベントにマッピングする</Anchor>ことで、広告収益データに基づいてキャンペーンを最適化できます。

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="リターゲティングアトリビューション">

AppsFlyerのMeta広告向けリターゲティングアトリビューションでは、既存ユーザーとFacebook広告とのエンゲージメントをアトリビューションし、その後のユーザーの質をAppsFlyerのレポートで評価できます。 Facebookで自社の既存ユーザーを対象とするキャンペーンを実際に運用している場合にのみ使用してください。

1. <Anchor target="_blank" href="/marketers/ja/docs/app-settings#reengagement-attribution">［アプリ設定］ページでリターゲティングをオンにします</Anchor>。
2. Meta広告のパートナーページで、<strong>［リエンゲージメントアトリビューション］</strong>をオンにします。
3. **リエンゲージメントのクリックスルールックバック期間**を設定します。  
   リエンゲージメントのルックバック期間とは、広告クリックから、リエンゲージメントとして記録するためのアプリ起動までに許容される期間です。  
   ルックバック期間の単位（時間または日）を選択し、スライダーで値を設定します。  
   [![](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)
4. <strong>［リエンゲージメントのビュースルーアトリビューション］</strong>を有効にします。
5. **リエンゲージメントのビュースルールックバック期間**のスライダーを、希望する値に設定します（最大24時間）。これは、広告の表示から、リエンゲージメントとして記録するためのアプリ起動までに許容される期間です。[![](https://files.readme.io/82028408b7475e6ad5bcd35f2d597b7f5344b9eca432157559265cf73bdb952c-30354145625873.png)](https://files.readme.io/82028408b7475e6ad5bcd35f2d597b7f5344b9eca432157559265cf73bdb952c-30354145625873.png)
6. **リエンゲージメント期間**を設定します。  
   これは、ユーザーのアプリ内イベントが、リターゲティングのメディアソースをプライマリソースとしてアトリビューションされる期間です。  
   日単位（1～90日）、時間単位（最大23時間）、またはライフタイムに設定できます。デフォルトは30日間です。  
   [![](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)

詳細は、<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">AppsFlyerのリターゲティングアトリビューション</Anchor>を参照してください。

<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#srnとのディープリンク">Meta広告などのSRNからのディープリンク</Anchor>についても参照してください。

<div id="whatsapp-retargeting-campaign-attribution" />

#### WhatsAppリターゲティングキャンペーンのアトリビューション

AppsFlyerは、iOSとAndroidの両方で、リエンゲージメントを目的としたWhatsApp Marketingメッセージキャンペーンを、ディープリンクアトリビューションで計測できます。

**連携単位**と**アプリ単位**の両方で**リエンゲージメント**が有効になっていれば、追加設定なしで、これらのキャンペーンが自動的に計測されます。

これらのキャンペーンでは、アトリビューションデータの**channel**フィールドに<strong>「WhatsApp」</strong>が表示されます。

</Accordion>

<div id="advanced_data_sharing" />

<Accordion title="拡張データ共有">

**拡張データ共有**がオンの場合、Metaは、広告ID（IDFA）を提供していないデバイスも含む、すべてのデバイスについて、デバイスレベルの識別子を含むポストバックとイベントを受信します。

また、**拡張データ共有**がオンの場合、AppsFlyerはこれらのイベントをアトリビューションします。オフの場合は、IDFAを取得できるデバイスのポストバックとイベントのみが送信され、アトリビューションされます。

この方法では、片方または両方でトラッキングをオプトアウトしているデバイスについて、iOSのクリックスルーおよびビュースルーインストールと、iOSのディープリンクによるリエンゲージメントをアトリビューションします。ラストタッチアトリビューションに基づき、アトリビューション期間の上限は24時間です。

<div id="note-3" />

> 📘 **注意**
>
> がオンになっているにもかかわらずMeta広告へのアトリビューションが発生しない場合は、共有しているイベントがMetaの利用要件を満たしているか確認してください。 <Anchor target="_blank" href="https://www.facebook.com/business/help/716239976391518?id=1877298665783613">Metaのドキュメント</Anchor>を参照してください。

</Accordion>

<div id="advanced_matching_data_sharing" />

<Accordion title="詳細マッチングデータの共有">

**詳細マッチングデータの共有**がオンの場合、AppsFlyerに送信されたイベント情報に、ハッシュ化したメールアドレス、電話番号、名、姓、FacebookログインIDなどの詳細マッチング用の項目が含まれていれば、それらがMetaと共有されます。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/advanced-matching-data-sharing">詳細マッチングデータの共有</Anchor>を参照してください。

</Accordion>

<div id="use-deep-links-in-meta-ads-campaigns" />

<Accordion title="Meta広告キャンペーンでのディープリンクの使用">

Meta広告キャンペーンでは、ディープリンクを使用して、特定のアプリ内ページや機能にユーザーを直接誘導できます。以下では、Meta広告でAppsFlyerのディープリンクを設定する方法を説明します。

キャンペーンの目的を選択する前に、アプリで以下のサポート対象のディープリンク（DL）形式のいずれかを使用していることを確認してください。

* AppsFlyer OneLink（アプリにユニバーサルリンクまたはAndroidのアプリリンクが実装されている場合）
* Appleのユニバーサルリンク
* Androidのアプリリンク
* カスタムURIスキーム
* Facebookのアプリリンク

以下の表では、Meta広告のキャンペーン目的ごとに、ダイレクトディープリンクとディファードディープリンク（DDL）の対応状況、設定手順、制限事項を説明します。

| キャンペーンの目的 | ダイレクトディープリンク | ディファードディープリンク（DDL） | 設定 | 制限事項と前提条件 |
| --- | --- | --- | --- | --- |
| アプリの宣伝／インストール | 対応 | 対応 | 広告レベルの<strong>［遷移先］</strong>セクションで、<strong>［ディファードディープリンク］</strong>欄にDDL URLを入力します。 | <ul><li>iOSでは、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-aggregate-event-measurement-aem-for-ios">AEMが有効なアプリ</Anchor>、またはMetaとアプリの両方でユーザーの同意を得ているアプリでのみ、DDLがサポートされます。</li><li>iOSとAndroidのどちらも、DDLにはFacebook SDKが必要です。</li></ul> |
| 売上 | 対応 | 非対応 | 広告セットレベルの<strong>［コンバージョン］</strong>で設定するか、カタログの設定を使用します。必要に応じて、カタログのディープリンクをWebサイトURLで上書きできます。 | <ul><li><strong>［インストールトラッキングを有効にする］</strong>がオンになっている必要があります。</li><li>遷移先はモバイルアプリである必要があります。</li></ul> |
| トラフィック | 対応 | 非対応 | 広告セットレベルの<strong>［コンバージョン］</strong>で設定します。 App StoreまたはWebサイトへのフォールバックに対応しています。 | <ul><li><strong>［インストールトラッキングを有効にする］</strong>がオンになっている必要があります。</li></ul> |
| 認知度 | 対応 | 非対応 | 広告レベルの<strong>［遷移先］</strong>セクションで設定します。 | <ul><li><strong>［インストールトラッキングを有効にする］</strong>がオンになっている必要があります。</li></ul> |
| リード | 対応 | 非対応 | 広告セットレベルの<strong>［コンバージョン］</strong>で設定します。 | <ul><li><strong>［インストールトラッキングを有効にする］</strong>がオンになっている必要があります。</li></ul> |

<div id="see-also" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLinkガイド</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLinkを使用したキャンペーン用ディープリンクとリダイレクトリンクの作成</Anchor>

</Accordion>

<div id="comply-with-california-consumer-privacy-act-ccpa" />

<Accordion title="カリフォルニア州消費者プライバシー法（CCPA）への対応">

CCPAのプライバシー規制に対応すると、米国カリフォルニア州のMeta広告ユーザーから取得するデータが制限されます。

<strong>CCPAに対応するには：［連携］</strong>タブで、<strong>［Meta広告によるユーザーの個人情報の利用を制限（CCPA）］</strong>をオンにします。

詳細は、<Anchor target="_blank" href="/marketers/ja/docs/send-opendsr-api-requests">データ保護法</Anchor>を参照してください。

</Accordion>

<div id="ad-revenue-recording" />

<Accordion title="広告収益の記録">

[![](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)

Meta Audience Networkで広告マネタイズを行っている場合、Meta広告からの収益をAppsFlyerに記録できます。アプリ内購入の収益データの有無にかかわらず、**ユーザーから得られる収益の全体像**を把握できます。

<div id="record-meta-audience-network-ad-revenue" />

#### Meta Audience Networkの広告収益の記録

1. <strong>［広告収益］</strong>タブで、<strong>［広告収益データを取得］</strong>をオンにします。
2. 取得する広告収益の集計データの種類として、**［アトリビューション済み収益］**、<strong>［マネタイズ収益の集計］</strong>のいずれか、または両方を選択します。
   * **アトリビューション済み収益**：ユーザー獲得の流入元に基づく収益です。  
     広告収益モデルを最も適切に表すイベントを、<strong>［イベントソース］</strong>に設定します。たとえば、インプレッションに基づいて収益が発生する場合は、ad\_viewedイベントをAppsFlyerに送信することを推奨します。マネタイズプラットフォームごとに、最適なイベントを個別に設定できます。ただし、`af_app_opened`イベントを使用することもできます。この場合、ユーザーによるアプリ起動ごとに広告収益がアトリビューションされます。
   * **マネタイズ収益の集計**：広告の配信元に基づく収益です。
3. <strong>［広告収益イベント］</strong>が表示されます。これは読み取り専用の項目で、[source event]\_monetizedという新しい広告収益イベントが表示されます（上の画像のAd\_Watched\_Monetizedなど）。広告収益イベントは、ダッシュボードに追加のイベントとして表示されます。
4. <strong>［Meta広告に接続］</strong>をクリックし、Meta広告側でMeta Audience Networkの広告収益データの収集を有効にします。 Meta広告の認証情報でログインし、Meta Audience Networkの広告収益へのアクセスを許可します。
5. **Audience NetworkアプリID（**[**FacebookアプリID**](/docs/meta-ads-integration-setup#facebook-app-id)）を入力します。このIDは、Meta Audience Networkで取得します。
   * [FacebookアプリID](/docs/meta-ads-integration-setup#facebook-app-id)を取得します。
   * 取得したIDを、AppsFlyerの<strong>［Audience NetworkアプリID］</strong>欄にコピーします。
6. <strong>［広告収益を保存］</strong>をクリックします。

</Accordion>

<div id="permissions" />

<Accordion title="権限">

利用可能な権限に応じて、Meta広告による各種操作とデータへのアクセスを許可します。

詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">連携済みパートナーへの権限付与</Anchor>を参照してください。

</Accordion>

<div id="aggregate-event-measurement-aem-for-ios" />

## iOSの合算イベント測定（AEM）

AppsFlyerは、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-aggregate-event-measurement-aem-for-ios">Meta広告の合算イベント測定（AEM）</Anchor>に対応しています。このソリューションは、iOSのコンバージョンやアプリ内イベントの最適化と、Meta広告でのiOSのリエンゲージメント計測に役立ちます。

<div id="meta-ads-integration-troubleshooting" />

## Meta広告連携のトラブルシューティング

基本連携が完了してもAppsFlyerのダッシュボードにMeta広告の成果が表示されない場合は、まず、連携後にMeta広告から新しいインストールが発生していることを確認してください。

発生している場合は、以下の主な原因と解決方法を確認してください。

<div id="no-idfa-collection" />

<Accordion title="IDFAが収集されていない">

iOSのSDK実装ガイドに記載されているとおり、IDFAを収集するには、プロジェクトにAdSupport.frameworkを追加する必要があります。インストールのローデータレポートで、IDFA列が空欄になっていないか確認してください。 iOSアプリではIDFA、AndroidアプリではGAIDを収集できるようにすることを推奨します。  
iOS 14.5以降では、IDFAを収集する前に、AppleのATTプロンプトを表示してユーザーの同意を得る必要があります。

**注意：** SKAdNetworkのアトリビューションは、IDFAを取得できるかどうかに影響されません。ただし、iOS 14のキャンペーンを設定する際は、Meta広告で［iOS 14キャンペーン］を必ずオンにしてください。

</Accordion>

<div id="wrong-facebook-app-id" />

<Accordion title="FacebookアプリIDが正しくない">

AppsFlyerでFacebookアプリIDが誤って設定されています。  
アプリIDが正しく、Meta広告のダッシュボードの値と一致していることを確認してください。  

注意：<Anchor target="_blank" href="https://developers.facebook.com/tools/explorer/?method=GET&path=&version=v6.0">FacebookのGraph API</Anchor>を使用して、FacebookアプリIDを検証することもできます。

</Accordion>

<div id="app-status-on-meta-ads" />

<Accordion title="Meta広告でのアプリの公開状態">

アトリビューションを行うには、Meta広告でアプリが<strong>［開発中］</strong>ではなく、<strong>［公開］</strong>に設定されている必要があります。

[![](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)

</Accordion>

<div id="wrong-type-of-meta-ads-campaign" />

<Accordion title="Meta広告キャンペーンの種類が正しくない">

Meta広告キャンペーンが、**モバイルアプリインストール広告**または**モバイルアプリエンゲージメント**を目的としていることを確認してください。他の目的のキャンペーンでモバイルアプリのインストールを計測するには、Meta広告のキャンペーン設定時に<Anchor target="_blank" href="/marketers/ja/docs/attributing-app-installs-to-non-mobile-ads-from-meta-ads"><strong>［アプリイベントの記録］</strong>をオンにする</Anchor>必要があります。

<div id="aem-attribution-is-not-working" />

<Accordion title="AEMによるアトリビューションが機能しない">

<strong>［拡張データ共有］</strong>がオンになっているにもかかわらずMeta広告へのアトリビューションが発生しない場合は、共有しているイベントがMetaの利用要件を満たしているか確認してください。 [Metaのドキュメント](https://www.facebook.com/business/help/716239976391518?id=1877298665783613)を参照してください。

</Accordion>

</Accordion>

<div id="meta-ads-app-install" />

<Accordion title="Meta広告のアプリインストール設定">

Meta広告のアプリインストールキャンペーンの設定では、ドロップダウンリストからアプリを選択する方法と、アプリのストアURL全体を貼り付ける方法があります。どちらもMeta広告側では機能しますが、後者ではAppsFlyerのアトリビューションが機能しません。

正しい設定：アトリビューションが機能します。

[![](https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png)](https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png)

誤った設定：アトリビューションが機能しません。

[![](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)

</Accordion>

<div id="ios-14-updates-relating-to-meta-ads" />

### Meta広告に関連するiOS 14の更新

AppsFlyerとMeta広告のMMP連携では、常に*Advertiser Tracking Enabled*フラグを実装しています。そのため、AppsFlyer側での追加対応は不要です。この情報は、2021年2月付のMeta広告のアプリ向けiOS 14チェックリストに基づいています。

<div id="see-also-1" />

> 📄 **関連情報**
>
> * iOS 14に関する注意事項は、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-interoperation-with-meta-ads">Meta広告とのSKAN連携</Anchor>を参照してください。
> * <Anchor target="_blank" href="/marketers/ja/docs/configuring-meta-campaign-management-partners">Metaキャンペーン管理パートナーの設定</Anchor>（<Anchor target="_blank" href="/marketers/ja/docs/bidalgo-meta-campaign-management-partner-configuration">Bidalgo</Anchor>／<Anchor target="_blank" href="/marketers/ja/docs/kenshoo-meta-campaign-management-partner-configuration">Kenshoo</Anchor>／<Anchor target="_blank" href="/marketers/ja/docs/adquant-meta-campaign-management-partner-configuration">Adquant</Anchor>／<Anchor target="_blank" href="/marketers/ja/docs/webpals-mobile-meta-campaign-management-partner-configuration">Webpals</Anchor>）

<div data-zendesk-anchors="facebook-ads-setup-guide=meta%E5%BA%83%E5%91%8A%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%AC%E3%82%A4%E3%83%89 01H7YJVNMSZ4WG4HWBZF648HZN=meta%E5%BA%83%E5%91%8A%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%AC%E3%82%A4%E3%83%89 basic-facebook-attribution-setup=meta%E5%BA%83%E5%91%8A%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%9F%BA%E6%9C%AC%E8%A8%AD%E5%AE%9A 01H7YJVNMTFW076FAJZGJWT4R9=meta%E5%BA%83%E5%91%8A%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%9F%BA%E6%9C%AC%E8%A8%AD%E5%AE%9A h_01JXYJW7AFB53PY7WHGM05HDMH=create-and-retreive-facebook-app-id h_01JKX03GC8ZSMGCSX84381QW0A=enable-meta-ads-device-level-data h_01JYPKG2RH3R08604V7B3NC5WQ=%E9%87%8D%E8%A6%81 h_01JXYHEFW19DJXXXRNN186E07B=set-the-meta-ads-active-integration %5Boptional%5D-configure-recommended-settings=optional--configure-recommended-settings h_01JXYHEFW15E6K39JY2VBCN79E=optional--configure-recommended-settings advanced-facebook-attribution-setup=meta%E5%BA%83%E5%91%8A%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E8%A9%B3%E7%B4%B0%E8%A8%AD%E5%AE%9A 01H7YJVNMTHF800PD5CEWPFS49=meta%E5%BA%83%E5%91%8A%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E8%A9%B3%E7%B4%B0%E8%A8%AD%E5%AE%9A h_01JKX03GC8B4VKC6KJT4CZ9VT8=getting-userlevel-data-for-android-installs h_01JKX2BE00WYHMJ3RX1FK8DQV5=google-play-install-referrer-api meta-install-referrer=meta%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9 h_01JKX2BNRDHHNJCN257H3QBZ65=meta%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9 h_01JKX03GC8JRZSD13TVDDM1MWE=%E6%B3%A8%E6%84%8F campaign-attribution-fields-available-via-the-referrer=%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9%E3%81%8B%E3%82%89%E5%8F%96%E5%BE%97%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E9%A0%85%E7%9B%AE h_01JKX2CF8RE4T5R3V83FS1PBQR=%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9%E3%81%8B%E3%82%89%E5%8F%96%E5%BE%97%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E9%A0%85%E7%9B%AE h_01JKX03GC9BG4GFDKR7JHG31BQ=%E6%B3%A8%E6%84%8F-1 meta-install-referrer%E2%80%94faq=meta%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01JKX2DSY85X6570AHYKHM34KS=meta%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F encrypted-data-from-google-play-referrer-api-or-meta-install-referrer=google-play-referrer-api%E3%81%BE%E3%81%9F%E3%81%AFmeta%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9%E3%81%AE%E6%9A%97%E5%8F%B7%E5%8C%96%E3%83%87%E3%83%BC%E3%82%BF h_01JKX2E4A44QHKADG4S8ZM9KC5=google-play-referrer-api%E3%81%BE%E3%81%9F%E3%81%AFmeta%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9%E3%81%AE%E6%9A%97%E5%8F%B7%E5%8C%96%E3%83%87%E3%83%BC%E3%82%BF 01H7YJVNMTBN9RJ6Q7TJ1AJ0XX=cost-clicks-and-impressions 01H7YJVNMTGRBQG54DVMJDHDKS=%E6%B3%A8%E6%84%8F-2 cost-data-sync-status=%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%90%8C%E6%9C%9F%E7%8A%B6%E6%B3%81 01H7YJVNMTRQAYG7TY29AX4MZS=%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%90%8C%E6%9C%9F%E7%8A%B6%E6%B3%81 01H7YJVNMTNRREKWY96CK9JJKV=inapp-event-mapping 01H7YJVNMT2DRVR26F8CDDTWHP=%E6%B3%A8%E6%84%8F-3 01H7YJVNMV5AZ9G2KCKEFF1CSV=retargeting-attribution whatsapp-retargeting-campaign-attribution=whatsapp%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01KBZ2CAGX18ZZPXQGMPTEPSCP=whatsapp%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 01H7YJVNMVSA4Y33MW6Q8Y777Y=advanced_data_sharing 01JDH9Y65409Y5E162NWJA25E3=%E6%B3%A8%E6%84%8F-4 h_01KPK96J1G0BY3PPEBN9RB005V=use-deep-links-in-meta-ads-campaigns h_01KPK96J1GZE9ZHQB5NHFCVAG6=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1 h_01JKTYRMD70ZGN31FSQ7BXF1HB=comply-with-california-consumer-privacy-act-ccpa 01H7YJVNMVWRG10SZY1B33H5EA=ad-revenue-recording record-meta-audience-network-ad-revenue=meta-audience-network%E3%81%AE%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E8%A8%98%E9%8C%B2 01H7YJVNMV1TTHKMMX4TFB2BF3=meta-audience-network%E3%81%AE%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E8%A8%98%E9%8C%B2 01H7YJVNMVMW5BXWEP8BPX4D7E=permissions aggregate-event-measurement-aem-for-ios=ios%E3%81%AE%E5%90%88%E7%AE%97%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E6%B8%AC%E5%AE%9Aaem 01H7YJVNMVGFYMHE5FACTD9NS0=ios%E3%81%AE%E5%90%88%E7%AE%97%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E6%B8%AC%E5%AE%9Aaem meta-ads-integration-troubleshooting=meta%E5%BA%83%E5%91%8A%E9%80%A3%E6%90%BA%E3%81%AE%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 01H7YJVNMVCAQ6ETKBGCAM31B9=meta%E5%BA%83%E5%91%8A%E9%80%A3%E6%90%BA%E3%81%AE%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 01H7YJVNMV3YRF59RX87TJCT8D=no-idfa-collection 01H7YJVNMVHCYVWKDW5WWPX1A5=wrong-facebook-app-id 01H7YJVNMVE9QJAXQBD4P14C88=app-status-on-meta-ads 01H7YJVNMVBRVTT9HH7KM8P33B=wrong-type-of-meta-ads-campaign h_01JKTYRMD7YPGJRZXR4Y66BAHG=aem-attribution-is-not-working 01H7YJVNMV4G3VP40E6VFD7SJD=meta-ads-app-install ios-14-updates-relating-to-facebook=meta%E5%BA%83%E5%91%8A%E3%81%AB%E9%96%A2%E9%80%A3%E3%81%99%E3%82%8Bios-14%E3%81%AE%E6%9B%B4%E6%96%B0 01H7YJVNMVQP5PR6XDHTCPXVDC=meta%E5%BA%83%E5%91%8A%E3%81%AB%E9%96%A2%E9%80%A3%E3%81%99%E3%82%8Bios-14%E3%81%AE%E6%9B%B4%E6%96%B0 h_01HDP0Y4CZBZEK5VZ6FG3T31JB=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1-1" />
