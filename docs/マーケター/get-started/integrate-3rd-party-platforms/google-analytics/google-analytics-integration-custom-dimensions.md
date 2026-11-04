---
title: Google Analyticsとの連携｜カスタムディメンション
metadata:
  keywords:
    - Analytics
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
  created_at: '2021-12-07T13:34:54Z'
  edited_at: '2026-10-28T09:04:19Z'
  id: 4413033740817
  locale: ja
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/ja/articles/4413033740817
---
> **At a glance:** カスタムディメンションを使用して、Google Analyticsとの連携を設定します。

<div id="custom-dimensions-on-google-analytics" />

## Google Analyticsのカスタムディメンション

AppsFlyerのアトリビューションデータをGoogle Analyticsに送信する方法として、AppsFlyer管理画面ではなく、GA側で設定する方法もあります。

> 🚧 **Important**
>
> **重要**
>
> ただし、次の理由から、カスタムディメンションを使用する方法は**推奨しません**。
>
> * AppsFlyer管理画面からのGoogle Analytics連携は、簡単かつ短時間で設定できるため
> * カスタムディメンションを使用する連携は複雑で、設定ミスが起きやすいため
> * カスタムディメンションを使用するには、AppsFlyer SDKとGoogle Analytics SDKの両方が必要なため
> * カスタムディメンションを使用すると、データの差異が生じる可能性が高くなるため

新しい<Anchor target="_blank" href="/marketers/ja/docs/google-analytics-ga4-integration">Google Analytics連携</Anchor>を使用している広告主は、カスタムディメンションによる方法を使用する必要はありません。

> 📘 **Note**
>
> **注意**
>
> この方法では、アプリにGA SDKを組み込む必要があります。
>
> * <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/android/v4/">Android用GA SDK</Anchor>
> * <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/ios/v3/">iOS用GA SDK</Anchor>

<div id="setting-media-source-as-a-custom-dimension-on-google-analytics" />

### Google Analyticsでのメディアソースのカスタムディメンション設定

Google Analyticsには、ユーザー単位のセグメント分けに使用できる、高機能なカスタムディメンションという機能があります。カスタムディメンションの値はモバイルデバイスから送信されます。これらのディメンションに基づいて、Google Analytics管理画面でレポートが生成されます。

<div id="step-1-define-it-on-google-analytics" />

### 手順1：Google Analyticsでの定義

