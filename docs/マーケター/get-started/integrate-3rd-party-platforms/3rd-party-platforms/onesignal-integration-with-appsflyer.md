---
title: OneSignalとAppsFlyerの連携
metadata:
  keywords:
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
  created_at: '2020-11-29T08:11:41Z'
  edited_at: '2026-10-28T09:03:38Z'
  id: 360015926437
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/360015926437
---
> **At a glance:** OneSignalは、100万人以上の開発者とマーケターが利用する、高機能なプッシュ通知・アプリ内メッセージ配信プラットフォームです。

![onesignal-logo-stack__3_.png](https://files.readme.io/49c50c481c00391f25cf8cc7eb2c35cc166f6a88a10db9120769a7d11affa26a-13013733757841.png)

OneSignalは、世界中で毎日80億件のメッセージを配信しています。優れたアーキテクチャと使いやすいプラットフォームを基盤に、世界のほかのソリューションよりも高速かつ効率的に、より大規模なメッセージ配信を実現します。詳細は[onesignal.com](https://onesignal.com/?utm_medium=partner&utm_source=appsflyer)をご覧ください。

> 🚧 **Important**
>
> **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="setting-up-onesignal" />

## OneSignalの設定

OneSignalと連携するには、アプリのAppsFlyer SDKに数行のコードを追加し、AppsFlyerで連携を有効にします。

<div id="set-up-the-appsflyer-sdk" />

### AppsFlyer SDKの設定

AndroidでOneSignalと連携するには、OneSignal Player ID（OneSignalでユーザーを一意に識別するID）をAppsFlyer Android SDKに設定する必要があります。このパラメータはすべてのポストバックに含まれ、ユーザーの識別に使用されます。

**AppsFlyer Android SDKを設定するには、次の手順に従います。**

1. SDKのバージョンが2.3.1.18以降であることを確認します。
2. 以下のコードをアプリに追加します。[OneSignal SDKの起動後](https://documentation.onesignal.com/docs/android-sdk-setup)、AppsFlyer SDKの初期化コードより前に追加してください。
   * OneSignal SDKバージョン3.x.xを使用するAndroidデバイスの場合：

     ```http
     OSPermissionSubscriptionState status = OneSignal.getPermissionSubscriptionState();

               String deviceId = status.getSubscriptionStatus().getUserId();

                 customData.put("onesignalCustomerId", deviceId);
     ```
   * Unity SDKの場合：

     ```http
     var status = OneSignal.GetPermissionSubscriptionState();

               String deviceId = status.subscriptionStatus.userId;

                 customData.put("onesignalCustomerId", deviceId);
     ```
   * OneSignal Native SDKバージョン4以降を使用するAndroidデバイスの場合：

     ```http
     OSDeviceState device = OneSignal.getDeviceState();

               String deviceId = device.getUserId();

                 customData.put("onesignalCustomerId", deviceId);
     ```

**AppsFlyer iOS SDKを設定するには、次の手順に従います。**

1. SDKのバージョンが2.3.1.18以降であることを確認します。
2. 以下のコードをアプリに追加します。[OneSignal SDKの起動後](https://documentation.onesignal.com/docs/android-sdk-setup)、AppsFlyer SDKの初期化コードより前に追加してください。
   * OneSignal SDKバージョン2.x.xを使用するiOSデバイスの場合：

     <Tabs>
     <Tab title="Swift">

     ```http
     let status: OSPermissionSubscriptionState = OneSignal.getPermissionSubscriptionState()
     if let deviceId = status.subscriptionStatus.userId{
         customData.put("onesignalCustomerId", deviceId);
     ```

     </Tab>

     <Tab title="Objective-C">

     ```http
     OSPermissionSubscriptionState* status = [OneSignal getPermissionSubscriptionState];
     NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:status.subscriptionStatus.userId, @"onesignalCustomerId", nil];
     [[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
     ```

     </Tab>
     </Tabs>

   * OneSignal Native SDKバージョン3以降を使用するiOSデバイスの場合：

     <Tabs>
     <Tab title="Swift">

     ```http
     if let deviceState = OneSignal.getDeviceState() {
         let deviceId = deviceState.userId
         customData.put("onesignalCustomerId", deviceId);
     ```

     </Tab>

     <Tab title="Objective-C">

     ```http
     OSDeviceState *deviceState = [OneSignal getDeviceState];
     NSString *deviceId = deviceState.userId;
     NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:deviceId, @"onesignalCustomerId", nil];
     [[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
     ```

     </Tab>
     </Tabs>

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

![onesignal-integration-tab.png](https://files.readme.io/95ec88041360d492367ed383aa3242bebe1cd5c5abcff8fba64e7888f0a9c052-360017329277.png)

［連携］タブは、以下のセクションで構成されています。

<div id="activate-partner" />

### パートナーを有効化

このパートナーと連携している間は、有効のままにしてください。  
詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation#パートナー統合を有効にする">パートナーの有効化</Anchor>を参照してください。

<div id="general-settings" />

### 一般設定

#### OneSignal AppID

OneSignalアカウントをAppsFlyerに接続するには、**OneSignal AppID**フィールドにアプリIDを入力します。  
OneSignalのアプリIDは、OneSignalの**Settings**＞**Keys & IDs**で確認できます。

![onesignal-app-id-en_us.png](https://files.readme.io/2801bce8ea7ef4be731d8429bd0408f432d4b5600fbd359e989b0013da56b93e-360015238678.png)

<div id="default-postbacks" />

### デフォルトポストバック

![onesignal-default-postbacks_en-us.png](https://files.readme.io/07e40365685543a318be8a16c9ea83638634d4a60333338eca0f76d140f84bef-360014377697.png)

AppsFlyerは、ユーザーのインストール後にOneSignalへポストバックを自動送信できます。このセクションでは、イベントごとに、ポストバック送信の対象とするユーザーの流入元を設定します。  
詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">デフォルトポストバック</Anchor>を参照してください。

**アプリをダウンロードしたすべてのユーザーのポストバックをOneSignalに送信するには**、<strong>［オーガニックを含むすべてのメディアソース］</strong>を選択します。

<strong>連携の設定を完了するには、［連携を保存］</strong>をクリックします。

AppsFlyerはすべてのイベントを送信しますが、OneSignalはオーガニックインストールを集計しないため、OneSignal APIでは無視されます。

設定を保存すると、AppsFlyerは、オーガニックと非オーガニックの各インストールについて、以下のデータをOneSignalに送信します。

* メディアソース
* キャンペーン名
* デバイスID
* 広告ID

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

このパートナーでは、計測リンクは利用できません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

このパートナーとの連携では、コストデータは利用できません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益は利用できません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このパートナーでは、権限の設定は利用できません。

</Accordion>

<div id="view-user-attribution-data-in-onesignal" />

## OneSignalでユーザーのアトリビューションデータを確認する

Segment EditorのOneSignalタグで、デバイスごとのアトリビューションデータを確認できます。キャンペーンに使用するセグメントの作成時にも確認できます。

![onesignal-view-attribution_en-us.png](https://files.readme.io/ac23c9310cad560f692598127f3e9efb7c2b905efb6fd5de21efabe90bf58eea-360014377737.png)

<div data-zendesk-anchors="setting-up-onesignal=onesignal%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJTEYDEZ8AGVQBHZZTP7K=onesignal%E3%81%AE%E8%A8%AD%E5%AE%9A set-up-the-appsflyer-sdk=appsflyer-sdk%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJTEY71PTXR1YSAK709QT=appsflyer-sdk%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWJTEZC62F9JW1KD4Y1CYS=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9HWJTEZH60AEPE7AB43X4YG=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9HWJTEZJAK2PTF4HQP3DQ1X=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9HWJTEZCNZX17K86H9KCRFN=onesignal-appid default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9HWJTEZ91KR3ZA8NX5BVZCF=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9HWJTEZZYRBS6PPRBBQAXZ5=attribution-link-tab h_01H9HWJTEZNT0EHJ7G4SFRD8K5=cost-tab h_01H9HWJTEZS7TN4FCAN40QB1NT=ad-revenue-tab h_01H9HWJTEZEY5VKCKDZ1Q7APRG=permissions-tab view-user-attribution-data-in-onesignal=onesignal%E3%81%A7%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B h_01H9HWJTEZZTJFTZC1Z2A6F5QM=onesignal%E3%81%A7%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B" />
