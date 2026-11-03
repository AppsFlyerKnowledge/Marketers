---
title: AppLovinキャンペーン設定
metadata:
  keywords:
    - Applovin
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-06T12:20:32Z'
  edited_at: '2026-10-14T09:37:06Z'
  id: 208335613
  locale: ja
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ja/articles/208335613
---
> **概要：** AppsFlyerの連携パートナーであるAppLovinは、モバイルアプリのトラフィックのための有名なアドネットワークです。AppLovinは、クリックベースのモバイルアトリビューションに加えて、コスト、広告収益、ビュースルーアトリビューションも提供しており、AppsFlyerで計測することができます。

## AppLovinの連携設定

**前提条件：** 連携を設定する前に、 <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>し、アカウントを開設してください。

**連携を有効化または編集する：**

1. **有効化するには：** AppsFlyer管理画面 左メニュー **連携** > **Partner Marketplace**へ移動します。  
   **編集方法：** AppsFlyer管理画面左メニュー **連携** > **連携済みパートナー**を選択します。
2. パートナーを検索し選択してください。
3. **連携の設定**をクリックします。連携の設定ページに移動します。
4. **連携**タブにて連携したいアプリを選択し、 **パートナーを有効にする**をオンにしてください。  
   **注：** パートナーと作業している間、トグルはオン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>のままにしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

AppLovinの設定画面には5つのタブがあります：連携、計測リンク、コスト、広告収益、および権限。次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="連携タブ">

### パートナーの有効化

このタブを**初めて**開く場合、連携タブのパラメーター設定を有効にするために**パートナーを有効にする**のトグルをオンにする必要があります。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーのライセンス認証の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をクリックしてください。

> 📘 **注意**
>
> 全てのインストールデータを受信できるネットワークであるAppLovinは、オーガニックを含む全てのメディアソースに紐づく新規インストールのポストバック受信を希望しています。オーガニックを含む全メディアソース を選択し、全てのインストールポストバックをYouAppiに送信することを推奨します。

### 一般的な設定

**オーガニック / 非オーガニックシグナルの共有**

このトグルがオンの場合、オーガニックを含むすべてのメディアソースに対してインストールポストバックが送信されると、AppLovinはインストールがオーガニックか非オーガニックかを示す情報を受け取ります。

**SDKキー**

AppLovinは、独自のsdk\_keyを介してAppsFlyerと接続します。sdk\_keyをまだお持ちでない場合は、AppLovinから取得し、連携を続行する必要があります。

**ビュースルー計測の有効化**

AppLovinでビュースルーインストールを計測したい場合は、このトグルをオンにしてください。ビュースルールックバック期間は、計測リンクタブ（下記参照）にて設定できます。

### デフォルトのポストバック

ユーザーのインストールおよびリエンゲージメント後に、自動でポストバックを送信します。このセクションでは、これらのポストバックの**送信を許可するユーザー**を定義してください。

AppLovinに紐づくユーザーからのイベントのみにするには、**このパートナーに紐づくイベントのみ**を選択します。  
**オーガニックを含む全メディアソース**を選択して、ユーザーベース全てをAppLovinにレポートできるようにします。

### アプリ内イベントの設定

このセクションでは、ポストバックでAppLovinに送信するAppsFlyerのイベントをマッピングできます。

1. ここでもう一度AppLovinのsdk\_keyを設定してください。
2. アプリ内イベントのポストバックのトグルをONにします。
3. SDK に定義済みの全てのイベントに対して、送信オプションを選択してください。  
   **- このパートナーに紐づけられたイベントのみ**：このパートナーに紐づけられたユーザー**のみ**から発生したイベント  
   **- いずれかのパートナーまたはオーガニックに紐づけられたイベント**：ユーザーベース全体をパートナーに報告できるようにする場合に選択
4. **イベントを追加**をクリックして、SDKイベントをリストに追加してください。
5. 次のパラメータを設定します。

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリと連携済みのSDKから、またはサーバー間（S2S）イベントからAppsFlyerが受信したイベント名  <br />**ヒント** - アプリ内イベント名がリストに表示されない場合、デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認してください。 |
| **パートナー側のイベント名** | AppLovin側で定義された各イベントの一意の名前またはID。  <br />AppLovinから対応するイベント名を取得し、テキスト項目に設定します。 |
| **収益値を送信** | **チェックなしの場合** - リッチアプリ内イベントのすべてのパラメーターをパートナーに送りますが、**af\_revenue**パラメーターに含まれる収益パラメーターは送信しません。  <br />**チェックありの場合：** 収益値（イベントに存在する場合）を含むすべてのパラメーターをパートナーに送ります。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

