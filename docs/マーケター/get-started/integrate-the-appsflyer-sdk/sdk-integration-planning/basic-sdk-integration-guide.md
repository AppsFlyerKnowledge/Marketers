---
title: SDKの基本実装ガイド
metadata:
  keywords:
    - sdk
    - iOS
    - Android
    - Integration
    - Advertisers
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2013-08-22T16:09:08Z'
  edited_at: '2026-10-28T09:09:29Z'
  id: 207032066
  locale: ja
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ja/articles/207032066
---
> **At a glance:** モバイルアプリまたはCTVアプリの開発者と協力して、AndroidまたはiOSアプリにSDKをインストールし、実装してください。基本的な実装作業が完了すると、インストールのアトリビューションとアプリ内イベントの計測を開始できる状態になります。

<div id="implementing-the-dev-key-in-your-app" />

## **アプリへのDevキーの組み込み**

AppsFlyerでは、Devキーを使用してアカウントを一意に識別します。 Devキーは、SDKがアカウントに属するデータを安全に送受信するために必須です。開発者は、SDKをインストールして実装し、Devキーを組み込む必要があります。

<div id="retrieve-the-dev-key" />

#### Devキーの取得

開発者がSDKをインストールして実装する前に、Devキーを取得してください。

1. AppsFlyerのサイドメニューで、**設定** > **アプリ設定** > **Devキー管理**を選択します。
2. Devキーをコピーし、モバイルアプリの開発者に共有します。

   ![](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)

<div id="provide-the-dev-key-to-your-developer" />

#### 開発者へのDevキーの共有

Devキー、アプリID、AppsFlyer API v2トークンをモバイルアプリの開発者に共有し、以下の手順に従って実装するよう依頼してください。

* <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration">SDK実装ウィザード</Anchor>を使用して、SDKのインストールと実装を自動化します。
* 手順に従って、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">SDKをインストール</Anchor>し、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-integration">実装</Anchor>します。

<div id="where-to-start-the-sdk" />

## **SDKを起動する箇所の選択**

AppsFlyer SDKの実装を計画する際は、まずアプリの起動フローのどこでSDKを初期化し、起動するかを決める必要があります。

基本的には、アプリの起動後、できるだけ早くSDKによるデータ送信を開始します。**これにより、SDKはインストールイベントと、そのセッション中に発生するその他すべてのアプリ内イベントを確実に取得できます。**

ただし、GDPRやCCPAなどのプライバシー保護に関する規制に対応するため、ユーザーが情報の共有に同意するまで、AppsFlyerへのデータ送信を遅らせる必要がある場合があります。

<Tabs>
<Tab title="Androidネイティブ">

<div id="starting-the-sdk-in-android-native" />

### AndroidネイティブでのSDK起動

<div id="select-in-what-class-to-start-the-sdk" />

#### SDKを起動するクラスの選択

グローバルな`Application`クラスと`Activity`クラスのどちらでSDKを起動するかを選択します。

* **グローバルな**`Application`**クラスでSDKを起動：** 一般的には、グローバルな`Application`クラスまたはそのサブクラスでSDKを初期化することが推奨されます。`Application`クラスは、アプリのUIが表示される前に読み込まれ、初期化されるためです。これにより、ディープリンクを含むあらゆる状況でSDKを起動できます。
* **SDKを**`Activity`**クラスで起動（遅延起動）：** ユーザーがデータ共有への同意を選択できるようにします。ユーザーの同意を得るには、`Activity`クラスで表示するユーザーインターフェース（UI）が必要なためです。

<div id="android-developer-instructions" />

#### Android開発者への依頼事項

* 以下について決定し、開発者に伝えてください。
  * `Application`と`Activity`のどちらのクラスでSDKを起動するか。
  * どのオプトイン／オプトアウトのシナリオを使用するか。
* 以下の参考リンクを開発者に共有してください。
  * [遅延起動の実装方法](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-the-android-sdk)

</Tab>

<Tab title="iOSネイティブ">

<div id="starting-the-sdk-in-ios" />

<div id="starting-the-sdk-in-ios-native" />

