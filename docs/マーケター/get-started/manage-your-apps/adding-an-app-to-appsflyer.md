---
title: AppsFlyerにアプリを追加する
metadata:
  keywords:
    - Add App
    - adding an app
    - Advertisers
    - could not add app
    - security reasons
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2016-01-20T08:57:00Z'
  edited_at: '2026-10-14T09:34:39Z'
  id: 207377436
  locale: ja
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ja/articles/207377436
---
> **概要：** アプリをAppsFlyerに追加して、インストールやアプリ内イベントに関するアトリビューションデータを取得し、AppsFlyerのさまざまなツールを使用してデータを分析する方法を学びましょう。

<div id="overview" />

## 概要

管理画面にまだアプリを追加していない場合、AppsFlyerにログインするとアプリのオンボーディングページが表示されます。アプリのオンボーディングでは、アプリを追加し、アトリビューションの準備を整えるために全てのステップをガイドします。

<div id="entering-the-wizard-for-adding-an-app" />

### アプリ追加ウィザードに入る

プラットフォームからアプリ追加ウィザードに入るか、アプリのオンボーディングページ（AndroidとiOSアプリのみ）からアプリを追加できます。

**アプリのオンボーディングページからウィザードにアクセスする：**

* **アプリを追加**するステップで**アプリを追加**をクリックし、アプリ追加の指示に従います。

<div id="note" />

> 📘 **注意**
>
> オンボーディングページが表示されない場合は、管理画面左メニュー 設定 > **アプリのオンボーディング**からアクセスします。

