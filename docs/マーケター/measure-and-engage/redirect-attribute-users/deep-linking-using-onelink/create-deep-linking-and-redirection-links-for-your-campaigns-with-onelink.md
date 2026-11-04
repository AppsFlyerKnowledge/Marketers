---
title: OneLink｜キャンペーン用ディープリンク・リダイレクトリンクの作成
metadata:
  keywords:
    - Marketers
    - onelink
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2016-05-22T10:03:37Z'
  edited_at: '2026-10-28T09:18:29Z'
  id: 208874366
  locale: ja
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ja/articles/208874366
---
> **概要：** OneLinkを使用して、意図したユーザー体験を提供するリンクを作成します。リンクをクリックしたユーザーは、適切なアプリストア、WebのURL、またはアプリ内へリダイレクトされ、メディアソースにアトリビューションされます。

<div id="onelink-links-and-experiences" />

## OneLinkリンクとユーザー体験

<Embed title="OneLink｜キャンペーン用ディープリンク・リダイレクトリンクの作成" typeOfEmbed="youtube" url="https://www.youtube.com/embed/KZBrxGEjVUE" providerUrl="https://www.youtube.com" />

顧客は、オンラインとオフラインのさまざまな接点でブランドに触れています。ユーザーの流入元を問わず、クリック、アプリのインストール、ディープリンク、ディファードディープリンクまで、最適な体験を提供するリンクを作成できます。

リンクの設定手順は以降のセクションで詳しく説明しますが、主に次の作業が必要です。

* ユーザー体験の選択
* 一般設定
* ユーザー体験に応じた設定
* ディープリンクとリダイレクトの設定
* 追加パラメータの設定

<div id="create-onelink-links-in-onelink-management" />

<div id="create-onelink-links-from-your-ai-tool" />

<div id="create-a-onelink-link" />

## OneLinkリンクの作成

| **担当者**<ul><li>ユーザーをアプリストアやWebのURLへ誘導するOneLinkリンクは、マーケターのみで作成できます。Android App LinksとiOS Universal Linksでアプリを開くようにテンプレートを設定済みであれば、アプリのホーム画面へ誘導するリンクもマーケターのみで作成できます。</li><li>リンクにディープリンクとディファードディープリンクの機能を追加するには、マーケターとAndroid／iOS開発者の両方による対応が必要です。</li></ul> |
| --- |
| **前提条件**<ul><li>少なくとも1つのアプリが登録されているAppsFlyerアカウント。</li><li>リンクの土台となる<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">OneLinkテンプレート</Anchor>。</li><li>アトリビューションを行う場合：各モバイルアプリに<Anchor target="_blank" href="/marketers/ja/docs/integrate-the-appsflyer-sdk">AppsFlyer SDKが実装済み</Anchor>であること。<ul><li>SDKがまだ実装されていない場合も、リダイレクトが機能するリンクは作成できます。ただし、管理画面でのインストール計測、ディープリンク、ディファードディープリンクは利用できません。</li></ul></li></ul> |
| **所要時間**<br /><br />通常のリンクは30分。ディープリンクまたはディファードディープリンクの機能が必要なリンクは約3時間。 |
| **作成結果**<ul><li>ユーザーのデバイスに応じて適切なアプリストア、Webページ、またはアプリ内へ誘導し、意図した体験を提供するリンク。</li></ul> |

> 👍 **Tip**
>
> **AIツールからのOneLinkリンクの作成**
>
> <Anchor target="_blank" href="/marketers/ja/docs/beta-appsflyer-mcp">AppsFlyer MCP</Anchor>に接続したAIツールに、作成したいリンクを普段の言葉で説明して、OneLinkリンクを作成することもできます<Anchor target="_blank" href="/marketers/ja/docs/beta-appsflyer-mcp">。</Anchor>例えば、「ブラックフライデーのメールマガジン用に、アプリ内のセールページを開くリンクを作成して」と依頼できます。 AIが依頼内容を適切なパラメータに変換してリンクの詳細を表示し、承認を得てからリンクを作成します。リンクは既存のOneLinkテンプレートの配下に作成されます。<Anchor target="_blank" href="/marketers/ja/docs/beta-appsflyer-mcp#onelink-management">詳細はこちら</Anchor>

**特定のユーザー体験を提供するOneLinkリンクを作成するには：**