### iOSネイティブでのSDK起動

<div id="delay-the-sdk-start-in-ios" />

#### iOSでのSDK起動の遅延

SDKの起動方法を計画する際は、ユーザーの同意が得られるまで`start`の実行を遅らせるかどうかを検討することが重要です。

SDKには`waitForATTUserAuthorization`メソッドが用意されています。このメソッドを使用すると、**AppsFlyerサーバーにデータを送信する前に、SDKがユーザーの同意を待つ時間を設定できます**。

このメソッドのデータフローと、iOSのATTフレームワークとの連携については、[App Tracking Transparency（ATT）への対応設定](/docs/basic-sdk-integration-guide#waitforattuserauthorizationの概要)のセクションをご覧ください。

<div id="ios-developer-instructions" />

#### iOS開発者への依頼事項

以下の情報を開発者に共有してください。

* AppsFlyerへのデータ送信を開始するまでのタイムアウト時間（秒）。
* 開発者向けの参考リンク：
  * [iOS SDKの起動](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#starting-the-ios-sdk)：SDKの起動方法に関する開発者向けガイドとリファレンスです。
  * [App Tracking Transparency（ATT）への対応設定](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support)：`waitForATTUserAuthorization`メソッドのデータフローと、iOSのATTフレームワークとの連携について説明しています。
  * [App Tracking Transparency（ATT）対応の有効化](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support)：`waitForATTUserAuthorization`に関する開発者向けガイドとリファレンスです。

</Tab>

<Tab title="Unity">

<div id="starting-the-sdk-in-Unity" />

<div id="starting-the-sdk-in-unity" />

### UnityでのSDK起動

SDKの起動方法を説明した<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#manual-integration">Dev Hubの記事</Anchor>を開発者に共有してください。

</Tab>

<Tab title="React Native">

<div id="starting-the-sdk-in-react" />

<div id="starting-the-sdk-in-react-native" />

### React NativeでのSDK起動

SDKの起動方法を説明した<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#startsdk">Dev Hubの記事</Anchor>を開発者に共有してください。

</Tab>
</Tabs>

<div id="select-your-privacy-preserving-strategy" />

## プライバシー保護の方針の選択

**ユーザーのプライバシーを保護する方法**を選択します。例えば、インストール時にSDKを停止する、第三者とのデータ共有を防ぐ、ユーザーデータを匿名化する、特定の識別子を無効にする、といった方法があります。

利用可能な各種プライバシー保護方法の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/apply-privacy-preserving-sdk-methods">SDKのプライバシー保護方法</Anchor>をご覧ください。

<div id="attribution" />

## **アトリビューション**

SDKは、アトリビューションのために<Anchor target="_blank" href="/marketers/ja/docs/about-device-identifiers">識別子</Anchor>を収集します。 インストールが正しく記録され、アトリビューションされるよう、以下のガイドラインを確認し、対応してください。

**すべてのプラットフォーム**

<Accordion title="インストールを一意に識別するID">

アプリが新規インストールされるたびに、AppsFlyer IDが自動的に作成されます。マーケティング担当者による作業は不要です。

この識別子を使用して、以下の操作を行えます。

* <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">サーバー間（S2S）でアプリ内イベントを送信</Anchor>します。
* AppsFlyer IDを、バックエンドシステムのユーザーレコードと照合します。
* <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">アプリ内イベントのローデータレポート</Anchor>をダウンロードし、**appsflyer\_id**を使用してユーザーの行動やジャーニーを分析します。

</Accordion>

<Accordion title="BIシステムの一意の識別子とAppsFlyerの連携">

AppsFlyer SDKに独自の顧客ユーザーID（CUID）を設定すると、BIシステムの一意のIDを、AppsFlyer IDやその他の識別子と照合できます。 CUIDは、AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">ローデータ</Anchor>レポートで確認できます。ポストバックAPIでもCUIDを使用し、自社の内部IDと照合できます。

CUIDの詳細は、<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">こちらの記事</Anchor>をご覧ください。

</Accordion>

**Androidのみ**

以下のセクションでは、Google Playストアまたはサードパーティのアプリストアにおけるアトリビューションの考慮事項を説明します。

<Accordion title="Google Playで公開しているアプリのアトリビューション">

#### Google Play Install Referrer

[Google Play Install Referrer API](https://developer.android.com/google/play/installreferrer)は、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#アトリビューション方法">アトリビューション</Anchor>の精度を高め、インストール不正を防ぎます。また、Google Playからリファラデータ（初回インストール時のアプリバージョンなど）を安全に取得できます。

[Google Play Install Referrer APIを追加する手順](https://developer.android.com/google/play/installreferrer/library)を開発者に共有することをおすすめします。

#### GAID

SDK V4.8.0以降では、AppsFlyerがこのデバイス識別子を自動的に収集します。

</Accordion>

<Accordion title="サードパーティのアプリストアで配信しているアプリのアトリビューション">

AppsFlyerでは、Amazon、Opera、GetJar、Baidu、Huaweiなど、<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution">サードパーティのアプリストア経由のインストールをアトリビューションできます</Anchor>。 これにより、Google Playストアを利用できない市場でもアプリを宣伝し、より多くのユーザーにリーチできます。

AppsFlyerは、サードパーティのアプリストアにおけるアトリビューションを、以下の方法でサポートしています。

* **IMEIまたはAndroid ID：** SDKは、IMEIやAndroid IDを自動的には収集しません。ただし、これらの識別子を収集する必要がある場合（<Anchor target="_blank" href="/marketers/ja/docs/measure-attribution-in-the-chinese-domestic-market#attribution-android-apps-in-the-chinese-domestic-market">中国国内市場向けのアプリ</Anchor>など）は、開発者が以下のいずれかの収集方法を実装できます。
  * 手動収集：アプリが`setImeiData`または`setAndroidIdData` APIを使用して、IMEIまたはAndroid IDをSDKに渡します（以下のタブにある関数リファレンスを参照）。 SDKは、このデータをAppsFlyerサーバーに送信します。

    <Tabs>
    <Tab title="Androidネイティブ">

    以下の関数については、Android SDKリファレンスをご覧ください。

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setimeidata">`setImeiData`</Anchor>
    * &lt;0>&lt;1>setAndroidIdData1>0>

    </Tab>

    <Tab title="Unity">

    以下の関数については、Unity SDKリファレンスをご覧ください。

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>
    </Tabs>

  * デバイスID収集のオプトイン：setCollectIMEIとsetCollectAndroidIDを使用して、SDKによるIMEIまたはAndroid IDの収集を有効にします（以下のタブにある関数リファレンスを参照）。

    <Tabs>
    <Tab title="Androidネイティブ">

    以下の関数については、Android SDKリファレンスをご覧ください。

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>

    <Tab title="Unity">

    以下の関数については、Unity SDKリファレンスをご覧ください。

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>

    <Tab title="React Native">

    以下の関数については、React Nativeのリファレンスをご覧ください。

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>
    </Tabs>

* **OAID：** サードパーティのAndroidアプリストア経由のインストールをアトリビューションします。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/android-oaid-implementation-in-the-sdk">OAIDの実装ガイド</Anchor>をご覧ください。
* **インストールリファラ：** SDKは、Samsung Galaxy StoreとHuawei AppGalleryからのリファラデータの取得に対応しています。

</Accordion>

**iOSのみ**

以下のセクションでは、iOS 14以降のデバイスへの対応に関する重要な情報を説明します。

<Accordion title="App Tracking Transparency（ATT）への対応設定">

**背景**

iOS 14.5以降では、IDFAの収集にユーザーの同意が必要です。つまり、IDFAへのアクセスは、[**App Tracking Transparency**](https://developer.apple.com/documentation/apptrackingtransparency)（ATT）フレームワークによって管理されます。 iOS 14以降のデバイスでは、SDKがATTフレームワークを使用してデバイスのIDFAにアクセスします。 ATTの基本的な仕組みについては、<Anchor target="_blank" href="/marketers/ja/docs/about-att-and-skan#att-principles">ATTの基本原則</Anchor>をご覧ください。

<Tabs>
<Tab title="iOSネイティブ">

Dev Hubの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support">ATTの実装に関する開発者向け手順</Anchor>をご覧ください。

</Tab>

<Tab title="Unity">

Dev Hubの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager">ATTの実装に関する開発者向け手順</Anchor>をご覧ください。

</Tab>
</Tabs>

IDFAを使用してアトリビューションを行う場合は、IDFAを**初回起動時に送信することが重要です。** このため、SDKには`waitForATTUserAuthorization`メソッドが用意されています。

<div id="waitforattuserauthorization-overview" />

#### waitForATTUserAuthorizationの概要

> 🚧 **Important**
>
> ATTの同意ダイアログを表示する予定がない場合は、waitForATTUserAuthorizationを呼び出さないでください。

`waitForATTUserAuthorization`を使用すると、AppsFlyerサーバーへのデータ送信を保留し、SDKがATTのステータスの確定を待つ時間を設定できます。

![](https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png)

ユーザーがアプリを起動すると、ATTのステータスは**notDetermined**です。 `waitForATTUserAuthorization`のタイムアウト時間中、SDKは起動イベントと、その後に発生するアプリ内イベントをメモリ上のキューに保存します。これは、[オフラインイベントを記録する仕組み](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events)と同様です。

* ユーザーがATTの同意ダイアログで**同意した**場合（IDFAの収集）：
  * SDKは、キャッシュされたイベントにIDFAを追加します。
  * SDKは起動し、タイムアウト時間の終了を待たずに、IDFAを含むキャッシュ済みイベントを送信します。
* ユーザーがATTの同意ダイアログで**拒否した**場合：SDKは起動し、タイムアウト時間の終了を待たずに、IDFAを含まないキャッシュ済みイベントを送信します。
* タイムアウト時間が終了してもATTのステータスが**notDetermined**のままの場合：SDKは起動し、IDFAを含まないキャッシュ済みイベントを送信します。

**考慮事項**

* [`requestTrackingAuthorization`](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/3547037-requesttrackingauthorization)を、`waitForATTUserAuthorization`を設定せずに呼び出すと、iOS 14以降のデバイスでは、起動イベントやその他のイベントがIDFAを含まずに送信されます。
* タイムアウト時間中にユーザーがアプリをバックグラウンドに移した場合：
  * アプリがフォアグラウンドに戻るまで、タイマーが一時停止します。
  * イベントはメモリ上にキャッシュされます。
* タイムアウト時間中にユーザーがアプリを終了し、アプリのプロセスが停止した場合：
  * 次回のアプリ起動時に、タイマーが再開始されます。
  * キャッシュされたイベントは失われます。

</Accordion>

<Accordion title="ATTの同意ダイアログのカスタマイズ">

ATTの同意ダイアログはカスタマイズできます。同意を求める目的を明確に伝えるメッセージを表示すると、ユーザーの同意率向上につながる可能性があります。

メッセージを作成する際は、以下の点を考慮してください。

* アプリが同意を求める理由を、ユーザーに最も分かりやすく伝えられる表現を使用します。
* ユーザーのデータをどのように使用するかを伝えます。 [ユーザーのプライバシーとデータの使用に関する詳細](https://developer.apple.com/app-store/user-privacy-and-data-use/)をご覧ください。

メッセージが完成したら、文面と実装手順を開発者に共有してください。

<Tabs>
<Tab title="iOSネイティブ">

Dev Hubの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#customizing-the-att-consent-dialog">ATTの同意ダイアログのカスタマイズに関する開発者向け手順</Anchor>をご覧ください。

</Tab>

<Tab title="Unity">

Dev Hubの[ATTの同意ダイアログのカスタマイズに関する開発者向け手順](https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager)をご覧ください。

</Tab>
</Tabs>

</Accordion>

<Accordion title="SKANアトリビューションへの対応">

> 📘 **Note**
>
> SKANアトリビューションに完全に対応するには、iOS SDK V6.2.3以降にアップグレードしてください。

SKANは、広告経由のアプリインストールを検証するためにiOSが使用するクラスです。アプリインストールの検証には、広告を表示するアプリと、広告対象のアプリが関わります。

広告を表示するアプリとは、アドネットワークの広告を表示することで広告キャンペーンに参加するアプリです。アプリに広告を表示するための設定は、AppsFlyer SDKの対応範囲外です。設定するには、[Appleの手順](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app)に従ってください。

広告対象のアプリ（AppsFlyer SDKを実装したアプリ）では、AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKANソリューション</Anchor>がSKANを使用してアトリビューションのポストバックを提供します。AppsFlyerは、ユーザーのプライバシーを保護しながら、データの収集・変換・集計を行います。アプリの初回起動時には、マーケティング担当者が指定した設定に基づき、AppsFlyerプラットフォームがSDKにSKANコンバージョン値の設定方法を指示します。

SKANソリューションを利用するには、以下の点を確認してください。

* マーケティング担当者は、AppsFlyerでSKAN計測を設定する必要があります。 開発者による作業は不要です。
* AppsFlyer SDKが、必要なSKAN APIを自動的に呼び出します。
* AppsFlyerでSKANアトリビューションを行う場合は、他のSDKによるSKANの呼び出しを必ず無効にしてください。
* 開発者・マーケティング担当者ともに、App Storeで追加の操作や登録を行う必要はありません。

SKANアトリビューションを無効にするには、SDK側で無効にするよう開発者に依頼してください。

<Tabs>
<Tab title="iOSネイティブ">

SKANアトリビューションを無効にするには、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableskadnetwork">`disableSKAdNetwork`</Anchor>を使用します。

</Tab>

<Tab title="Unity">

SKANアトリビューションを無効にするには、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#disableskadnetwork">`disableSKAdNetwork`</Anchor>を使用します。

</Tab>

<Tab title="React Native">

SKANアトリビューションを無効にするには、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#disableskad">`disableSKAd`</Anchor>を使用します。

</Tab>
</Tabs>

</Accordion>

<div id="recording-in-app-events" />

## **アプリ内イベントの記録**

アプリ内イベント（IAE）を使用すると、アプリ内で何が起きているかを把握できます。アプリ内イベントを記録することで、投資対効果（ROI）や顧客生涯価値（LTV）などのKPIを計測できます。記録するイベントは、時間をかけて定義することをおすすめします。

計測するアプリ内イベントが決まったら、イベント名とパラメータを開発者に共有し、以下のリンクも添えてください。

* アプリ内イベントの実装専用の手順が用意されている[SDK実装ウィザード](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration)。
* <Anchor target="_blank" href="http://dev.appsflyer.com/hc/docs/in-app-events-sdk">SDKでのアプリ内イベントの実装手順</Anchor>。

アプリ内イベントの定義方法と開発者への共有方法は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベントガイド</Anchor>をご覧ください。

**すべてのプラットフォーム**

<Accordion title="収益の記録">

収益は、どのアプリ内イベントでも送信できます。収益を含める場合は、必ず**af\_revenue**パラメータを使用してください。 AppsFlyerがダッシュボードとローデータレポートで実際の収益として集計するイベントパラメータは、このパラメータのみです。 <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">詳細はこちら</Anchor>。

<Tabs>
<Tab title="Androidネイティブ">

収益イベントの定義に関する開発者向け手順は、[こちら](https://dev.appsflyer.com/hc/docs/in-app-events-android#logging-revenue)をご覧ください。

</Tab>

<Tab title="iOSネイティブ">

収益イベントの定義に関する開発者向け手順は、[こちら](https://dev.appsflyer.com/hc/docs/in-app-events-ios#logging-revenue)をご覧ください。

</Tab>

<Tab title="Unity">

* アプリ内イベント全般に関する開発者向け手順は、[こちら](https://dev.appsflyer.com/hc/docs/inappevents#send-event)をご覧ください。
* iOSとAndroidでの収益の記録に関する具体的な手順は、AndroidとiOSのタブをご覧ください。

</Tab>
</Tabs>

</Accordion>

<Accordion title="アプリ内購入の検証">

AppsFlyer SDKは、アプリ内購入のサーバー側での検証に対応しています。アプリ内購入を検証すると、アプリ内購入イベントがAppsFlyerに自動送信されます。このイベントを別途送信すると、イベントが重複して記録されます。

</Accordion>

<Accordion title="業種別の推奨イベント">

旅行、ゲーム、Eコマースなどの<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#recommended-events-by-business-vertical">業種別の推奨アプリ内イベント一覧</Anchor>をご覧ください。

</Accordion>

<div id="deep-linking-with-onelink" />

## **OneLinkによるディープリンク**

OneLinkは、複数のプラットフォームにまたがるアトリビューション、**リダイレクト、ディープリンク**に対応するAppsFlyerのソリューションです。

**すべてのプラットフォーム**

<Accordion title="デバイスの検出とリダイレクト">

アプリをインストールしていないユーザーに対しては、OneLinkがデバイスの種類を検出し、適切な遷移先（Google Play、Apple App Store、サードパーティのアプリストア、Webページなど）にリダイレクトします。リダイレクト先は、OneLinkテンプレートの設定に基づいて決まります。 <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">詳細はこちら</Anchor>

</Accordion>

<Accordion title="ディープリンク">

アプリをインストール済みのユーザーに対しては、OneLinkがアプリを起動します。アプリを起動するだけでなく、ディープリンクによってアプリ内の特定のアクティビティやページにユーザーを誘導することも可能です。この機能を利用するには、開発者が以下のいずれかを使用して、統合ディープリンク（UDL）を実装する必要があります。

* ディープリンクの実装専用の手順が用意されている[SDK実装ウィザード](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration)、または
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">統合ディープリンクのSDK実装手順</Anchor>。

**注意**：

* UDLには、SDK V6.1以降が必要です。
* すでにOneLinkでディープリンクを利用している場合は、UDLではなく[従来の方法](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking)を使用している可能性があります。

設定方法は、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">ディープリンクとディファードディープリンク</Anchor>のガイドをご覧ください。

</Accordion>

<Accordion title="ディファードディープリンク">

アプリをインストールしていないユーザーに対しては、OneLinkがデバイスの種類を検出し、Google Play、Apple App Store、サードパーティのアプリストア、Webページなど、適切な遷移先にリダイレクトします。ユーザーがアプリを起動した後は、ディファードディープリンクを使用して、アプリ内の特定のアクティビティやページに誘導できます。

この機能を利用するには、開発者が以下のいずれかを使用して、ディファードディープリンクを実装する必要があります。

* ディープリンクの実装専用の手順が用意されている[SDK実装ウィザード](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration)、または
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">ディファードディープリンクのSDK実装手順</Anchor>。

**注意**：

* UDLには、SDK V6.1以降が必要です。
* すでにOneLinkでディファードディープリンクを利用している場合は、UDLではなく[従来の方法](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking)を使用している可能性があります。

設定方法は、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">ディープリンクとディファードディープリンク</Anchor>のガイドをご覧ください。

</Accordion>

<div id="accessing-attribution-and-deep-linking-data" />

## **アトリビューションデータとディープリンクデータの取得**

アトリビューションデータとディープリンクデータを取得する方法を、以下の表にまとめています。

| 方法 | 関係者 | 結果が返るまでの時間 | 取得方法 | アトリビューションデータ | ディープリンクデータ | 利用対象 |
| --- | --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/push-api-streaming-raw-data">**Push API**</Anchor> | • マーケティング担当者 • バックエンド開発者 | 通常、数分以内 | バックエンド | 可 | 不可 | プレミアム機能 |
| <Anchor target="_blank" href="/marketers/ja/docs/pull-api-raw-data">**Pull API**</Anchor> | • マーケティング担当者 • バックエンド開発者 | • 定期的に取得（リアルタイムではありません）。 • ローデータレポートのダウンロードをスケジュールできます。 | バックエンド | 可 | 可 | ローデータレポートはプレミアム機能 |
| <Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">**Data Locker**</Anchor> | • マーケティング担当者 • バックエンド開発者 | 1時間ごとのレポートを1～3時間以内に取得可能 | 以下のいずれかのクラウドストレージ：• AppsFlyerが所有するAWSバケット • 自社が所有するストレージ（AWSまたはGCS） | 可 | 可 | プレミアム機能 |
| <Anchor target="_blank" href="/marketers/ja/docs/conversion-data-payloads-and-scenarios#概要">**コンバージョンデータの取得（GCD）**</Anchor> | • マーケティング担当者 • モバイルアプリ開発者 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">開発者向けドキュメント</Anchor>を参照 | 最大5秒 | SDK | 可 | 可 | すべてのアカウント |
| <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">**統合ディープリンク（UDL）**</Anchor> | • マーケティング担当者 • モバイルアプリ開発者 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">開発者向けドキュメント</Anchor>を参照 | 最大1秒 | SDK | 不可 | 可 | すべてのアカウント |

iOS 14.5以降でATTに同意していないユーザーについては、以下の点に注意してください。

* 有料媒体とオウンドメディアでUDLを使用する場合、ディープリンクデータを取得できます。
* 有料媒体でGCDを使用する場合、取得できるデータは制限され、アトリビューションやディープリンクの詳細は含まれません。

> 👍 **Tip**
>
> 以下の方法をおすすめします。
>
> * Push APIを使用してアトリビューションデータを取得し、自社サーバーに送信して、後続の処理を行います。この方法では、データが利用可能になるまで待ってから取得するため、精度が高く、ほぼリアルタイムで処理できます。 GCDはリアルタイムでデータを返しますが、アトリビューションの最終的な判定までに5秒を超える時間がかかる場合は、データが不正確になる可能性があります。
> * Pull APIを使用して定期的（例えば日次）にリアルタイムのアトリビューションデータを補完し、通信エラーなどによって生じるデータの欠落にも対応します。

<div id="testing-your-sdk-integration" />

## **SDK実装のテスト**

SDKの実装が完了したら、AppsFlyer管理画面の「SDK実装テスト」ページで、オーガニック／非オーガニックインストール、アプリ内イベント、ディープリンク（リターゲティング）をテストできます。 これにより、インストールとアプリ内イベントが正しく記録され、アトリビューションされていることを確認できます。

テストのシナリオと手順は、<Anchor target="_blank" href="/marketers/ja/docs/testing-the-sdk-integration-for-marketers">SDK実装のテスト</Anchor>をご覧ください。

**注意：** アトリビューションのテストを行う際は、各インストールが新規インストールとして記録されるよう、<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">テストデバイスを登録</Anchor>してください（AndroidまたはiOS）。テストデバイスを登録すると、インストールが再インストールとして記録されるのを防げます。

> 📘 **Note**
>
> **関連記事**
>
> * CTV・PC・コンソール向けプラットフォームの概要

<div data-zendesk-anchors="retrieving-the-dev-key=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AEdev%E3%82%AD%E3%83%BC%E3%81%AE%E7%B5%84%E3%81%BF%E8%BE%BC%E3%81%BF h_01HAWCK9K4QBRE74JAS8Q7MEXW=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AEdev%E3%82%AD%E3%83%BC%E3%81%AE%E7%B5%84%E3%81%BF%E8%BE%BC%E3%81%BF retrieve-the-dev-key=dev%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 h_01HHHKTARNPQTBXQ6CQGEHMJRG=dev%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 embed-the-dev-key=%E9%96%8B%E7%99%BA%E8%80%85%E3%81%B8%E3%81%AEdev%E3%82%AD%E3%83%BC%E3%81%AE%E5%85%B1%E6%9C%89 h_01HHHKXMBGV6EM0CCW842RQQZ6=%E9%96%8B%E7%99%BA%E8%80%85%E3%81%B8%E3%81%AEdev%E3%82%AD%E3%83%BC%E3%81%AE%E5%85%B1%E6%9C%89 where-to-start-the-sdk=sdk%E3%82%92%E8%B5%B7%E5%8B%95%E3%81%99%E3%82%8B%E7%AE%87%E6%89%80%E3%81%AE%E9%81%B8%E6%8A%9E h_01HAWCK9K4MBS0F0HE6QE1W1AN=sdk%E3%82%92%E8%B5%B7%E5%8B%95%E3%81%99%E3%82%8B%E7%AE%87%E6%89%80%E3%81%AE%E9%81%B8%E6%8A%9E starting-the-sdk-in-android=android%E3%83%8D%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E3%81%A7%E3%81%AEsdk%E8%B5%B7%E5%8B%95 h_01HAWCK9K45HCJEDRW761WHKES=android%E3%83%8D%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E3%81%A7%E3%81%AEsdk%E8%B5%B7%E5%8B%95 select-in-what-class-to-start-the-sdk=sdk%E3%82%92%E8%B5%B7%E5%8B%95%E3%81%99%E3%82%8B%E3%82%AF%E3%83%A9%E3%82%B9%E3%81%AE%E9%81%B8%E6%8A%9E h_01HAWCK9K428SDFBFCCSZ15X9J=sdk%E3%82%92%E8%B5%B7%E5%8B%95%E3%81%99%E3%82%8B%E3%82%AF%E3%83%A9%E3%82%B9%E3%81%AE%E9%81%B8%E6%8A%9E android-developer-instructions=android%E9%96%8B%E7%99%BA%E8%80%85%E3%81%B8%E3%81%AE%E4%BE%9D%E9%A0%BC%E4%BA%8B%E9%A0%85 h_01HAWCK9K4XR1HZHP7Y15Q2Q4N=android%E9%96%8B%E7%99%BA%E8%80%85%E3%81%B8%E3%81%AE%E4%BE%9D%E9%A0%BC%E4%BA%8B%E9%A0%85 h_01HAWCK9K4693729EX1WYFR6XT=starting-the-sdk-in-ios h_01HAWCK9K4QSBP874RX2ZRA7EB=delay-the-sdk-start-in-ios h_01HAWCK9K4VHDFB9CYHC144BZN=ios-developer-instructions h_01JQ73M8DWMVQ98V1DQMPT0316=starting-the-sdk-in-Unity h_01JQ73M8DW350GBH9P52W4516V=starting-the-sdk-in-react select-the-optoutin-scenario::ae4c6e25=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E4%BF%9D%E8%AD%B7%E3%81%AE%E6%96%B9%E9%87%9D%E3%81%AE%E9%81%B8%E6%8A%9E h_01HAWCK9K4EXBA2F0BPVBXFAMG=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E4%BF%9D%E8%AD%B7%E3%81%AE%E6%96%B9%E9%87%9D%E3%81%AE%E9%81%B8%E6%8A%9E attribution=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HAWCK9K41T5GGWDB3ABYGRHW=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HAWCK9K4V91MPQHXDZBD0HKR=google-play-install-referrer h_01HAWCK9K4YD8CYQDB2YRA8W1F=gaid waitforattuserauthorization-overview=waitforattuserauthorization%E3%81%AE%E6%A6%82%E8%A6%81 h_01HAWCK9K5JHDWS8KTBTTGSS9G=waitforattuserauthorization%E3%81%AE%E6%A6%82%E8%A6%81 recording-inapp-events=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%98%E9%8C%B2 h_01HAWCK9K5ZZYQR8KPCWANZEA5=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%98%E9%8C%B2 deep-linking-with-onelink=onelink%E3%81%AB%E3%82%88%E3%82%8B%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF h_01HAWCK9K5PK9RE7WZQVCY97KC=onelink%E3%81%AB%E3%82%88%E3%82%8B%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF accessing-attribution-and-deep-linking-data=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A8%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97 h_01HAWCK9K5ACPZ2WKBTVR3VVTD=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A8%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97 testing-your-sdk-integration=sdk%E5%AE%9F%E8%A3%85%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01HAWCK9K6JQ33T32RYKYH20P1=sdk%E5%AE%9F%E8%A3%85%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88" />
