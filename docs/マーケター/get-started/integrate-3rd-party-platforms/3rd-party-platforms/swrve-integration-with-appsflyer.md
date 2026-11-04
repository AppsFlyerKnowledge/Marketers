---
title: SwrveとAppsFlyerの連携
metadata:
  keywords:
    - Swrve
    - Adobe Analytics
    - 3rd Party
    - SDK
    - Integration
    - integrated partner
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
  created_at: '2015-12-24T11:46:00Z'
  edited_at: '2026-10-28T09:03:52Z'
  id: 207040656
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/207040656
---
> **At a glance:** AppsFlyerの連携済みパートナーであるSwrveは、プラットフォームを横断した顧客コミュニケーションの基盤です。次の機能により、対象ユーザーに合った、最適なコミュニケーションを実現します。

* アプリの主要コンテンツの動的な最適化とテスト
* アプリ内メッセージとプッシュ通知のキャンペーン
* メール

SwrveはAppsFlyerとの連携により、ユーザー獲得から継続利用までを一貫して支援し、開発費とユーザー獲得費のROIを最大化するとともに、アプリの利用を通じて優れたユーザー体験を提供します。両プラットフォームで共有する獲得元に応じてアプリでの体験をカスタマイズすることで、ユーザーが初めてアプリを開いたときから、そのユーザーの流入経路や行動に合ったコンテンツを表示できます。

この連携では、REST APIを使ってインストールをSwrveのAPIに通知します。そのため、各モバイルアプリについて、AppsFlyerアカウントでサーバーポストバックを設定する必要があります。

> 🚧 **Important**
>
> **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="integrating-swrve-and-appsflyer" />

## SwrveとAppsFlyerを連携する

Swrveで獲得元別のLTVとユーザー行動を計測できるように、ポストバックを設定します。

**手順1**：Swrveを初期化した後、AppsFlyer SDKを呼び出す前に、次のコードでユーザーIDを設定します。

<Tabs>
<Tab title="Androidの場合">

```java
AppsFlyerLib.setCustomerUserId(SwrveSDK.getUserId());
```

</Tab>

<Tab title="iOSの場合">

```objectivec
NSString* swrve_user_id = [[Swrve sharedInstanceWithAppID:appId apiKey:apiKey] userID];
[[AppsFlyerTracker sharedTracker].customerUserID = swrve_user_id];
```

</Tab>

<Tab title="Unityの場合">

```swift
Appsflyer.setCustomerUserID(SwrveComponent.Instance.SDK.UserId);
```

</Tab>
</Tabs>

**手順2**：AppsFlyer管理画面で、次の操作を行ってポストバックを設定します。

<div id="setting-up-swrve" />

## Swrveの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。  
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

Swrveの設定で使用するのは、<strong>［連携］</strong>タブのみです。

パートナー設定画面のヘッダーについて詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>を参照してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

<div id="activate-partner" />

### パートナーを有効化

<strong>初めて設定する場合</strong>は、<strong><em>［パートナーを有効化］</em></strong>をオンにすると、［連携］タブのパラメータを設定できます。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>を参照してください。

<div id="general-settings" />

### 一般設定

**アプリIDとAPIキー**

SwrveとAppsFlyerの接続には、固有のアプリIDとAPIキーを使用します。まだ取得していない場合は、連携の設定を進める前にSwrveから取得してください。

![Swrve_msc_new_3.png](https://files.readme.io/feb1d5f846629d1909727b70b66e4b36138704ebbe4518e2dc03652b9fe5c57a-360001902065.png)

必要に応じて、以下の手順を実施します。

* **APP\_ID**を入力します。
* **api\_key**を入力します。
* EUのお客様は**EU**を選択します。
* 次の追加情報をSwrveに送信するには、<strong>［拡張データ共有］</strong>を選択します：cost\_value、channel、keywords、siteID、c（キャンペーン）。

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にSwrveへポストバックを自動送信できます。このセクションで、ポストバックの送信を設定します。

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

アプリをダウンロードしたすべてのユーザーのポストバックをSwrveに送信するには、［**すべてのパートナーまたはオーガニックのイベント**］を選択します。

［**保存**］をクリックします。

保存すると、AppsFlyerはオーガニックと非オーガニックのすべてのインストールについて、次のデータをSwrveに送信し始めます。

* api\_key
* SDKで設定したSwrveユーザーID
* メディアソース
* キャンペーン名

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Swrveでは、計測リンクは利用できません。

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

Swrveでは、権限の設定は利用できません。

</Accordion>

<div id="swrve-reporting-with-appsflyer-data" />

## AppsFlyerのデータを使用したSwrveのレポート

AppsFlyerからSwrveにアトリビューション情報を送信するサーバーポストバックを設定すると、Swrveで獲得データを確認し、Swrveのターゲティング・テスト機能をすべて活用できます。

アプリのメインダッシュボードでは、重要な情報をひと目で確認できます。メインのナビゲーションバーで該当するタブを選択すると、テスト、ターゲティング、レポートの各機能を利用できます。

![Swrveダッシュボードの獲得グラフ](https://files.readme.io/6a3e4cf709f58b20f2932ab47e6fa9289653504d85a0b6eec2580718e2a4dc7c-49839257162769.png)
![Swrveダッシュボードの獲得データ表](https://files.readme.io/561403abefae9e98e24934c96dd25b1ee34ae24cf30695354c4930404e0a7f19-49839257163537.png)

<div data-zendesk-anchors="integrating-swrve-and-appsflyer=swrve%E3%81%A8appsflyer%E3%82%92%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B h_01H9HWK5DM1K9P5XXC6S7ENAGV=swrve%E3%81%A8appsflyer%E3%82%92%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B setting-up-swrve=swrve%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWK5DMS8HAK25BF5EXZT51=swrve%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWK5DN9D0DS46X72EDAW54=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9HWK5DN375XJVHQCZ8Y3K13=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9HWK5DN0XK2E0HXS61GRECE=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9HWK5DNH6SYY8T9NX09MRYS=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9HWK5DNZVQDZ0Q1Z9WSKRSR=attribution-link-tab h_01H9HWK5DNPG89HSB0107TKHED=cost-tab h_01H9HWK5DNARD4K0MPHPXKBPXZ=ad-revenue-tab h_01H9HWK5DNFKAT0J98JWVRPQ1G=permissions-tab swrve-reporting-with-appsflyer-data=appsflyer%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9Fswrve%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01H9HWK5DN3QB9V593EV566GAQ=appsflyer%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9Fswrve%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88" />
