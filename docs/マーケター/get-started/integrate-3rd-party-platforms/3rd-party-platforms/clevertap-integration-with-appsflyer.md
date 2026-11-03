---
title: CleverTapとAppsFlyerの連携
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Clevertap
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2018-07-12T06:26:58Z'
  edited_at: '2026-10-28T09:02:54Z'
  id: 360001299165
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/360001299165
---
> **概要：** CleverTapは、デジタル分野の消費者向けブランドが顧客継続率と顧客生涯価値を高めるための、先進的な統合型クラウドプラットフォームです。

<Image alt="clevertap-logo.png" src="https://files.readme.io/ee01a7da1ae0c77758e279c47f2f588d90fdb7f52dce51161fce3891cc5fd498-4405112002833.png" width="193px" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

## CleverTapの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

### パートナーを有効化

パートナーとの連携を利用している間は、このトグルを有効にしておく必要があります。  
詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation#パートナー統合を有効にする">パートナーの有効化</Anchor>を参照してください。

### 一般設定

**アカウントトークン**

CleverTapとAppsFlyerの接続には、固有のAccount Token、Region、Account Passcode、Account IDを使用します。まだ取得していない場合は、連携の設定を進める前にCleverTapから取得するか、以下の手順で取得してください。

> 🚧 **重要**
>
> CleverTapにポストバックを送信するには、次の**両方**の設定を完了してください。
>
> * account\_token、account\_passcode、account\_idのうち、少なくとも**1つ**のフィールドを入力します。
> * AppsFlyer SDKでカスタマーユーザーIDを設定します（<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid#cuidの設定">iOS、Android</Anchor>）。カスタマーユーザーIDに使用する推奨パラメータについては、[CleverTapのドキュメント](https://developer.clevertap.com/docs/appsflyer#section-step-2-integration)を参照してください。カスタマーユーザーIDが空の場合、CleverTapにポストバックは送信されません。

