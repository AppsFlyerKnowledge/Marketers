---
title: '[クローズドベータ版 - 特別アクセス] AppsFlyerとのESP連携をセットアップする'
metadata:
  keywords:
    - Premium
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2024-07-24T14:10:54Z'
  edited_at: '2026-10-14T09:34:33Z'
  id: 26967438815377
  locale: ja
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ja/articles/26967438815377
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** AppsFlyerとのESP連携を設定して、メールキャンペーンでシームレスかつ安全なディープリンクを実現し、ユーザーエンゲージメントとコンバージョン率を向上させます。

## <Image alt="ESP final main KB image.png" src="https://files.readme.io/f14a193bb8d303adb93c01b33dcafba9053359fd92a187378cd324544a94dc88-27434531852049.png" width="613px" />

## AppsFlyerのESP連携について

マーケターは、大規模なメールキャンペーンを送信するために、メールサービスプロバイダー（ESP）を使用することがよくあります。これは、予測可能なユーザージャーニーを提供するシンプルなプロセスであるべきですが、実際にはそうではありません。この問題は、一般的なESPのアナリティクスの扱い方に起因しており、ディープリンクを破壊し、モバイルのユーザーエクスペリエンスに悪影響を及ぼす傾向があります。その結果、ユーザーがアプリではなくモバイルWebサイトに誘導されることがあり、コンバージョンの可能性が低くなります。

AppsFlyerは、AppsFlyerがESPサーバーとお客様のドメイン名の仲介を行う、ESP統合ソリューションによってサポートされています。プロキシとしての役割は、ディープリンクを容易にするアソシエーションファイル（AASA/アセットリンク）の提供を可能にする。さらに、AppsFlyerのソリューションでは、測定データをESPに送り返すため、メール分析を効果的に監視できます。

AppsFlyerとのESP連携を設定して、メールキャンペーンでのスムーズで安全なディープリンク体験を実現し、最適なモバイルユーザーエンゲージメントとコンバージョン率を実現します。

## 連携設定方法：

<span id="h_01J3JHFXRP57VS9D22FEWS2JZW"></span>このセクションでは、ESPとAppsFlyerの連携を設定する方法について説明します。

### 前提条件

AppsFlyerとのESP連携を設定する前に、サポートされているESP*のアカウントが必要です。これらには次のものが必要です。

