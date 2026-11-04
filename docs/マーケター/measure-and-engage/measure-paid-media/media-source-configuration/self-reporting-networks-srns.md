---
title: セルフレポーティングネットワーク（SRN）
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Ad Networks
    - srn
    - Self-reporting
    - networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-10-22T05:21:45Z'
  edited_at: '2026-10-14T09:28:22Z'
  id: 360001546905
  locale: ja
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ja/articles/360001546905
---
> **概要：** セルフレポーティングネットワーク（SRN）におけるアトリビューション、ディープリンク、iOSへの影響、FAQについて学びましょう。

<div id="srns-integrated-with-appsflyer" />

## SRN媒体

| **SRN** | **ロゴ** |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/amazon-ads-campaign-configuration">Amazon Ads</Anchor> | <Image alt="amazon-ads-logo.png" src="https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png" width="134px" /> |
| <Anchor target="_blank" href="/marketers/ja/docs/apple-ads-integration-setup">Apple Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/iossearchads.png" width="131px" /> |
| <Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers">Google広告</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png?v=1" width="47px" /> |
| <Anchor target="_blank" href="/marketers/ja/docs/google-marketing-platform-display-video-360-dv360-integration">Google Marketing Platform (DV360)</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png?v=1" width="45px" /> |
| <Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup">Meta広告</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/facebook.png?v=1" width="67px" /> |
| <Anchor target="_blank" href="/marketers/ja/docs/roku-integration-with-appsflyer">Roku</Anchor> | <Image alt="roku.png" src="https://files.readme.io/4909a45e611700e5c2a69f94710226e65e10faf620e3a7939a2c038bea1736ca-33565070184337.png" width="150px" /> |
| <Anchor target="_blank" href="/marketers/ja/docs/snapchat-advanced-srn-integration-setup">Snapchat— アドバンスSRN</Anchor> | <Image alt="snapchat_logo.png" src="https://files.readme.io/c9b62d55d5c1497011d7411a21dca6f1668308bbe2806ab238b71742c421b182-32259457816209.png" width="41px" /> |
| Tencentソーシャル広告 | <Image alt="blobid0.jpg" src="https://files.readme.io/6d6e9661c9d81f80ffeedfdf4850a84f3cc183faa49a514d1d3bb116641738da-32259428896017.jpg" width="80px" /> |
| <Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Business— アドバンスSRN</Anchor> | ![TTFB_logo__4C_horizontal_black.png](https://files.readme.io/caa8c9e02b161eea10740cb79f26d04d3324e87b9cfd929281374d2d7936ef2e-32259428903953.png) |
| <Anchor target="_blank" href="/marketers/ja/docs/x-ads-formerly-twitter-ads-setup-guide-overview">X広告</Anchor> | <Image alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="37px" /> |
| <Anchor target="_blank" href="/marketers/ja/docs/yahoo-integration-setup">Yahoo（Oath：Ad Platforms / Yahoo Gemini)</Anchor> | <Image alt="verizonmedia.png" src="https://files.readme.io/36291ff556d07a5dbf2ae8ff693ea33d21dae9e0518a94b251202634a24049cf-32259428916369.png" width="76px" /> |
| <Anchor target="_blank" href="/marketers/ja/docs/yahoo-japan-search-ads-campaign-configuration">Yahoo!検索広告</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yahoojapansearch.png" width="139px" /> |

**注記：** SRNには、<Anchor target="_blank" href="/marketers/ja/docs/user-level-data-retention">ユーザーレベルのデータ利用とデータ保持期間の制限</Anchor>が存在します。

<div id="attribution" />

## アトリビューション

非SRN（アドネットワーク）は計測リンクを使用してコンバージョンをAppsFlyerにレポートしますが、SRNは、AppsFlyerからインストール通知を受け取ると、デバイスIDを用いて自己アトリビューションを行います。iOSアプリに関しては、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKAN</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">高プライバシーフレームワーク</Anchor>がアトリビューションに使用されます。

SRNおよび非SRNのAppsFlyerアトリビューションは次の基準に基づいています：

* ラストタッチおよびマルチタッチの手法。
* 関連するインプレッションとクリックデータを順序付けるためのAppsFlyer標準のアトリビューションロジック。

<div id="how-does-attribution-work-with-srns" />

### SRNでのアトリビューションはどのように行われますか？

SRNは、新規インストールやアプリ内イベントなどのイベントを次の方法でAppsFlyerにレポートします：

