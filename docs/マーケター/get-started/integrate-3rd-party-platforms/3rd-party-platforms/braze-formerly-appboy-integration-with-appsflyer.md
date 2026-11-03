---
title: Braze（旧Appboy）とAppsFlyerの連携
metadata:
  keywords:
    - Appboy
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
  created_at: '2017-03-30T08:39:03Z'
  edited_at: '2026-10-28T09:02:51Z'
  id: 115001603343
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/115001603343
---
> **At a glance:** AppsFlyerの連携済みパートナーであるBrazeは、マーケティング、グロース、エンゲージメントの各チーム向けに、顧客との関係の各段階に応じたコミュニケーションを支援するプラットフォームを提供しています。多くの顧客に一人ひとりに合ったコミュニケーションを届けることで、エンゲージメントを深め、ROIを高めることができます。このプラットフォームの中心となるのは、顧客情報を一元化したユーザープロファイルです。

詳細は<Anchor target="_blank" href="https://www.braze.com/">braze.com</Anchor>をご覧ください。

> 🚧 **Important**
>
> **重要な注意事項**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。
> * 流入元がオーガニックの場合、ポストバックは送信されません。

## 連携の概要

以下の手順でBrazeとの連携を設定します。

AppsFlyer SDKの最低要件：

* <Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">Android</Anchor>（Android SDKバージョン2.3.1.18以降）
* <Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">iOS</Anchor>

AndroidでBrazeと連携するには、Brazeの<Anchor target="_blank" href="https://www.braze.com/docs/partners/advertising_technologies/attribution/appsflyer/#integration">Device ID</Anchor>（Brazeでユーザーを一意に識別するID）をAppsFlyer Android SDKに設定する必要があります。このパラメータはすべてのポストバックに含まれ、ユーザーの識別に使用されます。アプリのコードに、以下のコードを追加してください。

> 📘 **Note**
>
> **重要な注意事項**
>
> コードは、Braze SDKの起動後、AppsFlyer SDKの初期化コードより前に追加してください。Android SDK連携ガイドの「SDKの初期化」を参照してください。