* 新しい**クリックトラッキングドメイン（**[ステップ1](#step-1-create-a-onelink-template-for-your-email-campaign)で説明）
* **ESP エンドポイント**：エンドポイントはESPから提供されるため、クリックをESPのサーバーにルーティングできます。ESP エンドポイント構造の例: esp.endpoint.com
* **特定の ESP 統合要件：**
  * **Emarsys** - EmarsysカスタマーサクセスマネージャーにHTTPリダイレクトを有効にするよう依頼してください。
  * **Blueshift** - Blueshiftカスタマーサクセスマネージャーに次のことを依頼します。  
    クリックのHTTPレスポンスコードを302（デフォルトの307）に変更します。

**連携を設定するには、次の手順を実行します。**

<div id="step-1-create-a-onelink-template-for-your-email-campaign" />

<Accordion title="ステップ 1. ESPプラットフォームでクリックトラッキングドメインを作成する（IT／システム管理者タスク）">

クリックトラッキングドメイン（CTD）は、メールメッセージに表示されるURLのドメインコンポーネントです。   
サブドメインとメインドメイン（mail.yourbrand.com など）で構成されます。一部のESPは、これをリンクブランディング、トラッカー ドメイン、クリック ドメイン、リンク書き換え、クリック トラッキング、ホワイトラベルなどと呼んでいます。

既存の CTD をすでに使用している場合でも、新しい CTD の**作成は必須**です。これにより、現在のライブメールキャンペーンのトラフィックには影響しません。

> 📘 **備考**
>
> * SSL証明書はAppsFlyerによって処理されます（ステップ3）。
> * この段階では、メールリンクは保護されない可能性があります。つまり、URLプレフィックスはHTTPSではなくHTTPになります。これは[ステップ 5](#h_01JMYDQGPF3B9GNH0RY27JW3E4) で解決されます）。

</Accordion>

<div id="step-2-use-a-oneLink-template-for--your-email-campaign" />

<Accordion title="ステップ 2. OneLink テンプレート を作成し、メールキャンペーンに利用してください。">

<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLink テンプレート</Anchor>を作成し、「**When app is installed**」でユニバーサルリンク/アプリリンクを設定します。このテンプレートは、後でメールキャンペーンのOneLinkリンクを作成するために使用されます。

*既にユニバーサルリンク／アプリリンクを有効にするOneLinkテンプレートを設定している場合は、そのテンプレートを使用できます。

</Accordion>

<div id="step-3-set-your-esp-integration-in-appsflyer" />

<Accordion title="ステップ 3. AppsFlyerでESP連携を設定する">

次に、AppsFlyerでESP連携を設定します。この手順と、その次の手順（「[手順 4.アプリの設定](#step-2-configure-your-app-developer-task)）を同時に設定できます。

**AppsFlyerでESP統合を設定するには：**

1. **AppsFlyer**管理画面 左メニュー **エンゲージメント** > **ESP連携**を選択します。

<Image alt="Engage から ESP integration.png をクリックします。" src="https://files.readme.io/7b731446ce6158d5033020b63be5f386105e7899a8c1b291aa3cb13662a59ee5-27063684942481.png" width="196px" />

2.ESP を選択します。

<Image alt="select ESP.png" src="https://files.readme.io/526fed3aaf1e6fdbf2404243619159984e298752fdf5913fd3a65cc5a2ed9e1d-27086632495761.png" width="482px" />

3.Eメールキャンペーンに使用したい OneLink テンプレートを選択し、**[次へ**] をクリックします。

OneLinkテンプレートを選択

4.選択した ESP のアクティブなアカウントがあることを確認してください。

ESP から次のものが必要です。

* ステップ1で作成したクリックトラッキングドメイン。
* ESP エンドポイント

**次へ**をクリックします。

5.クリック追跡ドメインと ESP エンドポイントを入力し、**［Validate connection］** をクリックします。これにより、クリックトラッキングドメインが入力したエンドポイントを指していることが検証されます。

![ctd と esp endpoint.png を入力します。](https://files.readme.io/d068b7de020bed7ba979b25e0fe866c40a118b00bbfde06a36a4c097485ac885-27086632503441.png)

完了したら、**次へ**をクリックしてください。

6.リンク トラフィックを AppsFlyer にルーティングします

a.<strong>AppsFlyerでカスタマイズしたプレハブの手順をコピーして、IT管理者またはドメイン管理者に送信します。</strong>DNS CNAMEレコードをAppsFlyerが提供する新しいドメインで更新することにより、ESPサーバーからAppsFlyerサーバーにメールキャンペーントラフィックを再ルーティングする必要があります。

その結果、リンクがクリックされるたびに、クリックはAppsFlyerにリダイレクトされ、その後ESPエンドポイントにリダイレクトされます。

<Image alt="click to Af to ESP image.png" src="https://files.readme.io/8a53fa7e8e2574246ea6b1344cfec0ac2d8f319bb181f6956ecb6db5b05cd0c5-26982377140369.png" width="374px" />

b.手順をコピーして送信したら、**[完了**] をクリックします。

ESP 統合が作成されました。

以下の点にご注意ください：

* - ESP 統合ステータスは保留中であり、CNAME レコードがマッピングされた後にのみ機能し始めます。
* - マッピング後、新しい統合が機能し始めてアクティブになるまでに最大 24 時間かかる場合があります。

</Accordion>

<div id="step-2-configure-your-app-developer-task" />

<Accordion title="ステップ 4. アプリの設定（開発者タスク）">

開発者にアプリに次の設定を依頼します。

* [関連ドメインをサポートするようにアプリを構成する](#関連ドメインをサポートするようにアプリを設定する)
* [ディープリンクをサポートするようにアプリを設定します。](#ディープリンクをサポートするようにアプリを設定します)
* [Webリンクとアプリケーションリンクを処理するようにアプリを設定する](#webリンクとアプリケーションリンクを処理するようにアプリを設定する)

#### **関連ドメインをサポートするようにアプリを設定する**

AppsFlyerは、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#ユニバーサルリンク">ユニバーサルリンク（iOS）</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#android-app-link">アプリリンク（Android）</Anchor>を有効にするために、アプリの関連付けファイルをホストします。

**ファイルにアクセスするようにアプリを設定するには：**

**iOS：**  
**前提条件：** <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-ios-sdk-release-notes">v6.12.3</Anchor>以降のSDK  
メールメッセージからアプリへのユニバーサルリンクを有効にするようにアプリを設定します。  
<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">Universal Links</Anchor>の設定について詳細をご覧ください。  
**注：** クリックドメインは、既に関連ドメインで定義されている現在のドメインに追加する必要があります。

**Android：**  
**前提条件：** <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk">v6.12.5</Anchor>以降のSDK  
メールメッセージからアプリへのAndroid App Linkingを有効にするようにアプリを設定します。Android <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#ユニバーサルリンク">App Links</Anchor> の設定 を参照してください。  
**注：** クリックドメインは、Androidマニフェストで既に定義されている現在のドメインに追加する必要があります。


#### **ディープリンクをサポートするようにアプリを設定します**

アプリリンクまたはユニバーサルリンクがクリックされると、アプリが起動します。

**アプリがクリック記録ドメインの背後にあるOneLinkを抽出し、ディープリンクを解決する方法：**

1. クリック記録のドメインをSDK API setResolveDeepLinkURLs に提供します。このAPIは、SDK初期化の前に呼び出す必要があります。

* IOS の場合は、次の<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">手順</Anchor>に従ってください。
* Androidの場合は、次の<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup#flow-description">手順</Anchor>に従ってください。

2.<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Unified DeepLinking API</Anchor> を使用して、ディープリンクパラメータを取得し、ディープリンクデータを処理します。


#### **Webリンクとアプリケーションリンクを処理するようにアプリを設定する**

提供されたコードは、メールキャンペーン内のリンクの折り返し機能を規制することを目的としています。具体的には、次の2つのタイプに対応します。Webサイトを開くことを目的としたWebリンクと、ユニバーサルリンクまたはアプリリンクを介してアプリを開くことを目的としたリンク。  
開発者向けの情報については、以下のガイドを参照してください。

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">iOSディープリンクESP 2.0</Anchor>
* Androidディープリンク

</Accordion>

<div id="h_01JMYDQGPF3B9GNH0RY27JW3E4" />

<Accordion title="ステップ 5. ESP プラットフォームで SSL クリックトラッキングがオンになっていることを確認します。">

メールテストを実行して、リンクステータスを確認してください。   
CTD リンクが HTTP として識別される場合は、ESP チームに連絡して SSL クリックトラッキングを有効にしてください。   
これにより、すべてのHTTPリンクが自動的にHTTPSに変換されます。

ESP に問い合わせる際には、次のサンプル メッセージ テキストを使用できます。

こんにちはチーム  
CTD XXXのSSLクリックトラッキングを有効にしていただけますか？現在は HTTPS ではなく HTTP に設定されています。   
このアップデートにご協力いただきありがとうございます。

</Accordion>

<div id="step-4-customize-the-onelink-link-for-your-email-campaign" />

<Accordion title="ステップ 6. AppsFlyerでメールキャンペーンのOneLinkリンクをカスタマイズする">

**キャンペーンのOneLinkリンクを作成およびカスタマイズする方法：**

1. AppsFlyerにて、OneLink管理ページで（または手動で）、以前に作成したOneLinkテンプレート内に「Email-to-app」OneLinkリンクを作成します。これは、仕様に従ってユーザーをアトリビューションおよびリダイレクトする、メールキャンペーンで使用するリンクです。<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#onelinkリンクの作成">OneLinkリンク</Anchor>の作成方法を参照してください。

<Image alt="email-to-app.png" src="https://files.readme.io/4e30986e039ed4cc13b9963ef3d1bb7b933061176bed812dced45a7240023d54-27082280943761.png" width="652px" />

**ベストプラクティス：** ESPメールキャンペーンと、そのキャンペーンで使用されているAppsFlyer OneLinkリンクの両方で、同じキャンペーン名を使用してください。

</Accordion>

<div id="step-5-test-the-link" />

<Accordion title="ステップ 5：ESPプラットフォームでの連携テスト">

**作成したOneLinkリンクとの連携をテストするには：**

ESPメールエディターを使用して作成し、自分宛に送信するテストメールにOneLink URLを挿入します。

* モバイルデバイスから、メールを開き、リンクをクリックします。アプリがインストールされている場合は、アプリが起動し、関連するコンテンツにディープリンクされます。さらに、モバイルクリックは、AppsFlyer管理画面と、提供されたメディアソースとキャンペーン、およびESPアナリティクス管理画面に表示される必要があります。
* Webリンクをクリックして、正しいリンク先にリダイレクトされることを確認してください。

テストが成功すると、準備完了です。

</Accordion>

<div id="step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns" />

<Accordion title="ステップ 5：メールキャンペーンで安心してリンクを使用する">

よくやった！これで、Eメールキャンペーンでリンクを使用する準備が整いました。その後、ESPまたはAppsFlyerの管理画面でキャンペーン結果を確認できます。

</Accordion>

*この連携でサポートされているESPは次のとおりです。Blueshift、Braze、CleverTap、Customer.io、Emarsys、Expert Sender、Klaviyo、MailExpress、MailGun、Moengage、RDStation、Reteno、Sailthru、Sendgrid、Sparkpostなど完全な<Anchor target="_blank" href="/marketers/ja/docs/email-service-provider-esp-integration-guide">リスト</Anchor>を参照してください。

<div data-zendesk-anchors="overview=appsflyer%E3%81%AEesp%E9%80%A3%E6%90%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01J6RXTXCS7WC0P5X4J96T8JAP=appsflyer%E3%81%AEesp%E9%80%A3%E6%90%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01J3JHJCCASM6E5QYJB5VHQ8HK=appsflyer%E3%81%AEesp%E9%80%A3%E6%90%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 set-up-your-esp-integration-with-appsflyer=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 h_01J3JHFRGA6BTMWSK7EEEVGS6T=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01J3JJ74GYF5AJT9R2P2CXDXE1=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01J3W0Z161XE7BKMMR62SEEZN7=step-1-create-a-onelink-template-for-your-email-campaign h_01JMYJG3CTGE9Y3SBFAECV326G=%E5%82%99%E8%80%83 step-2-use-a-oneLink-template-for-%20your-email-campaign=step-2-use-a-oneLink-template-for--your-email-campaign h_01JMYD02VRGT8353RDBARRPJ2M=step-2-use-a-oneLink-template-for--your-email-campaign h_01J3W0Z161T0D075HPE3Y8H3J4=step-3-set-your-esp-integration-in-appsflyer h_01J3W0Z1613XPYM75GH65R793W=step-2-configure-your-app-developer-task configure-your-app-to-support-associated-domains=%E9%96%A2%E9%80%A3%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B%E3%82%88%E3%81%86%E3%81%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01J3W8XR5QS227XNCD453RWYZ9=%E9%96%A2%E9%80%A3%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B%E3%82%88%E3%81%86%E3%81%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B configure-your-app-to-support-deep-linking=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B%E3%82%88%E3%81%86%E3%81%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%97%E3%81%BE%E3%81%99 h_01J3WS4QWMRT8KSW6J3QHXM9TQ=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B%E3%82%88%E3%81%86%E3%81%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%97%E3%81%BE%E3%81%99 h_01J3W8Y7FMSWPG7MFF6FMSXFM3=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B%E3%82%88%E3%81%86%E3%81%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%97%E3%81%BE%E3%81%99 ::250c928e=web%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%A8%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E5%87%A6%E7%90%86%E3%81%99%E3%82%8B%E3%82%88%E3%81%86%E3%81%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B configure-your-app-to-handle-weblinks-and-application-links=web%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%A8%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E5%87%A6%E7%90%86%E3%81%99%E3%82%8B%E3%82%88%E3%81%86%E3%81%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01J3WS4QWMSKZ33APWFR8CG5TZ=web%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%A8%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E5%87%A6%E7%90%86%E3%81%99%E3%82%8B%E3%82%88%E3%81%86%E3%81%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01J3W8ZMHSXQGJPQEVR62Q28X9=web%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%A8%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E5%87%A6%E7%90%86%E3%81%99%E3%82%8B%E3%82%88%E3%81%86%E3%81%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01J3W0Z1616GFFYCS7WPTNCCHT=step-4-customize-the-onelink-link-for-your-email-campaign h_01J3W0Z161M9NDXAN0KZFA9J4G=step-5-test-the-link h_01J3W0Z161RAYTKH3V9VBAADBM=step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns" />
