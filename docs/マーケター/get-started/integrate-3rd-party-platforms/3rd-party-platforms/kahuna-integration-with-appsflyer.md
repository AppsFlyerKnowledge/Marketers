---
title: KahunaとAppsFlyerの連携
metadata:
  keywords:
    - kahuna
    - Advertisers
    - Ad Networks
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
  created_at: '2016-09-14T11:26:59Z'
  edited_at: '2026-10-28T09:03:15Z'
  id: 212561966
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/212561966
---
> **概要：** AppsFlyerの連携済みパートナーであるKahunaは、モバイル時代における企業の成長と発展を支援しています。 Web、メール、モバイル、ソーシャルなど、顧客が利用するさまざまなチャネルで、一人ひとりに合ったコミュニケーションを大規模に展開し、ブランドと顧客の関係を深めます。ビッグデータと機械学習を活用し、適切なメッセージを、適切なチャネルで、適切なタイミングに届けることで、すべての顧客に満足度の高い体験を提供します。

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

以下の手順でKahunaとの連携を設定します。

1. AppsFlyer SDKの最低要件：

* Android：V2.3.1.18以降
* iOS：V3.3.3以降

2. Kahunaと連携するには、Kahunaの<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/deviceid/">Device ID</Anchor>（Kahunaでユーザーを一意に識別するID）をAppsFlyer SDKに設定する必要があります。このパラメータはすべてのポストバックに含まれ、ユーザーの識別に使用されます。アプリのコードに、以下のコードを追加してください。

<div id="important-note" />

> 📘 **重要な注意事項**
>
> コードは、Kahuna SDKの起動後、appsflyer.sendtracking（Android）／trackAppLaunch（iOS）メソッドの呼び出し前に追加してください。