* APIを使用してアトリビューションおよび計測プロバイダーと通信します。
* サードパーティのアトリビューションプロバイダーがインストールを検出すると、広告IDを用いてネットワークに照会します。
* 関連する広告のクリックやインプレッションの詳細をレポートします。

AppsFlyerがアトリビューションを実行した後、<Anchor target="_blank" href="/marketers/ja/docs/user-level-data-retention#パートナー別のデータ保持期間">パートナーデータ保持期間</Anchor>内に、アプリ内ポストバックがSRNに送信されます。

<div id="how-does-attribution-work-with-advanced-srns" />

### アドバンスSRNのアトリビューションはどのように機能しますか？

アドバンスSRNは、通常のSRNと同じアトリビューション手法をサポートしています。さらに、アドバンスSRNは、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#aggregated-advanced-privacy">高プライバシーフレームワーク</Anchor>を通じた計測にも対応しています。ネットワークによっては、双方の同意が得られている場合に広告IDを使用したアトリビューションを行う方法や、クリックおよびインプレッションデータに基づいてキャンペーン計測をモデリングする方法が含まれます。

<div id="install-attribution" />

### インストールアトリビューション

アプリの潜在ユーザーは、アプリをインストールする前に複数の広告に接触します。一般的に、アトリビューションプロバイダーはラストタッチアトリビューションを提供し、実際のインストール前に発生した最後のクリックにインストールを紐付けます。

アプリを初めて起動したとき：

* AppsFlyerは次を確認します：
  * アプリがSRNからのトラフィックを受信するように設定されているかどうか
  * 広告ID（端末ID）が存在するかどうか
* これらの条件が両方とも満たされている場合、AppsFlyerは広告IDを使ってSRNを照会します。
* AppsFlyerはSRNの主張を考慮した上でアトリビューションを実行します。

<div id="install-attribution-examples" />

#### インストールアトリビューションの例

<div id="example-a-assisted-attribution" />

<Accordion title="例A：アシストアトリビューション">