1. AppsFlyerのサイドメニューから、［**Engage**］>［**OneLink管理**］を選択します。
2. カスタムリンクを追加する**OneLinkテンプレート**を選択します。
3. ［**リンクを追加**］をクリックします。
4. 提供する［[ユーザー体験](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#experiences)］を選択します。
5. メディアソースを選択するか、独自のメディアソースを入力します。 AppsFlyerでは、データがこのメディアソースに紐づいて表示されます。メディアソースは、リンク内の`pid`パラメータの値として設定されます。

   <div id="note" />

   > 📘 **注意**
   >
   > AppsFlyerは、メールやSMSなどのオウンドメディアで、予約済みの<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#srn媒体">SRN</Anchor>名をPID値に使用したアトリビューションリンクをブロックします。この制限は、アドバンスSRNには適用されません。

6. ［**次へ**］をクリックします。
7. ［[一般設定](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings)］を完了します。
8. ［**次へ**］をクリックします。
9. （任意）作成するユーザー体験に応じて、該当する手順を実施します。

   

| ユーザー体験 | 設定できる項目 |
| --- | --- |
| <ul><li>Social-to-app</li><li>Text-to-app</li><li>Referral-to-app</li><li>カスタムリンク</li></ul> | <ul><li>[ソーシャルメディアプレビュー](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[ソーシャルアプリ向けランディングページ](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li></ul> |
| Email-to-app | ESPを使用する場合は、<Anchor target="_blank" href="/marketers/ja/docs/email-service-provider-esp-integration-guide">ESPの連携手順</Anchor>に従ってください。 |
| App-to-app | <Anchor target="_blank" href="/marketers/ja/docs/cross-promotion-attribution-for-marketers">クロスプロモーション</Anchor>を利用すると、複数のアプリ間で機能する動的なリンクを作成できます。 |
| Referral-to-app | <ul><li>[ソーシャルメディアプレビュー](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[ソーシャルアプリ向けランディングページ](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li><li><Anchor target="_blank" href="/marketers/ja/docs/user-invite-attribution">ユーザー招待の連携</Anchor>を利用すると、アプリのSDK経由でReferral-to-appリンクを動的に作成できます。</li></ul> |

10. ［**次へ**］をクリックします。
11. （任意）［**ディープリンクとリダイレクト**］で、[ディープリンク／ディファードディープリンクの設定](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)を完了します。このリンクでディープリンクを使用しない場合は、このセクションをスキップします。
12. （任意）［**ディープリンクとリダイレクト**］で、[リダイレクト設定](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection)を変更します。 OneLinkテンプレートのリダイレクト設定が適切な場合は、このセクションをスキップします。
13. ［**次へ**］をクリックします。
14. ［**追加パラメータ**］で、リンクに[定義済みまたはカスタムのパラメータを追加](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#additional-parameters)し、より詳細な分析に活用します。<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">アトリビューションパラメータの詳細はこちら</Anchor>
15. ［**リンクを生成**］をクリックします。
16. ユーザーのリダイレクト先とするすべてのドメインが、<Anchor target="_blank" href="/marketers/ja/docs/set-up-your-domain-redirect-allowlist">ドメインのリダイレクト許可リスト</Anchor>に登録されていることを確認します。

<div id="experiences" />

<Accordion title="ユーザー体験">

以下のユーザー体験に対応するリンクを作成できます。

* **Social-to-app**：ソーシャルメディア上でユーザーの関心を引き、投稿からアプリへ誘導します。
* **App-to-app**：他のアプリ内に表示される広告から、自社アプリへユーザーを誘導します。
* <Anchor target="_blank" href="/marketers/ja/docs/qr-to-app-conversion">**QR-to-app**</Anchor>：オフラインでの顧客体験の要所でユーザーにQRコードを読み取ってもらい、アプリのインストールを促進します。デスクトップサイトやテレビ・CTV広告にQRコードを掲載して、ユーザーをアプリへ誘導することもできます。
* **Email-to-app**：メール配信サービスプロバイダー（ESP）を利用してメールでユーザーの関心を引き、受信トレイからアプリへ誘導します。
* **Text-to-app**：SMSやメッセージ配信キャンペーン用のリンクを作成し、テキストメッセージを通じてユーザーのエンゲージメントを促進します。
* **Referral-to-app**：ユーザーやインフルエンサーが他のユーザーをアプリに招待したり、記事などの特定のアプリ内コンテンツを共有したりできるユーザー招待リンクを作成します。
* **カスタムリンク**：上記のいずれにも該当しないユーザー導線には、OneLinkカスタムリンクを作成できます。デスクトップ／モバイル、オンライン／オフライン、オウンドメディア／有料メディアを問わず、あらゆる流入元のユーザーを適切な遷移先へ簡単に誘導できます。

</Accordion>

<div id="general-settings" />

<Accordion title="一般設定">

一般設定は、OneLinkリンクの作成時に、すべてのユーザー体験に共通して設定するセクションです。

**一般設定を行うには**：

1. （任意）メディアソース名を変更します。
2. （任意）キャンペーン名を変更します。
3. （任意）このリンクで既存ユーザーをターゲティングする場合は、［**リターゲティング**］を有効にします。

   これにより、カスタムリンクをクリックしたユーザーによるリエンゲージメントを確認できます。

   既存ユーザーがリターゲティング以外のリンク（UA）をクリックした場合も、アプリが開き、同じユーザー体験が提供されます。ただし、リエンゲージメントは通常のセッションとして記録されるため、オウンドメディアキャンペーンの成果を計測できません。

   <div id="important" />

   > 🚧 **重要**
   >
   > リターゲティングを機能させるには、アプリ側でもリターゲティングを有効にする必要があります。

4. （任意）［**アクティブユーザーをリターゲティング対象から除外**］を有効にし、非アクティブ期間を選択します。  
   これにより、リンクにaf\_inactivity\_window=[number of days]パラメータが追加され、指定した期間内にアクティブだったすべてのユーザーがリターゲティング対象から除外されます。
5. リエンゲージメント期間を設定します。これは、リエンゲージメント後に発生したユーザーのアプリ内イベントを、リターゲティングメディアソースにアトリビューションする期間です。
   * 日単位（1～90日）、時間単位（最大23時間）、または無期限に設定できます。
   * リエンゲージメント期間は、リンクのaf\_reengagement\_windowパラメータに追加されます。
6. （任意）［**リンクのブランディング**］サブセクションで、以下を設定します。
   * ブランドに合った別のドメインを選択します。<Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain">詳細はこちら</Anchor>
   * <span id="url-id"></span>キャンペーンの訴求内容が伝わるようにURL IDを編集します。 URL IDは英数字の組み合わせで、最大50文字です。デフォルトは8文字です。

<div id="enable-retargeting-for-the-app" />

#### アプリのリターゲティングの有効化

アプリでリターゲティングを一度も有効にしたことがない場合は、一度設定する必要があります。 <Anchor target="_blank" href="/marketers/ja/docs/app-settings#アトリビューション設定">詳細はこちら</Anchor>

**アプリ単位でリターゲティングを設定するには：**

1. AppsFlyerのサイドメニューから、［**設定**］>［**アプリ設定**］を選択します。
2. ［**アトリビューション**］セクションで、［**リエンゲージメントのアトリビューション**］を有効にします。
3. ［**設定を保存**］をクリックします。

</Accordion>

<div id="social-media-preview-og-tags" />

<Accordion title="ソーシャルメディアプレビュー：OGタグ">

リンクを共有すると、Open Graph（OG）タグを使用して、タイトル、説明、画像を含むプレビューが生成されます。

これらのOGタグは、リダイレクト先のWeb URLやアプリストアから自動的に取得される場合があります。ただし、この方法ではプレビューを生成できないことがあります。そのため、OneLinkでソーシャルメディアプレビューを設定することをおすすめします。OneLinkのUIを使用するか、UI以外で作成したリンクの場合はOGタグのパラメータをリンクに追加してください。

**OneLinkのUIで独自のソーシャルメディアプレビューを作成するには：**

1. OneLinkカスタムリンクエディターで、［**ソーシャルメディアで共有**］セクションに移動します。
2. ［**ソーシャルメディアプレビュー**］セクションで、リダイレクト先URLのOGタグを使用する場合は［**デフォルトのプレビュー（Webサイト／ストアから取得）**］を、独自に設定する場合は［**カスタムプレビュー（画像とタグ）**］を選択します。
3. ［**カスタムプレビュー（画像とタグ）**］を選択した場合は、以下を入力します。
   * タイトル
   * 説明
   * 画像URL
4. （任意）［**テンプレートのファビコン**］フィールドを確認します。
   * ここには、OneLinkの<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#h_favicon">テンプレート設定</Anchor>で設定されたファビコンが表示されます。対応するプラットフォームのリンクプレビューに、自動的に表示されます。
   * ファビコンを変更するには、<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#h_favicon">テンプレート設定</Anchor>に移動します。
   * ファビコンが表示されない場合は、テンプレートにまだ設定されていません。ファビコンがなくても、カスタムプレビューは利用できます。

**リンクにOGタグのパラメータを追加するには**（OneLinkのUI以外で作成したリンクの場合）：

* 以下の必須パラメータを追加します。
  * af\_og\_title（最大40文字）
  * af\_og\_description（最大300文字）
  * af\_og\_image

<div id="note-1" />

> 📘 **注意**
>
> * AppsFlyerのUI以外でも、リンクにOGタグのパラメータを追加できます。
> * X（旧Twitter）用のOGタグを別途追加すると、通常のAppsFlyerのプレビューよりも優先されます。

</Accordion>

<div id="social-app-landing-page" />

<Accordion title="ソーシャルアプリ向けランディングページ">

<div id="important-1" />

> 🚧 **重要**
>
> Meta広告でiOS Universal Linksがサポートされるようになりました。
>
> * Metaが<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-faq#are-ios-universal-links-and-android-app-links-supported-in-meta-ads">Universal Linksに対応</Anchor>したため、Universal Linksに対応するMetaの有料広告では、ソーシャルアプリ向けランディングページは不要になりました。
> * 自社の投稿（有料広告以外）には、ソーシャルアプリ向けランディングページが必要です。

ソーシャルメディアアプリでは、Universal Linksを利用する既存ユーザー向けのスムーズな導線が機能しない場合があります。これには、次の方法で対処できます。

* ［**推奨**］ソーシャルアプリ向けランディングページを作成します。  
  ソーシャルアプリ向けランディングページを作成する場合は、URIスキームを設定しておくことをおすすめします。  
  **注意：** X（旧Twitter）はiOSのURIスキームに対応していません。アプリの起動に関する問題を避けるため、Universal Linksを使用するソーシャルアプリ向けランディングページを利用してください。
* ［代替手段］`af_force_deeplink=true`パラメータを使用して、<Anchor target="_blank" href="/marketers/ja/docs/onelink-troubleshooting-and-faq#強制ディープリンク">アプリを強制的に開きます</Anchor>。  
  **注意**：このパラメータは、Kakaotalk、Naver、Naver-Blog、Chrome、Weibo、X（旧Twitter）では自動的に有効になります。

ソーシャルアプリ向けランディングページを使用すると、ソーシャルメディアアプリ内の広告をクリックしたユーザーは、AppsFlyerが生成するランディングページにリダイレクトされます。そのページから、ディープリンクでアプリ内へ移動するか、アプリのインストールに進むことができます。

AppsFlyerは、さまざまなソーシャルアプリ向けランディングページのテンプレートを提供しています。テンプレート内の要素の配置は固定されていますが、背景画像や背景色、タイトル、テキスト、画像、ボタン、タグなど、各要素はカスタマイズできます。

ソーシャルアプリ向けランディングページは、以下のソーシャルメディアアプリで使用できます。

* Instagram
* Facebook／Facebook Messenger（**注意**：FacebookとFacebook Messengerでは、URIスキームとソーシャルアプリ向けランディングページの両方が設定されている場合、ランディングページは表示されません。）
* LinkedIn
* iOS版Pinterest
* Snapchat
* X（旧Twitter）
* WeChat

**ユーザー体験**

ユーザーがランディングページのCTAボタンを操作した場合：

* **アプリがインストールされている場合**：クリックしたユーザーのアプリが開きます。
* **アプリがインストールされていない場合**：該当するアプリストアへ誘導されます。インストール後は、ディファードディープリンクでユーザーを誘導できます（[ディープリンクとディファードディープリンク](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)で説明しています）。

<div id="note-2" />

> 📘 **注意**
>
> ソーシャルアプリ向けランディングページは、OneLinkのショートURLにのみ対応しています。

<div id="to-use-the-social-app-landing-page" />

#### **ソーシャルアプリ向けランディングページを使用するには：**

1. 次のセクションの説明に従って、ランディングページを設定します。
2. 生成されたOneLinkの**ショート**URLを控えておきます。  
   OneLinkのロングURLでは、ソーシャルアプリ向けランディングページは機能しません。
3. OneLinkのショートURLをソーシャルアプリに投稿します。

アトリビューションは、アトリビューション設定に基づいて決まります。

<div id="to-set-up-the-social-apps-landing-page" />

#### **ソーシャルアプリ向けランディングページを設定するには：**

1. カスタムリンクの設定で、［**Social-to-app**］セクションに移動します。
2. ［**ソーシャルアプリ向けランディングページ**］セクションで、［**ソーシャルアプリ向けランディングページを作成**］をクリックします。  
   ランディングページのテンプレートを選択するウィンドウが開きます。  
   [![](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)
3. 使用するランディングページのテンプレートにカーソルを合わせ、［**作成**］をクリックします。**ヒント**：テンプレートの🛈アイコンにカーソルを合わせると、適した用途を確認できます。 Instagramでは、Clustered PosterとShowAndTellをおすすめします。
4. ランディングページのクリエイティブ内の各要素をカスタマイズします。要素名から選択するか、プレビュー画像内の要素をクリックして編集します。    
   **ヒント**：クリエイティブのテンプレートを変更する場合に備えて、入力したテキストを保存しておいてください。
5. テンプレートの画像をすべて独自の画像に置き換えます。  
   1. `https://example.com/image.png`のように、拡張子を含む画像URLを入力します。
   2. 使用できるファイル形式は、jpeg、jpg、pngです。   
      **注意**：webp形式には対応していません。
   3. 画像の推奨仕様は以下のとおりです。

| テンプレートの画像タイプ | 画像ファイルの最大サイズ | 画像の縦横比 |
| --- | --- | --- |
| Collection | 300KB | 16:9（横長） |
| <ul><li>Trapeze</li><li>Carousel</li><li>ShowAndTell</li></ul> | 300KB | 1:1 |
| <ul><li>Flyer</li><li>Poster</li><li>Blurry poster</li><li>Clustered poster</li></ul> | 300KB | 9:16（縦長） |

   4. いずれかの画像URLが正確でない場合はエラーが表示され、クリエイティブを確認できません。  
      [![](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)
6. ランディングページのクリエイティブを確認するには、［**確認**］をクリックします。  
   修正が必要な場合は、［**エディターに戻る**］をクリックします。  
   [![](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)
7. ランディングページを保存するには、［**完了**］をクリックします。  
   **重要**：作成・更新したランディングページのクリエイティブは、カスタムリンクを生成・更新してから適用されます。
8. （任意）ランディングページを編集するには、［**ソーシャルアプリ向けランディングページを編集**］をクリックします。

</Accordion>

<div id="deep-linking-and-deferred-deep-linking" />

<Accordion title="ディープリンクとディファードディープリンク">

ディープリンクでは、既存のアプリユーザーをリターゲティングし、アプリストアやアプリのホーム画面を経由せずに、アプリ内の特定の体験（特定のページなど）へ直接誘導します。これらのユーザーには、リターゲティングのアトリビューションが適用されます。

ディファードディープリンクでは、新規ユーザーにも既存ユーザーと同様のディープリンク体験を提供します。ただし、新規ユーザーはまずアプリストアへ誘導され、アプリをダウンロードして起動した後に、特定の体験やページへ移動します。

<div id="note-3" />

> 📘 **注意**
>
> ディープリンクとディファードディープリンクの設定には、Android／iOS開発者の対応が必要です。

**ユーザーをアプリ内の特定の体験へ誘導するディープリンクとディファードディープリンクを設定するには：**

1. iOS／Android開発者と相談し、リンクに設定する**deep\_link\_value**を決めます。
   * **deep\_link\_value**は、ユーザーの誘導先となる特定のアプリ内コンテンツを示す値です。開発者が、**deep\_link\_value**に応じた動作をコードに実装します。
   * 開発者が、意図した動作をコードに実装します。技術的な処理の流れや実装例を確認できるよう、開発者にガイドを共有してください。
     * アプリのインストール有無を問わず、新規・既存ユーザーに<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">ディープリンクとディファードディープリンクの両方</Anchor>を提供するためのガイドです。  
       **UDLに関する注意事項：**
       * SDK V6.1以降が必要です。
       * クリックのルックバック期間は最大15分です。
     * **注意**：OneLinkでディープリンクをすでに利用している場合は、UDLではなく、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_gcd_legacy">Android</Anchor>や<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_gcd_legacy">iOS</Anchor>の従来の方法を使用している可能性があります。

       <div id="tips" />

       > 📄 **ヒント**
       >
       > **deep\_link\_value**には、商品のSKU、ソーシャルメディアの投稿ID、URLのパス、その他任意の値を使用できます。
       >
       > **deep\_link\_value**やその他のパラメータ・値について、長期的な運用に適した仕組みを開発者と協力して検討することが重要です。これにより、追加のアプリアップデートを最小限に抑えられます。**その都度アプリのコードを変更せずに**、アプリ内の異なるコンテンツへ誘導するさまざまなディープリンクを生成できるよう、動的な値の利用について開発者と相談してください。
       >
       > 例えば、**deep\_link\_value**に果物の種類を指定することにし、開発者が動的な値に対応するよう実装したとします。この場合、開発チームの追加作業なしで、任意の果物を指定できます。
       >
       > &lt;0>https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month0>&lt;1>&lt;0>&&lt;2>deep\_link\_value=apples2>0>1>&lt;3>&lt;0>...0>0>
       >
       > &lt;0>https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month0>&lt;1>&lt;0>&&lt;2>deep\_link\_value=bananas2>0>1>&lt;3>&lt;0>...0>0>
       >
       > &lt;0>https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month0>&lt;1>&lt;0>&&lt;2>deep\_link\_value=peaches2>0>1>&lt;3>&lt;0>...0>0>

2. 選択したパラメータと値に応じてアプリが動作することを開発者に確認したら、リンク設定ページの［**ディープリンクとリダイレクト**］セクションで、開発者と決めた［**ディープリンクの値**］を入力します。
3. （任意）ディープリンクで複数のアプリ内体験を提供する場合（商品ページへ誘導し、さらに割引も提供する場合など）は、ディープリンクのデータペイロードに［**追加のディープリンクの値**］を追加できます（deep\_link\_sub1パラメータを使用）。さらにディープリンク用パラメータ（deep\_link\_sub2-10）を追加する場合は、［**追加パラメータ**］セクションで設定できます。
   1. iOS／Android開発者と相談し、使用する値を決めます。
   2. 開発者が、意図した動作をコードに実装します。 技術的な処理の流れや実装例を確認できるよう、開発者にOneLinkのガイドを共有してください。

      <Tabs>
      <Tab title="Android">

      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_overview">Android開発者向けの手順</Anchor>

      </Tab>

      <Tab title="iOS／Unity">

      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_overview">iOS開発者向けの手順</Anchor>

      </Tab>
      </Tabs>

   3. ［**追加パラメータ**］セクションで、開発者と決めた内容に従い、必要に応じてカスタムパラメータ**deep\_link\_sub2-10**とその値を追加します。

<div id="note-4" />

> 📘 **注意**
>
> 開発者がパラメータと動的な値を実装すれば、マーケターはOneLink APIで数千ものカスタムリンクを自動生成できます。<Anchor target="_blank" href="/marketers/ja/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">詳細はこちら</Anchor>

</Accordion>

<div id="redirection" />

<Accordion title="リダイレクト">

**新規ユーザーをアプリストアではなくランディングページへ誘導するには**：

1. リンク設定ページの［**ディープリンクとリダイレクト**］セクションで、［アプリがインストールされていない場合］の遷移先として別のURLを選択します。  
   AndroidとiOSそれぞれのカスタムURLにより、新規ユーザーは指定のランディングページへ誘導されます。   
   **注意** OneLinkテンプレートにカスタムURLがすでに設定されている場合は、カスタムリンクに指定したURLで上書きされます。
2. 新規ユーザーを<Anchor target="_blank" href="/marketers/ja/docs/redirect-users-to-custom-app-store-product-pages">カスタムプロダクトページ</Anchor>へ誘導することもできます。

</Accordion>

<div id="additional-parameters" />

<Accordion title="追加パラメータ">

キャンペーン、広告セット名、広告名、チャネル、独自のカスタムパラメータ、番号1～5の<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">サブパラメータ</Anchor>などをリンクに追加できます。これにより、マーケティング施策をより詳細に分析できます。<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">追加のアトリビューションパラメータ</Anchor>の詳細をご確認ください。

ディープリンク用の追加パラメータ（deep\_link\_sub2-10）も追加できます。

**パラメータを追加するには**：

1. リンク設定の［**追加パラメータ**］セクションで、［**パラメータを追加**］をクリックします。
2. 追加するパラメータを選択するか、カスタムパラメータを入力します。

</Accordion>

<div id="testing" />

<Accordion title="テスト">

以下のユーザーがリンクから正常にリダイレクトされるか、テストできます。

* アプリをインストールしていない新規ユーザー
* アプリをインストール済みの既存ユーザー

<div id="new-users-without-your-app-installed" />

#### アプリをインストールしていない新規ユーザー

**前提条件**：アプリがインストールされていない<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">登録済みテストデバイス</Anchor>。

**リンクをテストするには**：

1. AppsFlyerのサイドメニューから、［**Engage**］>［**OneLink管理**］を選択します。
2. テストするリンクの［**アクション**］アイコンにカーソルを合わせ、［**URLを取得**］をクリックします。
3. ショートURLまたはロングURLをスマートフォンに送信します。次のいずれかの方法を使用できます。
   * スマートフォンのカメラまたはQRコード読み取りアプリで、QRコードを読み取ります。
   * メールまたはWhatsAppで自分宛てにリンクを送信し、スマートフォンで開きます。  
     **注意：** iOSのメモやモバイルブラウザに直接貼り付けないでください。この場合、モバイルOSの仕様により、アプリが開かないことがよくあります。
4. モバイルデバイスでリンクをクリックします。  
   プラットフォームに応じて、アプリストアまたはランディングページが開くことを確認します。  
   **注意**：モバイルデバイス上で実際にクリックする必要があります。 JavaScriptや301／302リダイレクトでは、Universal LinksとAndroid App Linksを動作させることはできません。ブラウザによっては、これらの方法では基本的なリダイレクトも機能しません。
5. アプリをダウンロードして起動します。
   * アプリのホーム画面が開くことを確認します。
   * ディファードディープリンクを実装した場合は、リンクのパラメータで指定したコンテンツが開くことを確認します。
6. AppsFlyerの**Overview dashboard**で、新しいインストールを確認します。  
   URLに指定したメディアソース（例：test）とキャンペーン名に、新しいクリックとインストールが記録されていることを確認します。

リンクが想定どおりに機能しない場合 <Anchor target="_blank" href="/marketers/ja/docs/onelink-troubleshooting-and-faq">OneLinkのよくある質問とトラブルシューティングガイド</Anchor>をご確認ください。

<div id="existing-users-with-your-app-installed" />

#### アプリをインストール済みの既存ユーザー

**前提条件**：アプリがインストールされているAndroidデバイスまたはiOSデバイス（両方も可）。 開発者が変更を加え、Universal Links、App Links、URIスキームを実装したアプリの配布元とバージョンであることを確認してください。

**リンクをテストするには：**

1. AppsFlyerのサイドメニューから、［**Engage**］>［**OneLink管理**］を選択します。
2. 対象の**OneLinkテンプレート**をクリックします。
3. 一覧からカスタムリンクを選択します。
4. テストするリンクの［**アクション**］アイコンにカーソルを合わせ、［**URLを取得**］をクリックします。
5. ショートURLまたはロングURLをスマートフォンに送信します。次のいずれかの方法を使用できます。
   * スマートフォンのカメラまたはQRコード読み取りアプリで、QRコードを読み取ります。
   * メールまたはWhatsAppで自分宛てにリンクを送信し、スマートフォンで開きます。  
     **注意：** iOSのメモやモバイルブラウザに直接貼り付けないでください。この場合、モバイルOSの仕様により、アプリが開かないことがよくあります。
6. モバイルデバイスでリンクをクリックします。
   * アプリのホーム画面が開くことを確認します。
   * ディープリンクを実装した場合は、リンクのパラメータで指定したコンテンツが開くことを確認します。
7. AppsFlyerの**Overview dashboard**（［**表示タイプ：リターゲティング**］）に移動します。  
   リンクのメディアソース（例：test）とURLに指定したキャンペーン名に、新しいクリック／リエンゲージメント（アプリ起動）が記録されていることを確認します。

リンクが想定どおりに機能しない場合 <Anchor target="_blank" href="/marketers/ja/docs/onelink-troubleshooting-and-faq">OneLinkのよくある質問とトラブルシューティングガイド</Anchor>をご確認ください。

</Accordion>

<div id="additional-procedures" />

## その他の手順

<div id="create-a-custom-impression-url" />

<Accordion title="カスタムインプレッションURLの作成">

カスタムインプレッションリンクを使用すると、次のことが可能です。

* 配信する広告の<Anchor target="_blank" href="/marketers/ja/docs/about-conversion-rates#マーケティングファネルの各段階とコンバージョン率-1">インプレッションからクリックへの転換率</Anchor>を計測できます。
* インプレッションに基づくアトリビューションを行えます。

**前提条件：** 正常に機能するOneLinkのロングURL。ショートURLには対応していません。

**担当者：**

マーケターとWeb開発者

**インプレッションの計測のみを行うインプレッションURLを作成するには：**

1. AppsFlyerのサイドメニューから、［**Engage**］>［**OneLink管理**］を選択します。
2. テストするリンクのオプションメニュー**にカーソルを合わせ、**［**URLを取得**］をクリックします。
3. 編集するため、OneLinkのロングURLをコピーします。  
   例：`https://subdomain.onelink.me/j7rN?pid=email&c=Spring`
4. サブドメイン（ブランドドメインを使用している場合はその全体）を「impressions」に置き換えます。    
   例：ブランドドメインを使用したOneLinkが次の場合：`https://app.alltrails.com/Waim?` 次のインプレッションリンクに変更します：`https://impressions.onelink.me/Waim?`.
5. インプレッションURLをコピーして、開発者に送信します。
6. Web開発者に、Webサイトの処理にインプレッションURLを組み込むよう依頼します。

これで、Webサイトのページでインプレッション数をカウントするためのURLができました。ただし、このURLでは**新規インストールのアトリビューションは行えません**。 ビュースルーアトリビューションを行うには、次の手順に進みます。

**インプレッションURLをアトリビューションに使用するには：**

1. 前述の手順に従って、インプレッションURLを用意します。
2. <Anchor target="_blank" href="/marketers/ja/docs/measure-view-through-engagements">ビュースルーアトリビューションが有効になっている</Anchor>ことを確認します。
3. （任意）ビュースルーの<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">ルックバック期間</Anchor>をデフォルトの1日から変更する場合は、新しい値を指定した`af_viewthrough_lookback`パラメータを追加します。例：`af_viewthrough_lookback=1d`。
4. インプレッションURLをコピーして、開発者に送信します。
5. Web開発者に、Webサイトの処理にインプレッションURLを組み込むよう依頼します。

インプレッションURL全体の例：

```http
https://impressions.onelink.me/j7rN?pid=email&c=Spring&af_viewthrough_lookback=1d
```

</Accordion>

<div id="deep-linking-post-event" />

<Accordion title="イベント後のディープリンク">

次のようなイベントの後にのみ、ディープリンクでユーザーをアプリ内の特定の操作やページへ誘導したい場合があります。

* ログイン
* スプラッシュ画面の表示
* 利用規約への同意
* その他

**イベント後にディープリンクでユーザーを誘導するには**：

開発者に、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_dl_post_event">Android</Anchor>と<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_dl_post_event">iOS</Anchor>のイベント後のディープリンク手順に従って作業するよう依頼します。

</Accordion>

<div id="deferred-deep-linking-with-ios-private-relay" />

<Accordion title="iOSのプライベートリレー利用時のディファードディープリンク">

iOS 15以降、AppleはiCloud+ユーザーに<Anchor target="_blank" href="https://www.macworld.com/article/348965/icloud-plus-private-relay-safari-vpn-ip-address-encryption-privacy.html">プライベートリレー</Anchor>機能を提供しています。ユーザーはこの機能を使ってWeb閲覧時の通信を暗号化し、正確な位置情報、IPアドレス、閲覧時の通信内容を非公開にできます。ユーザーがプライベートリレーを有効にすると、アトリビューションとディファードディープリンクに影響が生じる可能性があります。つまり、アプリをインストールしていない新規ユーザーがApp Storeへ移動し、アプリをインストールして起動しても、プライベートリレーによってアプリ内の特定のページへ誘導できない場合があります。

ディファードディープリンク（DDL）を想定どおりに機能させるには、次のいずれかのAppsFlyerのソリューションを実装する必要があります。

* **［推奨］App Clipを利用する方法**：ユーザーのアトリビューションデータを取得し、DDLで実現したい体験に近い、カスタマイズした体験へユーザーを誘導するApp Clipを作成します。 App Clipからフル版アプリへユーザーを誘導する導線を追加することもできます。
* **クリップボードを利用する方法**：URLからディファードディープリンクのデータをコピーし、ユーザーをアプリへ正しくリダイレクトするWebランディングページを作成します。**注意**：この方法は、アトリビューションには対応していません。

<div id="app-clipbased-solution" />

<Accordion title="App Clipを利用する方法">

この方法では、OneLinkのショートURLとiOSのApp Clips技術を組み合わせ、フル版アプリをインストールしなくても、ユーザーを製品内の特定の操作フローへ誘導できます。 OneLinkのショートURLからユーザーのアトリビューションデータを取得し、DDLで実現したい体験に近い、カスタマイズしたApp Clipの体験へユーザーを誘導します。 App Clipからフル版アプリへユーザーを誘導する導線を追加することもできます。**注意**：App Clipを利用する方法でフル版アプリを再インストールすると、AppsFlyerでオーガニックインストールとして報告される場合があります。 0>

<div id="flow" />

#### **処理の流れ**

App Clipを利用したDDLの処理の流れは、以下のとおりです。

1. 広告主がApp Clipを作成し、プライベートリレーを有効にしているユーザー向けに、OneLinkテンプレートへ追加します。
2. ユーザーがOneLink URLをタップします。
3. AppsFlyerのWebハンドラーが、以下を確認します。
   * デバイスがiOS 15以降を使用していること
   * ブラウザがSafariであること
   * ユーザーがプライベートリレーを有効にしていること
4. 上記を確認すると、［**App Clipを再生**］または［**Safariで表示**］をクリックするよう、ユーザーに案内が表示されます。
   * ユーザーが［**App Clipを再生**］をクリックすると、App Clipカードが表示されます。
   * ［Safariで表示］をクリックすると、App Clipを開くよう案内するランディングページが開きます。
5. ユーザーがApp Clipを開きます。
6. App Clipが開き、アプリのマーケターと開発者が決めたユーザー体験が提供されます。
7. App Clipにフル版アプリへの導線がある場合、ユーザーはApp Storeへ誘導され、フル版アプリをダウンロードします。アプリを起動すると、開発者が定義したユーザー体験が提供されます。

**前提条件：** AppsFlyer SDK V6.4.0以降

**App Clipを利用するDDLを設定するには**：

1. 開発者に、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#app-clip-based-solution">App Clipを利用する方法の開発者向けドキュメント</Anchor>に従って作業するよう依頼します。あわせて、意図したユーザー体験を提供するApp Clipの作成を依頼します。 App Clipからフル版アプリへユーザーを誘導する導線を追加することもできます。
2. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">Universal Links</Anchor>と[ディファードディープリンク](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)を設定した<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">OneLinkテンプレート</Anchor>を作成または編集します。
3. OneLinkテンプレートで、［**プライベートリレーを使用しているユーザーにApp Clipを表示**］を有効にします。 App Clipを用意していない場合は、有効にしないでください。  
   **注意**：Universal Linksを設定したOneLinkテンプレートで、App Clip機能の追加・削除などの変更を行うと、AASAファイルの更新に数時間かかる場合があります。そのため、そのテンプレートから作成したリンクに、更新した機能がすぐには反映されないことがあります。
4. OneLinkテンプレートをもとにカスタムリンクを作成します。
5. App Store Connectで［**App Clip Experience**］セクションに移動し、［**App URLs**］までスクロールして、OneLinkテンプレートのURL（ドメイン＋テンプレートID）を入力します。例：`yourbrand.onelink.me/GrbZ`。または、特定のOneLinkカスタムリンクのショートURLを入力します。  
   **注意**：OneLinkカスタムリンクを入力した場合、App Clipを利用する方法は、そのリンクをタップしたユーザーにのみ機能します。同じOneLinkテンプレートから作成した他のリンクでは機能しません。

</Accordion>

<div id="clipboardbased-solution" />

<Accordion title="クリップボードを利用する方法">

<div id="flow-1" />

#### **処理の流れ**

クリップボードを利用したDDLの処理の流れは、以下のとおりです。

1. 広告主が、`af_cp_lp=true`パラメータを含むディファードディープリンクを作成します。
2. ユーザーがディファードディープリンクをタップします。
3. AppsFlyerが、以下を確認します。
   * デバイスがiOS 15以降を使用していること
   * ブラウザがSafariであること
   * ユーザーがプライベートリレーを有効にしていること
   * リンクに`af_cp_lp=true`パラメータが含まれていること
4. 上記を確認すると、アプリアイコン、画像、App Storeからアプリを入手するためのCTAを含むWebランディングページが読み込まれます。また、アプリ内の特定のページへ誘導して最適なユーザー体験を提供するために、URLをコピーすることを説明したメッセージも表示されます。  
   ![ios_15_ip_masking__1_.png](https://files.readme.io/c130314c98ebd42f50feaafd752c0cea954f42c5bfd99a6dbd94daf9e48c2ff4-30151216595345.png)
5. ユーザーが［**アプリを入手**］をタップします。
6. ユーザーはApp Storeへ誘導され、アプリをインストールします。その後、初回起動時にアプリ内の特定のページへ誘導されます。

<div id="requirements" />

#### **要件**

コピー＆ペースト用ランディングページを利用するDDLには、次の要件があります。

* ユーザーがSafariでWebを閲覧していること。
* ディファードディープリンクに`af_cp_lp=true`パラメータが含まれていること。
* AppsFlyer iOS SDK V6以降を使用していること。
* iOSアプリの開発者が、クリップボードからURL内のディファードディープリンクデータを貼り付けるコードを実装していること。このコードはAppsFlyer SDKには含まれていません。
* ユーザーがチェックボックスをオンのままにしていること（デフォルト）。チェックを外すとURLがコピーされず、ディファードディープリンクは機能しません。

<div id="setup" />

#### **設定**

**クリップボードを利用するDDLを設定するには**：

1. iOS開発者に、以下の対応を依頼します。
   1. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#clipboard-based-solution">開発者向けドキュメントの手順</Anchor>に従い、AppsFlyer SDKに必要なコードを組み込みます。
   2. クリップボードからURL内のディファードディープリンクデータを貼り付けるコードを実装します。このコードはAppsFlyer SDKには含まれていません。
2. リンクに`af_cp_lp=true`パラメータを追加します。   
   AppsFlyerのOneLinkカスタムリンクのUIでカスタムパラメータを追加するか、任意のリンクにこのパラメータを直接追記できます。

</Accordion>

</Accordion>

<div id="additional-information" />

## 補足情報

<div id="examples" />

<Accordion title="使用例">

**基本的な例**

Markは、人気の食料品配達サービス「Feed Me」のマーケターです。 Markは、ユーザーの電話番号を活用して、Feed Meの新しいiOS／Androidモバイルアプリのダウンロードを促そうとしています。 SMSキャンペーンを計画しています。しかし、どのユーザーがAndroidとiOSのどちらを使用しているかは分かりません。アプリがインストールされているかどうかも分かりません。

そこで、OneLinkのショートURLを含むSMSをユーザーに送信します。ユーザーがSMSを受信してリンクをクリックすると、次のように動作します。

* アプリが未インストールの場合は、適切なアプリストアまたはランディングページへ自動的に誘導され、簡単にアプリをインストールできます。
* アプリがインストール済みの場合は、アプリが開きます。

新規インストールとリエンゲージメントはSMSキャンペーンにアトリビューションされるため、MarkはAppsFlyerでキャンペーンの成果を確認できます。 

**ディープリンクの例**

前の例でマーケターのMarkが送信したSMSは、アプリのダウンロードと起動に一定の成果を上げました。しかし、リンクをクリックしてアプリを開いたユーザーのうち、注文まで至ったユーザーは多くありませんでした。

Markはコンバージョンを増やすため、購入ごとに桃、りんご、アボカドのいずれか1袋を無料で提供することにしました。そのために、既存ユーザー向けにスムーズなディープリンク体験を作成します。ユーザーに詳しいメールを送り、この3種類の健康的な果物のメリットを伝えます。 

メールで紹介する果物ごとに、OneLinkのディープリンクの値を設定したリンクを掲載し、モバイル開発者と協力して次の動作を設定します。

そこで、OneLinkのショートURLを含むSMSをユーザーに送信します。ユーザーがSMSを受信してリンクをクリックすると、次のように動作します。

* アプリがインストール済みの場合は、該当する果物のページが直接開きます。
* アプリが未インストールの場合は、デバイスに応じて適切なアプリストアまたはランディングページへ誘導されます。その後、アプリをダウンロードして開くと、果物のページが直接開きます。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特性と制限事項">

| 項目 | 説明 |
| --- | --- |
| <span id="onelink-characters"></span>OneLinkの文字数 | <ul><li>URL全体は2,000文字以内にしてください。</li><li>リンク名とメディアソースは150文字以内にしてください。</li><li>ショートURLのIDは50文字以内にしてください。</li><li>その他のリダイレクトパラメータの<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#special-characters">特性と制限事項</Anchor>もご確認ください。</li></ul> |
| <span id="maximum-links"></span>リンクの上限数 | AppsFlyerで作成できるOneLinkリンクは、1アカウントあたり最大120,000個です。 |
| <span id="posting-onelink-urls-in-web-pages"></span>WebページへのOneLink URLの掲載 | HTMLのhrefタグで`target="_blank"`を使用すると、Google PlayやApp Storeへリダイレクトされません。 OneLink URLを、**target="\_blank**"属性を持つHTMLの**a**タグ内に配置すると、AndroidとiOSのChromeで空白のページが開きます。これにより、OneLinkの機能に影響が生じます。 **a**タグにtarget属性を含めないでください。 |
| <span id="agencies"></span>代理店 | 代理店はOneLinkテンプレートやリンクを使用できません。これらはカスタムメディアソース／オウンドメディア専用です。 |
| <span id="ad-networks"></span>アドネットワーク | アドネットワークはOneLinkテンプレートやリンクを使用できません。これらはカスタムメディアソース／オウンドメディア専用です。 |
| <span id="social-media-preview-image"></span>ソーシャルメディアプレビューの画像 | <ul><li>ソーシャルメディアのプラットフォームが対応していない画像形式の場合、画像は表示されません。</li><li>WhatsAppでは、画像は300KB以下にしてください。</li></ul> |
| <span id="desktop"></span>デスクトップ | OneLinkのURLまたはテンプレートで、デスクトップユーザーを別のURLへリダイレクトするよう設定すると、そのWeb URLがリンクの`af_web_dp`パラメータに追加されます。リンクに`af_web_dp`が含まれている場合、AppsFlyerはデスクトップからのクリックを記録しません。 |
| <span id="af_enc_data"></span>af\_enc\_data | インプレッションURLには対応していません。 |
| <span id="android-social-apps-webview-deep-linking-redirection"></span>Androidのソーシャルアプリ内WebView | さまざまなAndroidのソーシャルアプリに最近加えられた変更により、アプリ内ブラウザ（WebView）で一部のディープリンクやストアへのリダイレクトが機能しなくなりました。<br /><br />**Android App Links**<br /><br />現在、Facebookのアプリ内ブラウザからクリックした場合、Android App Linksはサポートされていません。この導線でURIスキームを使用するリンクは、従来どおり機能します。<br /><br />**ストアへのリダイレクト**<br /><br />これらの変更に対応してストアへのリダイレクトを再び機能させるため、以下のAndroidソーシャルアプリでは、ユーザーによる追加操作が必要になりました。<ul><li>v420より後のバージョンのFacebook</li><li>Instagram</li><li>Facebook Messenger</li><li>Snapchat</li></ul>これらのアプリでは、Google Playストアや他のサードパーティストアへリダイレクトするために、ランディングページ上の追加ボタンをクリックする必要があります。<br /><br />このボタンは自動的に追加されるため、設定作業は不要です。<br /><br />**注意：**<ul><li>Facebook v420以前では、従来どおり動作し、ユーザーによる追加操作は不要です。</li><li>Facebookの投稿内のFacebook App Links（URIスキームを使用）は、従来どおり動作し、ユーザーによる追加操作は不要です。</li><li>Instagramのチャット内のFacebook App Linksは、従来どおり動作し、ユーザーによる追加操作は不要です。</li><li>ディープリンクの導線では、アプリが未インストールの場合にエラーメッセージのポップアップが表示されるという既知の制限があります。このメッセージは導線に影響せず、ユーザーは想定どおりストアへリダイレクトされます。</li></ul> |
| <span id="onelink-link-previews-sometimes-fail-to-display-correctly-on-facebook-and-linkedin"></span>OneLinkリンクのプレビュー | **説明**  <br />FacebookやLinkedInで、OneLinkリンクのプレビューが正しく表示されない場合があります。この問題は、リダイレクト先のWebサイトが、プレビューリクエスト内のユーザーエージェント文字列`AppsFlyerBot-Previewer/1.0`をロボット（クローラー）からのアクセスとして認識しない場合に発生します。この場合、Webサイトはプレビューに必要なOGタグ付きのコンテンツを返しません。<br /><br />**解決方法**  <br /><Anchor target="_blank" href="https://moz.com/learn/seo/robotstxt">Webサイトのrobot.txtファイルを更新</Anchor>することで、ユーザーエージェントのヘッダー文字列が`AppsFlyerBot-Previewer/1.0`であるアクセスを、ロボットからのものとしてランディングページで扱うよう設定できます。<br /><br />プレビュー用ロボットは、各リンクのリダイレクトパラメータがリダイレクト許可リストに適合するかも確認します。パラメータが許可リストにないドメインを指定している場合、ロボットはそのURLを無視するため、プレビューが空白のままになるか、一般的な内容になります。プレビューに表示したいすべてのランディングページのドメインを、リダイレクト許可リストに追加してください。 |
| <span id="deep-linking-is-not-supported-on-android-naver-blog-app"></span>Android版Naver Blogアプリ | Android版Naver Blogアプリは、ディープリンクに対応していません。ユーザーは、リンクの設定に従ってGoogle PlayまたはWebのリダイレクト先へ誘導されます。 |
| <span id="chrome-browser-on-ios"></span>iOSのChromeブラウザ | iOS版Chromeの変更により、ChromeでURIスキームのリンク（af\_dpパラメータ）を含むOneLinkリンクをクリックすると、アプリを開くかApp Storeへリダイレクトするかを確認するポップアップが表示されます。 |
| <span id="telegram-webview"></span>TelegramのWebView | TelegramのWebView（Telegramブラウザ）でのユーザーエンゲージメントでは、確率論的モデリングによるアトリビューションは機能しません。これは、WebViewからのエンゲージメントリクエストに、デバイスモデルとOSバージョンが含まれないためです。 |
| <span id="xiaomi-browser"></span>Xiaomi Browser | Xiaomi Browserでのユーザーエンゲージメントでは、確率論的モデリングによるアトリビューションは機能しません。 |

</Accordion>

<div data-zendesk-anchors="onelink-links-and-experiences=onelink%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%A8%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E4%BD%93%E9%A8%93 h_01H8Y6DDT4M8XGAEJJVTHKHPKV=onelink%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%A8%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E4%BD%93%E9%A8%93 create-a-onelink-link=onelink%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E4%BD%9C%E6%88%90 h_01H8Y6DDT41C6JYKXET0NDRB1G=onelink%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E4%BD%9C%E6%88%90 h_01JRX3VWTVE77QVNG37BKPKHWW=%E6%B3%A8%E6%84%8F h_01H8Y6DDT4C543RS2BXAGS487M=experiences h_01H8Y6DDT4WZ5FKZYBX2H08MFD=general-settings h_01KY2AWC72SCQKY3XEQGW2J269=%E9%87%8D%E8%A6%81 enable-retargeting-for-the-app=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H8Y6DDT4R7785X5DRES66BKJ=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H8Y6DDT4JT9H0R13ZNGHJ79S=social-media-preview-og-tags h_01KY2AWC72V1JR1BBGKHPDQ7AF=%E6%B3%A8%E6%84%8F-1 h_01H8Y6DDT4PHY2F5E3GK582P51=social-app-landing-page h_01H8Y6DDT463F5569B28DD17SV=%E9%87%8D%E8%A6%81-1 h_01H8Y6DDT4MMD1AW6D1PNGNX5X=%E6%B3%A8%E6%84%8F-2 to-use-the-social-app-landing-page=%E3%82%BD%E3%83%BC%E3%82%B7%E3%83%A3%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E5%90%91%E3%81%91%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF h_01H8Y6DDT4JB4RT438MAGNNX2S=%E3%82%BD%E3%83%BC%E3%82%B7%E3%83%A3%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E5%90%91%E3%81%91%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF to-set-up-the-social-apps-landing-page=%E3%82%BD%E3%83%BC%E3%82%B7%E3%83%A3%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E5%90%91%E3%81%91%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF h_01H8Y6DDT4G34S3RV3ZH64XT19=%E3%82%BD%E3%83%BC%E3%82%B7%E3%83%A3%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E5%90%91%E3%81%91%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF h_01H8Y6DDT5XNJVYW2Y8F6JWPK2=deep-linking-and-deferred-deep-linking h_01KY2AWC73CNKHAF4HV26F132E=%E6%B3%A8%E6%84%8F-3 h_01H8Y6DDT5JR3B3DMR87JCBZ69=%E3%83%92%E3%83%B3%E3%83%88 h_01H8Y6DDT5KSBE00WWDGQ5R1AQ=%E6%B3%A8%E6%84%8F-4 h_01H8Y6DDT58FC3HMSRZBMGZZRJ=redirection h_01H8Y6DDT5AAQ3BZD8QB9H19QB=additional-parameters h_01H8Y6DDT5B6M7CETQRD9NKX8R=testing new-users-without-your-app-installed=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%97%E3%81%A6%E3%81%84%E3%81%AA%E3%81%84%E6%96%B0%E8%A6%8F%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC h_01H8Y6DDT50DH5TGVVPJPJC4MG=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%97%E3%81%A6%E3%81%84%E3%81%AA%E3%81%84%E6%96%B0%E8%A6%8F%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC existing-users-with-your-app-installed=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E6%B8%88%E3%81%BF%E3%81%AE%E6%97%A2%E5%AD%98%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC h_01H8Y6DDT5KDEWS40XPYGYC8HK=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E6%B8%88%E3%81%BF%E3%81%AE%E6%97%A2%E5%AD%98%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC additional-procedures=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%89%8B%E9%A0%86 h_01H8Y6DDT5YR8JA5YMZFPMCC2X=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%89%8B%E9%A0%86 h_01H8Y6DDT58EFS8S46D1AVP3T1=create-a-custom-impression-url h_01H8Y6DDT5S4NEJMNJR4K3QMNH=deep-linking-post-event h_01H8Y6DDT58Y6CS27M2W3MHYAD=deferred-deep-linking-with-ios-private-relay h_01H8Y6DDT5A7J07KNNRWCXCBH2=app-clipbased-solution flow=%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C h_01H8Y6DDT5VDKAR89B8N6D7YMB=%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C h_01H8Y6DDT62H71A8DPG00A3ZTN=clipboardbased-solution flow::21baf6ac=%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C-1 h_01H8Y6DDT638T7C9HQHZ1CJ726=%E5%87%A6%E7%90%86%E3%81%AE%E6%B5%81%E3%82%8C-1 requirements=%E8%A6%81%E4%BB%B6 h_01H8Y6DDT6JGP33AWFQV6Z8FF0=%E8%A6%81%E4%BB%B6 setup=%E8%A8%AD%E5%AE%9A h_01H8Y6DDT61ENGJFZ1XS28GS1T=%E8%A8%AD%E5%AE%9A additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01H8Y6DDT679SGBTSM669F9FHV=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01H8Y6DDT6TX4WTP2HYRF11DZ3=examples h_01H8Y6DDT6TQYRS81BMHARB62S=traits-and-limitations" />
