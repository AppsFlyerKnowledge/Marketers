---
title: BatchとAppsFlyerの連携
metadata:
  keywords:
    - Advertisers
    - Batch
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
  created_at: '2019-01-28T10:06:24Z'
  edited_at: '2026-10-28T09:02:49Z'
  id: 360000833437
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/360000833437
---
> **At a glance:** AppsFlyerの連携済みパートナーであるBatchは、アプリ分析、マーケティングオートメーション、モバイルCRMのプラットフォームです。

Batchでは、ユーザーごとに最適な体験を提供しながら、ユーザーエンゲージメントを高めることができます。 Batchの高度なユーザーエンゲージメントプラットフォームを使用すると、スマートフォンのユーザー一人ひとりに合ったコミュニケーションを行い、離脱を抑え、アプリのROIを向上できます。 AppsFlyerとBatchを組み合わせることで、ユーザージャーニーに応じてユーザー体験やコミュニケーションをさらに最適化できます。たとえば、メディアソースやキャンペーンなどのアトリビューションデータに基づいて、アプリ内メッセージやプッシュ通知を出し分けることができます。 BatchとAppsFlyerは、簡単に連携できます。

> 🚧 **Important**
>
> **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

## BatchとAppsFlyerを連携する

### カスタマーユーザーIDの設定

BatchがAppsFlyerのデータを自社のデータと照合できるように、広告主は両方に同じ<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">カスタマーユーザーID</Anchor>を設定する必要があります。カスタマーユーザーIDはSDKで設定します。

仮の値ではなく、実際のカスタマーユーザーIDを設定してください。実際のカスタマーユーザーIDとは、自社システムで顧客の識別に使用しているユーザーIDです。

<Tabs>
<Tab title="Android">

#### Batch

Batch SDKでカスタマーユーザーIDを設定します。

```java
Batch.User.editor()
    .setIdentifier("user@example.com")
    .save();
```

#### AppsFlyer

AppsFlyer SDKでカスタマーユーザーIDを設定します。

```java
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>

<Tab title="iOS">

<Tabs>
<Tab title="Objective C">

#### Batch

Batch SDKでカスタマーユーザーIDを設定します。

```objectivec
BatchUserDataEditor *editor = [BatchUser editor];
[editor setIdentifier:@"user@example.com"];
[editor save];
```

#### AppsFlyer

AppsFlyer SDKでカスタマーユーザーIDを設定します。

```objectivec
[AppsFlyerTracker sharedTracker].customerUserID = @"user@example.com";
```

</Tab>

<Tab title="Swift">

#### Batch

Batch SDKでカスタマーユーザーIDを設定します。

```swift
let editor = BatchUser.editor()
editor.setIdentifier("user@example.com")
editor.save()
```

#### AppsFlyer

AppsFlyer SDKでカスタマーユーザーIDを設定します。

```swift
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>
</Tabs>

</Tab>
</Tabs>

### Batchの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。  
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

Batchの設定で使用するのは、<strong>［連携］</strong>タブのみです。ほかの4つのタブはこの連携では不要なため、無効になっています。

<div id="integration-tab" />

<Accordion title="連携タブ">

### パートナーを有効化

**初めて設定する場合**は、<strong>［パートナーを有効化］</strong>をオンにすると、［連携］タブのパラメータを設定できます。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>を参照してください。

### 一般設定

Batchとの連携を設定する前に、**Batch Rest API Key**と**Batch API Key**を取得してください。不明な場合は、[Batchに問い合わせて](mailto:hello@batch.com)ください。  

2つのキーを取得したら、それぞれ対応するフィールドに入力します。<strong>［一般設定］</strong>で、**Batch Rest API Key**を**BATCH\_REST\_API\_KEY**フィールドに、**Batch API Key**を**BATCH\_API\_KEY**フィールドに入力します。

![batch-general-settings-keys.png](https://files.readme.io/fb165253ec81c0ad4ee9569ef928dc63fb476efe6da8fc7c9120d6619b3124c1-360001692717.png)

### デフォルトポストバック

<strong>［デフォルトポストバック］</strong>の<strong>［送信オプション］</strong>ドロップダウンで、**［すべてのパートナーまたはオーガニックのイベント］***を選択します。*

![batch-default-postbacks.png](https://files.readme.io/e3e84f990d7f05c94fb69195a7e57caeffcd1ca35a5fb0148fc6a81ab9816673-360001778958.png)

画面右下の<strong>［保存］</strong>をクリックします。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Batchでは、計測リンクは利用できません。

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

Batchでは、権限の設定は利用できません。

</Accordion>

## Batch管理画面でAppsFlyerのデータを確認する

AppsFlyerからBatchへのインストールポストバックの送信が始まると、Batch管理画面でデータを確認し、アトリビューションデータに応じたユーザーコミュニケーションを設定できます。

データは、Batch管理画面の**Userbase**タブで確認できます。

![Userbase.png](https://files.readme.io/b0277dc43b81630d5b260273b208a5ab9b62e13c7caca08e8b631d73c8de3b2a-small-360001694717.png)

<div data-zendesk-anchors="integrating-batch-and-appsflyer=batch%E3%81%A8appsflyer%E3%82%92%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B h_01H9FK389GXG3CDFPNM5ASKJ3N=batch%E3%81%A8appsflyer%E3%82%92%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B setting-customer-user-id=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%83%BC%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCid%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK389MPKFN8J74BX1E3MGG=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%83%BC%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCid%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK389MK1HM1460VAT6X82Y=batch h_01H9FK389MPGNEX8B3923KYDB3=appsflyer batch::28a946d0=batch h_01H9FK389MC4K8PNVPAGC00TBW=batch appsflyer::3f0aa95b=appsflyer h_01H9FK389M7V83A66M6T9EV8QT=appsflyer batch::24c5c955=batch h_01H9FK389MRV4ARHMHXPAXVXQ9=batch appsflyer::deb78dd1=appsflyer h_01H9FK389MT6PD8FW21SYHBPCV=appsflyer setting-up-batch-in-appsflyer-dashboard=batch%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK389MCSR5YDSF4RKFDSDZ=batch%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK389MG9459909JZBDN77E=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FK389M19AVM63DEX5JTTQK=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FK389MN82EKHVGMM9Z6H58=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FK389MXA3DS403VXRRK5NX=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FK389MERP4XBF19T28E6DN=attribution-link-tab h_01H9FK389M3E05PVMNA83TBFJZ=cost-tab h_01H9FK389M06FEQ4RZJ04HTH33=ad-revenue-tab h_01H9FK389MB31S8BR8WX178GHX=permissions-tab viewing-appsflyer-data-in-the-batch-dashboard=batch%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A7appsflyer%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B h_01H9FK389M8BNRFECN0WG23BCD=batch%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A7appsflyer%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B" />