![SRN_1.png](https://files.readme.io/8e244c99f54b36a4e88b03bf05bb7ca0da2db5c7c601882ea9f68c191c38981b-32259428920337.png)

**月曜日：** ネットワークAがユーザーのクリックをレポートします。

**火曜日：** ネットワークBが動画とのエンゲージメントをレポートします。

**水曜日：** ネットワークCはプレイアブル広告のクリックをレポートし、30分後にインストールが行われます。

**AppsFlyer**はインストールをネットワークCにアトリビューションし、ネットワークAとBがインストールを「支援」（アシスト）したと見なします。

AppsFlyerは、広告主に対してインストール前のエンゲージメントを示すアシストデータを提供します。これにより、広告主はマルチタッチまたは細分化されたアトリビューションモデルをカスタマイズできます。詳細については、<Anchor target="_blank" href="/marketers/ja/docs/measure-assisted-installs">「アシストインストールの説明」</Anchor>をご覧ください。

</Accordion>

<div id="example-b-last-click-attribution" />

<Accordion title="例B：ラストクリックアトリビューション">

![SRN_2.png](https://files.readme.io/6817d8235acfdbbb5324d07ea8a31ace21cf2306e8e099129d9802e3e0d58b0c-32259457863825.png)

**ネットワークD** (SRN) はネットワークCより数分前にクリックをレポートします。

**ネットワークC**は標準のアトリビューション連携を使用します。

**AppsFlyer**は、最後のクリックを行ったネットワークCにインストールを帰属させます。

</Accordion>

<div id="attribution-windows" />

### アトリビューション期間

アトリビューション期間には、ルックバックとビュースルーが含まれます。 一部のSRNは、インプレッションコスト（CPM）やアクション単価（CPA）に基づいてインストールの費用を広告主に請求します。これらは1～28日間の期間内に発生したクリックまたはインプレッションを基にしています。

**AppsFlyer**は、広告主の希望するアトリビューション方法とルックバック期間に基づいて、インストール、アクティビティ、eCPI、eCPAをアトリビューションします。

**広告主**は、SRNアトリビューション期間とビュースルーモデルに基づきインストールに費用が発生する可能性があります。

* 広告主はAppsFlyerのサードパーティユニバーサルアトリビューション手法によって広告費用を最適化し、配分できると期待しています。
* どうしてでしょう？AppsFlyerは広告主が定義した条件に基づいて実際のeCPIとeCPAをレポートするためです。
* SRNは、独自の支払い条件を定めることが多いため、短期的に利益を得られる可能性があります。しかし、広告主はサードパーティのアトリビューションプロバイダーを利用してこの問題を解決します。

<div id="deep-linking-with-srns" />

## SRNとのディープリンク

ユーザーがリンクをクリックした際にアプリを開くためには、アプリリンク、ユニバーサルリンク、またはURIスキームを設定するだけです。ただし、アプリ内の特定のページまたはアクティビティへのディープリンクやディファードディープリンクを実行するには、SRNはAppsFlyerの方法を使わずに独自の方法を利用しています。

では、ユーザーをディープリンクし、SRNから関連するデータを取得するにはどうすればよいでしょうか？

<div id="direct-deep-linking" />

<Accordion title="ダイレクトディープリンク">

ユーザーのデバイスがディープリンクを実行するとき、AppsFlyerのディープリンクメソッドを呼び出さずに、SRNとのダイレクトディープリンクが行われます。以下の例では、既存ユーザーが広告をクリックするとFacebookの方法でアクティビティに直接リダイレクトされ、新規ユーザーはAppsFlyerのコンバージョンデータを使用して同様の体験をします。Meta広告がどのように<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-faq#who-needs-facebooks-sdk">OneLinkをディープリンクに活用しているかを学ぶ</Anchor>

<div id="example" />

> 📄 **例**
>
> "greatapp"のモバイルマーケティング担当者であるジルは、一般オーディエンスを対象にMeta広告でディープリンクキャンペーンを実行することを決めました。このキャンペーンでは、クリックしたユーザーを「ボーナス」アクティビティにリダイレクトします。
> モバイル開発者のジャックは、コンバージョンデータを取得した後、このロジックを追加します。
>
> 1. これはFacebook由来ですか（"is\_fb=true"）？
> 2. もしtrueであれば、広告グループパラメータの値を取得します。
> 3. 値に「ボーナス」という言葉が含まれている場合、ユーザーを「ボーナス」アクティビティに送ります。

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="ディファードディープリンク">

ディープリンクとは異なり、AppsFlyerのGCD APIを利用することで、SRNによるディファードディープリンクが可能になります。  AppsFlyerがコンバージョンデータの情報を受け取り、アプリの初回起動時にそのデータが利用可能になります。新規ユーザーがSRN上のリターゲティングキャンペーンをクリックした後にアプリインストールを行うことになった場合に、AppsFlyerが取得したコンバージョンデータを利用することで、初回起動時アプリ内で新規ユーザーを特定ページへ遷移させることが可能です。

ディファードディープリンクは、Google Ads、Meta（アプリにFasebook SDKがインストールされている場合）、Snapchat、および実際のディープリンク値を使用してTikTok for Businessをサポートしています。この値は、`af_dp`フィールドを使用してGCD経由でクエリできます。TikTok for Businessの場合、この値は `deep_link_value` フィールドからもアクセスできます。

しかし、他のSRNでは、通常のAppsFlyerディープリンクパラメーターはディープリンクデータに含まれていません。アプリ内でこのデータを使用するには、開発者は、キャンペーン、広告セット、または単一の広告名などの利用可能なパラメーターに基づくさらなるロジックを使用する必要があります。

</Accordion>

<div id="ios-implications" />

## iOSへの影響

ほとんどのSRNはSKAdNetworkをサポートしており、AppsFlyerと必要な連携を行えます。

<div id="ios-145-srn-attribution" />

<Accordion title="iOS 14.5 SRNアトリビューション">

iOS 14.5以降、ユーザーが広告主と媒体アプリの両方でATTに同意すると(<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#デュアル同意">二重同意</Anchor>)、SRNインストールはSKAdNetwork管理画面に記録<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">され、従来の管理画面にも</Anchor>表示されます。

<div id="note" />

> 📘 **注意**
>
> * 従来の管理画面では、SRN起因のインストールが減少する様子が示されています。SRNのパフォーマンスを評価する際は、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAdNetwork管理画面</Anchor>を使用してください。全体としてSRNアトリビューションのインストールは減少し、オーガニックインストールが増加することが予想されます。ただし、アドバンスSRNの場合、<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">高プライバシー</Anchor>フレームワークやその他のプライバシー保護手法による計測もサポートされているため、その影響は小さくなります。
> * <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAdNetwork管理画面</Anchor>は、インストール後48～72時間の遅延で更新されます。
> * Apple Ads（ASA）によるインストールは、SKAdNetwork管理画面には記録されません。

</Accordion>

<div id="sending-event-postbacks-to-srns" />

<Accordion title="SRNへのイベントポストバックの送信">

イベントポストバックを受信するSRNでは、ポストバックにデバイスIDが含まれていることが前提となります。これにより、SRNは報告されるユーザー行動を自力でアトリビューションすることができます。多くのiOS 14ユーザーは同意しておらず、デバイスID（IDFA）へのアクセスを許可していません。このケースでは、次のようなことが予想されます：

* SRNに送信されるイベントポストバックの数の減少
* すべてのイベントを記録するAppsFlyerとSRNの間で発生する、イベントポストバック数の差異

<div id="note-1" />

> 📘 **注意**
>
> * 広告IDを取得できない場合、インストール、アプリ起動、アプリ内イベントのポストバックはSRNに送信されません。[ただし、一部のケースでは、広告IDを取得できない場合でも、限定的なポストバックがSRNに送信されることがあります。](/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid)[。](/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid)
> * クリック型アドネットワークは、イベントポストバック情報のセルフアトリビューションにデバイスIDではなく独自のトランザクションIDを使用するため、影響を受けません。

</Accordion>

<div id="faq" />

## よくある質問

<div id="how-does-retargeting-work-with-srns" />

<Accordion title="SRNでのリターゲティングはどのように作業しますか？">

非SRNからのリターゲティングクリックは、リターゲティングアトリビューションリンクに `is_retargeting=true` パラメータが存在することで簡単に識別できます。  
SRNでは同様の指標はありません。代わりに、 AppsFlyerはSRNからのリエンゲージメントのアトリビューションを可能にするロジックを使用します。

* 前提条件：
  * **アプリ設定**画面で、**リターゲティングを有効にする**トグルをオンに設定します。
  * **連携済みパートナー**画面でSRNを選択し、**リターゲティング計測を有効にする**トグルをオンに設定します。
* アプリの起動ごとに、AppsFlyerはデバイスIDを用いてSRNにアプリのキャンペーン広告への直近のエンゲージメント状況を問い合わせます。
  * SRNからエンゲージメントの詳細が返ってきた場合、AppsFlyerはエンゲージメントのルックバック期間内であること、およびリエンゲージメントCV間の最短期間を超えていることを確認します。
  * 検証されたエンゲージメントはリエンゲージメントとして記録され、SRNにアトリビューションされます。

</Accordion>

<div id="what-is-srn-mistargeting" />

<Accordion title="SRNのミスターゲティングとは何ですか？">

SRNキャンペーンは特定のターゲット層を狙うべきですが、必ずしもそうなるとは限りません。ユーザー獲得キャンペーンでの非ユーザーとリターゲティングキャンペーンでの既存ユーザー。

1つのSRNを使用してユーザー獲得とリターゲティングキャンペーンの両方を実行すると、ユーザーのターゲットが誤る可能性があります。その結果、意図しないトラフィックに対して支払いをすることになります。

**シナリオ：** AppsFlyerプラットフォーム上で、SRNがユーザー獲得キャンペーン用に有効になっています。

* アプリが起動するたびに、AppsFlyerはSRNにクエリを行い、該当の広告ID（ユーザー）において直近エンゲージメントがあったかを問い合わせます。
* はいの場合、
  * SRNからキャンペーン名が返されます。
  * AppsFlyerはそれが初回起動かどうかを判断し、それに応じてアトリビューションをします。  
    **初回起動**：新しいインストールはそのキャンペーンによるものと見なされます。  
    **2回目以降の起動**：リターゲティングイベントがキャンペーンに紐づけられます。

**結論：** ユーザー獲得キャンペーンでリターゲティングイベントを取得するのは効率的ではありません。

<div id="is-mistargeting-a-problem" />

#### 誤ったターゲティングは問題でしょうか?

AppsFlyerのデータアナリストが、特定の月におけるMeta広告**ユーザー獲得**キャンペーンを解析しました。

* リターゲティングが有効化されていました。
* キャンペーンの30％では、少なくとも15％が既存のアプリユーザーでした。
* キャンペーンの5％では、少なくとも40％が既存のアプリユーザーでした。
* **結論：SRNのユーザー獲得キャンペーンでは、10人に1人がすでに既存のユーザーです。**

[![mistargeted_users.png](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)

<div id="solving-the-mistargeting-problem" />

#### 誤ったターゲティングの問題を解決する

**基本的なソリューション：** ユーザー獲得キャンペーンに既存のアプリユーザーを含めないでください。

* SRNは潜在的な新規ユーザーのみを対象とします。
* **同じ予算で新規ユーザー獲得の結果を最大化します**。
* たとえば、月に1回、定期的に（手動で）キャンペーンを更新します。
* しかし、時間差があるため、アプリのインストール後の最初の1か月に既存ユーザーがユーザー獲得キャンペーンの対象になり得ます。

AppsFlyerのプレミアム機能である<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide">**オーディエンス**</Anchor>を使用すると、ユーザーベースの任意のセグメントを毎日数十のアドネットワークに自動的に連携できます。

AppsFlyerの調査によると、誤ったターゲティングを解決することで、マーケティングやユーザー獲得の取り組みに大きな影響を与える可能性があります。

</Accordion>

<div id="why-is-the-original-url-field-empty-in-raw-data-reports" />

<Accordion title="ローデータレポートでオリジナルのURL項目が空白なのはなぜですか？">

クリックはSRN環境で行われるため、AppsFlyerの計測リンクは使用されていません。そのため、クリックに関連するオリジナルのURLデータはAppsFlyerでは利用できません。

</Accordion>

<div id="dashboard-doesnt-show-srn-clicks-and-impressions" />

<Accordion title="管理画面にSRNのクリック数とインプレッション数が表示されない">

クリックはSRN環境で行われるため、AppsFlyerの計測リンクは使用されていません。したがって、一部のSRNはクリックおよびインプレッションデータをAppsFlyerに提供しません。

<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta Ads</Anchor>および<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-cost-and-ad-revenue">Google</Anchor>は、AppsFlyerに集計データを提供します。

</Accordion>

<div id="can-agencies-configure-srn-campaigns" />

<Accordion title="代理店はSRNキャンペーンを設定できますか？">

はい、<Anchor target="_blank" href="/partners/ja/docs/about-agency-accounts#セルフレポーティング広告ネットワーク">代理店によるSRN設定についてはこちら</Anchor>をご覧ください。

</Accordion>

<div id="does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid" />

<Accordion title="広告IDが利用できない場合でもポストバックを送信できますか？">

広告IDが空の文字列（“”）になっている場合、または「00000000-0000-0000-0000-000000000000」（すべてゼロのIDFA）と表示される場合、インストール、アプリ起動、アプリ内イベントのポストバックは送信されません。ただし、以下のケースを除きます。

* Google広告：Google広告とのリマーケティング計測連携の一環として、双方の同意が得られていない状態でユーザーがアプリ起動またはアプリ内イベントを実行した場合、`gbraid`とイベント情報がGoogle Adsに送信されます（`additional_data_json`イベントの場合）。
* Google広告：AndroidでデバイスIDが取得できない場合でも、リファラー値に`gclid`が含まれている場合（インストール）、またはリエンゲージメントイベントに`gclid`パラメーターを含むディープリンクが含まれている場合、`gclid`とイベント情報がGoogle広告に送信されます。
* Meta：FacebookのクッキーまたはキャンペーンID（ディープリンクや以前のリエンゲージメント）またはAEMトグルが有効になっている場合。
* Snapchatおよび<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Business - アドバンスSRN</Anchor>：確率論的モデリングによってインストールがSnapchatまたはTikTokに紐付けられ、そのインストールに関連するアプリ内イベントが発生した場合、ポストバックが送信されます。

**Google広告** `gbraid` **パラメータ：** Googleによって生成される集約識別子で、デバイスのグループを識別し、ディープリンクによって参照されます。

**GoogleクリックID（** `gclid` **パラメータ)：** 広告クリックの際にURL内で渡されるパラメータで、キャンペーンや広告に関連するその他のクリック属性を識別します。これは広告のトラッキングとキャンペーンのアトリビューションに使用されます。

</Accordion>

<div id="are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />

<Accordion title="SRNからのクリックとインプレッションは、ローデータレポートで利用可能ですか？">

いいえ、SRNからのクリックとインプレッションのローデータレポートは共有されません。SRNデータはアトリビューションに使用されますが、クリックとインプレッションのローデータはレポートに含まれていません。これは、TikTok、Snap、Meta、Googleを含むすべてのSRNに適用されます。

</Accordion>

<div data-zendesk-anchors="srns-integrated-with-appsflyer=srn%E5%AA%92%E4%BD%93 h_01HFM2MET40AFB84AW5N8GKWF3=srn%E5%AA%92%E4%BD%93 attribution=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HFM2MET4ZNKEZBT3S74N8CMC=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 how-does-attribution-work-with-srns=srn%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AB%E8%A1%8C%E3%82%8F%E3%82%8C%E3%81%BE%E3%81%99%E3%81%8B h_01HFM2MET42R6C87XB5RWX9ABJ=srn%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AB%E8%A1%8C%E3%82%8F%E3%82%8C%E3%81%BE%E3%81%99%E3%81%8B how-does-attribution-work-with-advanced%E2%80%94srns=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9srn%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AB%E6%A9%9F%E8%83%BD%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B h_01HFM2MET4Q6WCSANH18VTGBQX=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9srn%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AB%E6%A9%9F%E8%83%BD%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B install-attribution=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HFM2MET4YQGN3GZKTTBRQ4HK=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 install-attribution-examples=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E4%BE%8B h_01HFM2MET40Y9V8YGA20CCGVNN=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E4%BE%8B h_01HFM2MET47BP3T07NTRVDWSJ3=example-a-assisted-attribution h_01HFM2MET4FY6SRS534NEA25WV=example-b-last-click-attribution attribution-windows=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93 h_01HFM2MET4ZJF290QNE3TPXQMA=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93 deep-linking-with-srns=srn%E3%81%A8%E3%81%AE%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF h_01HFM2MET4ZA6WD6HX92JNFW7X=srn%E3%81%A8%E3%81%AE%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF h_01HFM2MET4VZX943736W52V0ZJ=direct-deep-linking h_01HFM2MET4HSVHM0Q1C8D5Z279=%E4%BE%8B h_01HFM2MET4WGVMRJW7NJ7TF8GQ=deferred-deep-linking ios-implications=ios%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF h_01HFM2MET4DGERZJ18A7CEFDS9=ios%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF h_01HFM2MET4SRX0YRZRMHBY6DKT=ios-145-srn-attribution h_01HFM2MET471M5J2XFE7G2Z6J3=%E6%B3%A8%E6%84%8F h_01HFM2MET42KNAMWE9S9BSF4PK=sending-event-postbacks-to-srns h_01HFM2MET4WJ6TMTXM03NFFCAG=%E6%B3%A8%E6%84%8F-1 faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HFM2MET49FZ8QHDMA7H92BTE=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HFM2MET4VYGPWR98HMAWK4YP=how-does-retargeting-work-with-srns h_01HFM2MET4JGYTW6P1VGYMYGFS=what-is-srn-mistargeting is-mistargeting-a-problem=%E8%AA%A4%E3%81%A3%E3%81%9F%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AF%E5%95%8F%E9%A1%8C%E3%81%A7%E3%81%97%E3%82%87%E3%81%86%E3%81%8B h_01HFM2MET4C1HMWH715XP42ZAQ=%E8%AA%A4%E3%81%A3%E3%81%9F%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AF%E5%95%8F%E9%A1%8C%E3%81%A7%E3%81%97%E3%82%87%E3%81%86%E3%81%8B solving-the-mistargeting-problem=%E8%AA%A4%E3%81%A3%E3%81%9F%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E5%95%8F%E9%A1%8C%E3%82%92%E8%A7%A3%E6%B1%BA%E3%81%99%E3%82%8B h_01HFM2MET41CDCP8VNGR39YMCK=%E8%AA%A4%E3%81%A3%E3%81%9F%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E5%95%8F%E9%A1%8C%E3%82%92%E8%A7%A3%E6%B1%BA%E3%81%99%E3%82%8B h_01HFM2MET4DETEHT8PACHS6C6B=why-is-the-original-url-field-empty-in-raw-data-reports h_01HFM2MET48Y4ATGB1HNDGSFEP=dashboard-doesnt-show-srn-clicks-and-impressions h_01HFM2MET4JEA8BBGN564CQPYX=can-agencies-configure-srn-campaigns h_01HFM2MET42V7AVV2BPZGDRARV=does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid h_01JMJ79S862T4M96ECZPVRZVJJ=are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />
