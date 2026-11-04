---
title: LINE 広告プラットフォームのキャンペーン設定
metadata:
  keywords:
    - Advertisers
    - LINE Ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-10T15:26:17Z'
  edited_at: '2026-10-14T09:38:29Z'
  id: 213050543
  locale: ja
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ja/articles/213050543
---
> **概要：** AppsFlyer の連携済みパートナーの一つである LINE 広告プラットフォームは、入札システムとカスタマイズされたターゲティングシステムを組み合わせています。LINE 広告プラットフォームでは、クリックベースのモバイルアトリビューションに加えて、リターゲティング計測も提供しており、AppsFlyer で記録することができます。

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/lap.png" width="71px" />

<div id="setting-up-line-ads-platform" />

## LINE 広告プラットフォームの設定

**前提条件：** 連携を設定する前に、 <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>し、アカウントを開設してください。

**連携を有効化または編集する：**

1. **有効化するには：** AppsFlyer管理画面 左メニュー **連携** > **Partner Marketplace**へ移動します。  
   **編集方法：** AppsFlyer管理画面左メニュー **連携** > **連携済みパートナー**を選択します。
2. パートナーを検索し選択してください。
3. **連携の設定**をクリックします。連携の設定ページに移動します。
4. **連携**タブにて連携したいアプリを選択し、 **パートナーを有効にする**をオンにしてください。  
   **注：** パートナーと作業している間、トグルはオン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>のままにしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

LINE 広告プラットフォームの設定ウィンドウには、次の2つのアクティブタブが表示されます：連携とアトリビューションリンク。次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="連携タブ">

連携タブは次のセクションに分かれています。

<div id="note-1" />

<div id="connect-multiple-accounts-and-apps" />

<div id="note" />

> 📘 **注**
>
> 全てのインストールデータを受信できるネットワークであるLINEは、オーガニックを含む全てのメディアソースに紐づく新規インストールのポストバック受信を希望しています。そのためには、**全てのパートナーに紐づくイベント**を選択して、全てのインストールポストバックをLINEに送信してください。これはアカウント管理者のみが実行できます。

<div id="activate-partner" />

### パートナーの有効化

この画面を**最初に開く**際には、以下のトグルをオンにする必要があります。[***パートナーを有効にする***] トグルをオンにして、連携タブのパラメーター設定を有効にします。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーの有効化についての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

<div id="general-settings" />

### 一般的な設定

**Account ID と App ID**

LINE 広告プラットフォームは、一意の LINE\_Ad\_account\_id と LINE\_Ad\_app\_ID を介して、AppsFlyer と連携します。

* **LINE\_Ad\_account\_id and LINE\_Ad\_app\_ID**を入力します。


<div id="example" />

> 📄 **例**
>
> ```http
> https://app.appsflyer.com/id123456789?pid=example_int;...<mark>line_ad_account_id=A123456789123&line_ad_app_id=1234567891234&</mark>...;redirect=false
> ```

<div id="default-postbacks" />

### デフォルトのポストバック

インストールとリエンゲージメントに対して、自動ポストバックをLINE広告プラットフォームに送信できます。このセクションでは、これらのポストバックの**送信を許可するユーザー**を定義してください。

LINE 広告プラットフォームに紐づくユーザーからのイベントのみを表示するには、**このパートナーに紐づくイベントのみ**を選択します。  
**オーガニックを含む、全メディアソース** を選択して、全てのユーザーベースをLINE広告プラットフォームに送信します。

<div id="in-app-events-settings" />

### アプリ内イベントの設定

このセクションでは、ポストバックを介して、AppsFlyerイベントをLINE広告プラットフォームにマッピングできます。

1. LINE\_Ad\_app\_ID と LINE\_Ad\_account\_id を再度入力します。
2. アプリ内イベントのポストバックのトグルをONにします。
3. SDK に定義済みの全てのイベントに対して、送信オプションを選択してください。  
   **- このパートナーに紐づけられたイベントのみ**：このパートナーに紐づけられたユーザー**のみ**から発生したイベント  
   **- いずれかのパートナーまたはオーガニックに紐づけられたイベント**：ユーザーベース全体をパートナーに報告できるようにする場合に選択