<Tabs>
<Tab title="Android">

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId =(Braze.getInstance(MyActivity.this).getDeviceId());
customData.put("brazeCustomerId", deviceId);
AppsFlyerLib.getInstance().setAdditionalData(customData);
```

</Tab>

<Tab title="iOS">

**Swift**

Swift APIには、完了ハンドラーを使用するものと、新しいSwiftの並行処理機能を使用するものの2種類があります。どちらも同じ値を返すため、使用する場面に応じて選択してください。

**Swiftの完了ハンドラー**

```swift
let configuration = Braze.Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
braze.deviceId {
    brazeDeviceId in
    AppsFlyerLib.shared().customData = ["brazeDeviceId": brazeDeviceId]
}
```

**Swiftのawait**

```swift
let configuration = Braze.Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
let brazeDeviceId = await braze.deviceId()
AppsFlyerLib.shared().customData = ["brazeDeviceId": brazeDeviceId]
```

**Objective-C**

```objectivec
BRZConfiguration *configurations = [[BRZConfiguration alloc] initWithApiKey:@"BRAZE_API_KEY" endpoint:@"BRAZE_END_POINT"];
[configurations setUseUUIDAsDeviceId:NO];
Braze *braze = [[Braze alloc] initWithConfiguration:configurations];
[braze deviceIdWithCompletion:^(NSString * _Nonnull brazeDeviceId) {
    NSLog(@">>[BRZ]: %@", brazeDeviceId);
    [[AppsFlyerLib shared] setAdditionalData:@{
        @"brazeDeviceId": brazeDeviceId
    }];
}];
```

</Tab>

<Tab title="Unity">

```csharp
Appboy.AppboyBinding.getDeviceID()
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("brazeCustomerId", Appboy.AppboyBinding.getDeviceId());
AppsFlyer.setAdditionalData(customData);
```

</Tab>
</Tabs>

## Brazeの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで<strong>［連携＞パートナー連携＞マーケットプレイス］</strong>タブに移動します。  
   （<strong>既存の連携を編集する場合：［連携＞パートナー連携＞有効な連携］</strong>タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. <strong>［連携］</strong>タブで、<strong>［パートナーを有効化］</strong>をオンにします。  
   **注意：このパートナーと連携している間は、オン（有効）のままにしてください**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳細を見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携</Anchor>を参照してください。

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

### パートナーを有効化

**初めて設定する場合**は、***［パートナーを有効化］***をオンにすると、［連携］タブのパラメータを設定できます。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>を参照してください。

### 一般設定

BrazeとAppsFlyerの接続には、固有のAPIキーとRESTエンドポイントを使用します。

**BrazeのAPIキーとRESTエンドポイントを取得するには、次の手順に従います。**

1. Brazeアカウントで**Technology Partners**の**Attribution**に移動します。
2. **AppsFlyer**を選択します。  ![BrazeでテクノロジーパートナーとしてAppsFlyerを選択](https://files.readme.io/db96e8b5e2363f5250c6c1146a1f7a15e1ed6457fe4543dbe649f8818bb5db78-360017328637.png)
3. **Data Import for Install Attribution**で、Generate API Keyをクリックします。
4. 生成されたAPIキーとRESTエンドポイントをコピーします。
5. AppsFlyerにBrazeのAPIキーとRESTエンドポイントを入力します。  ![AppsFlyerにBrazeのAPIキーとRESTエンドポイントを入力](https://files.readme.io/b13aba84c394c0b4603e0aad2edd723525dadf204250349620b571bc47b0ba9d-360001907229.png)
6. <strong>［保存して閉じる］</strong>をクリックします。

設定を保存すると、AppsFlyerは、オーガニックと非オーガニックの各インストールについて、以下のデータをBrazeに送信します。

* Braze Dev\_ID
* メディアソース
* キャンペーン名
* 広告グループ名
* 広告名

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にBrazeへポストバックを自動送信できます。このセクションで、ポストバックの送信を設定します。

 ![デフォルトポストバックセクション](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png) 

アプリをダウンロードしたすべてのユーザーのポストバックをBrazeに送信するには、<strong>［すべてのパートナーまたはオーガニックのイベント］</strong>を選択します。

［**保存**］をクリックします。

> 📘 **Note**
>
> **注意**
>
> AppsFlyerはすべてのイベントを送信しますが、Brazeはオーガニックインストールを集計しないため、Braze APIでは無視されます。

</Accordion>

<Accordion title="計測リンクタブ">

Brazeでは、計測リンクは利用できません。

</Accordion>

<Accordion title="コストタブ">

このパートナーとの連携では、コストデータには対応していません。

</Accordion>

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益データには対応していません。

</Accordion>

<Accordion title="権限タブ">

Brazeでは、権限の設定は利用できません。

</Accordion>

## Brazeでユーザーのアトリビューションデータを確認する

Braze管理画面のInstall Attributionフィルターを使うと、アトリビューションデータに基づいてユーザーを分類できます。

 ![Braze管理画面のInstall Attributionフィルター](https://files.readme.io/7289491d4d301eb38618298536ac5b895a610024bf162c733409d3f50b10b8f4-360001908045.png) 

また、Braze管理画面の各ユーザープロファイルでも、そのユーザーのアトリビューションデータを確認できます。

 ![Brazeのユーザープロファイルに表示されるアトリビューションデータ](https://files.readme.io/d9ee5206a8bf3c092c5297c361cf38b2c77717fbb9638b282032e4fc4c31091e-360001907289.png)

<div data-zendesk-anchors="integration-overview=%E9%80%A3%E6%90%BA%E3%81%AE%E6%A6%82%E8%A6%81 h_01H9FK453A9W5DCPR4X8PR06MZ=%E9%80%A3%E6%90%BA%E3%81%AE%E6%A6%82%E8%A6%81 setting-up-braze=braze%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK453AWXF006KEVKD797QF=braze%E3%81%AE%E8%A8%AD%E5%AE%9A activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FK453AVK4YKF41FEP0YRJN=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FK453AG6AXA7J43X6NGZT1=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FK453ASAKVHT7GV8BG56YS=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF viewing-user-attribution-data-in-braze=braze%E3%81%A7%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B h_01H9FK453AQXG7NNT2841686MJ=braze%E3%81%A7%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B" />