![CleverTap_msc_new_2.png](https://files.readme.io/dd3f79fdce7dc4d48605f18021e328754d3e78aae98cb5214466c7489fd29fdf-360002305685.png)

### CleverTapのアカウントトークンを取得する

**CleverTapからアカウントトークンを取得するには、次の手順に従います。**

1. CleverTap管理画面の右上にある**Settings**に移動します。

   ![CleverTap_msc_new_4.png](https://files.readme.io/2fd248582c3e267b2eaacfc6bf49068bdd4c6811b066c8286f0059e18d8535ae-360002541969.png)  
   Settings画面の最上部で、Account ID、Account token、Passcodeの各欄に、CleverTapのアカウントID、アカウントトークン、パスコードが表示されます。

   ![CleverTap_msc_new_5.png](https://files.readme.io/795086dfc16cdee369b470e0b598b5089fff6469c77d0ccbf929e230d94191c8-360002537945.png)
2. 各フィールドの横にある目のアイコンをクリックすると、値を表示できます。
3. 値をコピーし、AppsFlyerのCleverTap設定ページに貼り付けます。

   > 📘 **注意**
   >
   > * リージョンは、アカウントのCleverTap管理画面のURLによって異なります。
   > * アカウントのURLが<Anchor target="_blank" href="https://eu1.dashboard.clevertap.com/">https://eu1.dashboard.clevertap.com</Anchor>の場合、リージョンはEU1です。アカウントデータはEU内のデータセンターに保管されています。
   > * アカウントのURLが<Anchor target="_blank" href="https://in1.dashboard.clevertap.com">https://in1.dashboard.clevertap.com</Anchor>の場合、リージョンはIN1です。アカウントデータはインドのデータセンターに保管されています。
   > * アカウントのURLが[https://aps3.dashboard.clevertap.com](https://aps3.dashboard.clevertap.com)の場合、リージョンはIDです。アカウントデータはインドネシアのデータセンターに保管されています。* リージョンの設定は大文字と小文字が区別されるため、必ず大文字で入力してください。小文字を使用した場合、ポストバックはデフォルトのサーバー（EU1）に送信されます。

4. <Anchor target="_blank" href="https://developer.clevertap.com/docs/appsflyer#section-step-2-integration">CleverTapのドキュメント</Anchor>に従って連携の設定を完了します。

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にCleverTapへポストバックを自動送信できます。このセクションでは、イベントごとに、ポストバック送信の対象とするユーザーの流入元を設定します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">デフォルトポストバック</Anchor>を参照してください。

![clevertap-default-postbacks_en-us.png](https://files.readme.io/58424df9f5e8ba0e30e2390e26e0ecec7fc827baa43f3b812181caa2283dca0a-360014085238.png)

<strong>アプリをダウンロードしたすべてのユーザーのポストバックをCleverTapに送信するには、［オーガニックを含むすべてのメディアソース］</strong>を選択します。

### アプリ内イベントの設定

![clevertap-in-app-events_en-us.png](https://files.readme.io/2ccc8a5a62cd601c45647d72caff0d94af814f78d9e1a8ae1548f973ed4c554f-360014005017.png)

このセクションでは、ポストバックを介してAppsFlyerのイベントをパートナーのイベントに対応付けます。  
詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">アプリ内イベントポストバック</Anchor>を参照してください。

**アプリ内イベントポストバックを設定するには、以下の手順を実施します。**

1. 必要なトークンをすべて入力します。
2. ［**アプリ内イベントポストバック**］を有効にします。
3. ［**イベントを追加**］をクリックし、SDKイベントをリストに追加します。
4. ドロップダウンメニューから［**SDKイベント名**］を選択します。
5. ［収益の送信］のドロップダウンメニューから、送信するデータを選択します。
   * **値も収益も送信しない：** イベント値を含めず、イベント自体のみを送信します。
   * **値のみ送信し、収益は送信しない：** 収益値を除くすべてのパラメータを送信します。
   * **値と収益を送信する**：収益値を含むすべてのイベントパラメータを送信します（イベントに収益値がある場合）。
6. ［**連携を保存**］をクリックして、連携の設定を完了します。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

このパートナーでは、計測リンクは利用できません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

このパートナーではコストデータは利用できません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーでは広告収益データは利用できません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

CleverTapでは、権限の設定は利用できません。

</Accordion>

## CleverTapの自社メディアの成果を計測する

CleverTapはメール、SMS、プッシュ通知などを使ってマーケティングを自動化するプラットフォームです。CleverTap経由の自社メディアの成果は、<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">AppsFlyer OneLink</Anchor>で計測できます。

<div data-zendesk-anchors="h_01H9FK5JT1TM77CAH0JTDCV376=%E9%87%8D%E8%A6%81 setting-up-clevertap=clevertap%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK5JT1ATCHY6WAVB6E2YEW=clevertap%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW9C39FKN3QN21NKDS6N3BQ=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FK5JT12Z1M6WW3GQQF5QVN=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FK5JT1FMC6JANBP9KBB0V2=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FK5JT1MQKT7KWJ3EVNEA1E=%E9%87%8D%E8%A6%81-1 obtain-clevertap-account-token=clevertap%E3%81%AE%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B h_01H9FK5JT1RVJ1V0CGXSH1XZPM=clevertap%E3%81%AE%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B h_01H9FK5JT2QV9CKSZ1N3S4WTGE=%E6%B3%A8%E6%84%8F default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FK5JT2CE0WQ9HAGVGAQA5B=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK5JT2YS7G5WDD4F5MPYVZ=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK5JT2939VDXQCDDG7MZ0R=attribution-link-tab h_01H9FK5JT2AEDDCD11K77WJHBX=cost-tab h_01H9FK5JT2WYWRGZAS1HBYYBSJ=ad-revenue-tab h_01H9FK5JT2FD6WN3Z1RET108JZ=permissions-tab measure-clevertap-owned-media=clevertap%E3%81%AE%E8%87%AA%E7%A4%BE%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%81%AE%E6%88%90%E6%9E%9C%E3%82%92%E8%A8%88%E6%B8%AC%E3%81%99%E3%82%8B h_01H9FK5JT2AZTT5936DD88ZZV3=clevertap%E3%81%AE%E8%87%AA%E7%A4%BE%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%81%AE%E6%88%90%E6%9E%9C%E3%82%92%E8%A8%88%E6%B8%AC%E3%81%99%E3%82%8B" />
