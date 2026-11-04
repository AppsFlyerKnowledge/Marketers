---
title: MixpanelとAppsFlyerの連携
metadata:
  keywords:
    - Attribution
    - Mixpanel
    - SDK
    - integrated partner
    - Advertisers
    - Ad Networks
    - facebook mixpabel
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
  created_at: '2015-12-24T11:33:01Z'
  edited_at: '2026-10-28T09:03:31Z'
  id: 207447103
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/207447103
---
> **概要：** AppsFlyerのデータを、プロダクト分析プラットフォームのMixpanelに自動で共有する方法を説明します。

![](https://cdn.appsflyer.com/marketplace/static/logo/mixpanel.png)

AppsFlyerとMixpanelを連携すると、AppsFlyerのユーザー獲得キャンペーン情報をMixpanelに取り込めます。

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="setting-up-mixpanel" />

## Mixpanelの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   **注意：** パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携</Anchor>を参照してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

<div id="general-settings" />

### 一般設定

<Image alt="mixpanel-general-settings.png" src="https://files.readme.io/df1b95eb3926aa7e10db338f156a87b88aabda6b97a4d28db2953e9e48a114e6-360017400598.png" width="542px" />

* **EU域内でのデータ保管**：AppsFlyerは、デフォルトでMixpanelの米国サーバーにデータを送信します。 MixpanelのEUサーバーに送信する場合は、この設定をオンにします。  
  **\*token**：MixpanelとAppsFlyerの接続には、固有のトークンを使用します。まだ取得していない場合は、連携の設定を進める前にMixpanelから取得してください。

  **Mixpanelのトークンを取得するには、以下の手順を実施します。**

  1. https://mixpanel.com/login/ からMixpanelアカウントにログインします。
  2. **Mixpanel**の**Analysis**ダッシュボードに移動し、歯車アイコンをクリックします。

     ![mixpanel-token-1.png](https://files.readme.io/f1fbc76fff621e12a7d91fed5ba49eb20f2b049de65c70b0ab32cadd997287d2-small-360014578477.png)
  3. プロジェクトのAccess Keysセクションからトークンをコピーし、AppsFlyerのMixpanel連携タブにある**token**フィールドに貼り付けます。

     ![mixpanel-token-2.png](https://files.readme.io/e8e633ec87d963244652a53b9b21c495b0a850e234621a44d93b3034c640bff7-360014578757.png)
* **広告IDを送信**：
  * AppsFlyerのcustomer\_user\_idパラメータを使用している場合、その値がインストールのたびにMixpanelに送信されます（<strong>［広告IDを送信］</strong>は無効のままにしてください）。
  * AppsFlyerのcustomer\_user\_idを使用していない場合は、<strong>［広告IDを送信］</strong>を有効にします。デバイスIDがcustomer\_user\_id（Mixpanelではunique\_id）としてMixpanelに送信されます。  
    詳しくは、AppsFlyer SDK連携ガイドの<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">Android</Anchor>および<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">iOS</Anchor>の説明を参照してください。
* **Events：** オンにすると、インストールデータをMixpanelのEventsエンドポイントに送信します。
* **People：** オンにすると、インストールデータをMixpanelのPeopleエンドポイントに送信します。

  <div id="note" />

  > 📘 **注意**
  >
  > Mixpanelにインストールポストバックを送信するには、**Events**または**People**の少なくとも一方のエンドポイントをオンにする必要があります。

* **拡張データ共有：** 有効にすると、c（キャンペーン）、network（pid）、impression\_based（is-impression）の追加情報をMixpanelに送信します。

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、インストールやリエンゲージメントの発生時に、Mixpanelへポストバックを自動送信できます。リエンゲージメントとは、すでにアプリをインストールしているユーザーが、キャンペーンをクリックした後にアプリを開くことです。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">デフォルトポストバック</Anchor>を参照してください。

[![](https://files.readme.io/6cf4f0e1b73c634c5fbe8f79e654ff3a3cd318bdca51d5e6b17933c307eb769d-36693858465809.png)](https://files.readme.io/6cf4f0e1b73c634c5fbe8f79e654ff3a3cd318bdca51d5e6b17933c307eb769d-36693858465809.png)

<div id="in-app-events-settings" />

### アプリ内イベントの設定

![mixpanel-in-app-events-settings.png](https://files.readme.io/db5e4e6d5bbe084a94b90425d49345511c214ddc39380a2b8419659ad752cdb2-360014576637.png)

このセクションでは、ポストバックを介してAppsFlyerのイベントをMixpanelのイベントに対応付けます。

<div id="note-1" />

> 📘 **注意**
>
> Mixpanelは、自社のSDKでアプリ内イベントを取得します。 Mixpanel自身が取得しないイベントのうち、Mixpanelに送信できるのはaf\_uninstallのみです。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">アプリ内イベントポストバック</Anchor>の詳細を確認してください。

**アプリ内イベントポストバックを設定するには、以下の手順を実施します。**

1. Mixpanelのトークンを入力します。
2. ［アプリ内イベントポストバック］を有効にします。
3. **アンインストールの広告IDを送信するには**、<strong>［広告IDを送信］</strong>を有効にします。
4. **アンインストールの追加情報を送信するには**、<strong>［拡張データ共有］</strong>を有効にします。
5. ［**イベントを追加**］をクリックし、SDKイベントをリストに追加します。
6. ドロップダウンメニューから**af\_uninstall**を選択します。
7. ドロップダウンメニューから、対応する<strong>［パートナーイベント識別子］</strong>を選択します。
8. ［収益の送信］のドロップダウンメニューから、送信するデータを選択します。
   * **値も収益も送信しない：** イベント値を含めず、イベント自体のみを送信します。
   * **値のみ送信し、収益は送信しない：** 収益値を除くすべてのパラメータを送信します。
   * **値と収益を送信する：** 収益値を含むすべてのイベントパラメータを送信します（イベントに収益値がある場合）。
9. ［**連携を保存**］をクリックして、連携の設定を完了します。

連携を保存すると、AppsFlyerはオーガニックと非オーガニックのすべてのインストールについて、次のデータをMixpanelに送信します。

* Mixpanelのトークンパラメータ
* Customer\_user\_idまたはデバイスID（IDFA／Google広告ID）
* メディアソース
* キャンペーン名

**注意**：アンインストールポストバックではCUIDは送信されません。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

このパートナーでは、計測リンクは利用できません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

このパートナーとの連携では、コストデータには対応していません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益データには対応していません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このパートナーでは、権限の設定は利用できません。

</Accordion>

<div id="integrating-with-mixpanel-when-using-a-login-mechanism" />

## ログイン機能を使用する場合のMixpanelとの連携

以下に連携手順の例を示します。

1. ユーザーがアプリを起動します。
2. Mixpanel SDKは、ランダムな一意のユーザー識別子（**distinct\_id**）を生成します。
3. Mixpanelのdistinct IDを取得し、AppsFlyer SDKの**setCustomerUserId**関数を使ってカスタマーユーザーIDに設定します。
4. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#start">**Start**</Anchor>を呼び出します。このAPIにより、AppsFlyerはインストール、セッション、アップデートを検出できます。
5. アプリのインストールの計測元が確定すると、Mixpanelのdistinct IDを含むカスタマーユーザーIDとともに、**install**イベントがMixpanelに送信されます。
6. ユーザーが登録またはログインすると、ユーザー識別子（メールアドレスや顧客IDなど）を指定してMixpanelのidentify()コマンドが呼び出されます。これにより、最初に生成されたランダムなdistinct IDが、登録済みのユーザーIDに紐付けられます。

   <Tabs>
   <Tab title="Android">

   Mixpanel Android：<Anchor target="_blank" href="https://developer.mixpanel.com/docs/android#section-combining-anonymous-and-identifiable-user-data">匿名ユーザーと識別済みユーザーのデータの統合</Anchor>

   ```java
   MixpanelAPI mixpanel = MixpanelAPI.getInstance(context, MIXPANEL_TOKEN);
   mixpanel.identify("user@example.com");

   // Mixpanel v6.2.0 and below should use the following API:
   mixpanel.getPeople().identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Objective C">

   Mixpanel iOS Objective C：<Anchor target="_blank" href="https://developer.mixpanel.com/docs/ios#section-combining-anonymous-and-identifiable-user-data">匿名ユーザーと識別済みユーザーのデータの統合</Anchor>

   ```objectivec
   [mixpanel identify:@“user@example.com”];
   ```

   </Tab>

   <Tab title="Swift">

   Mixpanel iOS Swift：[匿名ユーザーと識別済みユーザーのデータの統合](https://developer.mixpanel.com/docs/swift#section-combining-anonymous-and-identifiable-user-data)

   ```swift
   mixpanel.identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Unity">

   Mixpanel Unity：[匿名ユーザーと識別済みユーザーのデータの統合](https://developer.mixpanel.com/docs/unity#section-combining-anonymous-user-data-with-identifiable-user-data)

   ```csharp
   // set customer user id or device id
   Mixpanel.Identify(“user@example.com”);
   ```

   </Tab>
   </Tabs>

7. Mixpanelは、AppsFlyerからcustomer\_user\_idを受信し、ユーザーID（メールアドレスなど）との紐付けに使用します。

<div id="note-2" />

> 📘 **注意**
>
> アプリ内でユーザー登録を行わない場合は、上記の手順1～3を実装してください。

<div id="viewing-appsflyer-data-in-mixpanel" />

## MixpanelでのAppsFlyerデータの確認

以下のスクリーンショットは、メディアソース別に、インストールから価値のあるイベントまでのコンバージョンを確認するファネルレポートです。各メディアソースのコンバージョンまでの所要時間も確認できます。

[![](https://files.readme.io/fdffbe0a2f29c8a8b02b600966583cdeb4917bb48f0502e9b00ef39daa2fa835-9646475113361.png)](https://files.readme.io/fdffbe0a2f29c8a8b02b600966583cdeb4917bb48f0502e9b00ef39daa2fa835-9646475113361.png)

[![](https://files.readme.io/043a96a00e46a3daaef2b9fa4d58d252391ca2bb14307437f28c447d96ae97d6-9646475229841.png)](https://files.readme.io/043a96a00e46a3daaef2b9fa4d58d252391ca2bb14307437f28c447d96ae97d6-9646475229841.png)

<div data-zendesk-anchors="h_01H9FKEWTEN4F8FM5C9A9ES6HN=%E9%87%8D%E8%A6%81 setting-up-mixpanel=mixpanel%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKEWTEGMEVH3SK739DD719=mixpanel%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKEWTE90WR75PMNN93JAXE=integration-tab general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FKEWTEMT7VGTTFWFMJHYA8=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FKEWTEV3RWKMWZN0EXFFNP=%E6%B3%A8%E6%84%8F default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKEWTER31RXAH216TRXQPM=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKEWTERRVKPQFF1B8QQERE=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKEWTEEMMQ0KKRZXRJRE25=%E6%B3%A8%E6%84%8F-1 h_01H9FKEWTEEQ0GHF87V20TX9W0=attribution-link-tab h_01H9FKEWTEJ61197SN3R6JXYCP=cost-tab h_01H9FKEWTEA7GN2HHK3QD62A3A=ad-revenue-tab h_01H9FKEWTET4QD1RE0HJZM64D4=permissions-tab integrating-with-mixpanel-when-using-a-login-mechanism=%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B3%E6%A9%9F%E8%83%BD%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88%E3%81%AEmixpanel%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA h_01H9FKEWTE9DEANTXKPD286GD2=%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B3%E6%A9%9F%E8%83%BD%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88%E3%81%AEmixpanel%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA h_01H9FKEWTFZ107Y999WEMB3409=%E6%B3%A8%E6%84%8F-2 viewing-appsflyer-data-in-mixpanel=mixpanel%E3%81%A7%E3%81%AEappsflyer%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D h_01H9FKEWTF9PFNVHTZGDKBX75Y=mixpanel%E3%81%A7%E3%81%AEappsflyer%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D" />
