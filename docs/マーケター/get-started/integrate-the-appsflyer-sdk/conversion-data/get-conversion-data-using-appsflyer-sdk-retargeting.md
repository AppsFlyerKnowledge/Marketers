---
title: SDKを使用したコンバージョンデータの取得｜リターゲティング
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:17:47Z'
  edited_at: '2026-10-29T07:38:55Z'
  id: 4410481260817
  locale: ja
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/ja/articles/4410481260817
---
> **At a glance:** SRN経由とSRN以外の経路について、リアトリビューションとリエンゲージメントがコンバージョンデータにどのように反映されるかを説明します。

## リターゲティングのコンバージョン

リターゲティングのコンバージョンには、リアトリビューションとリエンゲージメントの2種類があります。

> 👍 **Tip**
>
> リターゲティングのコンバージョンデータだけでは、コンバージョンの種別を明確に判断できない場合があります。[コンバージョンデータを取得するその他の方法](#コンバージョンデータを取得するその他の方法)をご覧ください。

## SRN経由のリアトリビューション

SRN経由でユーザーがリアトリビューションされた場合、コンバージョンデータの内容（ペイロード）からは、リターゲティングキャンペーン経由であることを確認できません。 SRNはアトリビューションリンクを使用しないため、アトリビューションリンクに`is_retargeting=true`パラメータを設定できません。**リターゲティングに対応しているSRN**では、AppsFlyerがユーザーをリアトリビューションの対象とするかどうかを判断します。

つまり、SDKのデータだけでは、そのインストールがリターゲティングキャンペーン経由かどうかを判断できません。

> 📘 **Note**
>
> ただし、リターゲティングであることが分かるキャンペーン名を設定しても、**確実に判別できるとは限りません**。詳しくは、[具体例](#ユーザー獲得とリアトリビューションが混在する例)をご覧ください。

## SRN以外のアドネットワーク経由のリアトリビューション

アドネットワークへのアトリビューションには、アトリビューションリンクを使用します。リターゲティングの場合、通常のアトリビューションリンクとOneLinkのどちらにも、必ず`is_retargeting=true`パラメータを設定します。

<Accordion title="Criteoのリターゲティングキャンペーン">

#### アトリビューションリンク

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

#### コンバージョンデータの内容

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "criteo_int",
      "retargeting_conversion_type": "re-attribution",
      "adset_id": null,
      "campaign_id": null,
      "af_reengagement_window": "30d",
      "install_time": "2018-12-01 23:13:03.126",
      "adgroup_id": null,
      "redirect": "false",
      "af_sub5": null,
      "click_time": "2018-11-18 20:02:31.559",
      "agency": null,
      "cost_cents_USD": "0",
      "is_retargeting": "true",
      "af_cpi": null,
      "af_click_lookback": "30d",
      "af_siteid": null,
      "idfa": "68**********************************",
      "http_referrer": null,
      "orig_cost": "0.0",
      "af_sub4": null,
      "adset": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* `retargeting_conversion_type`パラメータ：リターゲティングの種別を示します。値はre-attribution、re-engagement、noneのいずれかです。
* `is_retargeting: true`パラメータ：そのインストールがリアトリビューションされたインストールであることを示します。
* `af_reengagement_window`：リエンゲージメント期間は、**リエンゲージメントしたユーザー**のイベントをリエンゲージメントに紐づけられる日数です。この例はリアトリビューションのコンバージョンのため、このパラメータは不要です。

</Accordion>

## ディファードディープリンクを使用したリアトリビューション

リアトリビューションの対象となるユーザーは、その定義上、アプリをインストールしていない状態です。このようなユーザーを、ディープリンクでアプリ内の画面に誘導したい場合があります。例えば、アプリをアンインストールしたユーザーに再び利用してもらうためのキャンペーンを設定する場合です。このキャンペーンで商品やサービスを宣伝する際には、その商品やサービスに関連するコンテンツをユーザーに表示したいと考えられます。

このような誘導を「ディファードディープリンク」と呼びます。ディファードディープリンクのコンバージョンデータは、`onConversionDataSuccess`メソッドから取得します。

<Accordion title="SRNでのディファードディープリンク">

SRNでディファードディープリンクを実装するには、SRNのキャンペーンに追加の処理が必要です。 `onConversionSuccess`の応答に含まれるcampaign、adset、adgroupなどのデータを使用して、プログラムでユーザーの遷移先を制御してください。

#### Meta広告でのディファードディープリンクのコンバージョンデータ

<Tabs>
<Tab title="Android">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"Non-organic",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

</Tab>

<Tab title="iOS">

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

</Tab>
</Tabs>

getConversionDataの応答に含まれるcampaign、adsetなどのデータを使用して、プログラムでユーザーの遷移先を制御し、関連するコンテンツを表示できます。

> 📘 **Note**
>
> スポーツウェア専門のECアプリを例に説明します。 アプリをインストールしていないユーザーが広告に反応し、アプリをインストールします。アプリを起動すると、SDKがコンバージョンデータを返します。開発者は、ストア内の**夏のランニングシューズコレクション**（campaign）の画面を開き、**女性用ランニングシューズ**のカテゴリ（adset）を表示するようにアプリを実装します。

</Accordion>

<Accordion title="アトリビューションリンクを使用したディファードディープリンク">

ディープリンクでユーザーを誘導する方法は3つあります。

#### URIスキーム

URIスキームを使用する場合、アトリビューションリンクとOneLink、および返却データは次のようになります。

**アトリビューションリンク**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**返却データ**

```json
{
      "af_deeplink": true,
      "campaign": "campaign_name",
      "media_source": "media_source_name",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-30 23:59:09",
      "install_time": "2018-12-30 23:59:39.330",
      "agency": null,
      "cost_cents_USD": "0",
      "adset": "AD_SET_NAME",
      "ad_id": "AD_ID",
      "af_siteid": null,
      "http_referrer": null,
      "af_cpi": null,
      "af_sub5": null,
      "af_sub4": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink: true`：このパラメータが含まれ、値がtrueの場合は、`scheme`と`host`の各フィールドを確認してください。
* `scheme`と`host`：これらのフィールドは、アトリビューションリンクの`af_dp`パラメータから取得され、ディープリンクに使用するスキームと遷移先の画面を示します。

#### iOSのUniversal LinksとAndroidのApp Links

これらが、ディープリンクを実現する3つの方法のうち、残りの2つです。

Universal LinksまたはApp Linksを使用する場合、OneLinkと返却データは次のようになります。

**OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**返却データ**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "Non-organic",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* `shortlink`フィールド：ユーザーの流入元となったOneLinkを特定するフィールドです。開発者はこのフィールドを参照することで、どの画面を開き、どのコンテンツを表示するかを判断できます。 `campaign`など、その他のフィールドも同じ目的で使用できます。

> 🚧 **Important**
>
> 長い形式のOneLinkを使用した場合、返却データに`shortlink`フィールドは含まれません。
>
> 短縮形式・長い形式のどちらのOneLinkでも、遷移先の画面を示すカスタムパラメータを追加することを推奨します。例：`&deep_link_activity=shoes_cateogry`

> 📘 **Note**
>
> Universal LinksとApp Linksは、OneLinkでのみ使用できます。

</Accordion>

## SRN経由のリエンゲージメント

リアトリビューションのキャンペーンと同様に、SRN経由でユーザーがリエンゲージメントした場合も、コンバージョンデータからは、リエンゲージメントキャンペーン経由であることを確認できません。

## SRN以外のアドネットワーク経由のリエンゲージメント

この場合も、コンバージョンデータの内容からは、ユーザーがリエンゲージメントキャンペーン経由であることを確認できません。この制限に対処するには、リエンゲージメントであることが分かるキャンペーン名を設定します。

## ディープリンクを使用したリエンゲージメント

リエンゲージメントでは、ユーザーをアプリ内の特定の画面に誘導することが主な目的の1つです。例えば、商品やセールを宣伝する場合が挙げられます。このような場合、広告をクリックしたユーザーを、その商品やセールのアプリ内の画面に直接誘導したいと考えられます。

これを実現するには、ディープリンクを使用します。ディープリンクでは、コンバージョンデータが非常に重要です。ユーザーに合わせた体験を提供し、適切な画面へ誘導するために開発者が必要とする情報が含まれているためです。

<Accordion title="リエンゲージメント：SRNでのディープリンク">

SRN経由でユーザーがリエンゲージメントした場合、コンバージョンデータは取得できません。開発者は、アプリの起動時にSRNが提供するメソッドを使用して、このデータを取得する必要があります。

</Accordion>

<Accordion title="リエンゲージメント：アドネットワークでのディープリンク">

ユーザーがリエンゲージメントしてアプリを起動すると、`onAppOpenAttribution`メソッドで次のコンバージョンデータを取得できます。

iOSとAndroidのどちらでも、短縮形式のOneLinkを使用した場合、コンバージョンデータはリンク上のすべてのパラメータを格納したマップ形式で返されます。

例：

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* アプリ開発者は、`af_dp`やキャンペーン名などのパラメータを使用して、ユーザーをアプリ内の特定の画面へ誘導し、関連するコンテンツを表示できます。

> 🚧 **Important**
>
> 短縮形式のOneLinkを使用することを推奨します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/understand-onelink-short-vs-long-urls">こちら</Anchor>をご覧ください。

短縮形式のOneLinkを推奨するもう1つの理由は、長い形式のOneLinkで返されるコンバージョンデータの構造にあります。長い形式を使用した場合、コンバージョンデータは`link`という単一のフィールドを持つマップ形式で返されます。このフィールドには、長い形式のOneLink全体が格納されます。

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

## コンバージョンデータを取得するその他の方法

* Push APIでは、リアトリビューションまたはリエンゲージメントを判別できる、詳細なコンバージョンデータを取得できます。 Push APIの返却データには、`re_targeting_conversion_type`というフィールドが含まれます。このフィールドは、コンバージョンの種別がリアトリビューションかリエンゲージメントかを示します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/push-api-streaming-raw-data">Push APIガイド</Anchor>をご覧ください。
* ローデータレポートにも、コンバージョンの種別を示す情報が含まれます。リターゲティングのコンバージョンを扱うローデータレポートには、***イベント名***という列があります。この列の値は、コンバージョンの種別に応じて***re-engagemen*t**または***re-attribution*** になります。

## ユーザー獲得とリアトリビューションが混在する例

> 📘 **Note**
>
> 1. ユーザーがアプリをインストールした後、アンインストールします。インストールした時点から、このユーザーには<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>が適用されます。 Meta広告で、リターゲティングではなくユーザー獲得のキャンペーンを設定します。また、AppsFlyerとMeta広告の連携設定で、リターゲティングを有効にします。リアトリビューション期間内に、ユーザーが広告を見てクリックし、アプリを再インストールします。 AppsFlyerでは、このユーザーをリアトリビューションされたユーザーとして扱います。これは、次の2つの条件を満たしているためです。
>
>    1. Meta広告との連携設定でリターゲティングが有効になっている
>    2. ユーザーがリアトリビューション期間内にいる
>
>    この場合、キャンペーン名からはリアトリビューションであることを判断できません。
> 2. 同じ例で、ユーザーがリアトリビューション期間外にいる場合を考えてみましょう。この場合、インストールは新規のノンオーガニックインストールとして扱われます。
> 3. 別の例を見てみましょう。 Meta広告でリターゲティングキャンペーンを設定します。そのキャンペーンを見た一部のユーザーが、アプリをインストールします。ただし、これらのユーザーは初めてアプリをインストールしています。このようなユーザーは、リアトリビューションされたユーザーとは見なされません。 AppsFlyerでは、ユーザー獲得キャンペーン経由のユーザーとして扱います。

<div data-zendesk-anchors="retargeting-conversion=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 h_01EHQ74JS84509GT6M93SZA4HX=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 reattribution-with-srns=srn%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01JNBRN0TBCVKBP6X6GCK3ADG9=srn%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 reattribution-with-regular-ad-networks=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01JNBRN0TCF7YC76661XNS78AD=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 attribution-link=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF h_01JNBRN0TCP9CAHV3X4QD0AVRS=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF conversion-data-payload=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%86%85%E5%AE%B9 h_01JNBRN0TCXAZKYVYY56Q4GVHN=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%86%85%E5%AE%B9 reattribution-with-deferred-deep-linking=%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01JNBRN0TCECNRZ5ZBH2WWAWHV=%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 conversion-data-for-deferred-deep-linking-with-facebook=meta%E5%BA%83%E5%91%8A%E3%81%A7%E3%81%AE%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF h_01JNBRN0TC3NAE862BG274DRWW=meta%E5%BA%83%E5%91%8A%E3%81%A7%E3%81%AE%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF uri-schemes=uri%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%A0 h_01JNBRN0TC909V4TNCEK4ZP83H=uri%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%A0 ios-universal-links-and-android-app-links=ios%E3%81%AEuniversal-links%E3%81%A8android%E3%81%AEapp-links h_01JNBRN0TCH7HYZ4BCZTNS89SS=ios%E3%81%AEuniversal-links%E3%81%A8android%E3%81%AEapp-links reengagement-with-srns=srn%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 h_01JNBRN0TCT2F11CQ4H8208JCB=srn%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 reengagement-with-regular-ad-networks=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 h_01JNBRN0TCNTAAD47ZTTK3NWYJ=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E7%B5%8C%E7%94%B1%E3%81%AE%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 reengagement-with-deep-linking=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 h_01JNBRN0TCGN9Y8ZHSEC4HMKPM=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 alternative-conversion-data-sources=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%96%B9%E6%B3%95 h_01JNBRN0TCZ8T35W3AAA4HVD9M=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%96%B9%E6%B3%95 examples-of-mixed-user-acquisition-and-reattribution=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97%E3%81%A8%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%8C%E6%B7%B7%E5%9C%A8%E3%81%99%E3%82%8B%E4%BE%8B h_01JNBRN0TC13RAZ73AFV6G92VB=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97%E3%81%A8%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%8C%E6%B7%B7%E5%9C%A8%E3%81%99%E3%82%8B%E4%BE%8B" />
