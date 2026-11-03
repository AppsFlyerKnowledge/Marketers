---
title: 受信パートナー接続 - Braze
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-17T09:55:26Z'
  edited_at: '2026-10-14T09:28:38Z'
  id: 4411130243217
  locale: ja
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ja/articles/4411130243217
---
> **概要:** BrazeメッセージエンゲージメントイベントをAppsFlyer オーディエンスに送信し、それによりオーディエンス定義の精度を高めます。

BrazeアカウントとAppsFlyer オーディエンスの間に着信接続を設定することで、Brazeメッセージエンゲージメントイベントデータをオーディエンスに取り込めます。その後、オーディエンスを定義する際に、このデータを<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#all-about-rulesets">ルールセット</Anchor>で活用できます。

> 🚧 **前提条件**
>
> * Braze SDKとAppsFlyer SDKの両方をアプリに統合する必要があります。
> * Brazeの**Currents**機能にサブスクライブする必要があります。

## Brazeの着信接続を設定する

Braze着信接続の設定は主に3つのステップから成ります。

1. [AppsFlyer SDKを設定する](/docs/audiences-use-braze-events-in-audience-creation#set-up-the-appsflyer-sdk)
2. [AppsFlyerで受信接続を作成する](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer)
3. [BrazeでCurrentsを作成する](/docs/audiences-use-braze-events-in-audience-creation#create-a-current-in-braze)

<div id="set-up-the-appsflyer-sdk" />

<Accordion title="AppsFlyer SDKをセットアップする">

Brazeからの着信接続を作成するには、アプリ内のAppsFlyer SDKを各ユーザーの**Braze外部ID**をAppsFlyerに渡すように設定する必要があります。次のいずれかの方法でこれを行えます。

* Braze External ID パラメータ
* CUIDフィールド

#### **Braze外部IDパラメータを利用する**

AppsFlyer SDKの`setPartnerData`関数を使用して、Braze外部IDをAppsFlyerに渡すための専用パラメータを設定できます。使用例は次のとおりです。

<Tabs>
<Tab title="Android">

```java
Map<String, Object> brazeData = new HashMap<>();
partnerData.put("external_user_id", "some-braze-external-id-value");
AppsFlyerLib.getInstance().setPartnerData("braze_int", brazeData);
```

</Tab>

<Tab title="iOS">

```objectivec
NSDictionary *brazeInfo = @{
@"external_user_id":@"some-braze-external-id-value"
};
[[AppsFlyerLib shared] setPartnerDataWithPartnerId:@"braze_int"
partnerInfo:brazeInfo];
```

</Tab>
</Tabs>

#### **CUIDフィールドの利用**

以下の場合、Braze外部ID専用のパラメータを設定する必要はありません:

* SDKを設定して、AppsFlyerに各ユーザーの<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">CUID</Anchor>を送信しています。
* CUIDはBraze外部IDと同じ値を持っています。

この場合は、[受信Braze接続を作成する](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer)際に、SDKパラメータとして**CUIDオプション**を選択するだけです。

</Accordion>

<div id="create-an-incoming-braze-connection-in-appsflyer" />

<Accordion title="AppsFlyerで受信Braze接続を作成する">

**AppsFlyerで着信接続を作成するには、次のステップに従ってください:**

1. AppsFlyerのサイドメニューから、**エンゲージ** > **オーディエンス**を選択します。
2. [オーディエンス]ページで、**[接続] > [受信]** **タブ**に移動します。
3. **[新しい着信接続]** ボタンをクリックします。
4. 利用可能なパートナーのリストからBrazeを選択します。
5. [**保存**] ボタンをクリックして接続を作成します。  
   **接続資格情報**ダイアログが開きます。
6. BrazeプラットフォームでAppsFlyerオーディエンスへの接続を設定するときに使用する接続資格情報をコピーします。
   * アクセスキーID
   * 秘密アクセスキー
   * バケット名
   * フォルダパス
7. Braze 外部ID を送信するために使用しているSDKパラメータを選択します。
   * Braze 外部ID
   * CUID

</Accordion>

<div id="create-a-current-in-braze" />

<Accordion title="Braze でCurrentを作成する">

**Braze で Current を作成するには、次の手順に従います。**

1. 左側のメニューバーの [**連携**] セクションに移動します。
2. [**Currents**] をクリックします。
3. [**現在を作成**] ボタンをクリックします。
4. **Amazon S3 データエクスポート**を選択します。
5. **Currents 連携の作成** セクションで次の操作を行います。
   1. 現在の名前を入力します (例: AppsFlyer オーディエンス)。
   2. Current の資格情報に問題が発生した場合に Braze が通知するチームメンバーのメールを入力します。
6. **認証情報**セクションで次の操作を行います。
   1. **AWS シークレットアクセスキー**のオプションを選択したままにします (これがデフォルト値です)。
   2. AppsFlyerからコピーした資格情報を適切なフィールドに入力します。
   3. [**暗号化を有効にする**] オプションはオフのままにしておきます。
7. [**全般設定**] で、[**匿名ユーザーからのイベントを含める**] をオンにしておきます。
8. **メッセージエンゲージメントイベント**セクションで、Braze からAppsFlyerに送信するイベントを選択します。サポートされているイベントのリストについては、[以下](/docs/audiences-use-braze-events-in-audience-creation#サポートされているイベント)を参照してください。
9. [カスタマー行動とユーザーイベント] セクションで、[**カスタマー行動とユーザーイベントを追跡する**] オプションをオフのままにします。
10. [**現在の起動**] ボタンをクリックして設定を保存し、Brazeメッセージエンゲージメントイベントをオーディエンスに送信し始めます。

#### サポートされているイベント

> 📘 **サポートされているBrazeイベント**
>
> * サブスクリプション グループの状態の変更
> * メールのクリック
> * メールを開く
> * メール送信
> * メール配信
> * メールをスパムとしてマーク
> * メール購読解除
> * メールバウンス
> * メールソフトバウンス
> * プッシュオープン
> * プッシュ送信
> * プッシュバウンス
> * iOSフォアグラウンドプッシュ
> * SMS\/MMS送信

</Accordion>

## オーディエンスで Braze データを利用する

Braze の着信接続が設定されると、定義したエンゲージメントイベントが、オーディエンスを定義するための[ルールセット フィルター](/docs/audiences-use-braze-events-in-audience-creation/%20/docs/audiences-guide#all-about-rulesets)のオプションとして表示されます。

[altオーディエンス\_braze\_ruleset.pngalt](https://support.appsflyer.com/hc/article_attachments/30205809793937)

**注:** Braze で現在のイベントを開始してから、BrazeメッセージエンゲージメントイベントがAppsFlyerで利用できるようになるまでに約24時間かかります。

<div data-zendesk-anchors="h_01HKW0BS5H5FS7MXZPHBARK3VR=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 set-up-the-braze-incoming-connection=braze%E3%81%AE%E7%9D%80%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01HKW0BS5H1ANWAJZTVBWDQHJH=braze%E3%81%AE%E7%9D%80%E4%BF%A1%E6%8E%A5%E7%B6%9A%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01HKW0BS5HKREHBKPMQ25AYTMH=set-up-the-appsflyer-sdk using-a-braze-external-id-parameter=braze%E5%A4%96%E9%83%A8id%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%99%E3%82%8B h_01HKW0BS5HGB2RYGWNXT1M163C=braze%E5%A4%96%E9%83%A8id%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%99%E3%82%8B using-the-cuid-field=cuid%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%81%AE%E5%88%A9%E7%94%A8 h_01HKW0BS5HQJZRR60VKBCWGHQB=cuid%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%81%AE%E5%88%A9%E7%94%A8 h_01HKW0BS5H6P7WTT6XBYF7HP3X=create-an-incoming-braze-connection-in-appsflyer h_01HKW0BS5J83HMXPWB6VNKD6P1=create-a-current-in-braze supported-events=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HKW0BS5JM8A9XFVX22KWFE3H=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HKW0BS5J6V57BDHKRY9A5XZE=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8Bbraze%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 using-braze-data-in-audiences=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%81%A7-braze-%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%99%E3%82%8B h_01HKW0BS5JTZQ71HFE305ZT1CS=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%81%A7-braze-%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%99%E3%82%8B" />
