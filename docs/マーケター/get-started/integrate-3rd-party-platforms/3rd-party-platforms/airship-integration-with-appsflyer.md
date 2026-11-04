---
title: AirshipとAppsFlyerの連携
metadata:
  keywords:
    - Attribution
    - SDK
    - Configure
    - urban airship
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
  created_at: '2015-12-16T11:31:38Z'
  edited_at: '2026-10-28T09:02:37Z'
  id: 207033976
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/207033976
---
> **概要：** AppsFlyerの連携済みパートナーであるAirshipは、世界をリードするモバイルエンゲージメントプラットフォームです。規模を問わず数千社の企業が、顧客と直接つながり、継続的な関係を築けるよう支援しています。 Airshipでは、アプリ、ウォレット、ユーザーレベルのデータなど、モバイル施策全体を一元的に管理できます。モバイルをはじめとするさまざまな顧客接点で、ユーザーの関心を引き、行動につながる体験を提供できます。

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="setting-up-airship" />

## Airshipの設定

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

<div id="activate-partner" />

### パートナーを有効化

**初めて設定する場合**は、<strong>［パートナーを有効化］</strong>をオンにすると、［連携］タブのパラメータを設定できます。**パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります**。  
詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効化</Anchor>を参照してください。

<div id="general-settings" />

### 一般設定

AirshipとAppsFlyerの連携には、一意のApp Keyとトークンを使用します。まだ取得していない場合は、以下の手順を参考に、Airshipから取得してください。

![airship-integration-tab.png](https://files.readme.io/dc33feec09fe551700586b9778a037fa0f5d610224944aea5a0fe56a6d288043-360017400878.png)

**Airshipとの連携の設定手順は、以下のとおりです。**

AppsFlyer SDKの最低要件：

* Android：V2.3.1.18以降
* iOS：V3.3.3以降

Airship SDKの最低要件：V13.1.0以降。

1. Airshipとの連携には、AppsFlyer SDKにchannelid（Airshipでユーザーを一意に識別するID）を設定する必要があります。

   * [iOSのChannel IDの詳細](https://docs.airship.com/platform/ios/segmentation/#airship-channel-ids)。
   * [AndroidのChannel IDの詳細](https://docs.airship.com/platform/android/segmentation/#airship-channel-ids)。

   このパラメータはすべてのポストバックに含まれ、ユーザーの識別に使用されます。アプリのコードに、以下のコードを追加してください。

   <div id="important-note" />

   > 📘 **重要な注意事項**
   >
   > コードを追加する位置に注意してください。iOS、Androidともに、Airship SDKの起動後、startメソッドを呼び出す前に追加します。


   <Tabs>
   <Tab title="Android">

   `setAdditionalData`メソッドの詳細は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">こちら</Anchor>を参照してください。

   ```java
   HashMap<String, Object> customData = new HashMap<String,Object>();
   String channelId = UAirship.shared().getChannel().getId();
   customData.put("channelid", channelId);
   AppsFlyerLib.getInstance().setAdditionalData(customData);
   ```

   </Tab>

   <Tab title="iOS">

   `setAdditionalData`メソッドの詳細は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">こちら</Anchor>を参照してください。

   ```objectivec
   let channelID = UAirship.channel().identifier
   print("My Application Channel ID: \(channelID)")
   ```

   </Tab>
   </Tabs>

2. AirshipからのApp Keyの取得
   1. [go.airship.com](http://go.urbanairship.com/)からAirshipアカウントにログインします。
   2. 左側のメニューで**Settings＞** **APIs &** **Integrations**に進み、**Airship API**をクリックします。

      ![airship-appkey-en_us.png](https://files.readme.io/c33611035d8dcadb73e41a3787690726608bddde55edbc38f34990c03948985d-360017666917.png)
   3. App Keyをコピーします。
   4. AppsFlyerの［App Key］欄に貼り付けます。
3. Airshipからのトークンの取得
   1. [go.airship.com](http://go.urbanairship.com/)からAirshipアカウントにログインします。
   2. 左側のメニューで**Settings＞** **APIs &** **Integrations**に進み、**Tokens**をクリックします。

      ![airship-token-creation-1.png](https://files.readme.io/b0c22d9844dbc93f7dd158a75916eca98404474a65be0c1528f83e6e4ac7b210-360017480697.png)
   3. ［**トークンを作成**］をクリックします。

      ![airship-token-creation-2.png](https://files.readme.io/656f6f5a6eebe3ccd1a786f6abec62739633e4150722fec41bc1fbdea78f8275-360017549138.png)
   4. トークン名を入力し、ロールを選択します。
   5. ［**トークンを作成**］をクリックします。
   6. AppsFlyerの［**トークン認証**］欄にトークンを貼り付けます。

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、インストールやリエンゲージメントの発生時に、Airshipへポストバックを自動送信できます。このセクションでは、ポストバックを送信する**対象ユーザーの流入元**を指定します。

![urban_airship_msc_new_3.png](https://files.readme.io/394dd47ff26742092f3012e333f137d706f41bc85cd6875013d792ce7f36b01d-360001900305.png)

アプリをダウンロードしたすべてのユーザーのポストバックをAirshipに送信するには、［**すべてのパートナーまたはオーガニックのイベント**］を選択します。

設定を保存すると、AppsFlyerは、オーガニックと非オーガニックの各インストールについて、以下のデータをAirshipに送信します。

* デバイスID（IDFA／Google広告ID）
* メディアソース
* キャンペーン名

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Airshipでは、計測リンクは利用できません。

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

Airshipでは、権限の設定は利用できません。

</Accordion>

<div id="set-up-and-manage-the-attribution-data-in-airship-console" />

## Airshipの管理画面でのアトリビューションデータの設定と管理

Airshipの属性は、オーディエンスに紐付けるキーと値の組み合わせです。ユーザーに応じてメッセージを届けるために使用します。属性を使うと、タグを使う場合よりも細かくオーディエンスを絞り込めます。

AirshipでAppsFlyerのアトリビューションデータを設定するには、[プロジェクトに属性を個別に追加](https://docs.airship.com/partners/appsflyer/#setting-attributes-for-integration)します。

<div data-zendesk-anchors="h_01H9FJYKH3V1TZ4GYEKKG46F2S=%E9%87%8D%E8%A6%81 setting-up-airship=airship%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FJYKH3SWMNC8CRPPDQMCGQ=airship%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FJYKH4KQMK2N5BTTFTY076=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FJYKH4NTCNVKBW9XSENFTP=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FJYKH4MMRE57BNEBD0P5NT=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FJYKH4H93Q5S41HK7S4RD6=%E9%87%8D%E8%A6%81%E3%81%AA%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FJYKH44F4YQSEPKTGN7EYK=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FJYKH44S8F34YJ97TE32PM=attribution-link-tab h_01H9FJYKH47DYTR8T197CEXH0Z=cost-tab h_01H9FJYKH46AC5X7F6GAD9MQJG=ad-revenue-tab h_01H9FJYKH4N4T5JTGWHQC0A18Z=permissions-tab set-up-and-manage-the-attribution-data-in-airship-console=airship%E3%81%AE%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%A8%E7%AE%A1%E7%90%86 h_01H9FJYKH4Q09JSBJ25RRE02Y3=airship%E3%81%AE%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%A8%E7%AE%A1%E7%90%86" />
