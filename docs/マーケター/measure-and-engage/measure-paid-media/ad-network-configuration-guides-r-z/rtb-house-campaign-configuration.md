---
title: RTB House 連携設定ガイド
metadata:
  keywords:
    - Advertisers
    - RTB
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-07-05T08:30:48Z'
  edited_at: '2026-10-14T09:33:09Z'
  id: 360001274325
  locale: ja
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ja/articles/360001274325
---
> **概要：** RTB Houseは、AppsFlyerの連携済みパートナーであり、eコマースおよびゲーム会社向けのリターゲティング技術を提供しています。RTB Houseは、リアルタイム入札モデルでオンライン広告を購入するための深層学習アルゴリズムに基づいた独自のリターゲティングソリューションを開発しました。クリックベースのモバイルアトリビューションに加えて、RTB Houseはリターゲティングアトリビューションを提供しており、これをAppsFlyerで計測できます。

## RTB Houseの連携設定

**前提条件：** 連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡</Anchor>してRTB Houseアカウントを開設してください。

**連携を有効化または編集する：**

1. **有効にする：** AppsFlyer管理画面 左メニュー 連携 > **パートナーマーケットプレイス**へ移動します。  
   **編集する：** AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**を選択します。
2. パートナーを検索し選択してください。
3. **連携の設定**をクリックします。 連携の設定ページに移動します。
4. **連携**タブで、**パートナーを有効にする**トグルをオンにします。  
   **注：** このトグルは、このパートナーの連携を続ける限り、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">オン（有効）</Anchor>のままにしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

RTB Houseの設定画面には、3つのアクティブタブが含まれています：連携、計測リンク、および権限。次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="連携タブ">

連携タブは次のセクションに分かれています。

### パートナーの有効化

この画面を**初めて**開く際には、**パートナーを有効にする**というトグルをオンにして、連携タブのパラメーター設定を有効にする必要があります。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーの有効化についての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

### デフォルトのポストバック

ユーザーのインストールとリエンゲージメント後に、自動でRTB Houseにポストバックを送信します。このセクションでは、これらのポストバックの**送信を許可するユーザー**を定義してください。

> 📘 **注意**
>
> 全てのインストールデータを受信できるネットワークであるRTB Houseは、オーガニックを含む全てのメディアソースに紐づく新規インストールのポストバック受信を希望しています。そのためには、**オーガニックを含む全てのメディアソース**を選択して、全てのインストールポストバックをRTB Houseに送信してください。

### アプリ内イベントの設定

このセクションでは、ポストバックを介して、AppsFlyerイベントをRTB Houseとマッピングできます。

#### 地域

RTB Houseのデータセンターの地域を入力してください。 例： **emea**, **us**, **asia**

#### アプリ内イベントのポストバック設定

1. アプリ内イベントポストバックを有効にしてください。
2. SDKに実装済みの全てのイベントに対して、送信オプションを選択してください。  
   **- このパートナーのみ**：このパートナーにアトリビューションされたユーザー**のみ**から発生したイベント  
   **- オーガニックを含む全てのメディアソース**：ユーザーベース全体をパートナーにレポートできるようにする場合に選択
3. **イベントを追加**をクリックして、SDKイベントをリストに追加してください。
4. 次のパラメーターを入力してください：

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリと連携済みのSDKから、またはサーバー間（S2S）イベントからAppsFlyerが受信したイベント名  <br />**ヒント** - アプリ内イベント名がリストに表示されない場合、デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認してください。 |
| **パートナー側のイベント名** | RTB House側で定義されている各イベントの一意の名前またはID。   <br />対応するイベントIDをAppleから取得して、テキストフィールドに設定してください。 |
| **収益値を送信** | **チェックなしの場合** - リッチアプリ内イベントのすべてのパラメーターをパートナーに送りますが、**af\_revenue**パラメーターに含まれる収益パラメーターは送信しません。  <br />**チェックありの場合：** 収益値（イベントに存在する場合）を含むすべてのパラメーターをパートナーに送ります。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

計測リンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UA およびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。シングルプラットフォームリンクまたは<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>のいずれかを使用できます。  
<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">計測リンクの構造とパラメーターについての詳細はこちら</Anchor>  

**計測リンクを作成**するには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">次の手順</Anchor>に従ってください。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

このパートナーとの連携では、コストデータはサポートされていません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益はサポートされていません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このタブでは、パートナーがアドネットワークの場合、代理店の場合、または両方の場合に、RTB Houseに付与する権限を選択できます。RTB Houseのアトリビューションが無効になっていても、権限タブはアクティブであり、RTB Houseにコントロールを与えることができることに注意してください。

### アドネットワークへの権限付与

これらのトグルを使用して、アプリごとにアドネットワークへの権限付与を設定してください：

* ***パートナー連携の設定を許可する*** - パートナーに連携タブの設定（アプリ内イベントのポストバックを除く）を許可します。
* *アプリ内イベントのポストバック設定を許可する* - 連携タブでアプリ内イベントのポストバックをマッピングする設定をパートナーに許可します。
* ***リテンションレポートへのアクセスを許可*** - パートナーのリテンションデータへのアクセスを許可します。
* ***リテンションレポートへのアクセスを許可する***  - このパートナー経由のロイヤルユーザーデータのみへアクセスを許可します。
* ***アプリ内イベント集計データへのアクセスを許可する** -* このパートナー経由のアプリ内イベントデータのみへアクセスを許可します。
* ***収益集計データへのアクセス権限を許可する***‐ このパートナーに紐づく収益データのみへアクセスを許可します。
* ***Protect360管理画面へのアクセスを許可する*** - Protect360のデータへのアクセスを許可します（パートナーのデータのみ）。＜広告主がProtect360を利用している場合のみ＞

詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークへの権限付与</Anchor>をご覧ください。

</Accordion>

<div data-zendesk-anchors="setting-up-rtb-house=rtb-house%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HJRZXXH277REM62TJA907WX0=rtb-house%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HJRZXXH2P8Q15V7DKQT7AVTT=%E3%83%92%E3%83%B3%E3%83%88 h_01HJRZXXH2DJ8WMYPQ0NV08R05=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HJRZXXH309BVZZ2VRRJQ02N8=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HJRZXXH3X46N8KQ8GTP4BYYP=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HJRZXXH3SDCH4K86YV4VC5VH=%E6%B3%A8%E6%84%8F inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HJRZXXH3HJP28D34NW8A8EZN=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A region=%E5%9C%B0%E5%9F%9F h_01HJRZXXH3E7STC8XVRDP39282=%E5%9C%B0%E5%9F%9F inapp-event-postback-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E8%A8%AD%E5%AE%9A h_01HJRZXXH3336ZJZZD1P8408GP=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E8%A8%AD%E5%AE%9A h_01HJRZXXH3R7F4QA9PYWY7EYZZ=attribution-link-tab h_01HJRZXXH30PDV0S32THB0C4FM=cost-tab h_01HJRZXXH37CHDD10ASEXPN7VH=ad-revenue-tab h_01HJRZXXH3CASE2ZTRJDSW9545=permissions-tab ad-network-permissions=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E h_01HJRZXXH3TJSTVG4Z8ZDQBATG=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E" />