![オンボーディングページ.png](https://files.readme.io/8903839c25f12df28e1c4b488699670e2dadca83af9ddfebfc0cf4eacd2ce744-33198275479953.png)

**プラットフォームからアプリ追加ウィザードに入るには：**

* メニューバー上部 > **アプリ一覧**から、**+ アプリを追加**をクリックします。
* AppsFlyerホームページから、**+アプリを追加**をクリックします。
* 上部のバーから、アカウントメニュー（メールアドレスドロップダウン）を開き、**アプリオンボーディング** で、**+ 別のアプリのオンボーディング**をクリックします。

<Image alt="アプリを追加 (1).png" src="https://files.readme.io/894b7b76c1da76e2308b110266cbffeb579c551033ce302ade182c1d63fd9384-33198275483793.png" width="593px" />

<div id="adding-an-app" />

## アプリの追加

[アプリ追加ウィザード](#アプリ追加ウィザードに入る)に到達したら、次の手順に従います：

1. [アプリの詳細を入力](#アプリの詳細を入力)します。
2. [追加情報を入力](#追加情報を入力しますwebアプリには該当しません)してください。
3. **アプリを追加**をクリックします。
4. <Anchor target="_blank" href="/marketers/ja/docs/getting-started-onboarding-for-marketers#ステップ2sdk--api実装">SDK実装</Anchor>や連携で使用するためにDevキーをコピーします（常時、<Anchor target="_blank" href="/marketers/ja/docs/app-settings#一般設定">アプリ設定</Anchor>画面からも取得可能です）。
5. 完了後、さらにアプリを追加するには**完了**または **+ 別のアプリを追加**をクリックします。さらにアプリを追加するにはこのプロセスを繰り返します。

<div id="note-1" />

> 📘 **注記**
>
> * アプリを追加できるのは、管理者と<Anchor target="_blank" href="/marketers/ja/docs/user-management">必要な権限を持つアカウントユーザー</Anchor>のみです。
> * アプリを追加する手順（下記）に従う際、以前に選択したオプションに応じて利用可能なオプションが変わります。

アプリを登録すると、管理画面に表示されます。インストールとアプリ内イベントを正しいメディアソースに記録・紐付けるには、次の操作を行ってください：

* SDKを実装する
* Partner Marketplaceでアプリをパートナー（広告媒体）に接続・連携する

オンボーディングプロセスを完了するための<Anchor target="_blank" href="/marketers/ja/docs/getting-started-onboarding-for-marketers">すべての手順</Anchor>をご確認ください。

<div id="note-2" />

<div id="enter-app-details" />

### アプリの詳細を入力

アプリプラットフォームを選択し、以下に示すように必要な詳細を入力します：

<div id="android-androidtv-fire" />

<Accordion title="Android、AndroidTV、Fire">

このオプションは次のプラットフォームで利用してください：

* Android（モバイル）
* AndroidTV
* Amazon Fire
* Amazon Fire TV
* Kindle

<Table>
  <thead>
    <tr>
      <th>
        Google Playのステータス
      </th>
      <th>
        使用するタイミング
      </th>
      <th>
        必要な詳細
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="in-store"></span>
        ストアで
      </td>
      <td>
        あなたのアプリは現在、Google Play ストアで利用可能です
      </td>
      <td>
        **Google Play URL** (Google Playよりコピーされたもの)

        * **例：** https://play.google.com/store/apps/details?id=com.appsflyer.adNetworkTest&hl=en&gl=GB
        * **重要！**
          * アプリが米国の Google Play ストアに掲載されて**いない**場合：
            * URLには、上記の例に示すように、URLがリストされているストアの国コードを含める必要があります：**&gl=** 国コードを含めない場合、アプリを追加しようとするとエラーが発生します。
            * 言語コードはオプションです: **&hl=`{language_code}`**
          * ストアが米国の Google Playストアに登録されて**いる**場合、国コードと言語コードの両方は省略可能です。
      </td>
    </tr>
    <tr>
      <td><span id="pending-approval-not-published"></span>
        承認待ち/未出版
      </td>
      <td>
        アプリはまだ公開されていないか、Google Playから承認待ちです。
      </td>
      <td>
        **Androidパッケージ名**

        * **例:** com.appsflyer.adNetworkTest
        * **注:** 注：パッケージ名は大文字と小文字が区別されます
        * **形式:**
          * 少なくとも2つのセグメント（1つ以上のドット）
          * 各セグメントは文字で始める必要があります
          * すべての文字は英数字またはアンダースコア（a-z、A-Z、0-9、または\_）でなければなりません
          * 最大長は100文字です

        詳細については、<Anchor target="_blank" href="https://developer.android.com/studio/build/application-id">Androidのディベロッパードキュメント</Anchor>を参照してください。
      </td>
    </tr>
    <tr>
      <td><span id="third-party-store-out-of-store"></span>
        サードパーティのストア/ストア外
      </td>
      <td>
        アプリが Google Play 以外の Android アプリストアにある場合や、アプリストア以外の場所からダウンロードできる場合
      </td>
      <td>
        * **Androidパッケージ名**要件の詳細は、前行（承認待ち／未公開）を参照してください
        * **チャンネル名: (オプション)** ストア/ロケーション用に準備された個々のAPKのAndroidManifest.xmlに設定するユニークな名前です。例えば、AmazonストアAPKの場合、`application`タグ内に以下を追加します。名前は大文字と小文字を区別し、アプリを追加したときに<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">チャンネル名フィールドに入力した名前と同一でなければなりません</Anchor>。詳細については、<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation">こちら</Anchor>をご確認ください。

          ```xml
          <application>
               ...
               <meta-data android:name="CHANNEL" android:value="Amazon"/>
               ...
          </application>
          ```

        * **アプリのURL** (サードパーティのアプリストアまたは外部ストアからコピーしたもの)

        <div id="important" />

        > 🚧 **重要！**
        >
        > 複数の媒体でアプリが利用できる場合（つまり Google Play、サードパーティストア、ストア外のロケーションのいずれかの組み合わせ）、<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution">複数ストアでのAndroid計測を設定する</Anchor>オプションを検討することが重要です。リリース当初から正しい実装をすることで、必要なデータを必要な形式でアクセスできるようになります。
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="ios-tvos-macos" />

<Accordion title="iOS、tvOS、MacOS">

このオプションは次のプラットフォームで利用してください：

* iOS
* tvOS
* MacOS

| App Store ステータス | 使用するタイミング | 必要な詳細 |
| --- | --- | --- |
| <span id="in-store::f93cfa22"></span>ストアで | あなたのアプリは現在App Storeで利用可能です | **App Store URL** (App Storeからコピーしたもの)<ul><li>**例:** https://apps.apple.com/us/app/partner-integrations/id1543229303</li><li>**注意:**<ul><li>URL内にストアを特定する2文字の国コードが含まれていることを確認してください（上記の例では、URL内の **us**）</li><li>2019年6月14日以前にApp Storeに追加されたアプリは、URLに（apps.apple.com の代わりに）itunes.apple.com が含まれています。</li></ul></li></ul> |
| <span id="pending-approvalnot-published"></span>承認待ち/未出版 | アプリはまだ公開されていないか、App Storeから承認待ちです | アプリが提出されたApp Storeの**国**<br /><br />App Storeによって割当てられた**アプリID** - 最初につく id を付けずに入力します。<ul><li>**例:** 1543229303</li><li>**形式:** 9または10の数字、0-9</li></ul> |

</Accordion>

<div id="windows-xbox" />

<Accordion title="Windows">

このオプションは次のプラットフォームで利用してください。

* Windows Phone
* Windows（デスクトップ）

| Microsoft Store ステータス | 使用するタイミング | 必要な詳細 |
| --- | --- | --- |
| ストアで | アプリは現在Microsoft Storeで利用可能です | **Microsoft Store URL** (Microsoft Storeからコピーしたもの)<ul><li>**例:** https://www.microsoft.com/en-us/p/wordament/9wzdncrfhwfg</li><li>**注:** 注：上記のURLは、Windows Phoneアプリの例です。URLの形式は、Windowsデスクトップアプリによって異なります。</li></ul>**App ID:** 最大文字数は150文字です。 |
| 承認待ち/未出版 | アプリはまだ公開されていないか、ストアから承認待ちです | Microsoft Storeから割り当てられた**アプリID**<ul><li>**最大長:** 150文字</li><li>**例:** 9wzdncrfhwfg</li><li>**注:アプリIDでは大文字小文字の区別があります。**</li></ul> |

</Accordion>

<div id="web-pba" />

<Accordion title="Web（PBA）">

<div id="note-3" />

> 📘 **注記**
>
> Webアプリは、ピープルベースドアトリビューション（PBA）機能向けにブランドバンドルに含めるWebサイトを指定します。
>
> * このオプションはPBAをサブスクライブしているお客様のみが利用できます。
> * PBAとWeb訪問、Webイベント、Webサイトのアシストインストールの計測し、チャネル、プラットフォーム、デバイス全体のカスタマージャーニーを把握するには<Anchor target="_blank" href="/marketers/ja/docs/people-based-attribution-pba-overview">こちら</Anchor>を参照してください。

**完全なURL:** 完全なURL： トラフィックを計測したいWebサイトの完全なURLを入力してください。これは <Anchor target="_blank" href="/marketers/ja/docs/onboarding-guide-to-people-based-attribution#2">PBA Web SDK</Anchor> を実装した（または実装する予定の）Webサイトです。

[altURL\_diagramalt](https://support.appsflyer.com/hc/article_attachments/30306774125457) 実施されています。

次を含める –

* スキーム
* サブドメイン [オプション]
* ドメイン名
* トップレベルドメイン
* パス（任意）– Webサイトの特定のディクショナリまたはページのアドレス

**アプリ名:** あなたが選択した名前

* 最大文字数:100文字
* XSSタグは許可されません

<div id="important-1" />

> 🚧 **重要！**
>
> 一度作成した Webアプリは、削除して再作成しないとプロパティ（URLとアプリ名）を編集できません。**つまり、<Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle">その一部であるブランドバンドル</Anchor>も削除する必要があります**。

**次のステップ:**

* 新しく作成したWebアp類を<Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings">PBAブランドバンドル</Anchor>に追加すると、PBA管理画面に表示されます。
  * バンドルを作成する前に、ブランドバンドルに含めたい全てのモバイルアプリがアカウントに追加されていることを確認してください。
* Webアプリで指定したWebサイトに<Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide">PBA Web SDKを実装</Anchor>して、計測データを取得してください。

</Accordion>

<div id="web" />

<Accordion title="Web">

Webプラットフォームを使用して新しいWebアプリを作成し、Webアトリビューションを使用してウェブサイトの訪問とコンバージョンを測定します。

<div id="before-you-begin" />

#### **始める前に**

* レガシーの人に基づくアトリビューション（PBA）Webアプリは、「<strong>Web (PBA)」</strong>としてレガシーとしてマークされて表示されます。
* レガシーPBA Webアプリから移行する場合は、既存のPBA Web Devキーを使用できます。

<div id="to-add-a-web-app" />

#### **Webアプリを追加する**

1. **マイアプリ** > **アプリを追加**に移動します。
2. **ウェブサイト**を選択します。
3. 以下を入力してください:

**App name**あなたが選択した名前

* **文字数：** 1000文字まで。
* **許可されている文字:** 文字（任意の言語）、数字、スペース（開始または終了にない）、および特殊文字: . - \_ :
* **ブロックされた文字:** ; \`{ }\` $ &lt; > \` \

**例:** 私のオンラインストア, 企業ウェブサイト2024, 電子商取引\_生産

**プライマリドメイン（フルURL）**:あなたのウェブサイトのプライマリドメインです。これはWebアプリ作成時に設定され、その後変更することはできません。

* **形式:** 有効なドメイン名のみ（プロトコル、パス、またはポートなし）
* **文字数：** 最大500文字
* 処理中AppsFlyerは自動的に
  * http://またはhttps://を削除します
  * 末尾のスラッシュを削除します
  * ドメインを小文字に変換します
* **不変性:** アプリ作成後は編集できません

<strong>【重要】</strong>プライマリドメインを変更するには、ウェブアプリを削除して再作成する必要があり、その結果、履歴データの継続性が失われます。

**例：**

* https://shop.example.com/checkout → shop.example.comとして保存 → アプリID: website-shop.example.com
* example.com/ → example.comとして保存 → アプリID: [website-example.com](http://website-example.com)

app\_idAppsFlyerがプライマリドメインに基づいてウェブアプリのために作成するユニークID。

* フォーマットを使用して自動的に生成されます: website-`<primary_domain>`
* 例: website-shop.example.com

**Web SDK ID**:Web SDKが帰属のために使用する識別子（以前はweb\_dev\_keyと呼ばれていました)。

アプリ作成時の2つのオプション:

**オプション1：新しいものを生成（デフォルト）**

* 新しいWeb SDK IDを自動的に作成します
* フォーマット: website-`{yourdomain.com}`
* 例: website-shop.example.com
* ユースケース新しいウェブ帰属実装

**オプション2：既存のPBA開発キーを再利用**

* 既存のPBA（人に基づく帰属）ウェブアプリ開発キーのドロップダウンから選択します
* ウェブサイトのコードを変更せずにシームレスな移行を可能にします
* ユースケースレガシーPBAから新しいウェブ帰属ソリューションへの移行

**注:** PBA開発キーを再利用することで、ウェブアプリ**への移行が可能です。ウェブサイトの実装に変更を加えることなく。**

各PBA開発キーは**1つの**ウェブアプリにのみ割り当てることができます。PBA開発キーがウェブアプリに使用されると、他のウェブアプリには利用できなくなります。

* **文字数：** 1000文字まで。
* **不変性:** アプリ作成後は変更できません
* **PBA移行:** ドロップダウンには、アカウントのPBAウェブアプリからの開発キーのみが表示されます

**通貨：** アプリの報告に使用される通貨。

* 標準ISO 4217通貨コード（例：USD、EUR、GBP、ILS）
* ドロップダウンから選択
* こちらは必須項目です。

**time\_zone**アプリの報告に使用されるタイムゾーン。

* IANAタイムゾーン形式（例：America/New\_York、Europe/London、Asia/Tokyo）
* ドロップダウンから選択
* こちらは必須項目です。

4. **アプリを作成する**をクリックします。

**制限事項**

* アプリが作成された後は**プライマリドメインを変更できません**。
* プライマリドメインは自動的に**除外ドメイン**にタイプ**プライマリ**として追加されます。

各レガシー**ウェブ開発キーは新しい**ウェブアプリに対してのみ再利用できます。

<div id="note-4" />

> 📘 **注記**
>
> ウェブ帰属設定に関する詳細情報は<Anchor target="_blank" href="/marketers/ja/docs/configure-web-performance-measurement-settings">こちらを参照してください</Anchor>。

</Accordion>

<div id="roku" />

<Accordion title="Roku">

**アプリ名:Roku Developer Dashboardからコピーした**アプリ名/strong>。

* **例:** 私のRokuチャンネル
* **形式:**
  * 最大長は100文字です
  * XSSタグは許可されません

**チャンネルID:Rokuより割り当てられた数値ID**

* **形式:**
  * 数値（0～9）
  * 最大文字数:50文字
* **どうやって見つけますか?**
  * <Anchor target="_blank" href="https://developer.roku.com/developer">Roku Developer Dashboard</Anchor>から、AppsFlyerに追加するチャネル名をクリックしてください。これにより、そのチャネルの Roku Preview & Publish ページが開きます。
  * URLページの末尾の数字はチャネルの

    ![](https://files.readme.io/89f6513eee03558a9dc8e465fe67953780074477fc0fe20675b721d8116671af-33198275490577.png)

</Accordion>

<div id="amazon-vega-os" />

<Accordion title="Amazon Vega OS">

**アプリ名:あなたが選択した名前**

アプリID:アプリのID逆DNS表記を使用して見つかりました：`<tld>`.`<company_name>`.`<app_name>`  
最低2つのセグメントを含む必要があります。各セグメントは文字で始まり、次の文字から構成される必要があります: `A-Z` `a-z` `0-9.` `-`  

例：com.company.myapp

詳細については、<Anchor target="_blank" href="https://developer.amazon.com/docs/vega/0.21/manifest-package.html#fields">Amazon Vega OS ドキュメント</Anchor>の「id」フィールドを参照してください。

</Accordion>

<div id="vizio-smartcast" />

<Accordion title="Vizio SmartCast">

**アプリ名:あなたが選択した名前**

**アプリID:アプリが識別されるID。`vz`で始まり、次に`A-Z` `a-z` `0-9.` `-`からの2〜20文字が続きます。アプリIDを確認する必要がある場合は、Vizio の担当者に確認してください。**

</Accordion>

<div id="samsung-tizen" />

<Accordion title="Samsung Tizen">

**アプリ名:** あなたが選択した名前

**App ID:** アプリID：Samsungによってアプリに割り当てられたバンドルID。文字`G`で始まり、8〜15桁の数字が続きます。アプリIDを取得するには:

1. Samsung TV Seller Officeにサインインしてください。

   1. ここにあるガイドを<Anchor target="_blank" href="https://developer.samsung.com/tv-seller-office/guides/applications/entering-application-information.html%20">アプリ内広告情報</Anchor>の下で参照してください。
2. 開発者URLを入力してください。
3. バンドルIDは自動的に生成され、表示されます。これを使用してアプリストアのURLにアクセスできます。
4. アプリ広告の検証をサポートするために、広告タグや入札リクエストにバンドルIDとアプリストアURLを使用してください。
5. 問題がある場合は、セラーオフィスで問題ボードのチケットを開いてください。

注意：ユニークなアプリストアのウェブページにアクセスするには、バンドルIDをURL "[https://www.samsung.com/us/appstore/app/](https://www.samsung.com/us/appstore/app/)"に追加してください。

例えば、バンドルIDが"G15147002586"の場合、ページのURLは"[https://www.samsung.com/us/appstore/app/G15147002586/](https://www.samsung.com/us/appstore/app/G15147002586/) "になります。開発者URL、バンドルID、およびアプリストアIDは、そのページのメタデータに表示されます。

![](https://files.readme.io/ee4b192abab24e064013a4a034bda38fb3ed49497ae333e327e1b78dd05d5349-33198275491729.png)

</Accordion>

<div id="lg-webos" />

<Accordion title="LGウェブOS">

**アプリ名:** あなたが選択した名前

**App ID:** LG WebOS アプリID。

* **形式:**
  * 最大長は50文字です。
  * バンドル形式での`A-Z` `a-z._`からの文字。文字で始まる必要があります。
* **例:** com.my-company.app

アプリIDを確認する必要がある場合は、LB WebOS の担当者にお問い合わせください。

</Accordion>

<div id="playstation" />

<Accordion title="プレイステーション">

**アプリ名:** あなたが選択した名前

**App ID:** アプリ ID： PlayStationコンセプトID、ゲームまたはその他のコンテンツコンセプトに割り当てられた一意の識別子これは、PSストアのURLに 5〜9桁の数字として表示されます：アプリのアプリストアURLの最後にあります。

![playstation_app_id_url.png](https://files.readme.io/df92705244e55e7adc44a88076556609983ec3dff89c03df77e19f0f1a061bbb-33198323434513.png)

</Accordion>

<div id="vidaa" />

<Accordion title="Vidaa">

**アプリ名:** あなたが選択した名前

**App ID:** Vidaa アプリID。最大文字数は150文字です。

</Accordion>

<div id="steam" />

<Accordion title="Steam">

**アプリ名:** あなたが選択した名前

**App ID:** Steam アプリID。SteamストアのURLに表示される5〜8桁の数字です。

![steam_store_app_url.png](https://files.readme.io/4976c0323eab0c08b61d4a1a7a75ebf7ea9fcd819176ff574421f0de4d8c614c-33198275497617.png)

</Accordion>

<div id="meta-quest" />

<Accordion title="Meta Quest (Oculus)">

**アプリ名:** あなたが選択した名前

**アプリID:** Meta QuestアプリIDは、アプリがダウンロードされるMetaアプリストアURLの末尾に表示されます。`A-Z` `A-Z` の 3 ～ 50 文字が含まれます

<Image alt="" src="https://files.readme.io/1938b3f89b866ebdd3452367d7410c423ce57372544a801ca3d1b409f3bff541-33198323442449.png" width="397px" />

</Accordion>

<div id="nintendo-switch" />

<Accordion title="Nintendo Switch">

**アプリ名:** あなたが選択した名前

**App ID:** Nintendo SwitchアプリIDは、アプリがダウンロードされるストアのURLの末尾に表示されます。14桁の数字が含まれます。

* **例:** 70010000012345

</Accordion>

<div id="xbox" />

<Accordion title="Xbox">

**アプリ名:** あなたが選択した名前

**App ID:** XboxアプリIDは、アプリがダウンロードされるXboxストアURLの末尾に表示されます。12文字と数字のみを含みます (`A-Z` `a-z0-9`)。

![](https://files.readme.io/c33ffcb35d4488b9340cfa8b475097eab7b79bfeaf94e8cf8ce6478dda07d341-33198275505041.png)

**注:** アプリIDでは大文字小文字の区別があります。

</Accordion>

<div id="epic-games" />

<Accordion title="Epic Games">

**アプリ名:** あなたが選択した名前

**App ID:** アプリID： Epic GamesアプリID（アプリのダウンロード元のストアに表示されるもの）`a-z0-9._-` `A-Za-z0-9._-` の 3 ～ 50 文字が含まれます

![](https://files.readme.io/81d1f043c8a7ef5e367a62d564f8c6241c6057445363b21286e3f72ad4210cf6-33198275508497.png)

</Accordion>

<div id="native-pc" />

<Accordion title="Native PC">

**アプリ名:** あなたが選択した名前

**App ID:** ネイティブ PC アプリID。`a-z0-9._-` `A-Za-z0-9._-` の 3 ～ 50 文字が含まれます

</Accordion>

<div id="enter-additional-information-not-applicable-to-web-apps" />

### 追加情報を入力します（Webアプリには該当しません）:

<Image alt="" src="https://files.readme.io/561aea51bbfaa733721040706cac2b9520e35cfe71027fa34d08ed7890baf00c-33198323448081.png" width="559px" />

<div id="select-currency" />

#### **通貨を選択**

このアプリのデータを管理画面で表示する際の通貨を選択してください。収益と使うイベントは、イベント時点の為替レートを基にこの通貨に変換されます。<Anchor target="_blank" href="/marketers/ja/docs/app-settings#localization-currency">アプリの通貨設定とその影響について詳細はこちら</Anchor>。

<div id="important-2" />

> 🚧 **重要！**
>
> アプリで使用する通貨を選択する際には慎重に選んでください。コストと収益が一度記録されると、変更することはできません。

<div id="select-timezone" />

#### **タイムゾーンを選択**

ここで選択したタイムゾーンを、Meta広告やGoogle広告など、他のアトリビューションパートナーで設定したタイムゾーンに合わせてください。これにより、AppsFlyer管理画面で報告されるデータとこれらのパートナーから受け取るデータの一致度が高まります。

<div id="note-5" />

> 📘 **注意**
>
> * タイムゾーンを一度設定するとロックされ、翌日まで変更できません。
> * <Anchor target="_blank" href="/marketers/ja/docs/changing-app-time-zone-settings">アプリのタイムゾーン設定とその影響について</Anchor>詳細はこちら。

<div id="define-app-audience" />

#### **アプリのユーザー層を定義する**

アプリが子供向けか混合ユーザー向け（子供と大人の両方）かを示すために、「**はい**」または「**いいえ**」を選択します。  
**はい**を選択した場合

1. 子供向けアプリのコンプライアンスの実装に関する<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">ガイド</Anchor>を開いてお読みください。
2. ガイドを読んだこと、および指定されたコントロールを実装することを確認するためには、ボックスを選択します。

<div id="note-6" />

> 📘 **注意**
>
> * アプリを追加してから2週間後に、子供向けアプリのプライバシーコントロールを実装したことを確認するよう通知が届きます。確認後、確認メッセージが表示されます。通知センターから確認メッセージにいつでもアクセスでき、<Anchor target="_blank" href="/marketers/ja/docs/audit-log">監査ログ</Anchor>で確認の詳細を確認できます。
> * 子供向けアプリに関する<Anchor target="_blank" href="/marketers/ja/docs/child-directed-apps-faq">よくある質問</Anchor>をご覧ください。

<div id="manage-your-apps-in-bulk-via-api" />

#### API経由でアプリを一括管理

アカウント管理者は、UIの主要機能をサポートする専用のAPIを利用して、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/app-management-v2-overview">複数のアプリを一括管理</Anchor>できます。これには、アプリの追加と削除、およびアプリ設定の更新が含まれます。APIには同じエラー検証メカニズムが組み込まれています。

<div id="note-7" />

> 📘 **注意**
>
> 現時点では、モバイルアプリに対してのみ、API経由でのアプリの追加とアプリ設定の更新が可能です。アプリの削除はすべてのプラットフォームで可能です。

<div id="add-a-debug-or-testing-app" />

### デバッグまたはテストアプリを追加してください。

開発者が**デバッグ**、**サンドボックス**、または**テストアプリ**を作成した場合、そのアプリをダッシュボードに追加する必要があります。開発者がアプリでテストを開始すると、データがアプリのダッシュボードに表示されます。

<div id="note-8" />

> 📘 **注記**
>
> App Storeに公開されていないiOSアプリで有効なApp Store IDがまだない場合でも、**ダミーのiOS App Store ID**を使用してSDKテストを進めることができます。これにより、実際のApp StoreリストなしでSDKの統合とテストが可能になります。

デバッグアプリを作成し、ダッシュボードに追加する方法についての開発者向けの指示は、次を参照してください：

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/testing-android#creating-an-android-debug-app">Androidの指示</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/testing-ios#creating-an-ios-debug-app">iOSの指示</Anchor>

<div id="about-pending-apps" />

## 保留中のアプリについて

保留中のステータスのアプリを操作すると、AppsFlyer SDKをテストするときに役立ちます。

管理画面上でアプリが保留中であることは、データの収集と計測にインパクトしません。アプリがアプリストアで保留中か公開中かに関係なく、ユーザーがそれをインストールして操作すると、インストールとアプリ内イベントのデータが管理画面に記録されます。

保留中のアプリが公開されると、AppsFlyerがそのステータスを検出して自動的に更新するため、再度追加する必要はありません。保留中のアプリについてと、ステータスを手動で更新するオプションの手順について<Anchor target="_blank" href="/marketers/ja/docs/why-is-my-app-still-pending">詳細はこちら</Anchor>。

<div id="troubleshooting" />

## トラブルシューティング

一般的な問題についてのソリューションを見つけます:

<div id="app-wasnt-added" />

<Accordion title="アプリが追加されませんでした">

このエラーが発生した場合は、CSM に連絡するか、[hello@appsflyer.com](mailto:hello@appsflyer.com) にメールを送信してください。

</Accordion>

<div id="app-not-in-the-store" />

<Accordion title="アプリがストアにない">

アプリ名またはIDを適切に使用して、ストアURLを正確にコピーしたか確認してください。

</Accordion>

<div id="cant-access-marketplace" />

<Accordion title="マーケットプレイスにアクセスできません">

このエラーは、米国以外のストアからAndroidアプリを追加する際に発生することがあります。この問題を解決するには、以下の手順に従ってください。

1. 上記のように、**承認待ち・未公開**のステータスでアプリを追加します。
2. AppsFlyerの**アプリ設定**ページに移動してください。
3. **アプリストアの国**を正しい国（例：日本）に変更します。

</Accordion>

<div id="something-went-wrong" />

<Accordion title="問題が発生しました。再度お試しください。">

このエラーが発生する可能性がある理由として、国コードなしでAndroidアプリを追加しようとしていることが挙げられます（アプリ**未**リストの米国のGoogle Playストアの場合）。この問題の詳細な解決方法については、[上記](/docs/adding-an-app-to-appsflyer#in-store)をご覧ください。

</Accordion>

<div id="my-ios-app" />

<Accordion title="私のiOSアプリはApp Storeから削除されました。なぜまだインストールが表示されているのですか？">

これが起こるのは、ユーザーが以前デバイスに存在していたアプリをオペレーティングシステムを介して再インストールできるからです。アプリがApp Storeで利用できなくなっても、ユーザーはまだインストールでき、これらのインストールはAppsFlyerにカウントされます。

</Accordion>

<div id="other-information" />

## その他の情報

<div id="product-line" />

<Accordion title="プロダクトライン">

製品ラインからアプリを追加または削除できます。製品ラインとその提供内容についての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/product-line-group-apps-for-cross-platform-attribution">こちらを参照</Anchor>してください。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 01H8Y09SSKZS2RHM35JT16ESKM=%E6%A6%82%E8%A6%81 entering-the-wizard-for-adding-an-app=%E3%82%A2%E3%83%97%E3%83%AA%E8%BF%BD%E5%8A%A0%E3%82%A6%E3%82%A3%E3%82%B6%E3%83%BC%E3%83%89%E3%81%AB%E5%85%A5%E3%82%8B 01H8Y0K9EHWH05DB5K02ASJG11=%E3%82%A2%E3%83%97%E3%83%AA%E8%BF%BD%E5%8A%A0%E3%82%A6%E3%82%A3%E3%82%B6%E3%83%BC%E3%83%89%E3%81%AB%E5%85%A5%E3%82%8B 01H8F2TENNWXADKVZFHY9SE8JC=%E6%B3%A8%E6%84%8F adding-an-app=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%BF%BD%E5%8A%A0 01H8ECFB7V0DCNE0ZKPZ2GCVMP=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%BF%BD%E5%8A%A0 01H81661SR41SQFZZ0AW6K2EDM=%E6%B3%A8%E8%A8%98 enter-app-details=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%A9%B3%E7%B4%B0%E3%82%92%E5%85%A5%E5%8A%9B 01H815FE64VZZS9WGJSC8VY74D=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%A9%B3%E7%B4%B0%E3%82%92%E5%85%A5%E5%8A%9B 01H815FE64CXEHWTV40NVYQHGJ=android-androidtv-fire 01H815FE641Q6N5JY5846QE59Y=%E9%87%8D%E8%A6%81 01H815FE64X0SPA71TBQ9T4ZVB=ios-tvos-macos 01H815FE64ZZA2N1XQFBRXVF41=windows-xbox 01H815FE64XZKDJW1CX5R1JE1T=web-pba 01H815FE646GWA7KJ83KTGHH05=%E6%B3%A8%E8%A8%98-1 01H815FE65R1Z06TJR0DNC8PFY=%E9%87%8D%E8%A6%81-1 h_01KGEPG8V7ZZ6V2EYYPES0QM77=web before-you-begin=%E5%A7%8B%E3%82%81%E3%82%8B%E5%89%8D%E3%81%AB h_01KGPM33BA6AJSX32CTN808AXM=%E5%A7%8B%E3%82%81%E3%82%8B%E5%89%8D%E3%81%AB to-add-a-web-app=web%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B h_01KGPM3GTYJJ0ARD3R1XHVAQ8F=web%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B h_01KGPM5TTNSECSWEAQY5VH7DTY=%E6%B3%A8%E8%A8%98-2 01H815FE65X37H40AN99EZJ940=roku h_01KDJP1G4QZHAKH13M5D3CD793=amazon-vega-os 01H815FE654W6D4FCANR1DET8A=vizio-smartcast 01H815FE65J6T610QQXWJS0CJS=samsung-tizen 01H815FE65CRW81AD1006KHGV4=lg-webos 01H815FE65ESQZ56C8B4HG9P8M=playstation 01H815FE65483DV8MD4STH3QTR=vidaa 01H815FE655PZS1H9YW95X1R53=steam 01H815FE655XP075WYRVVFKD4F=meta-quest 01H815FE65XJEVHNT45SHGWJS4=nintendo-switch 01H815FE6598PD87PNBE7MFEQ8=xbox 01H815FE658WJCB1ZCPGAD4GGS=epic-games 01H815FE652P3HCWY2PEDJJARM=native-pc enter-additional-information-not-applicable-to-web-apps=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1%E3%82%92%E5%85%A5%E5%8A%9B%E3%81%97%E3%81%BE%E3%81%99web%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AB%E3%81%AF%E8%A9%B2%E5%BD%93%E3%81%97%E3%81%BE%E3%81%9B%E3%82%93 01H815FE65AWE8VKV9FYJ7N8MV=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1%E3%82%92%E5%85%A5%E5%8A%9B%E3%81%97%E3%81%BE%E3%81%99web%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AB%E3%81%AF%E8%A9%B2%E5%BD%93%E3%81%97%E3%81%BE%E3%81%9B%E3%82%93 select-currency=%E9%80%9A%E8%B2%A8%E3%82%92%E9%81%B8%E6%8A%9E h_01HHCFD94K6PGQRED6Z6KXKRQF=%E9%80%9A%E8%B2%A8%E3%82%92%E9%81%B8%E6%8A%9E 01H815FE65X7BCFKH1EEFA91GQ=%E9%87%8D%E8%A6%81-2 select-timezone=%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E3%82%92%E9%81%B8%E6%8A%9E h_01HHCFDE25S92GZ9TPGQW4PXHV=%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E3%82%92%E9%81%B8%E6%8A%9E h_01HMNSSBP2EFXCVW290MKW1EFV=%E6%B3%A8%E6%84%8F-1 define-app-audience=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E5%B1%A4%E3%82%92%E5%AE%9A%E7%BE%A9%E3%81%99%E3%82%8B h_01HHCFDRNFDERZZV3TT8BVXMB4=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E5%B1%A4%E3%82%92%E5%AE%9A%E7%BE%A9%E3%81%99%E3%82%8B h_01H9MYF17VNBETQ0HS745EJ85H=%E6%B3%A8%E6%84%8F-2 manage-your-apps-in-bulk-via-api=api%E7%B5%8C%E7%94%B1%E3%81%A7%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E4%B8%80%E6%8B%AC%E7%AE%A1%E7%90%86 h_01HR3Z81NXCAZKK26HWCN5VD9D=api%E7%B5%8C%E7%94%B1%E3%81%A7%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E4%B8%80%E6%8B%AC%E7%AE%A1%E7%90%86 h_01HR3ZJW7YD4B8WV0NW9MX6EVP=%E6%B3%A8%E6%84%8F-3 add-debug-or-testing-app=%E3%83%87%E3%83%90%E3%83%83%E3%82%B0%E3%81%BE%E3%81%9F%E3%81%AF%E3%83%86%E3%82%B9%E3%83%88%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%97%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84 h_01K2F8JX66F614HF8D5MWQ26P7=%E3%83%87%E3%83%90%E3%83%83%E3%82%B0%E3%81%BE%E3%81%9F%E3%81%AF%E3%83%86%E3%82%B9%E3%83%88%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%97%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84 ios-dummy-app-id-note=%E6%B3%A8%E8%A8%98-3 h_01K2F8JX662XEY0A47DZG6DHWQ=%E6%B3%A8%E8%A8%98-3 about-pending-apps=%E4%BF%9D%E7%95%99%E4%B8%AD%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H815FE65MYPABC3DTVEMA8E9=%E4%BF%9D%E7%95%99%E4%B8%AD%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 troubleshooting=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 01H815FE655HS8EA4R00D0VCYD=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 01H815FE65V2GYP0Q612512DE0=app-wasnt-added 01H815FE65A0HPTVVCT42QQA6M=app-not-in-the-store 01H815FE65EN3PBSH5BKRGNNXD=cant-access-marketplace 01H815FE65FR4ATDA4CVX2FW9N=something-went-wrong h_01JNK9HB2ZWQ78XK9B33QWHV49=my-ios-app other-information=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%83%85%E5%A0%B1 h_01K7KSRWCB1Y89T21JFJR42VAJ=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%83%85%E5%A0%B1 h_01K7KSPDSSG8CRCQB5V545Y12Z=product-line" />
