---
title: OneLinkテンプレートの作成
metadata:
  keywords:
    - template
    - Marketers
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2014-11-03T12:35:49Z'
  edited_at: '2026-10-28T09:18:25Z'
  id: 207032246
  locale: ja
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ja/articles/207032246
---
> **概要：** 各種マーケティングキャンペーンで作成するすべてのOneLinkリンクに共通する、リダイレクト設定の土台となるテンプレートを作成します。リンクを作成してユーザーに適切な体験を提供するには、テンプレートが必要です。

## OneLinkテンプレート

<Embed title="OneLinkテンプレートの作成" typeOfEmbed="youtube" url="https://www.youtube.com/embed/d4AtCJ9122Q" providerUrl="https://www.youtube.com" />

OneLinkテンプレートには、次の特徴があります。

* ユーザーが実際にクリックするリンクではなく、多数のカスタムリンクを作成するための土台です。通常、テスト目的を除けば、アプリごとにテンプレートが1つあれば、さまざまな広告キャンペーンに必要な数だけリンクを作成できます。
* ユーザーのデバイスのプラットフォームと、アプリをインストール済みかどうかに応じたリダイレクト先を設定します。
* 各種マーケティングキャンペーンで作成するすべてのOneLinkリンクに共通する、振り分けルールを定義します。具体的には、次のリダイレクトを設定します。
  * **アプリをインストールしていない新規ユーザー**：適切なアプリストアまたはWebのURLへ誘導します。
  * **アプリをインストール済みの既存ユーザー**：Android App Links、iOS Universal Links、またはURIスキームを使用してアプリを開きます。この設定には、開発者による作業が必要です。
  * **注意**：Webサイトまたはアプリストアへのリダイレクト設定は、リンク単位で上書きできます。

## OneLinkテンプレートの作成

| 担当者 | 前提条件 | 所要時間 | 作成結果 |
| --- | --- | --- | --- |
| <ul><li>アプリをインストールしていない新規ユーザー向けのリダイレクト設定（適切なアプリストアやWebページへの誘導など）は、マーケターのみで行えます。</li><li>アプリをインストール済みの既存ユーザー向けのリダイレクト設定（アプリを開くなど）を追加するには、マーケターとAndroid／iOS開発者の両方による対応が必要です。</li></ul> | <ul><li>少なくとも1つのアプリが登録されているAppsFlyerアカウント。</li><li>マーケターは、AppsFlyerの管理者ユーザーであるか、OneLinkテンプレートの追加・編集権限を持っている必要があります。</li></ul> | Android／iOS開発者と共同で作業し、約1.5時間。 | ユーザーのデバイスに応じて、適切なアプリストア、Webページ、またはアプリ内へ誘導するリンクを作成できるテンプレート。 |

<div id="create-a-onelink-template-with-redirection-logic-for-new-app-users" />

<Accordion title="新規アプリユーザー向けのリダイレクトを設定したOneLinkテンプレートの作成">

**OneLinkテンプレートを作成するには：**