4. ドロップダウンリストから、***SDKイベント名***を選択します。
5. ***パートナー側のイベント名*** のドロップダウンリストから、対応するオプションを選択してください。
6. [***イベントを追加***] をクリックしてさらにイベント名を追加します。
7. 次のパラメーターを入力してください:

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリと連携済みの SDK から、またはサーバー間（S2S）イベントから AppsFlyer が受信したイベント名  <br />**ヒント** - アプリ内イベント名がリストに表示されない場合、デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認してください。 |
| **パートナー側のイベント名** | LINE 広告プラットフォーム側で定義した各イベントの一意の名前またはID。  <br />対応するイベント ID を LINE 広告プラットフォームから取得し、テキスト項目に設定します。 |
| **収益値を送信** | **チェックなしの場合** - リッチアプリ内イベントのすべてのパラメーターをパートナーに送りますが、**af\_revenue** パラメーターに含まれる収益パラメーターは送信しません。  <br />**チェックありの場合：** 収益値（イベントに存在する場合）を含むすべてのパラメーターをパートナーに送ります。 |

<div id="custom-in-app-events-mapping" />

### カスタムアプリ内イベントマップ

AppsFlyerでは、CUSTOMパートナーイベント識別子オプションを使用することで、カスタムアプリ内イベントをLINEにマッピングすることができます。

SDKで定義されたイベント名とイベント値（イベントパラメーターを含む）は、そのままLINEに転送されます。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="アトリビューションリンクタブ">

計測リンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UA およびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。シングルプラットフォームリンクまたはOneLinkのいずれかを使用できます。  
<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">計測リンクの構造とパラメーターについての詳細はこちら</Anchor>

**アトリビューションリンクを作成** するには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">次の手順</Anchor>に従ってください。

LINE 広告プラットフォームでアトリビューションリンクを有効にするには<Anchor target="_blank" href="https://lineforbusiness.com/th-en/service/line-ads/manual">こちらの手順に従ってください</Anchor>。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

このパートナーはコストデータをサポートしていません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーは広告収益をサポートしていません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

LINE広告プラットフォーム向けには権限の設定は利用できません。

</Accordion>

<div data-zendesk-anchors="setting-up-line-ads-platform=line-%E5%BA%83%E5%91%8A%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW2TJ83EZSV30XH3CM0HHB7=line-%E5%BA%83%E5%91%8A%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW2TJ83XGFNKRFA672675TS=%E3%83%92%E3%83%B3%E3%83%88 h_01HKW2TJ83RG7W6F2PZMAY7BXZ=integration-tab h_01HKW2TJ83VEK727ZH9FPH6TPJ=%E6%B3%A8 activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW2TJ83VPWD1GK99S4MY3ZB=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01HKW2TJ83PFS3TCPHKZ9HY5PE=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A connect-multiple-accounts-and-apps=%E6%B3%A8 h_01JAA89AWAQ4JZS3522EVZZN8D=%E6%B3%A8 01JB6YF9SFD2TWTZGR0RPVEBTC=%E6%B3%A8 01JAT9SYW9C06P185S9TWKAFM0=%E4%BE%8B default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HKW2TJ838FFTAR7NQC9WX295=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW2TJ833VC6SGSRNJSZ53WR=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A custom-inapp-events-mapping=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9E%E3%83%83%E3%83%97 h_01HKW2TJ83GQ7SFKV6YPM49QP1=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9E%E3%83%83%E3%83%97 h_01HKW2TJ83JPB6DSW8Z5PCY1SC=attribution-link-tab h_01HKW2TJ839R8NS3PFHCAJGXTZ=cost-tab h_01HKW2TJ835JT0WD3GN4H3XHT5=ad-revenue-tab h_01HKW2TJ83MPGHKGEMDQQYGGJ1=permissions-tab" />
