---
title: Adobe AnalyticsとAppsFlyerの連携
metadata:
  keywords:
    - Adobe Analytics
    - Integration
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-07-05T07:20:10Z'
  edited_at: '2026-10-14T09:29:13Z'
  id: 115003326706
  locale: ja
  section: Adobe
  section_id: 6551419728657
  url: https://support.appsflyer.com/hc/ja/articles/115003326706
---
> **概要：** [Adobe Analytics](http://www.adobe.com/marketing-cloud/web-analytics.html) (旧：Omniture) は、サードパーティのソースに統合可能な予測分析およびリアルタイム分析のためのツールです。Marketing ReportsとAnalytics（SiteCatalyst）、アドホック分析 (Adobe Discover)、Insightの各アプリケーションが含まれており、お客様のインタラクションをインサイトに変換することで、ビジネス活動の全体像を把握することができます。

<div id="overview" />

## 概要

この連携は、AdobeとAppsFlyerの間の双方向のデータフローで構成されています。この連携が正常に機能するには、アプリ内でのコード実装が必要です。連携には、AppsFlyerとAdobeの両方の要件を満たす必要があります。

<div id="setting-up-adobe-analytics-integration" />

## Adobe Analyticsとの連携設定

キャンペーン全体のパフォーマンス分析やセグメント作成にAdobe Analytics Report Suiteを使用している場合、AppsFlyerとAdobe Analyticsの連携により、AppsFlyerからAdobeへアトリビューションデータを自動的に転送することができ、キャンペーンの目標達成に役立ちます。

<div id="prerequisites" />

### 前提条件：

* <Anchor target="_blank" href="https://developer.adobe.com/client-sdks/documentation/">Adobe Experience Platform モバイルSDKドキュメント</Anchor>の設定
* Marketing Cloud Visitor ID または ExperienceクラウドIDサービスを利用している
* 各レポートスイートに、今回の連携のみを目的として使用できる3つのeVarを用意する必要があります。

<div id="step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer" />

### ステップ1：Adobe Experience Cloud ID（ECID、Marketing Cloud ID、またはVisitor ID）をAppsFlyerへ共有

Adobe Experience Cloud IDを抽出・共有する：

1. Adobe SDKが初期化された直後に<Anchor target="_blank" href="https://developer.adobe.com/client-sdks/documentation/mobile-core/identity/api-reference/#getexperiencecloudid">アプリを更新し、Adobe SDKのメソッドを使用してMarketing Cloud Visitor ID</Anchor>を抽出します。
2. 以下のAppsFlyer SDKのメソッドのいずれかを使用して、Adobe Marketing Cloud Visitor IDを設定します：

<div id="setadditionaldata" />

<Accordion title="setAdditionalData">

<Tabs>
<Tab title="Android">

詳細は [setAdditionalDataメソッド](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata)をご覧ください。

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
customData .put("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyerLib.setAdditionalData(customData);
```

</Tab>

<Tab title="iOS">

詳細は [setAdditionalDataメソッド](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata)をご覧ください。

Objective C

```objectivec
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{
  @"marketingCloudID" : "ADOBE_VISITOR_ID"
}];
```

Swift

```swift
let CustomDataMap: [AnyHashable: Any] = [
  "marketingCloudID" : "ADOBE_VISITOR_ID"
]
AppsFlyerTracker.shared().customData = CustomDataMap
```

</Tab>

<Tab title="Unity">

詳細は [setAdditionalDataメソッド](https://dev.appsflyer.com/hc/docs/api#setadditionaldata)をご覧ください。

```csharp
Dictionary<string, string> CustomDataMap = new Dictionary<string, string>();
CustomDataMap.Add("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyer.setAdditionalData(CustomDataMap);
```

</Tab>
</Tabs>

</Accordion>

<div id="setcustomeruserid" />

<Accordion title="setCustomerUserId">

<Tabs>
<Tab title="Android">

詳細：  <Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">setCustomerUserId</Anchor>  <Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">メソッド</Anchor>

```java
AppsFlyerLib.getInstance().setCustomerUserId("ADOBE_VISITOR_ID");
```

</Tab>

<Tab title="iOS">

詳細： <Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">setCustomerUserId メソッド</Anchor>

Objective C

```objectivec
NSString *customerUserID = [AppsFlyerLib shared].customerUserID;
```

Swift

```swift
let customerUserID = AppsFlyerLib.shared().customerUserIDp
```

</Tab>
</Tabs>

</Accordion>

<div id="step-2-configure-adobe-analytics-in-appsflyer" />

### ステップ2：AppsFlyerでAdobe analyticsを設定する

**前提条件：** 連携を設定する前に、[Adobe Marketing Cloud Visitor IDをAppsFlyer SDKに渡している](/docs/adobe-analytics-integration-with-appsflyer#ステップ1adobe-experience-cloud-idecidmarketing-cloud-idまたはvisitor-idをappsflyerへ共有)ことを確認してください。

**連携を有効化または編集する：**

1. **連携を有効に設定する：** AppsFlyer管理画面 左メニュー **連携** > パートナーマーケットプレイスへ移動します。  
   **連携設定を変更する：** AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**へ移動します。
2. **Adobe Analytics** を検索して選択します。
3. **連携の設定**をクリックします。連携設定ページに移動します。
4. **連携**タブで、連携アプリを選択し、**パートナーの有効化**をオンにします。  
   **注： パートナーとの作業中はトグルをオン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（アクティブ化）</Anchor>にしておいてください。**
5. **Adobe Analytics SDK**から、**ADBMobileConfig.XML** ファイルの一部として、**Report\_Suite\_ID**（青でハイライト）と **Adobe\_Analytic\_server\_URL**（緑でハイライト）をコピーし、AppsFlyer の Adobe Analytics 連携画面の各項目に貼り付けてください。  

   <Image align="center" alt="" src="https://files.readme.io/fb46a40178b88dc8f8fb0f9bcce5aa289fc27c2dbf52d1e67783c7b764729f0f-360001063605.png" />
6. **連携を保存**をクリックしてください。

保存すると、AppsFlyerは、オーガニックおよび非オーガニックインストールを計測したたびに、Adobe Analyticsに以下のデータを送信します：

* Adobe ID （MCVID）
* Report Suite ID & Server URL
* Customer Device ID
* Media Source
* Campaign Name

<div id="note" />

> 📘 **注意**
>
> MetaとX広告は、媒体の利用規約に基づき、AppsFlyerはユーザーレベルのデータを第三者と共有することを禁じられています。これは、Meta広告と X広告のインストールがオーガニックとして送信されることを意味します。

<div id="step-3-map-data-to-evars-in-adobe-analytics" />

### ステップ3：Adobe AnalyticsでデータをeVarsにマッピングする

Adobe Analytics Data Connectorsが廃止されたため、処理ルールを活用してコンテキスト変数をeVarsに対応させる必要があります。

詳しくはこちら： [処理ルールの使い方](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html?lang=en)

AppsFlyerのコンテキストデータ変数は、これに応じてマッピングされます：

* MobileAdCampaign (Context Data)
* MobileAdNetwork (Context Data)
* MobileAdProvider (Context Data)

処理ルールによるAppsFlyerコンテキストデータ変数のマッピングに問題がある場合は、Adobeアカウントチームへお問い合わせください。

<div id="step-4-optional-set-up-your-marketing-channel" />

### ステップ 4 [オプション]：マーケティングチャネルを設定する

彼らのプラットフォームでマーケティング チャネルを設定する方法については、<Anchor target="_blank" href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-channels.html">Adobe Analyticsドキュメント</Anchor>を参照してください。識別ルールの下で次のフィールドを選択してください：

1. "Adobe のウェブビーコンによって設定されたコンバージョン変数の値："**AppsFlyer** と **Exists** を選択します。
2. "チャネルを次のように識別します："**モバイルアプリのアトリビューション** を選択します。
3. "チャネルの値を次のように設定します："**AppsFlyer キャンペーン** を選択します。

<div id="domain-and-security-details" />

## ドメインとセキュリティの詳細

ドメインの詳細とセキュリティ上の問題については以下の通りです：

1. ANALYTIC\_SERVER\_DOMAINは、アプリのConfigファイルの中のサーバー変数として見つけることができます。アトリビューション分析には、任意のドメインを選択できます。一般的には、sc.omtrdc.netのようなAdobe Analyticsコレクションサービスの標準的なドメインが使用されます。これは、アナリティクス（サーバー）の設定の **ADBMobile.config** ファイルにあります。
2. URLのプロトコル (HTTP/HTTPS) は、ANALYTICサーバのドメインが安全かどうかによって異なります。正しいプロトコルを使用することが重要です。設定が安全であるかどうかは、**ADBMobile.config** ファイルで、アナリティクス（SSL）の設定が **true** になっているかどうかを確認してください。接続が安全な場合は HTTPS を、安全でない場合は HTTP を使用してください。
3. REPORT SUITE IDは、アプリのConfigファイルにある **rsids**変数で確認できます。レポートスイートには任意の名前をつけることができます。
4. ts=`{timestamp}` は、Configファイルで **offlineEnabled** の設定が true の場合にのみ使用されます。**offlineEnabled** が False に設定されている場合や、レポートスイートが **Time Stamp** を有効にしていない場合は、このパラメーターをURLから削除してください。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HA4ZWDM1MEW2VDFXYMAJ2QE2=%E6%A6%82%E8%A6%81 setting-up-adobe-analytics-integration=adobe-analytics%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HA4ZWDM11RJ6GRJ7W8QMFACT=adobe-analytics%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A prerequisite=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HA4ZWDM1YK58Q56Y0S8PC1E2=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971adobe-experience-cloud-idecidmarketing-cloud-id%E3%81%BE%E3%81%9F%E3%81%AFvisitor-id%E3%82%92appsflyer%E3%81%B8%E5%85%B1%E6%9C%89 h_01HA4ZWDM1J65D32PVXY0ZD9YV=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971adobe-experience-cloud-idecidmarketing-cloud-id%E3%81%BE%E3%81%9F%E3%81%AFvisitor-id%E3%82%92appsflyer%E3%81%B8%E5%85%B1%E6%9C%89 h_01HA4ZWDM1RDRDGZ3X7WC0ACV1=setadditionaldata h_01HA4ZWDM1CAXZH7ZNJ0Z37EE1=setcustomeruserid step-2-configure-adobe-analytics-in-appsflyer=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972appsflyer%E3%81%A7adobe-analytics%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01HA4ZWDM26AVEQKC4CXF18D22=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972appsflyer%E3%81%A7adobe-analytics%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01HA4ZWDM23A6BFXDV2JH4NR2J=%E6%B3%A8%E6%84%8F step-3-map-data-to-evars-in-adobe-analytics=%E3%82%B9%E3%83%86%E3%83%83%E3%83%973adobe-analytics%E3%81%A7%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92evars%E3%81%AB%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%81%99%E3%82%8B h_01HA4ZWDM27S52KY36GS1QPKJ5=%E3%82%B9%E3%83%86%E3%83%83%E3%83%973adobe-analytics%E3%81%A7%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92evars%E3%81%AB%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%81%99%E3%82%8B step-4-%5Boptional%5D-set-up-your-marketing-channel=%E3%82%B9%E3%83%86%E3%83%83%E3%83%97-4-%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%81%E3%83%A3%E3%83%8D%E3%83%AB%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01HA4ZX6FG6RM5JNDKQP6GVAD1=%E3%82%B9%E3%83%86%E3%83%83%E3%83%97-4-%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%81%E3%83%A3%E3%83%8D%E3%83%AB%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B domain-and-security-details=%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%A8%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%81%AE%E8%A9%B3%E7%B4%B0 h_01HA4ZWDM2NNFVPP1XYWKPS89A=%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%A8%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%81%AE%E8%A9%B3%E7%B4%B0" />
