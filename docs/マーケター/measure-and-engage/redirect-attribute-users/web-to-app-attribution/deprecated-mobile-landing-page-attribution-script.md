---
title: ［非推奨］モバイルランディングページのアトリビューションスクリプト
deprecated: true
metadata:
  keywords:
    - Landing Page
    - Facebook
    - Adwords
    - Advertisers
    - Agencies
    - GCLID
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Agencies
    - Smart Banners and Scripts
  created_at: '2020-12-16T17:28:55Z'
  edited_at: '2026-10-28T09:19:53Z'
  id: 360016643258
  locale: ja
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ja/articles/360016643258
---
> **概要：** このスクリプトは2020年12月17日をもって非推奨となり、<Anchor target="_blank" href="/marketers/ja/docs/onelink-smart-script-overview">OneLink Smart Script</Anchor>に置き換えられました。このバージョンは引き続き動作しますが、今後の更新や変更は行われません。このスクリプトは、モバイルWebサイトのボタンに設定するURLを生成し、訪問者をアプリのダウンロード先へ誘導します。生成されるURLは、インストールのアトリビューションとディープリンクにも対応しています。

![5648_Sunset_and_deprecation-01.png](https://files.readme.io/f2a154145e26577b698d00c4c3719be3eea7298576e6883bd47e6fb42897c71a-360015062398.png)

**<Anchor target="_blank" href="/marketers/ja/docs/onelink-smart-script-overview">OneLink Smart Scriptへの移行</Anchor>**

ランディングページは、デジタルマーケティングで広く活用されています。初回訪問でコンバージョンに至らなかった場合でも、見込み顧客の情報を取得し、リマーケティングに活用できます。

ただし、モバイルユーザーの獲得にランディングページを活用する場合には、メリットとデメリットがあります。

<div id="the-upsides" />

#### メリット：

* 最終的にインストールに至った見込み顧客は、アプリへの関心がより高いと考えられます。
* 金融サービスなど、内容が複雑でコンバージョンまでに詳しい説明が必要なサービスでは、ランディングページで十分に説明できます。

<div id="the-downsides" />

#### デメリット：

* コンバージョンまでの経路が長くなるため、最終的にコンバージョンに至る見込み顧客の数が減ります。
* アトリビューションの技術的な難易度が上がります。

<div id="the-challenges-of-mobile-attribution-on-landing-pages" />

## ランディングページにおけるモバイルアトリビューションの課題

* ランディングページを経由する経路で正確なアトリビューションデータを取得するには、**メディアソースごとに異なる方法で対応する必要があります**。
* ランディングページに独自のアトリビューションリンクがある場合、**ラストクリックアトリビューションモデルによって、本来の流入元に正しく成果が紐づかなくなる可能性があります**。
* ランディングページに独自のアトリビューションリンクがない場合、**Webサイトへの直接訪問はオーガニックとして記録されます**。
* ランディングページに、デスクトップからの訪問者がモバイルアプリのユーザーになったことを記録する仕組みがなければ、**デスクトップからの訪問者はオーガニックとして記録されます**。

<div id="the-solution" />

## 解決方法

これらの課題を解決するには、ランディングページにJavaScriptによる処理を実装する必要があります。実装に利用できるサンプルスクリプトを用意しています。要件に合わせてスクリプトを調整してください。

場合によっては、キャンペーン側でも調整が必要です。

以下では、各メディアソースで想定されるケースと、必要な対応を説明します。

<div id="landing-page-scenarios" />

## ランディングページの利用ケース

ランディングページへ見込み顧客を誘導する**すべてのメディアソースについて**、以下の実装手順に従ってください。

<div id="facebook-ads-crossplatform-attribution" />

<Accordion title="Meta ads｜クロスプラットフォームのアトリビューション">

<div id="description" />

#### 説明：

Meta adsはSRNであり、外部のアトリビューションリンクを使用しません。

アプリの初回起動時に、AppsFlyerはMeta adsに対して、そのユーザーが過去28日以内にFacebookアプリで広告主の広告に接触したかどうかを照会します。接触していた場合、Meta adsが自らの成果として申告します。

Meta adsはクロスプラットフォームのアトリビューションにも対応しているため、ユーザーがどのプラットフォームで、どの種類のキャンペーンに接触した場合でも、モバイル向けかどうかにかかわらず、自らの成果として申告できます。

<div id="conclusion" />

#### 対応の要点：

デバイスIDを取得できる見込み顧客がFacebookアプリからランディングページに移動した場合、その成果はMeta adsに正しく紐づきます。これは、ランディングページで新たなクリックが記録されるかどうかにかかわりません。  
ただし、2021年のiOS 14ユーザーで想定されているように、ユーザーがデバイスIDを共有しないことを選択すると、Meta adsのクロスプラットフォームのアトリビューションが機能しなくなる可能性があります。

**デバイスIDの共有が任意になった場合は、Meta adsでも[他のSRN向けの方法](/docs/deprecated-mobile-landing-page-attribution-script#other-srns-add-parameter)を使用してください。**

* デバイスIDを共有する新規ユーザーは、Meta adsに正しく紐づきます。
* デバイスIDを共有しない新規ユーザーは、「Facebook\_LP」に紐づきます。

<div id="instructions" />

#### 手順：

1. Meta adsのアカウントで、**モバイルアトリビューションを有効にした［トラフィック］または［コンバージョン］キャンペーン**を作成し、見込み顧客をランディングページへ誘導します。
2. ランディングページのAndroid用ダウンロードボタンには、Google Playへの直接リンクを設定します。
3. ランディングページのiOS用ダウンロードボタンには、iTunesへの直接リンク、または**デバイスIDを含まない**アトリビューションリンクを設定します。

<div id="what-the-script-does" />

#### スクリプトの動作

ランディングページのスクリプトは、リンクを変更しません。スクリプトは、ユーザーがFacebookアプリから訪問したかどうかを検出します。 Facebookアプリからの訪問を検出した場合は、何も処理しません。ランディングページに設定されているアプリストアへの直接リンクを、そのまま使用します。これにより、CTRに影響する可能性のある追加のクリックが記録されるのを防ぎます。

Facebookアプリから訪問したユーザーに対する処理の詳細は、スクリプト内の<strong><em>isFacebook()</em></strong>メソッドを確認してください。

</Accordion>

<div id="google-ads-gclid-offline-conversion-upload" />

<Accordion title="Google広告｜GCLIDとオフラインコンバージョンのアップロード">

<div id="description-1" />

#### 説明：

Google広告キャンペーンの通常のインストールアトリビューションでは、広告をクリックした見込み顧客をアプリのストアページURLへリダイレクトする必要があります。

そのため、Google広告からランディングページへ誘導する場合は、モバイルアプリのインストールと、モバイル向けではないGoogle広告キャンペーンの元のクリックを紐づける仕組みが必要です。

<div id="conclusion-1" />

#### 対応の要点：

Google広告への対応は、2つの部分で構成されます。

前半では、Googleからランディングページへ移動し、そこからアプリをインストールしたモバイルユーザーの成果を**AppsFlyer上で紐づけます**。 GoogleからのクリックURLにタグを付け、ランディングページで識別し、そのURLのデータを使ってOneLinkを動的に生成します。

後半では、Googleのオフラインコンバージョンのアップロード機能を使って、これらのモバイルアプリのインストールを**Google広告に通知します**。

<div id="note" />

> 📘 **注意**
>
> GCLIDを使用するこの方法は、Googleが公式にサポートまたは推奨しているものではありません。
> GoogleがGCLIDパラメータを廃止した場合は、その変更に対応するようスクリプトを更新します。
> 記事や添付スクリプトの更新通知を受け取れるよう、記事上部の<strong><em>［フォロー］</em></strong>ボタンをクリックして、この記事をフォローすることをおすすめします。

<div id="instructions-1" />

#### 手順：

パート1｜AppsFlyer上でGoogle広告に成果を紐づける

Googleの管理画面で**自動タグ設定を有効にします**（<Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">設定方法</Anchor>）。

自動タグ設定を有効にすると、**ランディングページのURLにGCLIDパラメータが含まれます**。

URLの例：`http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}`

ランディングページの読み込み時に、次の処理を行います。

1. JavaScriptの***generateUrl***関数を実行します。
2. この関数（後述）は***GCLID***パラメータを探し、その値をaf\_sub1パラメータに含めた長い形式のOneLink URLを生成します（af\_sub1～af\_sub5のいずれかの<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">サブスクライバーパラメータ</Anchor>を使用できます）。
3. ランディングページのダウンロードボタンには、生成されたOneLink URLを使用します。  
   OneLink URLの例：`https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}`
4. 新規モバイルユーザーは、メディアソース**google\_lp**と、任意で指定するCAMPAIGN\_NAMEキャンペーンに紐づきます。
5. メディアソースにポストバックは送信されません。

この時点では、インストールはAppsFlyer上でメディアソース***google\_lp***にGCLIDとともに記録されますが、Google広告には記録されません。

パート2｜インストールをオフラインコンバージョンとしてGoogleにアップロードする

**この手順は、Google広告にもコンバージョンを記録する場合にのみ必要です。**

google\_lpに紐づいたユーザーについては、AppsFlyerのローデータの**af\_sub1**列にGCLIDの値が表示されます。 Google広告にオフラインコンバージョンをアップロードするには、GCLIDが必要です。手順の詳細は<Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">こちら</Anchor>を参照してください。

コンバージョンは、手動またはAdwords APIでアップロードできます（APIの詳細は<Anchor target="_blank" href="https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions">こちら</Anchor>）。

AppsFlyerのアカウントから、この情報を含むCSVをエクスポートできます。また、Push APIでインストールごとのデータをリアルタイムに取得することも可能です。

<div id="tip" />

> 👍 **ヒント**
>
> GCLIDと同様の方法で、ユーザーが検索したキーワードもAppsFlyerのローデータで確認できます。
>
> 1. キーワードを記録するには、Google広告からランディングページへ誘導する最終ページURLに、keywordの<Anchor target="_blank" href="https://support.google.com/google-ads/answer/2375447">ValueTrackパラメータ</Anchor>を含める必要があります。
>    URLの例：`http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}&keyword={USER_KEYWORD}`
> 2. JavaScript関数（後述）は、***keyword***パラメータを探します。
> 3. その値を、生成するOneLink URLのaf\_keywordsパラメータに追加します。
>    OneLink URLの例：`https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}&af_keywords={USER_PARSED_KEYWORD}`
>
> 以下のJavaScript関数には、keywordパラメータを解析するコードも含まれています。

<div id="what-the-script-does-1" />

#### スクリプトの動作

Google広告のURLには、gclidパラメータが含まれます。スクリプトは、ランディングページのURLからこのパラメータを探します。見つかった場合は、Google広告からの訪問であることを反映したOneLinkを生成します。次に、生成したOneLinkをランディングページのダウンロードボタンのリンク先に設定します。

Google広告からの訪問を検出し、OneLinkを生成する処理の詳細は、スクリプト内の**gclidValue**を確認してください。

</Accordion>

<div id="other-srns-add-parameter" />

<Accordion title="他のSRN｜パラメータの追加">

<div id="description-2" />

#### 説明：

SnapchatやTwitterなどの他の<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#srn媒体">SRN</Anchor>は、Meta adsのようなクロスプラットフォームのアトリビューションに対応していないため、モバイルユーザーの成果を紐づけるには追加の対応が必要です。

他のSRNのキャンペーンでは、ユーザーをランディングページへ誘導し、その後モバイルアプリのユーザーになったかどうかにかかわらず、見込み顧客のクリックに基づいて課金されます。

<div id="conclusion-2" />

#### 対応の要点：

Meta adsとGoogle広告以外のSRNでキャンペーンのランディングページURLを設定する際は、元のSRNを示すパートナーIDパラメータをURLに追加します。  
ランディングページでJavaScript（後述）を実行し、そのパラメータを解析して、パートナーIDの値を含むOneLink URLを生成します。モバイルユーザーがそのOneLinkをクリックしてインストールすると、指定したメディアソースに成果が紐づきます。

<div id="instructions-2" />

#### 手順：

SRNのアカウントで、次の設定を行います。

1. モバイル向けではないキャンペーンを作成します。
2. ランディングページURLを設定する際は、URL（AppsFlyerのアトリビューションリンクではありません）に「パートナーID＋ランディングページ」を示すパラメータを追加します。形式は「***&af\_pid=srn\_lp***」です。以下の例を参照してください。

ランディングページの読み込み時に、次の処理を行います。

1. JavaScriptの***generateUrl***関数を実行します。
2. この関数は***af\_pid***パラメータを探し、その値を***pid***パラメータに含めたOneLink URLを生成します。
3. ランディングページのダウンロードボタンには、生成されたOneLink URLを使用します。
4. 新規モバイルユーザーは、独自に設定した「パートナーID＋ランディングページ」のメディアソースに紐づきます。
5. メディアソースにポストバックは送信されません。

twitter\_intなど、実際のSRN名を指定すると、そのSRNにポストバックが送信される可能性があります。その結果、二重課金が発生するおそれがあります。代わりに使用する名前については、以下の注意を参照してください。

スクリプトには、実際のSRN名の使用を防ぐロジックが含まれています。スクリプト内の`var SRNs`を確認してください。 SRN名のリストと、`pidValue`がそのいずれかに一致するかどうかを確認する条件があります。スクリプトのテストが完了したら、このロジックを削除してください。

<div id="note-1" />

> 📘 **注意**
>
> ユーザーをランディングページへ誘導する場合は、ランディングページのURLに以下のパラメータを含めることをおすすめします。
>
> * Twitter：「***&af\_pid=twitter\_lp***」を使用します。
> * Snapchat：「***&af\_pid=snapchat\_lp***」を使用します。
> * Doubleclick：「***&af\_pid=doubleclick\_lp***」を使用します。
> * Meta adsの投稿（無料）：「***&af\_pid=fbpost\_lp***」を使用します。
> * Oath（旧Yahoo Gemini）：「***&af\_pid=oath\_lp***」を使用します。

<div id="what-the-script-does-2" />

#### スクリプトの動作

スクリプトは、ランディングページURLのaf\_pidパラメータを検出すると、SRNまたはその他の独自のネットワークからの訪問であると判断します。その情報に基づいてOneLinkを生成し、ランディングページのダウンロードボタンのリンク先に設定します。

処理の詳細は、スクリプト内の**pidValue**を確認してください。

</Accordion>

<div id="attribution-links-redirect-with-af_r" />

<Accordion title="アトリビューションリンク｜af_rによるリダイレクト">

<div id="description-3" />

#### 説明：

SRN以外のメディアソースでは、アトリビューションリンクを使用します。数千社の連携済みパートナーに加え、成果を計測したいオウンドメディアにも使用できます。

AppsFlyerのアトリビューションリンクを使用すれば、ランディングページ経由の成果も簡単に紐づけられます。対応方法はMeta adsの場合と似ています。

<div id="conclusion-3" />

#### 対応の要点：

アトリビューションリンクで見込み顧客をランディングページにリダイレクトすることで、その後モバイルアプリがインストールされた場合の成果も正しく紐づけられます。

あとは、新たなラストクリックによって、本来の流入元への紐づけを妨げないようにします。

<div id="instructions-3" />

#### 手順：

1. メディアソース用の<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#onelinkリンクの作成">アトリビューションリンクを作成します</Anchor>。
2. アトリビューションリンクに、ランディングページへ誘導するための<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection">ランディングページパラメータ</Anchor>を追加します。
3. アトリビューションリンク内の**各リダイレクトパラメータ**（af\_r、af\_ios\_url、af\_android\_url）に指定したランディングページURLに、`&af_redirect=true`を追加します。  
   例：`https://yourapp.onelink.me/abcd?pid=email&c={CAMPAIGN_NAME}&af_r=http://www.yoursite.com/yourlandingpage?af_redirect=true`
4. **任意**：確率論的モデリングの代わりにIDマッチングで成果を紐づけるには、アトリビューションリンクにデバイスID（GAID／IDFA）を追加します。
5. ランディングページのAndroid用ダウンロードボタンには、Google Playへの直接リンクを設定します。
6. ランディングページのiOS用ダウンロードボタンには、iTunesへの直接リンクを設定します。  

   <div id="note-2" />

   > 📘 **注意**
   >
   > スクリプトとHTMLのサンプルページでは、AndroidとiOSの両方に対応するダウンロードボタンを1つだけ設置することもできます。実装方法は、スクリプト内のコメントを確認してください。


<div id="what-the-script-does-3" />

#### スクリプトの動作

スクリプトは、ランディングページURLから**af\_redirect**パラメータを探します。見つかった場合は、ランディングページのダウンロードボタンを変更しません。 af\_redirectパラメータは、ユーザーがクリック後にランディングページに到達したことを示すためです。そのため、追加のアトリビューションリンクは必要ありません。

アトリビューションリンクをクリックしてランディングページに到達したユーザーに対する処理の詳細は、スクリプト内の**isAFLink()** メソッドを確認してください。

</Accordion>

<div id="links-with-utm-parameters-dynamic-onelink" />

<Accordion title="UTMパラメータ付きのリンク｜OneLinkの動的生成">

<div id="description-4" />

#### 説明

流入元によっては、UTMパラメータ付きのリンクでユーザーをランディングページへ誘導している場合があります。

<div id="conclusion-4" />

#### 対応の要点：

元のURLがAppsFlyerのアトリビューションリンクではない場合、スクリプトはリンク内の***utm\_source***と***utm\_campaign***パラメータを探します。見つかった場合は、それぞれの値をメディアソース名（pid）とキャンペーン名（c）に設定したOneLink URLを生成します。

AppsFlyerのアトリビューションリンクにUTMパラメータも含まれている場合は、UTMパラメータではなくAppsFlyerのパラメータが使用されます。

<div id="instructions-4" />

#### 手順：

メディアソース側で、次の設定を行います。

1. リンクに***utm\_source***が含まれていることを確認します。
2. ***utm\_campaign***パラメータは任意ですが、設定することを強くおすすめします。

ランディングページの読み込み時に、次の処理を行います。

1. JavaScriptの***generateUrl***関数を実行します。
2. この関数は***utm\_source***と***utm\_campaign***パラメータを探し、その値を含むOneLink URLを生成します。
3. ランディングページのダウンロードボタンには、生成されたOneLink URLを使用します。
4. 新規モバイルユーザーは、***utm\_source***の値をメディアソースとして紐づけられます。
5. メディアソースにポストバックは送信されません。

<div id="what-the-script-does-4" />

#### スクリプトの動作

スクリプトは、ランディングページURLからUTMパラメータを探します。見つかった場合は、OneLinkのパラメータに変換します。これにより、最終的なアトリビューションまでキャンペーン情報を引き継げます。

</Accordion>

<div id="mobile-organic-visitors-onelink-with-pidwebsite" />

<Accordion title="モバイルのオーガニック訪問者｜pid=websiteを指定したOneLink">

<div id="description-5" />

#### 説明

モバイルのオーガニック訪問者とは、流入元が不明で、モバイルWebサイトへ直接訪問した見込み顧客を指します。専用のランディングページを訪問することはあまりありませんが、広告主のWebサイトを経由したモバイルアプリのインストールの大半を占める場合があります。

<div id="conclusion-5" />

#### 対応の要点：

Webサイトにモバイルのオーガニック流入が多い場合は、自社サイトからの流入についてもアトリビューションデータを記録することを強くおすすめします。

<div id="instructions-5" />

#### 手順：

モバイルのオーガニック訪問者の成果を紐づけるには、Webサイトに<strong><em>［ダウンロード］</em></strong>または<strong><em>［インストール］</em></strong>ボタンを設置し、リンク先にOneLinkのアトリビューションリンクを設定します。 OneLinkはデバイスの種類を判別し、それに応じたアプリストアへ見込み顧客をリダイレクトします。

OneLink URLの設定・作成方法は、<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">こちら</Anchor>を参照してください。

<div id="tip-1" />

> 👍 **ヒント**
>
> これらの訪問者すべてを自社Webサイトに紐づけるには、アトリビューションリンクに「&pid=website」を追加します。
> Webサイト内でアトリビューションリンクを設定したダウンロード／インストールボタンがある各ページについて、リンクに「&c=`{PAGE NAME}`」を追加します。これにより、Webサイト内でコンバージョン率が最も高いページと最も低いページを特定できます。

<div id="what-the-script-does-5" />

#### スクリプトの動作

他のどの条件にも該当しない場合、スクリプトはそのユーザーを、キャンペーン経由ではないオーガニックユーザーと判断します。その情報を反映したOneLinkを生成し、ランディングページのダウンロードボタンのリンク先に設定します。

</Accordion>

<div id="desktop-visitors-telephoneemail-form" />

<Accordion title="デスクトップからの訪問者｜電話番号・メールアドレスの入力フォーム">

<div id="description-6" />

#### 説明

ここまでの方法はすべて、ユーザーがモバイルデバイスでキャンペーンに接触し、ランディングページを訪問することを前提としています。

では、デスクトップからの訪問者にはどう対応すればよいでしょうか。

デスクトップユーザーは、ランディングページやWebサイトを訪問した後、その経路とは別にモバイルデバイスでアプリストアを開き、アプリをインストールする場合があります。モバイルデバイスでの事前の接触がないため、これらのユーザーの成果は紐づけられず、「オーガニック」として扱われます。

<div id="conclusion-6" />

#### 対応の要点：

この課題には、デスクトップユーザーに限って、**ダウンロード用リンクをSMSで受け取るためのフォームをランディングページに設置する**方法が有効です。フォームへの入力後、OneLink URLを含むSMSまたはメールをモバイルデバイスに送信します。

<div id="instructions-6" />

#### 手順：

1. 訪問者がデスクトップユーザーであることを判別します。
2. ユーザーが電話番号を入力したら、アプリへのリンクとしてOneLinkの短縮URLをSMSで送信します。メールアドレスを入力してもらい、アプリのダウンロード案内をメールで送信することもできます。
3. 送信時点ではユーザーのモバイルデバイスのプラットフォームが不明なため、OneLinkの使用が重要です。 OneLinkのデバイス判別機能とリダイレクト機能が、適切な誘導先へ振り分けます。
4. この流入元を識別できるよう、OneLink URLに「&pid=desktop\_website」を追加します。
5. 「&c=`{PAGE NAME}`」を追加すると、デスクトップユーザーのコンバージョン率が最も高いページと最も低いページを特定できます。

<div id="what-the-script-does-6" />

#### スクリプトの動作

スクリプトは、ユーザーのデバイスまたはプラットフォームを検出します。デスクトップの場合はWebフォームのURLを返し、ダウンロードボタンのリンク先に設定します。ユーザーがダウンロードボタンをクリックするとWebフォームに移動し、情報を入力することで、アプリのダウンロードリンクを含むSMSまたはメールを受け取れます。

Webフォームは自社で作成し、そのURLをスクリプトに設定してください。詳細は、スクリプト内の**isMobileDevice()** を確認してください。

</Accordion>

<div id="landing-page-javascript" />

## ランディングページ用JavaScript

以下は、ランディングページを経由するケースでメディアソースとキャンペーンに成果を紐づける、一連の処理を実装したJavaScriptのコードです。**広告セットや広告IDなどの追加データを取得する場合は、スクリプトを適宜調整してください**。

添付のランディングページのサンプルもダウンロードして利用できます。

コードの後に、ランディングページの要件に合わせて調整する手順を記載しています。

<div id="the-script" />

<Accordion title="スクリプト">

スクリプトの実装前に、以下を確認してください。

* このスクリプトは、あくまでサンプルとして提供するものです。ランディングページ経由の一般的なアトリビューションの流れに対応しています。要件に合わせてスクリプトを調整してください。
* スクリプトは、ランディングページURLからメディアソース、キャンペーン、キーワードなどの特定のパラメータを探します。サイトIDや広告セットなどのパラメータを追加する場合は、スクリプトを適宜変更する必要があります。

```javascript
//Returns the value of a parameter existing in the page's URL or ' ' if not exists.
function getParameterFromURL(name, url) {
  if (!url) url = window.location.href;
  name = name.replace(/[\[\]]/g, '\\$&');
  var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
    results = regex.exec(url);
  if (!results) return null;
  if (!results[2]) return '';
  return decodeURIComponent(results[2].replace(/\+/g, ' '));
}

function isMobileDevice() {
  return (typeof window.orientation !== "undefined") || (navigator.userAgent.indexOf('IEMobile') !== -1);
}

function getMobileOperatingSystem() {
  var userAgent = navigator.userAgent || navigator.vendor || window.opera;
  if (userAgent) {
    if (/android/i.test(userAgent)) {
      return "Android";
    }

    // iOS detection from: http://stackoverflow.com/a/9039885/177710
    if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
      return "iOS";
    }
  }
  return "unknown";
}

function isAFLink() {
  return getParameterFromURL('af_redirect');
}

// Note - when device ID sharing becomes optional stop calling this method (or always return false)
function isFacebook() {
  if (document.referrer && document.referrer != "") {
    return document.referrer.toLowerCase().includes('facebook');
  } else {
    return false;
  }
}

// generateUrl returns the URL to use behind the iOS and Android "Download" buttons on a landing page, based on the source of the page visitor.
// By default these buttons should direct to the apps' pages on iTunes and Google Play.
// If these links should be kept with no change, generateUrl returns ' '.
// Otherwise, generateUrl returns the URL to be used under BOTH buttons (a single app download button could also be used in this case).
// Parameters: isDebug - if true, alerts are issued for each of the cases, otherwise not.  	 
function generateUrl(isDebug) {
  var oneLinkURL = 'https://yourapp.onelink.me/abcd';   // **** Replace with your own basic OneLink URL ****
  var webFormURL = 'https://yoursite.com/webform.html'; // **** Replace with your own web form URL for getting the user's email or SMS ****
  var finalURL = "";
  var partnerIDParam = '?pid=';

  var campaignValue;
  if (getParameterFromURL('c')) {
    campaignValue = getParameterFromURL('c');
  } else if (getParameterFromURL('utm_campaign')) {
    campaignValue = getParameterFromURL('utm_campaign');
  } else if (document.getElementsByTagName('title')[0]) {
    campaignValue = document.getElementsByTagName('title')[0].innerText;
  } else {
    campaignValue = 'unknown';
  }
  var campaignParam = '&c=';
  var gclidParam = '&af_sub1=';
  var gclidValue = getParameterFromURL('gclid');
  var kwParam = '&af_keywords=';
  var pidValue;
  var kwValue = getParameterFromURL('keyword');

  if (getParameterFromURL('af_pid')) {
    pidValue = getParameterFromURL('af_pid');
  } else if (getParameterFromURL('utm_source')) {
    pidValue = getParameterFromURL('utm_source');
  }

  // Prevent the use of real SRN names. Remove this part after you are done testing the script.
    var SRNs = [
    'twitter_int',
    'facebook_int',
    'snapchat_int',
    'doubleclick_int',
    'yahoogemini_int',
    'yahoojapan_int',
  ];

  if (SRNs.includes(pidValue)) {
  	alert("DO NOT USE NAMES OF SRNS IN af_pid or utm_source - use the names listed in Other SRNs: Add Parameter section in the landing page article\nhttps://support.appsflyer.com/hc/en-us/articles/360000677217#other-srns-add-parameter");
    return;
  }

  // Desktop user
  if (!isMobileDevice()) {
    return webFormURL;
  }

  // User was redirected using af_r parameter on an AppsFlyer attribution link
  if (isAFLink()) {
    if (isDebug) {
      alert("This user comes from AppsFlyer by redirection and is ready to be attributed. \nKeep direct app store links.");
    }
    return; // in this case, the original store links in the install buttons stay the same

    /*
    If you want one install button in the landing page that serves both iOS and Android, uncomment the code below
    The code identifies the operating system and returns the relevant direct link to Google Play or iTunes

    if (getMobileOperatingSystem() === 'Android') {
      return 'direct link to Google Play';
    } 

    if (getMobileOperatingSystem() === 'iOS') {
      return 'direct link to iTunes';
    }
    */
  }

  // Google Ads
  if (gclidValue) {
    partnerIDParam += 'google_lp';
    campaignParam += campaignValue;
    gclidParam += gclidValue
    if (!kwValue) {
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam;
      if (isDebug) {
        alert("This user comes from Google AdWords\n " + finalURL);
      }
      return finalURL;

    } else { // Google Ads with KW
      kwParam += kwValue;
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam + kwParam;
      if (isDebug) {
        alert("This user comes from Google AdWords - there is a keyword associated with the ad\n " + finalURL);
      }
      return finalURL;
    }

  // Other SRNs and custom networks  
  } else if (pidValue) {
    campaignParam += campaignValue;
    partnerIDParam += pidValue;
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("This user comes the SRN or custom network " + pidValue + "\n" + finalURL);
    }
    return finalURL;
  } else if (isFacebook()) {
    if (isDebug) {
      alert("This user comes from a paid Facebook ad - don't do anything. \nKeep direct app store links.");
    }
    return ' ';

  } else { // organic mobile user
    campaignParam += campaignValue;
    partnerIDParam += 'website'; //**** Replace value if you wish organic users to be attributed to another media source than 'website' ****
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("This user comes from an unknown mobile source.\n The user would be attributed to media source 'website' and to the campaign " + campaignParam + "\n" + finalURL);
    }
    return finalURL;
  }
}
```

</Accordion>

<div id="html-sample-for-landing-page" />

<Accordion title="ランディングページのHTMLサンプル">

```html Markup
<html>
<head>
  <title>Landing Page</title>
</head>
<body>
  <h1>Landing Page</h1>
  <!-- By default, the install buttons should have direct links to the stores -->
  <div>
    <a id="andrd_link" href="https://play.google.com/store/apps/details?id=com.appsflyer.sampleapp"><img src="/images/andrd.png"alt=""></a>
  </div>
  <div>
    <a id="ios_link" href="https://itunes.apple.com/us/app/id3********"><img src="/images/ios.png" alt=""></a>
  </div>
  <!-- If you want one button to serve both Android and iOS, use the code below instead
  <a id="store_link" href=""><img src="download.png" alt=""></a>
  -->
  <script type="text/javascript" src="/landing-page-test.js"></script>
  <script type="text/javascript">
    window.onload = function () {
      var url = generateUrl(true);

      // onelink is generated
      if (url) {
        document.getElementById('andrd_link').setAttribute('href', url);
        document.getElementById('ios_link').setAttribute('href', url);
      }

      //otherwise, if onelink is not generated it means that the user is redirected
      // and the store links in the buttons stay the same

      /* for the one button solution for both Android and iOS, use the code below instead

      document.getElementById('store_link').setAttribute('href', url);

      */

    };
  </script>
</body>

</html>
```

</Accordion>

<div id="tip-2" />

> 👍 **ヒント**
>
> JavaScriptのスニペットは、Googleタグマネージャーを使って実装できます。 Googleタグマネージャーを使うと、ランディングページ用JavaScriptを実行するタイミングやページを簡単に管理できます。

<div id="instructions-7" />

### 手順

1. ユーザーが直接訪問する可能性があり、モバイルアプリの<strong><em>［ダウンロード］</em></strong>ボタンを設置しているWebサイト内の各ページで、読み込み時に<strong><em>generateUrl</em></strong>スクリプトを実行します。  

   <div id="important" />

   > 🚧 **重要**
   >
   > <strong><em>［ダウンロード］</em>ボタンには、デフォルトでiTunesとGoogle Playのアプリページへの直接リンクを設定してください<strong>。これらのリンクを変更しない場合（AppsFlyerのアトリビューションリンクやMeta adsからの訪問など）、</strong><em>generateUrl</em></strong>は' 'を返します。それ以外の場合は、両方のダウンロードボタンで使用するURLを返します（この場合は、OneLinkを使い、両アプリに対応する<strong><em>［ダウンロード］</em></strong>ボタンを1つだけ設置することもできます）。

2. ***oneLinkURL***パラメータの値を、自社の基本となるOneLink URLに置き換えます。プレースホルダーの`https://yourapp.onelink.me/abcd`と同じ形式にしてください。  
   Meta adsの有料広告を除くすべてのSRNと、モバイルのオーガニック訪問者の成果を紐づけるために必須です。
3. ***webFormURL***パラメータの値を、自社のWebフォームへのリンクに置き換えます。 WebフォームではユーザーのメールアドレスまたはSMSの送信先を取得し、アプリをダウンロードするためのOneLink URLを含むメッセージをモバイルデバイスに送信できるようにします。  
   デスクトップからの訪問者の成果を紐づけるために必須です。
4. モバイルのオーガニックユーザーをwebsite以外のメディアソースに紐づけたい場合は、***partnerIDParam***パラメータの値を置き換えます。
5. ランディングページURLで別のキャンペーン名（`&c={CAMPAIGN_NAME}`）を指定していない場合、デフォルトでは、ユーザーが<strong><em>［ダウンロード］</em></strong>ボタンをクリックしたWebページに成果が紐づきます。この設定を変更するには、<strong><em>campaignParam</em></strong>パラメータの値を置き換えます。  
   Meta adsの有料広告を除くすべてのケースで任意の設定です。

<div id="viewing-the-results" />

## 結果の確認

[![dashboard_landing_page_results.png](https://files.readme.io/29d7b6b096687a1f106efa4dcfc65ab1f550976516c87c3ffafde29f852855bb-360001342158.png)](https://files.readme.io/29d7b6b096687a1f106efa4dcfc65ab1f550976516c87c3ffafde29f852855bb-360001342158.png)

他のメディアソースと同様に、ランディングページの成果は、アプリのダッシュボード、ローデータ、またはAppsFlyer APIで確認できます。

モバイルマーケティングの経路が常にランディングページを経由する場合、各メディアソースは以下のユーザーを表します。

| **流入元** | **説明** |
| --- | --- |
| **organic** | ランディングページを経由していない、またはランディングページで接触がなかったユーザー。または、ランディングページで接触したものの、アプリ起動前にアトリビューションのルックバック期間を過ぎたなどの理由で成果が紐づかなかったユーザー。 |
| **website** | ランディングページやWebサイトを訪問し、その後インストールしたモバイルのオーガニックユーザー。 |
| **Meta ads** | Meta adsの有料広告から流入したユーザー。 |
| **fbpost\_lp** | 拡散されたMeta adsの無料投稿から流入したユーザー。 |
| **google\_lp** | Google広告から流入したユーザー。 |
| **[SRN]\_lp** | 他のSRNから流入したユーザー。具体的には、次のSRNが該当します。 Twitter（twitter\_lp）、Snapchat（snapchat\_lp）、Doubleclick（doubleclick\_lp）、Oath（oath\_lp）。 |
| **連携済みパートナーのID** | AppsFlyerのアトリビューションリンクを使用する、連携済みパートナーの広告から流入したユーザー。例：inmobi\_int、tapjoy\_int |
| **desktop** | Webフォームに情報を入力した後、モバイルデバイスに届いたSMSまたはメールのリンクをクリックし、インストールを完了したデスクトップユーザー。 |
| **その他の流入元** | AppsFlyerのアトリビューションリンクを使用するオウンドメディアから流入したユーザー。例：email、sms、blog\_postなど |

<div id="onelink-for-landing-page-solution" />

## ランディングページ向けのOneLinkソリューション

OneLink™は、デバイスの判別とリダイレクト、またはディープリンクに使用する、AppsFlyer独自のアトリビューションリンクです。

<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">ソーシャルアプリ向けランディングページ</Anchor>を利用するには、広告主側で基本となるOneLink URLを用意する必要があります。 ソーシャルメディアアプリ内の広告をクリックしたユーザーは、AppsFlyerが生成するランディングページへリダイレクトされます。そのページから、ディープリンクでアプリを開くか、アプリのインストールへ進むことができます。

AppsFlyerは、ソーシャルメディアアプリ向けにさまざまなランディングページのテンプレートを提供しています。テンプレート内の要素の配置は固定されていますが、背景画像や背景色、タイトル、テキスト、画像、ボタン、タグなど、各要素の内容はカスタマイズできます。

アプリにOneLinkをまだ実装していない場合は、次の手順に従ってください。

1. <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor>を設定します。
2. そのテンプレートを基に<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#onelinkリンクの作成">OneLink URL</Anchor>を作成します。
3. スクリプト内の[https://yourapp.onelink.me/abcd](https://yourapp.onelink.me/abcd)を、自社のOneLink URLに置き換えます。

<div data-zendesk-anchors="the-upsides=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 the-downsides=%E3%83%87%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 the-challenges-of-mobile-attribution-on-landing-pages=%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E8%AA%B2%E9%A1%8C the-solution=%E8%A7%A3%E6%B1%BA%E6%96%B9%E6%B3%95 landing-page-scenarios=%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E5%88%A9%E7%94%A8%E3%82%B1%E3%83%BC%E3%82%B9 description=%E8%AA%AC%E6%98%8E conclusion=%E5%AF%BE%E5%BF%9C%E3%81%AE%E8%A6%81%E7%82%B9 instructions=%E6%89%8B%E9%A0%86 what-the-script-does=%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%83%88%E3%81%AE%E5%8B%95%E4%BD%9C description::7888dd9d=%E8%AA%AC%E6%98%8E-1 conclusion::11bed45=%E5%AF%BE%E5%BF%9C%E3%81%AE%E8%A6%81%E7%82%B9-1 instructions::5aa3290f=%E6%89%8B%E9%A0%86-1 what-the-script-does::2a675257=%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%83%88%E3%81%AE%E5%8B%95%E4%BD%9C-1 description::650e3f28=%E8%AA%AC%E6%98%8E-2 conclusion::a982e4bd=%E5%AF%BE%E5%BF%9C%E3%81%AE%E8%A6%81%E7%82%B9-2 instructions::afffc83f=%E6%89%8B%E9%A0%86-2 what-the-script-does::3fd4ce35=%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%83%88%E3%81%AE%E5%8B%95%E4%BD%9C-2 description::9c3fcdaa=%E8%AA%AC%E6%98%8E-3 conclusion::bf993a93=%E5%AF%BE%E5%BF%9C%E3%81%AE%E8%A6%81%E7%82%B9-3 instructions::350b4cb1=%E6%89%8B%E9%A0%86-3 what-the-script-does::3dda504d=%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%83%88%E3%81%AE%E5%8B%95%E4%BD%9C-3 description::5150e1b5=%E8%AA%AC%E6%98%8E-4 conclusion::d51c1aec=%E5%AF%BE%E5%BF%9C%E3%81%AE%E8%A6%81%E7%82%B9-4 instructions::e083609=%E6%89%8B%E9%A0%86-4 what-the-script-does::85ffec6c=%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%83%88%E3%81%AE%E5%8B%95%E4%BD%9C-4 description::f5a2038b=%E8%AA%AC%E6%98%8E-5 conclusion::4593a93c=%E5%AF%BE%E5%BF%9C%E3%81%AE%E8%A6%81%E7%82%B9-5 instructions::2e4dd2ee=%E6%89%8B%E9%A0%86-5 what-the-script-does::d6370587=%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%83%88%E3%81%AE%E5%8B%95%E4%BD%9C-5 description::e20640cf=%E8%AA%AC%E6%98%8E-6 conclusion::c818491=%E5%AF%BE%E5%BF%9C%E3%81%AE%E8%A6%81%E7%82%B9-6 instructions::ba61ae3e=%E6%89%8B%E9%A0%86-6 what-the-script-does::3668d917=%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%83%88%E3%81%AE%E5%8B%95%E4%BD%9C-6 landing-page-javascript=%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E7%94%A8javascript instructions::10da52a9=%E6%89%8B%E9%A0%86-7 viewing-the-results=%E7%B5%90%E6%9E%9C%E3%81%AE%E7%A2%BA%E8%AA%8D onelink-for-landing-page-solution=%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E5%90%91%E3%81%91%E3%81%AEonelink%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3" />