<Tabs>
<Tab title="Androidの場合">

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId = Kahuna.getInstance().getKahunaDeviceId();
customData .put("customData", deviceId);
AppsFlyerLib.setAdditionalData(customData);
```

</Tab>

<Tab title="iOSの場合">

```objectivec
NSString *kahunaDeviceID = [Kahuna getKahunaDeviceId];
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{@"customData" : kahunaDeviceID}];
```

</Tab>
</Tabs>

<div id="setting-up-kahuna" />

## Kahunaの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   **注意：** パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携</Anchor>を参照してください。

Kahunaの設定で使用するのは、<strong><em>［連携］</em></strong>タブのみです。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

<div id="activate-partner" />

### パートナーを有効化

**初めてこの画面を開いたとき**は、下にあるトグルをオンにする必要があります。［***パートナーを有効化***］をオンにすると、［連携］タブのパラメータを設定できるようになります。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>を参照してください。

<div id="general-settings" />

### 一般設定

**Kahunaのシークレットキー、ステージング環境、本番環境**

KahunaとAppsFlyerの接続には、固有のシークレットキーを使用します。まだ取得していない場合は、連携の設定を進める前にKahunaから取得するか、以下の手順で取得してください。 [![](https://files.readme.io/941ce1b787ab4c34a502f254f7ec3ec8da356a05c99625f5e60e54b0da1f06b6-360002216249.png)](https://files.readme.io/941ce1b787ab4c34a502f254f7ec3ec8da356a05c99625f5e60e54b0da1f06b6-360002216249.png)

<div id="obtaining-the-kahuna-secret-key" />

### Kahunaのシークレットキーの取得

1. Kahunaアカウントにログインします。

2. 管理画面の右上にあるユーザーアイコンをクリックし、**Settings**を選択します。

<Image align="center" alt="" src="https://files.readme.io/4962454c4dd428c69e90d4ebcfa20304dc0ea57c7d58a1368c9a9369ba3e563a-207206166.png" />

3. Kahunaのシークレットキーをコピーします。

<Image align="center" alt="" src="https://files.readme.io/73d24826e6c55636dafbc22766910fea12fbe7a58c49079c800d5056be45352a-207229823.png" />

4. **APIs & Integrations**を選択します。このページでパラメータを確認できます。

* Kahunaコンソールから取得したKahuna Master Keyを入力します（セクション3を参照）。
* Kahunaのサンドボックス環境にイベントを送信する場合は、Staging欄にSと入力します（「Kahunaのサンドボックスでのテスト」を参照）。
* 本番環境を使用する場合は、production欄にPと入力します。
* 両方を入力した場合は、本番環境にイベントが送信されます。
* ［**保存**］をクリックします。

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にKahunaへポストバックを自動送信できます。このセクションで、ポストバックの送信を設定します。

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

アプリをダウンロードしたすべてのユーザーのポストバックをKahunaに送信するには、［**すべてのパートナーまたはオーガニックのイベント**］を選択します。

［**保存**］をクリックします。

設定を保存すると、AppsFlyerは、オーガニックと非オーガニックの各インストールについて、以下のデータをKahunaに送信します。

* Kahuna Dev\_ID
* メディアソース
* 国コード
* OSバージョン

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Kahunaでは、計測リンクは利用できません。

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

Kahunaでは、権限の設定は利用できません。

</Accordion>

<div id="view-user-attribution-data-in-kahuna" />

## Kahunaでユーザーのアトリビューションデータを確認する

インストールイベントは、KahunaのメインダッシュボードでNewbiesとして確認できます。

<Image align="center" alt="" src="https://files.readme.io/ebbb7f265e37ead80dd77a9956b9629ce07eeb2fcc9b283ad7b6cc927fe10758-207230483.png" />

特定のユーザーを検索するか、左側のナビゲーションからTop Peopleに移動します。

<Image align="center" alt="" src="https://files.readme.io/ea6ae8494f600bb8a9b9b0af3e36a976e65d72b64052da3e7399f9a9b0c9458c-207230503.png" />

ユーザーを選択するとMini Profileが開き、Top Eventsセクションにインストールイベント「af\_install」が表示されます。

<Image align="center" alt="" src="https://files.readme.io/3e0a99f178cc1a9ab18886a576b4ba56878fecb6dbd0866926730fb32b65bc59-207230563.png" />

<div id="testing-with-sandbox" />

## サンドボックスでのテスト

アプリをまだアプリストアで公開しておらず、Kahunaのサンドボックス環境で連携をテストしたい場合は、次の手順に従ってください。

1. AppsFlyerでKahunaを設定する際に、Stagingのテキストボックスに「s」と入力してください。

<Image align="center" alt="" src="https://files.readme.io/b69fc390ed7f1303ee8ba6dd1345d2c76b5b4c22b4b0b6ec0957a108d709247b-360002217229.png" />

2. 前述の手順に従い、AppsFlyer SDKとKahuna SDKを連携するコードをアプリに追加したことを確認します。

3. テストデバイスの広告IDを取得します。デバイスにアプリをインストールし、ログを確認すると取得できます。

4. 広告IDを許可リストに登録するよう、AppsFlyerに依頼します。

5. デバイスからアプリをアンインストールします。

6. 以下のURLに、アプリのパッケージ名、広告ID、キャンペーン名などの情報を設定します。角括弧は含めないでください。[https://app.appsflyer.com/[APP PACKAGE NAME]?pid=[SOMETHING]&advertising\_id=](https://app.appsflyer.com/com.dailylabs.kahunatest?pid=Testing_Installs&advertising_id=0eea1488-3037-44b2-a944-11f8bfc3e479)[DEVICE’S ADVERTISING ID]

7. URLにアクセスすると、以下のような画面が表示される場合があります。

<Image align="center" alt="" src="https://files.readme.io/8b16b6d84f0244db3510e4376bf5fc51b6a737e13df89da82e951e1bda90711a-207230963.png" width="486px" />

8. デバイスにアプリをインストールします。

9. Kahuna管理画面でユーザーを検索します。Kahunaのデバッグを有効にしてログを確認すると、そのユーザーのKahuna固有のデバイスIDである 「dev\_id」を取得できます。また、アプリでログインが必要で、認証情報をKahunaに渡している場合は、その情報でも検索できます。ユーザーが見つかったら、そのユーザーの「af\_install」イベントが表示されていることを確認します。

<Image align="center" alt="" src="https://files.readme.io/b365a27e7638a6a87e6a5b46a67d329956f6a678b234bd1fd802acaeeceaaeb2-207207606.png" width="629px" />

<div data-zendesk-anchors="h_01H9FKAF22A3FTGC7CSE5K0CY4=%E9%87%8D%E8%A6%81 h_01H9FKAF22W59PMYJRFW8HKBQ7=%E9%87%8D%E8%A6%81%E3%81%AA%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85 setting-up-kahuna=kahuna%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKAF222ES9240V0THQQ5X0=kahuna%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKAF227SZWFTCP9P1B7HEK=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FKAF22EFF1F8D2QR1F38PV=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FKAF221EXQYBJGS8GFRF4S=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A obtaining-the-kahuna-secret-key=kahuna%E3%81%AE%E3%82%B7%E3%83%BC%E3%82%AF%E3%83%AC%E3%83%83%E3%83%88%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 h_01H9FKAF22XMJW7A89MBD0J276=kahuna%E3%81%AE%E3%82%B7%E3%83%BC%E3%82%AF%E3%83%AC%E3%83%83%E3%83%88%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKAF2258JVR3XS6P7TT8H3=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKAF22DMF1NNJRY3SJB5XX=attribution-link-tab h_01H9FKAF22KPY1ABFJN63XZ5CM=cost-tab h_01H9FKAF22KRDEFTVBR954JSJT=ad-revenue-tab h_01H9FKAF22HJPHZZM59TQ7RRFM=permissions-tab view-user-attribution-data-in-kahuna=kahuna%E3%81%A7%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B h_01H9FKAF22A5910NXRFDGC1JTG=kahuna%E3%81%A7%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B testing-with-sandbox=%E3%82%B5%E3%83%B3%E3%83%89%E3%83%9C%E3%83%83%E3%82%AF%E3%82%B9%E3%81%A7%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01H9FKAF22KW2J6H2B6F9AMDP9=%E3%82%B5%E3%83%B3%E3%83%89%E3%83%9C%E3%83%83%E3%82%AF%E3%82%B9%E3%81%A7%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88" />
