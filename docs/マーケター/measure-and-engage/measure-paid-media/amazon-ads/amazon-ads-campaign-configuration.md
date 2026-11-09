---
title: Amazon Adsキャンペーン連携設定
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2023-01-04T10:14:20Z'
  edited_at: '2026-10-14T09:36:03Z'
  id: 11904659502737
  locale: ja
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/ja/articles/11904659502737
---
> **概要：** Amazon Ads（amazondsp\_int）はAppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">SRN</Anchor>連携パートナーで、TV・タブレット・モバイルデバイスにおけるクリックおよびインプレッションベースのアトリビューションをAppsFlyer上で計測できます。

<Image align="center" alt="mceclip0.png" src="https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png" />

<div id="activate-partner" />

## 連携設定

**前提条件：** 連携設定を行う前に、<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">必ずパートナーへ連絡</Anchor>し、アカウントを開設してください。

**連携を有効化または編集するには：**

1. **有効化する場合：** AppsFlyer管理画面 左メニュー **連携** > **Partner Marketplace**へ移動します。  
   **編集する場合：** AppsFlyer管理画面左メニュー **連携** > **連携済みパートナー**を選択します。
2. Amazon Adsを検索して選択します。  
   **重要：** 必ず「amazondsp\_int」を選択し、「amazon\_int（旧連携）」は選択しないようご注意ください。
3. **連携の設定**をクリックします。**連携済みパートナー**設定画面に移動します。
4. **連携**タブで、**パートナーを有効にする**トグルをオンにします。  
   **注：<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーと作業している間は、トグルをオン（</Anchor><Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">アクティブ</Anchor>）にしたままにする必要があります。**
5. 次のセクションで説明されている関連タブを使用して設定を完了します。

<div id="complete-the-setup-in-amazon-ads" />

## Amazon Ads側での設定

Amazon Adsでは以下の対応が必要です：

1. アプリがAmazon Ads上に正しく登録されていることを確認してください。（詳細は「<Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">Register apps</Anchor>」を参照してください）
2. キャンペーン作成時に、対象のコンバージョンをキャンペーンに紐付けてください。（詳細は「<Anchor target="_blank" href="https://advertising.amazon.com/help/GMQBB4PRFK8C33AE">Assign a conversion definition to a campaign</Anchor>」を参照してください）

<div id="setting-up-amazon-ads" />

## Amazon Adsの設定

Amazon Adsとの連携は、クリックとインプレッションのアトリビューションをサポートします。設定ウィンドウには次のタブが含まれます：連携、計測リンク、コスト、広告収益、権限（Amazon Adsで利用できるタブは、連携と権限のみです）

<div id="note" />

> 📘 **注意**
>
> この連携はAndroid、iOS、Fireアプリに対応しています。iOSについてはSKAN経由での計測にも対応しています。

<div id="integration-tab" />

<Accordion title="連携タブ">

**連携**タブには、以下で説明するセクションがあります。

<div id="activate-partner-1" />

#### 連携設定

