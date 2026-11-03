---
title: ［旧版］OneLink Smart Script V1の設定
deprecated: true
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-02T17:00:19Z'
  edited_at: '2026-10-28T09:19:56Z'
  id: 4415354290321
  locale: ja
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ja/articles/4415354290321
---
> **概要：** OneLink Smart Scriptを設定すると、流入元を問わず、モバイルWebサイトの訪問者をモバイルアプリへ誘導し、その成果を紐づけられます。**注意**：必須ではありませんが、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors">OneLink Smart Script V2</Anchor>への移行をご検討ください。

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

## 設定

OneLink Smart Scriptには、次の2つのバージョンがあります。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors">**OneLink Smart Script V2（推奨）**</Anchor>：初めてOneLink Smart Scriptを設定する場合は、このバージョンの使用をおすすめします。開発者の実装作業が簡単になり、Googleタグマネージャーを使った設定にも対応しています。**注意**：必須ではありませんが、V2への移行をご検討ください。 

**OneLink Smart Script V1（旧版）**：すでにOneLink Smart Scriptを設定している場合は、このバージョンのドキュメントを参照してスクリプトを保守・編集してください。 

<div id="responsibilities" />

<Accordion title="役割分担">

| **担当者**<ul><li>**広告主**：<ul><li>送信URLに含める情報を決めます。リンクに追加するアトリビューションデータや、ディープリンクに必要なデータが含まれます。受信URLの情報を加工するか、使用する値を固定で指定します。</li><li>モバイルWebサイトへ誘導するすべてのキャンペーンについて、受信URLにスクリプトが処理できるパラメータが含まれていることを確認します。</li></ul></li><li>**Web開発者**：<ul><li>スクリプトの初期化に使用するデータを設定します。</li><li>マーケターから提供された受信URLのパラメータに基づき、OneLinkの送信URLを生成するためのセッターを設定します。必須パラメータと任意パラメータの両方を設定します。</li><li>Webサイト全体、または特定のページにスクリプトを埋め込みます。</li></ul></li></ul> |
| --- |
| **前提条件**<ul><li>少なくとも1つのアプリが登録されたAppsFlyerアカウント。</li><li>[OneLinkURLパラメータ](/docs/legacy-onelink-smart-script-v1-setup#parameters)の値として使用する<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor>。</li></ul> |

**Webページにスクリプトを実装するには：**

1. 自動生成するOneLinkの送信URLに、どのパラメータと値を含めるかを決めます。使用可能な[パラメータの一覧](/docs/legacy-onelink-smart-script-v1-setup#parameters)を参照してください。
   * すべてのキャンペーンの受信URLに、スクリプトが処理し、**pid**と**c**に設定できるパラメータが含まれていることを確認します。
2. [パラメータの一覧](/docs/legacy-onelink-smart-script-v1-setup#parameters)をWeb開発者に渡します。
3. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script">開発者向けの手順</Anchor>に従ってスクリプトを実装し、正しい送信URLが生成されるよう、開発者に依頼します。

</Accordion>

<div id="parameters" />

<Accordion title="パラメータ">

#### Smart Scriptの実装用に開発者へ渡すパラメータと値

| パラメータ／値 | 説明 | 設定内容の記入欄（開発者への共有用） |
| --- | --- | --- |
| oneLinkURL（必須） | <ul><li>OneLinkテンプレートのドメインとテンプレートIDを指定します。**注意：** OneLinkのカスタムリンクURLではありません。</li><li>例：**yourbrand.onelink.me/A1b2**</li><li>ブランドドメインの例：**click.yourbrand.com/A1b2**</li></ul> |  |
| pidKeysList（メディアソース） | <ul><li>受信URLに含まれるメディアソースのパラメータのうち、送信URLのメディアソース（pid）に値を引き継ぐものを、すべて指定します。</li><li>例：['af\_pid', 'utm\_source']</li></ul> |  |
| pidOverrideList | <ul><li>送信リンクでメディアソースの値を変更する場合は、受信URL内の元の値と、置き換え後の値を組み合わせて指定します。</li><li>例：`{<br />'twitter': 'twitter_int',<br />'snapchat': 'snapchat_int',<br />'some_social_net': 'some_social_net_int'<br />}`</li></ul> |  |
| pidStaticValue | <ul><li>該当するパラメータが見つからない場合に、代わりに使用するメディアソースを指定します。</li><li>pidKeysListで指定したメディアソースパラメータが見つからない場合、送信URLのメディアソース（pid）にはpidStaticValueが使用されます。</li><li>例：'website'または'landing\_page'</li></ul> |  |
| campaignKeysList（キャンペーン） | <ul><li>受信URLに含まれるキャンペーンのパラメータのうち、送信URLのキャンペーン（c）に値を引き継ぐものを、すべて指定します。</li><li>例：['af\_campaign', 'utm\_campaign']</li></ul> |  |
| campaignStaticValue | <ul><li>該当するパラメータが見つからない場合に、代わりに使用するキャンペーンを指定します。</li><li>campaignKeysListで指定したキャンペーンパラメータが見つからない場合、送信URLのキャンペーン（c）にはcampaignStaticValueが使用されます。</li><li>例：'website'または'landing\_page'</li></ul> |  |
| gclIdParam | <ul><li><Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">GCLID</Anchor>を格納するパラメータの名前を指定します。<br />**注意** AppsFlyerのローデータレポートに表示するには、**af\_sub[1-5]** のいずれかを使用する必要があります。</li></ul> |  |
| skipList | <ul><li>特定のクリックについてSmart Scriptを実行しない条件として、HTTPリファラに含まれる文字列（TwitterやFacebookなど）を指定します。指定した文字列が見つかった場合、Smart Scriptは実行されません。 X AdsやMeta adsなど、クリックがすでにレポートされるSRNで役立ちます。</li><li>SRNも含め、常にSmart Scriptを実行したい場合は、空のスキップリストを渡すよう開発者に依頼してください。</li></ul> |  |
| その他のクエリパラメータ | <ul><li>アトリビューションやディープリンクのために、OneLinkの送信URLに含めるその他のパラメータを指定します。</li><li>ディープリンクには、**deep\_link\_value**を追加します。<ul><li>パラメータの追加に加え、開発者と協力してディープリンクのロジックを実装する必要があります。<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#onelinkリンクの作成">詳細はこちら</Anchor>。</li></ul></li><li>受信URLのパラメータを使用するか、固定値を指定できます。</li></ul> |  |

</Accordion>

## 利用ケース

以下では、よくあるキャンペーンとメディアソースの組み合わせについて、Smart Scriptの利用ケースを説明します。

<div id="facebook-ads-crossplatform-attribution" />

<Accordion title="Meta ads ｜ クロスプラットフォームのアトリビューション">

Meta adsはSRNであり、外部のアトリビューションリンクを使用しません。

アプリの初回起動時に、AppsFlyerはMeta adsに対して、そのユーザーが過去<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-discrepancies#クリックスルーアトリビューションとビュースルーアトリビューション">7日以内</Anchor>にアプリの広告に接触したかどうかを照会します。ユーザーが広告主のFacebook広告に接触していた場合、Meta adsが自らの成果として申告します。 Meta adsはクロスプラットフォームのアトリビューションにも対応しているため、ユーザーがどのプラットフォームで、どの種類のキャンペーンに接触した場合でも、モバイル向けかどうかにかかわらず、自らの成果として申告できます。

**対応**：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script#skip-clicks-from-twitter-or-facebook">skipListメソッド</Anchor>を使用し、Meta adsやその他の指定した文字列を条件にSmart Scriptを無効にするよう、開発者に依頼してください。クリックのHTTPリファラにMeta ads、またはスキップリスト内のいずれかの文字列が含まれる場合、Smart Scriptは`null`を返します。

**注意**：2021年のiOS 14ユーザーで想定されているように、ユーザーがデバイスIDを共有しないことを選択すると、Meta adsのクロスプラットフォームのアトリビューションに影響する可能性があります。

</Accordion>

<div id="google-ads-gclid-and-utm-parameters" />

<Accordion title="Google広告 ｜ GCLIDとUTMパラメータ">

GCLIDパラメータを含むGoogle広告キャンペーンの通常のインストールアトリビューションでは、広告をクリックした見込み顧客をアプリのストアページURLへリダイレクトする必要があります。

このケースではGoogle広告からWebページやランディングページへ誘導するため、スクリプトはGoogle広告のインストールキャンペーンURLからGCLIDを取得し、送信URLで指定した**af\_sub[1-5]パラメータに設定します。注意**これはインストールキャンペーンに適用されます。 ACI以外の検索キャンペーン、つまりリエンゲージメントキャンペーンでは、Smart Scriptの出力にかかわらず、Googleがメディアソースとして紐づく場合があります。

**前提条件**：Googleの管理画面で<Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">自動タグ設定を有効にします</Anchor>。  
自動タグ設定を有効にすると、URLに*GCLID*パラメータが含まれます。

**Google広告用にスクリプトを設定するには：**

1. 受信リンクに含まれるメディアソースとキャンペーンのパラメータ名を一覧にします。  
   例：**utm\_source**、**utm\_campaign**。
2. 送信URLでGCLIDを格納するパラメータを選択します。  
   推奨：AppsFlyerのローデータレポートにデータを表示できるよう、**af\_sub[1-5]** のいずれかを選択してください。
3. これらを[パラメータの一覧](/docs/legacy-onelink-smart-script-v1-setup#parameters)に記入し、Web開発者に渡します。

**結果**：

* 受信リンクのメディアソースとキャンペーンのパラメータ（**utm\_source**、**utm\_campaign**）の値が、それぞれ送信リンクの**pid**と**c**に設定されます。
* 送信URLでは、GCLIDが**af\_sub[1-5]** のいずれかの値として設定されます。

**これらのインストールをGoogle広告に通知するには：**

1. CSVから、またはインストールごとにPush APIでリアルタイムに、**af\_sub[1-5]** パラメータのGCLIDデータを取得します。
2. GCLIDデータを、<Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">手動</Anchor>または<Anchor target="_blank" href="https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions">Adwords API</Anchor>でGoogleにアップロードします。

> 📘 **注意**
>
> GCLIDを使用するこの方法は、Googleが公式にサポートまたは推奨しているものではありません。 GoogleがGCLIDパラメータを廃止した場合は、その変更に対応するようスクリプトを更新します。記事や添付スクリプトの更新通知を受け取れるよう、記事上部の<strong>［フォロー］</strong>ボタンをクリックして、この記事をフォローしてください。

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="SRN、オウンドメディア、その他のメディアソースのリンク">

SnapchatやX Adsなどの<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#srn媒体">SRN</Anchor>は、Google広告やクロスプラットフォームに対応するMeta adsとは仕組みが異なります。これらのSRNのキャンペーンでは、ユーザーをWebページやランディングページへ誘導し、その後モバイルアプリのユーザーになったかどうかにかかわらず、見込み顧客のクリックに基づいて課金されます。

これらのSRNでは、オウンドメディアやその他のメディアソースのリンクと同じ方法でスクリプトを設定します。

**スクリプトを設定するには：**

1. 受信リンクに含まれるメディアソースとキャンペーンのパラメータ名を一覧にします。
2. これらを[パラメータの一覧](/docs/legacy-onelink-smart-script-v1-setup#parameters)に記入し、Web開発者に渡します。  
   受信URLでは、メディアソースの値にSRNまたはメディアソースの種類を指定します。スクリプトはその値を取得し、Webページやランディングページのダウンロードボタンで使用するOneLinkの送信URLの**pid**に設定します。送信URLの**pid**を変更する場合は、pidの上書きリストに、受信したメディアソースの値と、置き換え後の**pid**の値を指定します。

**結果**：これらのSRNやメディアソースでは、受信リンクのメディアソースとキャンペーンの値が、それぞれ送信リンクの**pid**と**c**に設定されます。

> 📄 **例**
>
> **受信URL**：https://hotel.me/af_pid=twitter&af_c=big_social
>
> **送信URL**：https://hotel.onelink.me/Ac4G?pid=twitter&c=big_social

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="AppsFlyerのアトリビューションリンク">

クリックの計測に対応するアドネットワークでは、AppsFlyerのアトリビューションリンクを使用できます。 AppsFlyerでこのリンクを設定する際に、モバイルWebサイトの誘導先URLを***［リダイレクト先URLのパス（af\_r）］***パラメータに追加すると、Webキャンペーンからアプリへのアトリビューションに対応できます。 

**結果**：受信リンクに**af\_r**と**af\_redirect=true**が含まれている場合、ランディングページのスクリプトはリンクを変更しません。 Webページやランディングページに設定されているアプリストアへの直接リンクを、そのまま使用します。 

> 📄 **例**
>
> **受信URL**：https://app.appsflyer.com/id123456789?pid=click_ad_network_int&c=orlando&af_redirect=true&af_r=hotel.me
>
> **送信URL**：受信URLと同じ

</Accordion>

<div id="desktop" />

<Accordion title="デスクトップ">

この記事の利用ケースの多くは、モバイルデバイスからの訪問を想定しています。そのため、モバイルWebサイトからアプリストアに誘導すると、その場でアプリをダウンロードできます。

一方、デスクトップユーザーのデバイス（デスクトップPCやノートPC）ではモバイルアプリをダウンロードできないため、そのままアプリストアへ誘導すべきではありません。

**デスクトップユーザー向けにスクリプトを設定するには：**

* <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor>の<strong>［デスクトップでリンクがクリックされた場合］</strong>に、誘導先URLを設定します。専用のWebページまたはランディングページにリダイレクトするURLを指定してください。ランディングページには、ユーザーが情報を入力すると、アプリのダウンロードリンクを含むSMSまたはメールを受け取れるWebフォームを設置できます。 Webフォームは自社で作成し、そのURLをスクリプトに設定してください。

**結果**：スクリプトは、ユーザーのデバイスまたはプラットフォームを検出します。デスクトップの場合は、専用のWebページまたはランディングページへ誘導するOneLinkの送信URLを生成します。

<Anchor target="_blank" href="/marketers/ja/docs/qr-to-app-conversion">デスクトップからアプリへのコンバージョン</Anchor>も参照してください。

</Accordion>

<div id="limitations" />

<Accordion title="制限事項">

| 制限事項 | 説明 |
| --- | --- |
| タグマネージャー | Smart Scriptは、タグマネージャー経由では実装できません。代わりに利用できるWeb-to-appアトリビューションのソリューションとして、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors">OneLink Smart Script V2</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor>を参照してください。 |

</Accordion>

<div data-zendesk-anchors="setup=%E8%A8%AD%E5%AE%9A h_01HDNWHSY8HM30HV1PAF5C3M4E=%E8%A8%AD%E5%AE%9A h_01HDNWHSY8J65EB1RZCFP1606H=responsibilities h_01HDNWHSY8CH29FQ2V5DCG2XSP=parameters parametersvalues-provided-to-the-developer-to-implement-the-smart-script=smart-script%E3%81%AE%E5%AE%9F%E8%A3%85%E7%94%A8%E3%81%AB%E9%96%8B%E7%99%BA%E8%80%85%E3%81%B8%E6%B8%A1%E3%81%99%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%A8%E5%80%A4 h_01HDNWHSY8WSPX47VB43MC516Q=smart-script%E3%81%AE%E5%AE%9F%E8%A3%85%E7%94%A8%E3%81%AB%E9%96%8B%E7%99%BA%E8%80%85%E3%81%B8%E6%B8%A1%E3%81%99%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%A8%E5%80%A4 use-cases=%E5%88%A9%E7%94%A8%E3%82%B1%E3%83%BC%E3%82%B9 h_01HDNWHSY8N77ZH4CK49ZQ2KZB=%E5%88%A9%E7%94%A8%E3%82%B1%E3%83%BC%E3%82%B9 facebook-ads%E2%80%94crossplatform-attribution=facebook-ads-crossplatform-attribution h_01HDNWHSY85QFABA6FAX1XTEPE=facebook-ads-crossplatform-attribution google-ads%E2%80%94gclid-and-utm-parameters=google-ads-gclid-and-utm-parameters h_01HDNWHSY878JTPZSN719KF1Y5=google-ads-gclid-and-utm-parameters h_01HDNWHSY8BJH39TAN46W7HE4G=%E6%B3%A8%E6%84%8F h_01HDNWHSY8NER2M8X4DGHCWYPJ=srns-owned-media-and-other-media-source-links h_01HDNWHSY828Q587S28GYB85VR=%E4%BE%8B h_01HDNWHSY8K1AFSEA1RY04KXJ9=appsflyer-attribution-links h_01HDNWHSY8DDTA6VATN0XXBEY5=%E4%BE%8B-1 h_01HDNWHSY821DADGKATKH12PSJ=desktop h_01HDNWHSY80QA9CC4S2BPBTJYG=limitations" />