1. GAメニューから、対象のアプリを選択します。
2. GA管理画面の上部で、<strong><em>［管理］</em></strong>を選択します。
3. <strong><em>［プロパティ］</em></strong>列で、<strong><em>［カスタム定義］</em></strong>を選択します。
4. <strong><em>［カスタムディメンション］</em></strong>を選択します。 ![Google Analyticsの管理パネルのカスタムディメンション](https://files.readme.io/e475ad1eda5b6338825b712e6c8254f245d5339f50ae40e723f465207e124262-4413121542033.png)
5. 新しいディメンションを作成します。名前を<strong>AppsFlyer Media Source</strong>にし、範囲に<strong><em>［ユーザー］</em></strong>を選択します。これにより、複数のセッションにわたってデータが保持されます。 ![ga2.png](https://files.readme.io/b2d85fd068e5523265a2b49b4218234fc77d5896ad41801cbe0e017752763cf2-4413121449873.png)

   各ディメンションにはインデックスが割り当てられます。後でアプリからGA APIを使用する際に必要なため、控えておいてください。この例では、新しいディメンションのインデックスは10です。

   ![ga3](https://files.readme.io/6efc2249ede92291a2aadd16eccbc5b38b580723c6277e3746bdd467de29764a-11179413394193.png)

   同じ手順でもう1つディメンションを作成し、名前を**AppsFlyer Campaign**にします。

<div id="step-2-setting-and-sending-the-data-from-the-app" />

### 手順2：アプリでのデータの設定と送信

まず、AppsFlyer SDKからメディアソースの値を取得します。 `onConversionDataSuccess`メソッドを使って取得できます。

**注意：** SDK V5以降では、コンバージョンデータを取得するメソッド名は`onConversionDataSuccess`です。 SDKバージョン5.0.0より前を使用している場合、メソッド名はAndroidでは`onInstallConversionDataLoaded`、iOSでは`onConversionDataReceived`です。 SDK 5.0.0へのアップグレードを推奨します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/links-to-appsflyer-sdk-release-notes">こちら</Anchor>を参照してください。

次に、Google Analytics SDKを使って、メディアソースをカスタムディメンションに設定します。実装方法は、次のコード例を参照してください。

<Tabs>
<Tab title="Android">

```objectivec
private static Tracker sTracker;
@Override
public void onConversionDataSuccess(Map<String, String> conversionData)
{
  if (conversionData.get("af_status") == "Non-organic")
  {
    String mediaSource = conversionData.get("media_source");
    String campaign = conversionData.get("campaign");
    sTracker.set(Fields.customDimension(10), mediaSource);
    sTracker.set(Fields.customDimension(1), campaign);
  }
  else if (conversionData.get("af_status") == "Organic")
  {
    sTracker.set(Fields.customDimension(10), "Organic");
  }
}
```

</Tab>

<Tab title="iOS">

```objectivec
-(void)onConversionDataSuccess:(NSDictionary*) installData {
  id status = [installData objectForKey:@"af_status"];
  if([status isEqualToString:@"Non-organic"]) {
		id mediaSource = [installData objectForKey:@"media_source"];
		id campaign = [installData objectForKey:@"campaign"];
		[[[GAI sharedInstance] defaultTracker] set:[
				GAIFields customDimensionForIndex:10
			] value: mediaSource];
    [[[GAI sharedInstance] defaultTracker] set:[
				GAIFields customDimensionForIndex:1
			]
			value: campaign];
   }
	 else if([status isEqualToString:@"Organic"]) {
    [[[GAI sharedInstance] defaultTracker] set:[
				GAIFields customDimensionForIndex:10
			]
			value: "Organic"];
   }
}
```

</Tab>
</Tabs>

<div id="step-3-see-the-results-in-google-analytics" />

### 手順3：Google Analyticsでの結果の確認

GAのほとんどのレポートでは、***［カスタムディメンション］***という詳細表示オプションを利用できます。[手順1で設定した](/docs/google-analytics-integration-custom-dimensions#手順1google-analyticsでの定義)***AppsFlyer Media Source***または***AppsFlyer Campaign***を選択すると、どのメディアソースやキャンペーンからアプリをインストールしたユーザーを獲得したか確認できます。

![G_analytics1.png](https://files.readme.io/dde9219a7a8eec5c861b5031ad741ff7377d85ba9c3693bcbc455fd735f8af2d-4413121449617.png)

<div data-zendesk-anchors="custom-dimensions-on-google-analytics=google-analytics%E3%81%AE%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3 h_01HDP3FHGNR06EV1KS8F1PFQ09=google-analytics%E3%81%AE%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3 setting-media-source-as-a-custom-dimension-on-google-analytics=google-analytics%E3%81%A7%E3%81%AE%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%AD%E5%AE%9A h_01HDP3FHGP9H18VJKNSR27HXEZ=google-analytics%E3%81%A7%E3%81%AE%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%AD%E5%AE%9A step-1-define-it-on-google-analytics=%E6%89%8B%E9%A0%861google-analytics%E3%81%A7%E3%81%AE%E5%AE%9A%E7%BE%A9 h_01HDP3FHGPTJ4EVYPDA7RWPJF9=%E6%89%8B%E9%A0%861google-analytics%E3%81%A7%E3%81%AE%E5%AE%9A%E7%BE%A9 step-2-setting-and-sending-the-data-from-the-app=%E6%89%8B%E9%A0%862%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%A8%E9%80%81%E4%BF%A1 h_01HDP3FHGPF3BJZSG6G0QP5T1R=%E6%89%8B%E9%A0%862%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%A8%E9%80%81%E4%BF%A1 step-3-see-the-results-in-google-analytics=%E6%89%8B%E9%A0%863google-analytics%E3%81%A7%E3%81%AE%E7%B5%90%E6%9E%9C%E3%81%AE%E7%A2%BA%E8%AA%8D h_01HDP3FHGP9G9BP956KM4ACDRC=%E6%89%8B%E9%A0%863google-analytics%E3%81%A7%E3%81%AE%E7%B5%90%E6%9E%9C%E3%81%AE%E7%A2%BA%E8%AA%8D" />