連携を設定するには、まず**パートナーを有効にする**トグルを[オン](/docs/amazon-ads-campaign-configuration#連携設定)にする必要があります。詳細：<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation#パートナー統合を有効にする">パートナー連携</Anchor>

<div id="general-settings" />

#### 一般設定

**Amazon advertiser ID**

これは、Amazonにより生成された広告主固有のキーです。連携を完了し、Amazon 広告のアトリビューションを可能にするためには、Amazon広告主IDが必要です。Amazon advertiser IDを見つけるには：

* **セルフサービス広告主の場合：** 広告主IDは、Amazon Adsレポートコンソールの「Amazon DSPキャンペーンマネージャー」の「広告主」タブ内で、広告主名の下に表示されます。
* **マネージドサービス広告主の場合：** AmazonアカウントマネージャーにAmazon advertiser IDを問い合わせてください。
* 同じアプリに対して複数のAmazon広告アカウント（複数のAmazon Advertiser ID）を使用している場合、以下の方法で連携を設定します：
  1. Amazon Ads側で、1つの広告アカウントを **source account（ソースアカウント）** として指定します。その他の広告アカウントは **destination account（宛先アカウント）** として指定します。
  2. Amazonのアカウントチームへ連絡し、バックエンドで設定してもらいます。
  3. AppsFlyerでは、source accountに紐づくAmazon Advertiser ID を入力します。これにより、関連するすべてのdestination accountに連携設定が適用されます。

**Amazon app ID**

* **Androidアプリの場合：** パッケージ名を入力してください。例： `com.example.app`
* **Fire テレビまたはFireタブレットアプリの場合：** 製品のASIN（Amazon標準商品番号）
* **iOSアプリの場合：** App StoreのアプリID（"`id`"の部分を除いた状態）例： `12345678`
* <Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution#単一管理画面-vs-ストアごとの管理画面">**単一管理画面アプリ**</Anchor> （同じAppsFlyerアプリのGoogle PlayとAmazonストアのデータを統合した管理画面）の場合：App IDとしてAndroidのパッケージ名を入力してください。  
  **注：<Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">アプリがAmazon AdsアカウントでAndroidアプリとして</Anchor><Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">登録</Anchor>されていることを確認してください。**

<div id="install-attribution" />

#### インストールアトリビューション

インストール（初回起動）のクリックとビュースルーアトリビューション期間を設定します。ルックバック期間内のインストールのみがAmazon Adsへのアトリビューション対象となります。

**注意：** 再インストール（デバイスの初期セットアップ以外のインストール）のアトリビューションはサポートされていません。

1. **インストールのクリックルックバック期間**を1-24時間または1-14日に設定します。  
   **注意：** Amazon Adsでは、そのアトリビューション期間と一致させ、矛盾を回避するためにクリックルックバック期間を14日間に設定することを推奨しています。
2. [オプション] **インストールのビュースルー計測**を有効にし、**インストールのビュースルールックバック期間**を1-24時間に設定します。   
   **注意：** Amazon Adsでは、そのアトリビューション期間と一致させ矛盾を避けるためにビュースルールックバック期間を14日間に設定することを推奨しています。

<div id="re-engagement-attribution" />

#### リエンゲージメント計測

**リエンゲージメントCV計測**を有効にし、広告を閲覧、クリック、または***エンゲージした***既存ユーザーのリエンゲージメントを計測するためのさまざまなアトリビューション期間を設定します。ルックバック期間内のリエンゲージメントのみがAmazon Adsへのアトリビューション対象となります。

1. [オプション] **リエンゲージメントCV計測**を有効にし、ルックバック期間を設定します。
   * **リエンゲージメントCVのクリックルックバック期間**を1-23時間または1-14日に設定します。
2. [オプション] **リエンゲージメントCVのビュースルー計測**を有効にし、ルックバック期間を設定します。
   * **リエンゲージメントCVのビュースルールックバック期間**を1-23時間または1-14日に設定します。
3. **リエンゲージメント期間**を1-23時間、1-90日間、または全期間に設定します。

<div id="ignore-active-users-for-retargeting" />

#### リターゲティングでアクティブユーザーを無視する

直近アプリを起動したユーザーの、<Anchor target="_blank" href="/marketers/ja/docs/set-retargeting-inactivity-window#休眠期間">リエンゲージメントとリアトリビューションを計測しない</Anchor>期間を設定します。したがって、この期間中のアクティビティはAppsFlyerに記録されません。

<div id="note-1" />

> 📘 **注意**
>
> 設定された期間中に**休眠状態**だったユーザーのリエンゲージメントと再アトリビューションのコンバージョンは**記録されます**。

1. **リターゲティングでアクティブユーザーを無視する**をオンにします。
2. **休眠期間**を1-30日間に設定します。  
   **注意：** Amazon広告は矛盾を避けるために、休眠期間を7日間に設定することを推奨しています。

<div id="in-app-event-postbacks" />

#### アプリ内イベントポストバック

ポストバックで送信されるアプリ内イベントとAmazon広告イベントのマッピングを設定します。

**アプリ内イベントポストバックを設定する：**

1. **アプリ内イベントポストバック**をオンにします。
2. **イベントを追加**をクリックして、SDK または サーバー間イベントをリストに追加してください。各項目の説明は以下を参照してください。

| パラメーター名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>非オーガニックインストールとして計測された端末上で、そのアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>**AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントマッピングの詳細</Anchor>をお読みください。</li></ul> |
| **パートナー側のイベント名** | パートナー側で定義されている各イベントの一意の名前またはIDです。定義されたパートナーイベントのリストから、アプリイベント(AppsFlyerイベント)に対応するイベントを選択します。<br /><br />**注意：**<ul><li>アプリイベントに直接対応しないイベントには、OTHERを選択することができます。</li><li>リエンゲージメント計測を有効にしている場合、`af_app_opened` をマッピングしないか、`OTHER` にのみマッピングすることを推奨します。これにより、イベント送信時の重複を防げます。</li></ul> |
| **送信オプション** | イベントの送信オプションを選択してください：<ul><li>**このパートナーのみ：** このイベントがこのパートナーに紐づく場合のみポストバックを送信します。</li><li>**オーガニックを含むすべてのメディアソース：** 任意のパートナーに紐づくイベント及びオーガニックイベントのポストバックを送信します。</li></ul> |
| **含む** | <ul><li>**データなし（デフォルト）：** イベント値なしでイベント自体のみを送信します。</li><li>**イベント値と収益：** 収益の額を**含む**（存在する場合）、すべてのイベント値を送信します。</li><li>**収益を除いたイベント値：** 収益の額を**含まない**、すべてのイベント値を送信します。</li></ul> |

   <div id="note-2" />

   > 📘 **注意**
   >
   > S2SでAppsFlyerへイベント送信する場合、Amazonは IPアドレスを含めること を推奨しています。これによりAppsFlyerがイベントのジオロケーションに基づく 国コード をAmazonへ送信でき、DMA規制の分類に役立ちます。その結果、アプリ内イベントの最適化が最大化されます。

3. ［任意］ポストバックするイベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor>するには、　**条件を追加**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> アイコンをクリックします。
4. **連携を保存** をクリックします。
5. ［任意］連携を保存した後、設定画面に留まりつつ、ほかのアプリ / OSの設定へ進みます。
   1. 左上隅のパートナー名下にあるアプリ名をクリックし、アプリ一覧を開きます。
   2. ドロップダウンリストから別のアプリを選択します。
   3. 選択したアプリに対し、[連携手順](#integration-tab)を再度実行します。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

計測リンクはAmazon Adsでは使用されません。アトリビューションは、Amazon AdsのエンゲージメントデータとAppsFlyerのデータを組み合わせ、[連携タブ](#integration-tab)で設定したクリックスルーおよびビュースルーのルックバック期間に基づいて実行されます。

</Accordion>

<div id="cost-tab" />

<Accordion title="コスト、クリック、インプレッションタブ">

Amazon広告では、コスト、クリック、インプレッションデータは利用できません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

Amazon広告では広告収益は得られません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

Amazon Ads にデータアクセスや各種操作を許可する権限を選択します。

<div id="note-3" />

> 📘 **注意**
>
> * 権限トグルがオンの状態で連携が<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">非アクティブ化</Anchor>された場合でも、権限は付与されたままです。
> * 詳細：<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">権限の付与</Anchor>

</Accordion>

<div id="see-also" />

> 📄 **参照**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/setting-up-amazon-fire-tv-ad-attribution">Amazon Fireテレビ広告のアトリビューション設定</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/attribution-discrepancies-between-amazon-ads-and-appsflyer">AppsFlyerとAmazon Ads間のアトリビューションの不一致</Anchor>

<div id="deferred-deep-linking" />

## ディファードディープリンク

* Amazon広告ではディープリンクはサポートされていません。
* ディファードディープリンク：ディファードディープリンクのためのAppsFlyerの両方のメソッドは、Amazon広告では使用できません：
  * [UDL](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl)（Unified Deep Link） - SRNではサポートされていません。
  * [GCD](https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking)（Get Conversion Data） - Amazon Adsのアトリビューションデータは[制限されている](/docs/amazon-ads-campaign-configuration#ローデータの制限)ため、Amazon Adsでは機能しません。

<div id="raw-data-restrictions" />

## ローデータの制限

Amazon広告からのローデータは、<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">AppsFlyerプラットフォーム上で制限されています</Anchor>。その結果、メディアソースは restricte（制限有り）としてレポートされ、キャンペーンの詳細は null となります。Amazon Adsのクリックとインプレッションはローデータレポートには含まれません。

<div id="ctv-to-mobile-attribution" />

## CTV-to-mobileの計測について

Amazonでは、Amazon Prime VideoなどのCTV（Connected TV）キャンペーンに対して、モバイルアプリのインストールがアトリビューションされる場合があります。これは、CTV広告を視聴したユーザーがモバイルデバイス上のAmazonアプリにログインしている場合に発生します。

**注意：** キャンペーンがCTVであることを**明示的に示すレポート指標**はありません。可視性と計測を改善するため、該当する場合は キャンペーン名の中に「CTV」などの値を含めることを推奨します。

<div id="support-amazon-eu-consent-policy" />

## Amazon EUの同意ポリシーをサポートする

Google は、 デジタル市場法（DMA）の施行に備えて、<Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">EUユーザーの同意ポリシー</Anchor>を更新しています。Amazonのアプリアトリビューションパートナーとして、AppsFlyerはこれらのポリシー変更に適応し、広告主がAmazonでの広告から最大限の効果を得られるよう支援しています。更新されたポリシーは2026年6月30日に発効します。

<div id="note-4" />

> 📘 **注意**
>
> 更新されたEU同意ポリシーは、EU、UK、またはスイス（CH）のユーザーからのデータ（インストール、再エンゲージメント、アプリ内イベント）にのみ適用されます。

準拠するために、<Anchor target="_blank" href="/marketers/ja/docs/support-google-eu-consent-policy">GoogleのDMA同意</Anchor>に使用されるのと同じ方法でAppsFlyer DMA同意情報を送信してください。

<div id="dma-consent-methods" />

### DMA同意方法

AppsFlyerは現在、DMA同意共有の2つの方法をサポートしています：

| 方法 | 詳細 |
| --- | --- |
| **マニュアル** | Amazonが要求する唯一のフィールドは`ad_user_data_enabled`です。 |
| <Anchor target="_blank" href="https://iabeurope.eu/transparency-consent-framework/">**TCF**</Anchor>**（透明性と同意のフレームワーク）** | 同意管理プラットフォーム（CMP）を使用する場合は、Amazon AdsベンダーID（**793**）が許可されたベンダーリストに含まれていることを確認してください。 |

<div id="note-5" />

> 📘 **注意**
>
> Amazonはまた、<Anchor target="_blank" href="https://iabtechlab.com/gpp/">グローバルプライバシープラットフォーム（GPP）</Anchor>を介した同意信号もサポートしていますが、AppsFlyerは現在この方法をサポートしていません。

<div id="see-also-1" />

> 📄 **参照**
>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance">AppsFlyer SDKを介してDMA同意を送信する</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-overview">AppsFlyer S2Sを介してDMA同意を送信する</Anchor>（`consent_data`を検索）

<div id="traits-and-limitations" />

## 特性と制限

| 特性 | 備考 |
| --- | --- |
| 代理店 | Amazon Adsの連携は、現時点では代理店向けにはサポートされていないため、広告主アカウントからのみ設定・成果の確認が可能です。 |
| インプレッション、クリック、コスト | この連携では、インプレッション、クリック、コストのデータはまだ利用できません。 |
| ディープリンク | [この連携ではディープリンクはサポートされていません](#ディファードディープリンク)。 |
| 再インストールとリアトリビューション | この連携では、再インストールとリアトリビューションはサポートされていません。 |
| プリロードアトリビューション | プリロードは、この連携の一部としてはサポートされていないが、レガシーのamazon\_int連携を介して達成することができます。 |
| ポストバック制限 | Androidでは、`advertiserIdEnabled`フィールドが「false」に設定されている場合、インストールまたは再エンゲージメントは、広告主IDが利用可能であってもAmazonに送信されません。 |

<div data-zendesk-anchors="activate-partner=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A 01H88VAJH3B5ESK12D3ATMMVZ8=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A complete-the-setup-in-amazon-ads=amazon-ads%E5%81%B4%E3%81%A7%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KMG57HR62CC9TX495SG3WSRD=amazon-ads%E5%81%B4%E3%81%A7%E3%81%AE%E8%A8%AD%E5%AE%9A setting-up-amazon-dsp-integration=amazon-ads%E3%81%AE%E8%A8%AD%E5%AE%9A 01H88VAJH3VENKYVRQY5RXN63P=amazon-ads%E3%81%AE%E8%A8%AD%E5%AE%9A 01H88VAJH3BYZSXQGGZZJQ9N0C=%E6%B3%A8%E6%84%8F 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A-1 01H88VAJH34GP7FK1KTJGRDPM7=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A-1 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A 01H88VAJH3F2FJK5YP3M2V7RWD=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A install-attribution=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 01H88VAJH3SSG6ZNV7XQ46W5CX=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 reengagement-attribution=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E8%A8%88%E6%B8%AC h_01J4RC3GR8B04RNFSD61QK45C0=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E8%A8%88%E6%B8%AC ignore-active-users-for-retargeting=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A7%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E7%84%A1%E8%A6%96%E3%81%99%E3%82%8B h_01HNWSTJZPFQVQ5C8M0JA1J0T5=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A7%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E7%84%A1%E8%A6%96%E3%81%99%E3%82%8B h_01HMXNJVHK9C3FT8E04RE0TH99=%E6%B3%A8%E6%84%8F-1 inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3AS37MVF75GANWX4B=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01JEXXHXMEC5M7N1BDSGS3ZZ51=%E6%B3%A8%E6%84%8F-2 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%E6%B3%A8%E6%84%8F-3 h_01HDNZ59NQEDFC3D8JYGENR1NR=%E5%8F%82%E7%85%A7 deferred-deep-linking=%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF 01J9G5FQGB0219RGWVW06BQPG7=%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF raw-data-restrictions=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%B6%E9%99%90 01JBY7HD39BA9ZNR2N2TYYPBW3=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%B6%E9%99%90 ctvtomobile-attribution=ctv-to-mobile%E3%81%AE%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01JZG6S5TB1888XG9560MKEBF3=ctv-to-mobile%E3%81%AE%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 support-amazon-eu-consent-policy=amazon-eu%E3%81%AE%E5%90%8C%E6%84%8F%E3%83%9D%E3%83%AA%E3%82%B7%E3%83%BC%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B h_01KP0DJ73P9FRX51SR3RS4YWVP=amazon-eu%E3%81%AE%E5%90%8C%E6%84%8F%E3%83%9D%E3%83%AA%E3%82%B7%E3%83%BC%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B h_01KP0DJ73PDB7FM1RG0VV99707=%E6%B3%A8%E6%84%8F-4 dma-consent-methods=dma%E5%90%8C%E6%84%8F%E6%96%B9%E6%B3%95 h_01KP0DJ73PG0JMWG3WAWCKXE1S=dma%E5%90%8C%E6%84%8F%E6%96%B9%E6%B3%95 h_01KP0DJ73PNPYT0TRWF089VE9R=%E6%B3%A8%E6%84%8F-5 h_01KP0DJ73PC4ABGRPRDAR7BW5B=%E5%8F%82%E7%85%A7-1 traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90" />