計測リンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UA およびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。シングルプラットフォームリンクまたはOneLinkのいずれかを使用できます。  
<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">計測リンクの構造とパラメーターについての詳細はこちら</Anchor>

**計測リンクを作成**するには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">次の手順</Anchor>に従ってください。  
参照：Applovin - クリックとビューの定義詳細

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

AppsFlyerはコストの詳細をAPIで取得します。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークのコスト連携に関する表</Anchor>を参照してください。　**注意**：コストデータの取得にはROI360のご契約が必要です。

**コストAPIを有効にする方法**：

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータス</Anchor>と一致するコストデータを引き出すことができた最後の時刻を、AppsFlyerがコスト（および広告収益）連携ステータス管理画面、または個別のアドネットワーク管理画面のいずれかで確認してください。

> 🚧 **Applovinの請求可能コスト**
>
> 2024年8月1日現在、Applovinは確率的インストールに基づいてすべての顧客に請求しています。この日以前は、SKANのインストールに基づいて請求される顧客もいました。<Anchor target="_blank" href="https://support.applovin.com/hc/en-us/articles/28531589437965-iOS-Billing-Method">詳細はApplovinのドキュメントを参照してください。</Anchor>
>
> AppsFlyerとAppLovinのコスト連携は、この請求可能なコストを正確に反映します。AppsFlyerのコストがAppLovinプラットフォームのコストと正しく一致することを意味します。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

* Applovinは、広告収益メディエーションに集計データを提供します。
* <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution">広告収益アトリビューション</Anchor>（広告収益）について

**広告収益APIを有効にする方法**：

* <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">これらの連携手順</Anchor>に従ってください。

> 📘 **注意**
>
> * Applovinは、自社で生み出した広告収益を配信します。
> * ironSourceやUnityなどのメディエーションパートナーからの広告収入は、Applovinのダッシュボードに表示されることがありますが、AppsFlyerには送信されません。AppsFlyerのダッシュボードで他のメディエーションパートナーが広告収入データを直接AppsFlyerに送信できるようにする。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このタブでは、AppLovinに許可する権限を選択することができます。AppLovinのアトリビューションが無効になっていても、パーミッションタブはアクティブであり、AppLovinにコントロールを与えることができることに注意してください。

### アドネットワークへの権限付与

これらのトグルを使用して、アプリごとにアドネットワークへの権限付与を設定してください：

* **パートナー連携の設定を許可する** - パートナーに連携タブの設定（アプリ内イベントのポストバックを除く）を許可します。
* **アプリ内イベントのポストバック設定を許可する** - 連携タブでアプリ内イベントのポストバックをマッピングする設定をパートナーに許可します。
* **リテンションレポートへのアクセスを許可** - パートナーのリテンションデータへのアクセスを許可します。
* **リテンションレポートへのアクセスを許可する**  - このパートナー経由のロイヤルユーザーデータのみへアクセスを許可します。
* **アプリ内イベント集計データへのアクセスを許可する** - このパートナー経由のアプリ内イベントデータのみへアクセスを許可します。
* **収益集計データへのアクセス権限を許可する**‐ このパートナーに紐づく収益データのみへアクセスを許可します。
* **Protect360管理画面へのアクセスを許可する** - 広告主がProtect360機能を利用している場合、パートナーのProtect360データへアクセスを許可します。

詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークへの権限付与</Anchor>をご覧ください。

</Accordion>

<div data-zendesk-anchors="setting-up-applovin=applovin%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HKW93TKBNYVC05MA5GB37JVH=applovin%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HKW93TKBXS56A4RZQ0DYWQAC=%E3%83%92%E3%83%B3%E3%83%88 h_01HKW93TKCPCFYD6HV2XH1QTHS=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW93TKCG5JCQK52QJ65483M=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW93TKC2XGTZ7WAQ2E2AGPD=%E6%B3%A8%E6%84%8F general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01HKW93TKCZCK6GB7M4VV5C1NB=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HKW93TKCCRB21JAFDA2GWH6F=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW93TKCVWKTM9C8J220Q41E=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW93TKCCXVQMBCGW02J7JK4=attribution-link-tab h_01HKW93TKCXMG7BHMEWRFSCM6N=cost-tab h_01J43V7Z67C98TG7CE2QQGVVWE=applovin%E3%81%AE%E8%AB%8B%E6%B1%82%E5%8F%AF%E8%83%BD%E3%82%B3%E3%82%B9%E3%83%88 h_01HKW93TKDDWXA2C7456E8Q8GG=ad-revenue-tab h_01HKW93TKD8Z0QQADBJWMBP962=%E6%B3%A8%E6%84%8F-1 h_01HKW93TKDBCXNA68YVMQVBVP0=permissions-tab ad-network-permissions=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E h_01HKW93TKD21RF42KMNA9J9WXF=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E" />