1. AppsFlyerのサイドメニューから、［**Engage**］>［**OneLink管理**］を選択します。  
   OneLinkスイートはアカウント単位の機能で、アカウント内のすべてのアプリについてOneLinkテンプレートとカスタムリンクを作成できます。  
   [![](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)**注意**：テンプレートをまだ作成していない場合は、導入ウィザードが開きます。ウィザードの案内に従ってください。この場合、以降の手順は不要です。
2. メニューアイコン>［**OneLinkテンプレートを追加**］をクリックします。  
   OneLinkテンプレートの設定ページが開きます。  
   &lt;0>&lt;1> 0>
3. ［**OneLinkテンプレート名**］フィールドに名前を入力します。

   > 📘 **注意**
   >
   > * OneLinkテンプレート名には、**アプリ名**（例：feed\_me）や、OneLinkの用途または提供する体験が分かる名前（例：pre\_launch\_landing\_page）を含めることをおすすめします。
   > * キャンペーン名、チャネル名、メディアソース名は含めないでください。テンプレート自体はユーザーが実際に使用するリンクではなく、多数のリンクを作成するための土台です。また、通常、複数のプラットフォームに対応することがOneLinkテンプレートの利用目的であるため、プラットフォーム名（Android、iOS）も含めないでください。
   > * テンプレート名は内部管理にのみ使用されます。マーケティングのアトリビューションデータには影響せず、ユーザーにも表示されません。

4. ［**サブドメイン**］フィールドに、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#サブドメイン">サブドメイン</Anchor>名を入力します。
   * ブランドに合ったサブドメインを選択してください。例えば、Webサイトがwww.abcd.comの場合、サブドメインにはabcdを選択します。
   * このサブドメインは、リンクURLの一部としてユーザーに表示されます。例：`https://abcd.onelink.me/RPsv/37e5cd36`。
   * このテンプレートをもとにカスタムリンクを作成すると、サブドメインは変更できなくなります。
   * 使用できる文字は、英小文字、数字、ハイフン（-）のみです。
   * OneLinkは独自のブランドドメインにも対応しており、キャンペーンのパフォーマンス向上やブランドの露出拡大に役立ちます。 <Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain">詳細はこちら</Anchor>
5. Androidアプリ、iOSアプリ、またはその両方を選択します。
6. （任意）パラメータの追加によるリンクの不正利用を防ぐには、［ショートリンクの改ざん防止］を有効にします。**ショートリンクの改ざん防止を有効にするには：**

   ［**ショートリンクの改ざん防止**］で、［**パラメータが追加されたリンクのクリックをアトリビューション対象外にする**］を有効にします。

   この設定を有効にすると、このテンプレートから作成したショートリンクにパラメータが追加された場合、そのクリックはアトリビューション対象外になります。ユーザーはテンプレートのリダイレクト設定に従って誘導されます。影響を受けるのはアトリビューションのみです。  

   **例：**

| リンク | 結果 |
| --- | --- |
| `[subdomain].onelink.me/[template_id]/[shortlink_id]` | 通常どおりアトリビューションが行われます。 |
| `[subdomain].onelink.me/[template_id]/[shortlink_id]?param=value` | パラメータが追加されているため、クリックはアトリビューション対象外になります。 |

   **注意：**

   * この設定はテンプレート単位で適用されます。個々のリンクで有効・無効を切り替えることはできません。
   * この機能のリリース前に作成されたテンプレートでは、無効になっています。利用する場合は、有効にしてください。リリース後に作成されたテンプレートでは、デフォルトで有効です。不要な場合は、無効にしてください。
7. ［**アプリがインストールされていない場合**］のユーザーのリダイレクト先を設定します。  
   * AndroidアプリとiOSアプリの両方を選択した場合、デフォルトでは新規アプリユーザーが適切なアプリストアへ誘導されるように設定されます。
   * AndroidまたはiOSのいずれか一方のアプリのみを選択した場合、iOS／Android、新規／既存を問わず、すべてのユーザーが指定された1つの遷移先へ誘導されます。
   * Google Playに掲載されていないAndroidアプリを選択した場合は、Androidユーザーのリダイレクト先URLを入力する必要があります。
   * （任意）アプリをGoogle Play以外のストアにも掲載している場合は、［**サードパーティアプリストアにリダイレクト**］を設定します。他のストアのアプリが、OneLinkテンプレートで選択したAndroidアプリと同じパッケージ名を使用していることを確認してください。
   * （任意）［**別のURLに変更**］：新規ユーザーをアプリストアへ直接誘導する代わりに、モバイルWebへ誘導したい場合があります。また、アプリがストアに掲載されていない場合もあります。この場合は、URLフィールドにリダイレクト先のURLを入力します。**注意**：サードパーティアプリストアへのリダイレクトと別のURLの両方を設定した場合、デフォルトではサードパーティアプリストアへリダイレクトされます。
   * （任意）［**プライベートリレーを使用しているユーザーにApp Clipを表示**］を有効にします（iOS 14以降で利用可能）。 <Anchor target="_blank" href="/marketers/ja/docs/apple-app-clips-integration-guide">App Clipsの詳細はこちら</Anchor>。
8. ［**アプリがインストールされている場合**］の設定はスキップします。この設定については、[次の手順](/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users)で説明します。
9. （任意）［**デスクトップでリンクがクリックされた場合**］の遷移先を変更します。0>  
   * 特にリンクをメールやソーシャルメディアで送信する場合、デスクトップPCでリンクがクリックされることがあります。デスクトップからのアクセスが多いと予想される場合は、適切なアプリストアへ誘導する代わりに、ランディングページ、Webサイトのホームページ、または携帯電話へのSMSリンク送信をリクエストできるページへ誘導することもできます。
   * デフォルトでは、テンプレートに設定されたアプリに応じて、デスクトップユーザーはWeb版のApp StoreまたはGoogle Playストアへ誘導されます。
     * デフォルトのストアを変更するには、［デスクトップWeb URL］を選択し、該当するWebストアのURLを追加します。ストアのドメインをリダイレクト許可リストに追加してください。
10. （任意）［**他のプラットフォームのアプリを選択**］  
    以下のプラットフォーム専用のアプリがある場合に設定します。
    * **Windows phone**：トグルを有効にしてアプリを選択するか、［**別のURLに変更**］を選択します。
    * **iPad**：トグルを有効にしてiPadアプリを選択します。
    * **Amazon Kindle Fire**：トグルを有効にして、AmazonストアのASINまたはアプリページのURLを追加します。
11. ［**OneLinkテンプレートを保存**］をクリックします（既存のテンプレートを編集した場合は［OneLinkテンプレートを更新］）。   
    OneLinkテンプレートが作成されました。このテンプレートから、ユーザーがクリックできるさまざまなリンクを作成できます（<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLinkリンクとユーザー体験</Anchor>を参照）。

</Accordion>

<div id="add-redirection-logic-for-existing-app-users" />

<Accordion title="既存アプリユーザー向けのリダイレクト設定の追加">

アプリをインストール済みのユーザーは通常、アプリストアやWebページではなく、アプリが直接開くことを期待します。クリック後にアプリを直接開く方法として、次の3つの技術を利用できます。

* **iOS Universal Links**：iOS 9以降に対応し、アプリをスムーズかつ安全に開けます。
* **Android App Links**：Android 6以降に対応し、アプリをスムーズかつ安全に開けます。**注意**：Samsung Internet Browserでは、Android App Linksを使用してアプリを開くことはできません。
* **URIスキーム**：  
  * 代替手段としての利用：
    * Android：Android App Linksが動作しない、または未設定のためアプリを開けない場合に、URIスキームを有効な代替手段として利用できます。
    * iOS：Universal Linksが動作しない、または未設定のためアプリを開けない場合、代替手段として利用できる範囲は限定的です。<Anchor target="_blank" href="/marketers/ja/docs/uri-scheme-fallback-for-ios">詳細はこちら</Anchor>
  * Samsungデバイスでは、アプリを開くための主な方法です。
  * アプリがインストールされている場合に、アクセスするとアプリが開くアドレスです。 Webサイトのリンクに似ていますが、Webサイトではなくアプリを開きます。
  * iOSとAndroidで同じ値にする必要があります。

ユーザー体験、セキュリティ、対応デバイスの範囲を最適化するため、できるだけ多くの技術を有効にすることをおすすめします。 すべてのリンク技術を有効にすると、OneLinkがユーザーごとに最適な方法を自動的に適用します。

**OneLinkテンプレートに既存アプリユーザー向けのリダイレクト設定を追加するには：**

1. AppsFlyerのサイドメニューから、［**Engage**］>［**OneLink管理**］を選択します。
2. 編集するOneLinkテンプレートを選択します。
3. メニューアイコン（⋮）をクリックし、［**OneLinkテンプレートを編集**］をクリックします。
4. ［**アプリがインストールされている場合**］までスクロールします。 [![](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)
5. iOS、Android、代替手段のそれぞれについて、以下の手順に従って設定します。

   <Tabs>
   <Tab title="iOS Universal Links">

   Universal Linksは通常のWebリンクと同じ形式（例：https://yourbrand.onelink.meまたはhttps://www.yourbrand.com）を使用するため、サブドメインの設定が必要です（[前のガイド](/docs/create-a-onelink-template#onelinkテンプレートの作成)で説明しています）。 OneLinkは独自の<Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain">ブランドドメイン</Anchor>にも対応していますが、このガイドの手順を完了するうえで設定は必須ではありません。

   **Universal Linksを使用してアプリを開くには**：

   1. iOS開発者に、次の対応を依頼します。
      * このOneLinkテンプレートのサブドメインを伝えます。
      * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">こちらの手順</Anchor>に従って作業するよう依頼します。
      * 開発者からTeam ID（Apple App ID Prefixとも呼ばれます。例：PF23MIWNTW）を受け取ります。
      * アプリが未公開の場合は、Bundle Identifier（例：com.myapp.something）も開発者から受け取る必要があります。  
        [![](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)
   2. OneLinkテンプレートのページで、［**Universal Linksを使用してアプリを開く設定に変更**］をクリックします。
   3. 開いたウィンドウで、［**Universal Linksを使用してアプリを開く**］を選択します。
   4. ［**Team ID**］フィールドに、開発者から受け取ったTeam IDを入力します。
   5. アプリが未公開の場合は、［**Bundle Identifier**］も入力します。
   6. ［**変更を保存**］をクリックします。

   </Tab>

   <Tab title="Android App Links">

   App Linksは通常のWebリンクと同じ形式（例：https://yourbrand.onelink.meまたはhttps://www.yourbrand.com）を使用するため、サブドメインの設定が必要です（[前のガイド](/docs/create-a-onelink-template#onelinkテンプレートの作成)で説明しています）。 OneLinkは独自の<Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain">ブランドドメイン</Anchor>にも対応していますが、このガイドの手順を完了するうえで設定は必須ではありません。

   **作業を始める前に**：

   このOneLinkテンプレートで選択したサブドメインを控えておきます。

   **Android App Linksを使用してアプリを開くには**：

   1. Android開発者に連絡します。  
      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#generating-a-sha256-fingerprint">こちらの手順</Anchor>に従ってSHA256フィンガープリントを生成するよう依頼します。  
      開発者からSHA256フィンガープリントを受け取ります。例：`DC:65:43:67:F3:BD:02:52:AC:B4:50:F1:74:54: 23:49:4D:49:6C:E6:DF:56:BD:CB:53:06:11:5B:C9:4E:5D:0C`
   2. OneLinkテンプレートのページで、［**App Linksを使用してアプリを開く設定に変更**］をクリックします。
   3. 開いたウィンドウで、［**App Linksを使用してアプリを開く**］を選択します。
   4. ［**SHA256フィンガープリント**］フィールドに、開発者から受け取ったSHA256フィンガープリントを入力します。  
      intent-filterのコードが自動生成され、表示されます。
   5. Android開発者に連絡します。  
      自動生成されたintent-filterのコードを渡します。  
      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">こちらの手順</Anchor>に従って作業し、完了したら連絡するよう依頼します。

   </Tab>

   <Tab title="URIスキーム">

   URIスキームは主にiOS／Androidユーザー向けの代替手段として使用するため、両方で同じ値にする必要があります。

   **AndroidとiOSでURIスキームによる代替手段を設定するには：**

   1. iOSとAndroidの両方の開発者に連絡し、使用するURIスキームを決めます。例：`feedmeapp://`

      <div id="h_01H9Q4E7VR4CAK0PJY269GQ9XJ" />

      > 👍 **ヒント**
      >
      > * AppleもGoogleも、アプリのスキーム名が一意であることを必須としていません。 他のアプリとスキームが競合しないよう、**自社ブランド固有のスキーム名を選択してください**。スキーム名には、例えば**com.company.app**のような、アプリのバンドルIDを使用するとよいでしょう。
      > * OneLinkをiOSとAndroidの両方で機能させるには、**両プラットフォームで同じスキームを定義する**ことが重要です。 <Anchor target="_blank" href="https://help.contrast.co/hc/en-us/articles/200865293-URL-Scheme-Intro-for-App-Developers">iOS</Anchor>と<Anchor target="_blank" href="https://developer.android.com/training/app-links/deep-linking.html">Android</Anchor>の設定手順を参照してください。
      > * URIスキームの先頭にはhttpやhttpsを使用しないでください。

   2. iOS開発者に、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-uri-scheme">こちらの手順</Anchor>に従ってアプリにURIスキームを実装するよう依頼します。  
      **さらに**  
      Android開発者にも、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#procedures-for-uri-scheme">こちらの手順</Anchor>に従ってアプリにURIスキームを実装するよう依頼します。
   3. 作業が完了したら、実装されたURIスキームの値を開発者に確認します。値は、`exampleapp://`、`exampleapp://home`、`exampleapp://main`などの形式になります。
   4. OneLinkテンプレートのページで、［**アプリを開くためのURIスキームを追加**］をクリックします。
   5. ［**URIスキームを使用してアプリを開く**］を選択します。
   6. URIスキームの値を入力します。
   7. ［**変更を保存**］をクリックします。
   8. URIスキームをテストします（担当者または開発者が実施できます）。
      1. アプリがインストールされているiOSデバイスとAndroidデバイスの両方で、<Anchor target="_blank" href="https://halgatewood.com/deeplink/">こちらの無料公開テストツール</Anchor>を開きます。
      2. ツールで生成されたリンクをタップします。  
         URIスキームが正しければ、アプリが開きます。

   </Tab>
   </Tabs>

6. ［**OneLinkテンプレートを更新**］をクリックします。

> 📘 **注意**
>
> * OneLinkテンプレートを保存または更新すると、AppsFlyerはアプリのドメインを検証するためのAASAファイルやDigital Asset LinksのJSONファイルを自動生成し、ホストします。これらのファイルは、Universal LinksとApp Linksが正常に機能するために不可欠です。
> * OneLinkテンプレートの更新が反映されるまでに、最大1時間かかる場合があります。

</Accordion>

<div id="customize-qr-codes" />

<Accordion title="QRコードのカスタマイズ">

![OnelinkQRFinal__1_.gif](https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif)

OneLinkで生成したQRコードには、次のカスタマイズが可能です。

* QRコードへのロゴの追加
* QRコードの色の変更

**注意**：QRコードのカスタマイズは個々のリンク単位ではなく、テンプレート単位で行います。そのため、変更は編集したテンプレートに基づくすべてのQRコードに適用されます。

**QRコードをカスタマイズするには**：

1. AppsFlyerのサイドメニューから、［**Engage**］>［**OneLinkカスタムリンク**］を選択します。
2. 編集するテンプレートの［**アクション**］アイコンにカーソルを合わせ、［**QRコードをカスタマイズ**］をクリックします。  
   QRコードエディターが開きます。
3. ロゴがホストされているURLを入力します。例：https://yourbrand.com/logo.png。  
   ロゴの要件：

   * PNG形式またはJPG形式
   * 背景が透明な正方形または円形
   * 最小サイズ：400×400ピクセル
   * 印刷する場合は、最大解像度の画像を使用
4. QRコードの色を設定します。
5. ［**保存**］をクリックします。

</Accordion>

<div id="h_favicon" />

<Accordion title="リンクプレビュー用のファビコンの設定">

ファビコンは、ソーシャルメディアやメッセージアプリでリンクを共有したときに、リンクのタイトルの横に表示される小さなアイコンです。独自のアイコンを追加して、表示をカスタマイズできます。この設定は、このテンプレートに基づくすべてのリンクに適用されます。カスタムのソーシャルメディアプレビューを設定してリンクを共有すると、対応するプラットフォームに表示されます。

> 📘 **注意**
>
> このファビコンは、対応するプラットフォームのリンクプレビューにのみ表示されます。また、リンク単位で［**カスタムプレビュー（画像とタグ）**］を設定している必要があります。<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags">詳細はこちら</Anchor>

**OneLinkテンプレートにファビコンを設定するには：**

1. AppsFlyerのサイドメニューから、［**Engage**］>［**OneLink管理**］を選択します。
2. 編集するOneLinkテンプレートを選択します。
3. メニューアイコン（⋮）をクリックし、［**OneLinkテンプレートを編集**］をクリックします。
4. ［**ファビコン**］セクションまでスクロールします。
5. ［**ファビコン画像のURL**］フィールドに、ファビコン画像のURLを入力します。
   * 対応形式：ICO
   * 推奨アイコンサイズ：32×32または64×64ピクセル
   * ファイルサイズは100KB以下にしてください。
   * URLは一般公開されている必要があります。
6. ［**プレビュー**］でアイコンが正しく表示されることを確認します。
7. ［**OneLinkテンプレートを更新**］をクリックします。

</Accordion>

## 特性と制限事項

<div id="key-traits-and-limitations" />

<Accordion title="主な特性と制限事項">

| 項目 | 説明 |
| --- | --- |
| 代理店 | 代理店はOneLinkテンプレートやリンクを作成できません。 |
| OneLinkテンプレートの追加・編集 | アカウントユーザーがOneLinkテンプレートを追加・編集するには、<Anchor target="_blank" href="/marketers/ja/docs/user-management">権限</Anchor>が必要です。 |
| OneLinkテンプレート | 1アカウントあたり最大600個のOneLinkテンプレートを作成できます。 |
| デスクトップ | OneLinkのURLまたはテンプレートで、デスクトップユーザーを別のURLへリダイレクトするよう設定すると、そのWeb URLがリンクの`af_web_dp`パラメータに追加されます。リンクに`af_web_dp`が含まれている場合、AppsFlyerはデスクトップからのクリックを記録しません。 |
| サードパーティアプリストアへのリダイレクト | OneLinkテンプレートに複数のアプリストアを設定できるのは、すべてのストアでアプリのパッケージ名が同じ場合のみです。 OneLinkによるサードパーティAndroidアプリストアへのリダイレクトの詳細は、<Anchor target="_blank" href="/marketers/ja/docs/bulletin-onelink-redirection-to-third-party-android-app-stores?query=3rd%20party%20store">こちら</Anchor>を参照してください。<br /><br />**注意**：<ul><li>Huaweiなどのサードパーティストアでは、異なるパッケージ名が必要な場合があります。この場合、複数のアプリストアに同じOneLinkテンプレートを使用することはできません。</li><li>一部のXiaomiデバイスには、Google Playと同じURIスキームを使用するGetAppsストアが搭載されています。そのため、これらのデバイスのユーザーをGoogle Playへ誘導しようとしても、アプリがXiaomiのストアにない場合、リンクはGetAppsへリダイレクトされます。</li><li>パッケージ名が同じでもチャネルが異なる場合、リダイレクトは機能しますが、アトリビューションは行われません。</li><li>サードパーティアプリストアのアトリビューションとデータの詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution">こちら</Anchor>を参照してください。</li></ul> |
| テンプレートの更新 | <ul><li>OneLinkテンプレートの設定変更が反映されるまでに、最大1時間かかります。</li><li>関連付けられたアプリがアカウントから削除されている場合、OneLinkテンプレートは編集できません。この場合は、次のいずれかの対応が可能です。<ul><li>新しいテンプレートを作成します。</li><li>AppsFlyerのカスタマーサクセスマネージャーに連絡するか、hello@appsflyer.com宛てにメールで、削除されたアプリの復元を依頼します。</li></ul></li></ul> |
| URIスキーム | <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#chrome-browser-on-ios">こちら</Anchor>を参照してください。 |

</Accordion>

OneLinkテンプレートに関するご質問はありますか？<Anchor target="_blank" href="/marketers/ja/docs/onelink-troubleshooting-and-faq#onelinkテンプレートに関するよくある質問">よくある質問</Anchor>をご確認ください。

## 次のステップ

手順に従い、テンプレートをもとに<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLinkリンクを作成</Anchor>します。

<div data-zendesk-anchors="onelink-templates=onelink%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88 h_01H9Q4E7VQ0GKZ9HFF88190TYN=onelink%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88 procedures=onelink%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88%E3%81%AE%E4%BD%9C%E6%88%90 h_01H9Q4E7VQYGZ1MH5SS3ZYZF1K=onelink%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88%E3%81%AE%E4%BD%9C%E6%88%90 h_01H9Q4E7VQ648CQ1VJTB1TC571=create-a-onelink-template-with-redirection-logic-for-new-app-users h_01H9Q4E7VQ15AAR1VXNKWR1XGT=%E6%B3%A8%E6%84%8F h_01H9Q4E7VQ4NEWYAD6AMR9YKGY=add-redirection-logic-for-existing-app-users h_01H9Q4E7VR8164HR6MD0EAV2SN=%E6%B3%A8%E6%84%8F-1 h_01H9Q4E7VR0F4B7CTF08YTG715=customize-qr-codes set-a-favicon-for-link-previews=h_favicon h_01KT6GG94CRBYFDWZ28BA8HEYY=%E6%B3%A8%E6%84%8F-2 traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KZX85DYWA1TJ0AS3QV27VPA4=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01H9Q4E7VR2B50EQE31DDG8GNZ=key-traits-and-limitations next-step=%E6%AC%A1%E3%81%AE%E3%82%B9%E3%83%86%E3%83%83%E3%83%97 h_01H9Q4E7VRJK31P9CSGJFCKQQF=%E6%AC%A1%E3%81%AE%E3%82%B9%E3%83%86%E3%83%83%E3%83%97" />
