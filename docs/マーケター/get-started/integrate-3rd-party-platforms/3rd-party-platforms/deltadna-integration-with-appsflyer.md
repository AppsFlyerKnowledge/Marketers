---
title: deltaDNAとAppsFlyerの連携
metadata:
  keywords:
    - deltaDNA
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
  created_at: '2016-09-04T06:41:51Z'
  edited_at: '2026-10-28T09:02:59Z'
  id: 212247706
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/212247706
---
> **At a glance:** AppsFlyerの連携済みパートナーであるdeltaDNAは、モバイルゲーム向けのリアルタイム分析・マーケティングプラットフォームです。詳細なデータ分析機能、高速な処理性能、柔軟でオープンな環境を組み合わせ、プレイヤーのセグメント分け、予測モデル、対象ユーザーに応じたリアルタイムの働きかけによって、エンゲージメントと顧客生涯価値を高めることができます。

> 🚧 **Important**
>
> **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="integrating-with-deltadna" />

## deltaDNAとの連携

> 🚧 **Important**
>
> **重要**
>
> AppsFlyerから受信したアトリビューションデータを正しいユーザーに紐付けるため、deltaDNA SDKのuserIDをAppsFlyer SDKのカスタマーユーザーIDに設定する必要があります。userIDが自動生成されたものでも、ゲーム側から指定されたものでも同様です。この設定は、deltaDNA側のLIVE環境に接続するゲームのビルドにのみ適用してください。

1. 独自のユーザーIDを使用し、AppsFlyerのcustom\_user\_idパラメータとdeltaDNAのuserパラメータの両方に設定している場合、コードの追加実装は不要です。
2. 独自のユーザーIDを使用していない場合は、deltaDNAのuserIDプロパティを取得し、AppsFlyer SDKの**customer\_user\_id**パラメータに設定する必要があります。以下のコードは、両方のSDKを初期化した後に実装してください。

<Tabs>
<Tab title="Android">

```java
AppsflyerLib.getInstance().setCustomerUserId(DDNA.instance().getUserId())
```

</Tab>

<Tab title="iOS">

```objectivec
[AppsFlyerTracker sharedTracker].customerUserID = [DDNASDK sharedInstance].userID;
```

</Tab>

<Tab title="Unity">

```swift
AppsFlyer.setCustomerUserID (DDNA.Instance.UserID)
```

</Tab>
</Tabs>

以下の手順でdeltaDNAとの連携を設定します。

**deltaDNA側の設定：**

1. deltaDNAのEvent Managementツールで、AppsFlyerAttributionイベントを作成します。

![Delta DNA 1](https://files.readme.io/e5224bbaa730d997699e1a930425946f69a2b86ef94e241b4ba6fdb9ad978c66-206781083.png)

2. deltaDNA管理画面のGame Detailsページで、Live環境のキーを取得します。

![Delta DNA 2](https://files.readme.io/6b28184264dfd695000e8bfae9538862a3e17ea6f9d355af0996ccf107b4e6c2-206768886.png)

**AppsFlyerで連携を有効化または編集します。**

1. **有効化する場合：** AppsFlyerのサイドメニューで<strong>［連携］</strong>＞<strong>［パートナー連携＞マーケットプレイス］</strong>タブを選択します。  
   **編集する場合**：AppsFlyerのサイドメニューで<strong>［連携］</strong>＞<strong>［パートナー連携＞有効な連携］</strong>タブを選択します。
2. **deltaDNA**を検索して選択します。
3. <strong>［連携を設定］</strong>をクリックします。連携設定ページが開きます。
4. <strong>［連携］</strong>タブで連携するアプリを選択し、<strong>［パートナーを有効化］</strong>をオンにします。  
   **注意：** このパートナーと連携している間は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">オン（有効）</Anchor>のままにしてください。
5. deltaDNAコンソールから取得したEnviorment\_keyを入力します（セクション2を参照）。
6. <strong>［送信オプション］</strong>を<strong>［オーガニックを含むすべてのメディアソース］</strong>に設定します。
7. ［**連携を保存**］をクリックします。

設定を保存すると、AppsFlyerは、オーガニックと非オーガニックの各インストールについて、以下のデータをdeltaDNAに送信します。

* 環境キー
* User ID
* インストール時刻
* メディアソース
* キャンペーン名

> 📘 **Note**
>
> **注意**
>
> カスタマーユーザーIDまたはUserIDが定義されていない場合、deltaDNAはAppsFlyerからのインストールポストバックを拒否します。

<div id="viewing-the-attribution-data-in-the-deltadna-console" />

## deltaDNAコンソールでアトリビューションデータを確認する

AppsFlyerから受信したアトリビューションデータは、以下に使用できます。

* Measureチャートでの絞り込み
* カスタムダッシュボードやレポートの作成
* 詳細な分析の実施
* 独自のプレイヤーセグメントを作成し、対象のプレイヤーに合ったキャンペーンやオファーを配信します。

すべてのMeasureチャート、継続率マトリクス、LTV、継続率予測ツールの上部にあるAcquisition Channelフィルターは、AppsFlyerのメディアソースに基づいています。

![Delta DNA 3](https://files.readme.io/21cf4f1c8641351a1ecc200d8b95d7558b92f4daf38f49975601d996a0fcfb86-206781123.png)

AppsFlyerからdeltaDNAに送信できるアトリビューションパラメータは8つあり、分析、レポート、クエリに使用できます。いずれも**afAttrで始まります。**   
*例：キャンペーンはafAttrCampaign、代理店はafAttrAgency、メディアソースはafAttrMediaSourceです。*

すべてのアトリビューションパラメータは、Event Management画面に追加された**appsFlyerAttribution**に一覧表示されます。

![Delta DNA 4](https://files.readme.io/e0af8513fdda3268ab799a6ef08396c03970bd0850bde851f07649e459a8b20e-206781143.png)

deltaDNAの各Analyzeツールで、これらのパラメータを使って独自の分析クエリやレポートを作成できます。

![Delta DNA 5](https://files.readme.io/f4b9d0320feb3990182a0c9a835a18565ba959fabf7269c45a4651506666f941-206768946.png)

<div data-zendesk-anchors="integrating-with-deltadna=deltadna%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA h_01H9FK6N8V597T8AY0RF0H6CZW=deltadna%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA viewing-the-attribution-data-in-the-deltadna-console=deltadna%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%81%A7%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B h_01H9FK6N8W8011X3JVG2EZ66H4=deltadna%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%81%A7%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B" />
