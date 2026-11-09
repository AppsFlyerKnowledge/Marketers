---
title: OneLinkのトラブルシューティングとよくある質問
metadata:
  keywords:
    - faq
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2020-10-27T11:26:30Z'
  edited_at: '2026-10-28T09:18:46Z'
  id: 360014821438
  locale: ja
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ja/articles/360014821438
---
> **At a glance:** OneLinkカスタムリンクのリダイレクトや動作に関する問題を、すばやくテスト・デバッグするための解決策を確認できます。

<div id="onelink-troubleshooting-guide" />

## OneLinkトラブルシューティングガイド

<div id="onelink-frequently-asked-questions" />

## OneLinkに関するよくある質問

<div id="onelink-template-faq" />

### OneLinkテンプレートに関するよくある質問

<Accordion title="アプリを開くには、Universal Links、App Links、URIスキームのどれを使用すればよいですか？">

**Universal Links：** iOSユーザーの98%以上で必要です。

**App Links：** Android 6.0以降のユーザー向けです。**注意**：Samsung OSでは、Android App Linksを使ってアプリを開くことはできません。

> 📘 **Note**
>
> Universal LinksとApp Linksはいずれも、クリックされたURLのドメイン（OneLinkカスタムリンクのドメインまたはブランドドメイン）が、開こうとしている特定のアプリに所有・関連付けられていることを証明する必要があります。このドメインとアプリの関連付けは、iOSでは**Apple App Site Association（AASA）ファイル**、Androidでは**Assetlinks**ファイルを使用して行います。
>
> これらのファイルは、AppsFlyerまたは広告主のWebサイトのいずれかでホストされます。デフォルトでは、OneLinkテンプレートを作成してUniversal LinksとApp Linksを設定すると、これらのファイルはAppsFlyerによって生成・ホストされます。

**URIスキーム：** Samsungデバイスでアプリを開くための主要な方法です。それ以外では、従来方式およびフォールバックとして使用するアプリ起動方法です。以下の場合に使用できます。

* Android 6.0より前のバージョンを使用しているユーザー（Androidユーザーの15%未満）
* Universal LinksやApp Linksが機能しない、または設定されていないためにアプリを開けない場合のフォールバック<strong>注意：</strong>Universal LinksのフォールバックとしてURIスキームを使用する場合、iOS固有の制限があります。<Anchor target="_blank" href="/marketers/ja/docs/uri-scheme-fallback-for-ios">詳細はこちら</Anchor>。

<div id="deep-linking" />

#### ディープリンク

Universal Links、App Links、URIスキームは、アプリを**開く**ための安全な方法です。ユーザーをディープリンクしてアプリ内の特定のアクティビティやページへ遷移させるには、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">OneLinkのディープリンク設定手順</Anchor>に従ってください。

</Accordion>

<Accordion title="URIスキームでアプリを開けるOSはどれですか？">

| OS | URIスキームでアプリを開けますか？ |
| --- | --- |
| iOS | **はい。** Universal Linksが機能しない場合のフォールバックとして使用します。<br /><br />**重要な注意事項：**<ul><li>URIスキームをフォールバックとして使用する場合、iOS固有の制限があります。</li><li>Safariを含む多くのブラウザでは、URIスキームをフォールバックとして使用するために、URLへ`af_force_deeplink=true`パラメータを追加する必要があります。<Anchor target="_blank" href="/marketers/ja/docs/uri-scheme-fallback-for-ios">詳細はこちら</Anchor>。</li><li>「問題が発生しました。アプリケーションを開けませんでした。」というエラーメッセージが表示される場合、通常はアプリがインストールされていないか、誤ったURIスキームが使用されています。</li></ul> |
| Android | **はい。** Samsungデバイス、Android 6.0より前のバージョン、およびそれ以降のAndroidでApp Linksが機能しない場合のフォールバックとして使用します。 |
| Amazon | **いいえ** |
| Windows Mobile | **いいえ** |

</Accordion>

<Accordion title="iOS Universal LinksやAndroid App Linksを設定した後、アプリをアップデートする必要がありますか？">

<strong>はい。</strong>既存ユーザーがアプリを開くためにUniversal LinksまたはApp Linksを実装すると、iOSのAssociated DomainsまたはAndroidManifest.xmlが更新されます。そのため、該当するアプリストアへ新しいバージョンのアプリをアップロードする必要があります。**ヒント：** アプリのアップデート回数を最小限に抑えるため、<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">アプリを開く</Anchor>ための設定と<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">ディープリンク</Anchor>に必要な開発作業を、できるだけ一度にまとめて行ってください。

</Accordion>

<Accordion title="既存ユーザーをアプリではなくWebページへリダイレクトできますか？">

<strong>はい。</strong>ただし、テンプレートをそのように設定すると、新規・既存を問わずすべてのユーザーに適用され、全員がランディングページ／Web URLへ遷移します。つまり、新規ユーザーもアプリストアには送られません。

ユーザーをWebページへ送るには：

1. テンプレートでUniversal Links、App Links、URIスキームを設定しないでください。
2. アプリがインストールされていない場合のリダイレクト先として、ランディングページ／Web URLを設定します。
   * ランディングページ／Web URLは、af\_android\_urlおよびaf\_ios\_urlパラメータの値として追加されます。
   * リダイレクト先として使用するURLが、<Anchor target="_blank" href="/marketers/ja/docs/set-up-your-domain-redirect-allowlist">ドメインリダイレクト許可リスト</Anchor>に追加されていることを確認してください。
   * このリダイレクトは、アプリがインストールされている場合（既存ユーザー）にも自動的に適用されます。

**注意**：既存ユーザーをアプリ起動後にのみモバイルWebページへリダイレクトしたい場合は、アプリ開発者側でその動作を実装する必要があります。

</Accordion>

<Accordion title="タブレットユーザーを、モバイルユーザーとは別のアプリやURLへリダイレクトできますか？">

以下については、個別のリダイレクト先を設定できます。

* Windows Phone
* iPad
* Amazon Kindle Fire

その他のタブレットでは、現時点で個別のリダイレクト設定はサポートされていません。

</Accordion>

<Accordion title="1つのアプリを複数のOneLinkテンプレートに割り当てることはできますか？">

**はい。** 1つのOneLinkテンプレートから無制限にOneLink URLを作成できますが、場合によっては1つのアプリを複数のOneLinkテンプレートに割り当てる必要があります。たとえば、ストア外市場向けにAndroidアプリの複数バージョンがある場合、各Androidバージョンごとに個別のOneLinkテンプレートを用意し、同じiOSアプリをすべてのテンプレートへ割り当てることがあります。

**重要**：

iOS Universal LinksとAndroid App Linksを使ってアプリを開くテンプレートで、**テンプレートごとに異なるサブドメインを使用する場合**は、それぞれに合わせてiOS／Androidアプリの設定と更新が必要です。

* **iOS Universal Links：** 新しいOneLinkテンプレートを作成し、アプリ内のAssociated Domainを更新した後、新しいバージョンをApp Storeへ申請します。新しいテンプレートで作成されたOneLink URLを利用できるのは、新しいバージョンへ更新したiOSユーザーのみです。
* **Android App Links：**
  1. 新しいOneLinkテンプレートを作成した後、App Linkセクション下部のXMLスニペットをコピーし、既存のintentに加えて、ディープリンク先として使用するintent内の**AndroidManifest.xml**ファイルへ追加します。
  2. 新しいバージョンをストアへリリースします。新しいテンプレートで作成されたOneLink URLを利用できるのは、新しいバージョンへ更新したAndroidユーザーのみです。

</Accordion>

<Accordion title="OneLinkテンプレートを削除できますか？">

はい。

**テンプレートを削除するには：**

1. AppsFlyerでOneLink管理ページを開きます。
2. 対象のOneLinkテンプレートを選択します。
3. 三点リーダーメニューから［テンプレートを編集］をクリックします。

   <Image align="center" alt="delete template.png" src="https://files.readme.io/72b68cb979e2360f4e3065f99fbb547a91713a40dcc9adee59028ed2945f794a-31094482204945.png" width="1204px" />
4. ゴミ箱アイコンをクリックします。

**注意：** 削除したテンプレートをもとに作成された既存のOneLink URLがある場合、<strong>そのリンクはアプリストアへユーザーを誘導する用途でも機能しなくなります。</strong>そのため、テンプレートを削除する前に、そのテンプレートを使用しているOneLink URLが存在しないことを必ず確認してください。また、テンプレートを削除せず、既存テンプレートの設定変更で必要な結果を実現できないか検討することもおすすめします。

</Accordion>

<Accordion title="OneLinkテンプレートのサブドメインを変更できますか？">

**はい。AppsFlyer上で、そのテンプレートをもとに作成された既存のカスタムリンクがない場合に限り変更できます。**

OneLinkテンプレートをもとに作成されたカスタムリンクがすでにAppsFlyerに存在する場合、サブドメインは変更できません。この制限は、公開中のリンクのリダイレクト／ディープリンク動作が壊れるのを防ぐためのものです。

既存のカスタムリンクがあるテンプレートでサブドメインを変更する必要がある場合は、次のいずれかを行います。

* 新しいサブドメインでOneLinkテンプレートを新規作成し、そのテンプレートをもとにリンクを作成する。
* サブドメインを変更したいテンプレートをもとに作成された既存のカスタムリンクをすべて削除する。そのテンプレートをもとにしたリンクをすべて削除すると、サブドメインを編集できるようになります。

</Accordion>

<Accordion title="OneLinkテンプレートのドメイン／サブドメインを、別のテンプレートIDへ適用できますか？">

<strong>いいえ。</strong>特定のテンプレートとテンプレートIDに設定されたサブドメイン／ドメインを、別のテンプレートIDへ手動で組み合わせると、Universal LinksやApp Linksが機能しなくなり、セキュリティ上のリスクも生じます。

**例：**

* テンプレート1ABCには、サブドメイン**bank.onelink.me**が設定されています。
* テンプレートD123には、サブドメイン**game.onelink.me**が設定されています。
* リンク**bank.onelink.me/1ABC/shorturl**はテンプレート1ABCをもとに作成されており、正常に機能します。
* リンク**game.onelink.me/D123/exampleurl**はテンプレートD123をもとに作成されており、正常に機能します。
* リンク**game.onelink.me/1ABC/shorturl**は機能しません。
* **リンク bank.onelink.me/D123/exampleurl**は機能しません。

</Accordion>

<Accordion title="複数のテンプレートで同じサブドメインを使用できますか？">

<strong>はい。</strong>ただし、そのサブドメインを使用するテンプレートはそれぞれ個別に作成してください。テンプレートIDへサブドメインを手動で追加するだけでは機能しません。

</Accordion>

<Accordion title="デスクトップユーザーをリダイレクトするにはどうすればよいですか？">

デスクトップユーザーも、たとえばメールキャンペーンなどからOneLinkカスタムリンクを利用できます。ただし、デスクトップユーザーがこれらのリンクをクリックしても、モバイルサイト、アプリストア、アプリへ直接リダイレクトすることはできません。デフォルトでは、デスクトップユーザーはApp StoreまたはGoogle PlayストアのWeb版へリダイレクトされます。

**では、デスクトップユーザーにも良好なユーザー体験を提供し、モバイルユーザーへ転換するにはどうすればよいでしょうか？**

OneLink URLまたはテンプレートで、デスクトップユーザー（WindowsまたはMac）を別のURLへリダイレクトできます。このWeb URLは、リンクの`af_web_dp`パラメータに追加されます。リダイレクト先として使用するすべてのURLが、ドメインの<Anchor target="_blank" href="/marketers/ja/docs/set-up-your-domain-redirect-allowlist">リダイレクト許可リスト</Anchor>に追加されていることを確認してください。追加されていない場合、リダイレクトは機能しません。

**注意：** リンクに`af_web_dp`が含まれている場合、デスクトップからのクリックはAppsFlyerで記録されません。

> 👍 **Tip**
>
> デスクトップユーザーを、専用のWebフォームを含むWeb URLへリダイレクトする方法もあります。そのフォームからSMSまたはメールで、デスクトップユーザーのモバイル端末へOneLink URLを送信できます。この方法について詳しくは、OneLink Smart Scriptソリューションを参照してください。

</Accordion>

<Accordion title="Chrome OSユーザーをリダイレクトするにはどうすればよいですか？">

Chromebook上のアプリはAndroidアプリとして扱われます。

Chromebookで、アプリをインストールしていない新規ユーザーを別のWeb URLへリダイレクトするには：

1. OneLinkテンプレート設定で、［**リンクの動作を設定**］>［**アプリがインストールされていない場合**］>［**Android**］の順に進み、［**別のURLに変更**］をクリックします。  
   または  
   OneLinkリンク設定で、［**ディープリンクとリダイレクト**］>［**リダイレクト**］>［**アプリがインストールされていない場合**］>［**Android**］の順に進み、［**Web URL**］を選択します。
2. URLを入力します。  
   リンク設定から追加した場合、そのURLはリンクの`af_android_url`パラメータに追加されます。

</Accordion>

<Accordion title="デスクトップでOneLinkをクリックした場合、どのアプリのクリックとして記録されますか？">

OneLinkテンプレートには、iOSアプリとAndroidアプリを1つずつ、計2つのアプリを関連付けることができます。モバイル端末でOneLinkリンクがクリックされた場合、その端末のプラットフォームに一致するアプリのクリックとして記録されます。 iOS端末でのクリックはiOSアプリ、Android端末でのクリックはAndroidアプリのクリックとして記録されます。

デスクトップでOneLinkリンクがクリックされた場合、照合できる端末プラットフォームがありません。この場合、クリックは次のように記録されます。

* テンプレートにiOSアプリとAndroidアプリの両方が関連付けられている場合、iOSアプリのクリックとして記録されます。
* テンプレートに1つのアプリのみ関連付けられている場合、そのアプリのクリックとして記録されます。

</Accordion>

<div id="onelink-link-faq" />

### OneLinkリンクに関するよくある質問

<Accordion title="AppsFlyer SDKがなくてもOneLinkは機能しますか？">

**はい。ただし、一部の機能に限られます。**

モバイルWebサイトの訪問者をすぐにアプリユーザーへ転換したいものの、AppsFlyer SDKをまだ連携できない場合でも対応可能です。

AppsFlyer SDKがまだアプリに組み込まれていなくても、基本的なユーザーのリダイレクトとアプリ起動は機能します。 Smart BannersもSDKを必要とせず、SDKなしで利用できます。

ただし、SDKがない場合は次の制限があります。

* リンクをクリックしたユーザーを、アプリ起動後に特定のコンテンツへディープリンクできません。
* アトリビューションデータが記録されません。
* アプリ内イベントが記録されません。

</Accordion>

<Accordion title="OneLinkカスタムリンクには、どのような作成方法がありますか？">

以下の表で、OneLinkカスタムリンクの各作成方法を比較します。

| リンク作成方法 | 用途 | 短縮URL／ロングURL | プレミアム機能 | 管理画面に表示されるか | アトリビューションTTL（有効期間）の最大値／デフォルト値 |
| --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">AppsFlyer管理画面</Anchor> | OneLinkテンプレートとカスタムリンクの作成 | 両方 | -- | ✓ | TTLなし |
| <Anchor target="_blank" href="/marketers/ja/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> | 数千件のOneLinkをすばやく作成 | 短縮 | ✓ | -- | 31日 |
| <Anchor target="_blank" href="/marketers/ja/docs/perform-onelink-bulk-actions-via-csv">OneLink一括リンク作成</Anchor> | CSVで定義したパラメータを使用して、数千件のOneLink短縮URLをすばやく作成 | 短縮 | -- | -- | 365日 |
| <Anchor target="_blank" href="/marketers/ja/docs/user-invite-attribution">SDK</Anchor> | ユーザー招待（リファラル）キャンペーン | 短縮 | -- | -- | 60日 |
| <Anchor target="_blank" href="/marketers/ja/docs/onelink-smart-script-overview">OneLink Smart Script</Anchor> | モバイルWeb-to-appキャンペーン | ロング | -- | -- | TTLなし |
| <Anchor target="_blank" href="/marketers/ja/docs/understand-onelink-short-vs-long-urls">スプレッドシート</Anchor> | 独自の数式を使用して数千件のOneLinkカスタムリンクを作成 | ロング | -- | -- | TTLなし |

</Accordion>

<Accordion title="OneLink管理ページからOneLink URLを削除するとどうなりますか？">

2025年11月以降、

* OneLink管理セクションからリンクを削除すると、そのリンクは一覧とデータベースの両方から削除されます。その後エンドユーザーがリンクを見つけてクリックした場合、OneLinkテンプレートの設定に基づいてリダイレクトされます。アトリビューションパラメータ、ディープリンクパラメータ、リンク単位のリダイレクト設定は適用されません。
* リンクは削除後2分以内に機能しなくなります。
* 2025年11月5日以降に管理画面から削除したリンクは、OneLink管理内の**削除済みリンク**一覧から復元できます。

  <Image align="center" alt="deleted links.png" src="https://files.readme.io/d5a2cc7047fda06ba8249cc00b2830c309ec6137f10306cdabca61bcfe3d4d15-small-41829768141713.png" width="2768px" />
* リンクは削除日から90日以内であれば復元できます。削除日から90日を超えたリンクは復元できません。

</Accordion>

<Accordion title="OneLinkカスタムリンクからブラウザ経由でアプリを開けますか？">

<strong>はい。</strong>ただし、Universal LinksとApp Linksは、リンクが実際にクリックされた場合（Webページやメール内のリンクをクリックする場合など）にのみ機能します。<strong>ブラウザのアドレスバーへリンクを貼り付けても、アプリは起動しません。</strong>リンクをテストするときは、ブラウザのURL欄へ貼り付けるのではなく、URLをクリックしてください。

</Accordion>

<Accordion title="OneLink URLでアプリが開かない、または既存ユーザーがディープリンクされないのはなぜですか？">

適切に設定していても、OneLink URLが意図したとおりにディープリンクしない場合があります。その場合、アプリが開いたりアプリ内の特定の画面へディープリンクしたりする代わりに、ユーザーがアプリストアやエラーページへリダイレクトされます。

考えられる主な原因は以下のとおりです。

* **ホストアプリ：** WhatsApp、Gmail、WeChatなど、アトリビューションリンクが共有されるアプリは、独自のアプリ内ブラウザなど、それぞれ異なる方法でクリックされたリンクを開きます。これらの中には、すべてのアトリビューションリンクをブロックすることが知られているものもあります。
* **ブラウザ：** ブラウザやOSプラットフォームによって、リンクの動作が異なる場合があります。たとえば一部のブラウザでは、リンクを貼り付けるだけでは機能しません。リンクを実際にクリックする必要があります。
* **OSアップデート：** iOS／Androidの新しいOSアップデートにより、ディープリンクを妨げる予期しない不具合が発生する場合があります。
* **デバイス：** スマートフォン、タブレット、ノートPCなどのデバイスや、iOS、Android、Windows MobileなどのOSバージョンによって、アトリビューションリンクの処理方法が大きく異なる場合があります。
* **設定ミス：** ディープリンク値に<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#traits-and-limitations">特殊文字</Anchor>を使用すると、リンクが正しく機能しません。

ユーザー体験を改善する方法として、フォールバックURLと強制ディープリンクの2つがあります。

<div id="fallback-urls" />

#### フォールバックURL

フォールバックURLを設定すると、アプリ起動やディープリンクが何らかの理由で失敗した場合に、ユーザーを指定したWebページへ送ることができます。**注意：** この設定を使用すると、アプリをインストールしていないユーザーも、適切なアプリストアではなくフォールバックURLへ送られます。そのため、このオプションはアプリをすでにインストールしているユーザーへのリターゲティング時にのみ使用してください。

フォールバックURLを設定するには、OneLinkテンプレートまたはカスタムリンク設定で、アプリがインストールされていない場合のリンク動作を「別のURLへリダイレクト」に設定します。

<Image align="center" alt="different_url.png" src="https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png" />

この設定を使用すると、フォールバック先のパラメータとして`af_ios_url`と`af_android_url`が追加されます。iOSユーザーは`af_ios_url`で指定したページへ、Androidユーザーは`af_android_url`で指定したページへリダイレクトされます。

> 👍 **Tip**
>
> 例として、次のOneLink URLを考えてみます。
>
> このリンクをクリックしたiOS／Androidユーザーは、どちらもアプリ内へディープリンクされる想定です。ただし、ディープリンクに失敗した場合は、次のようにリダイレクトされます。
>
> * iOS：www.yoursite.com/ios-bonus
> * Android：www.yoursite.com/android-bonus

> 📘 **Note**
>
> リダイレクトが発生すると、OneLink URLのパラメータはaf\_ios\_urlまたはaf\_android\_urlで指定した遷移先ページへ引き継がれます。この動作を防ぐには、OneLinkにaf\_param\_forwarding=falseパラメータを追加します。

<div id="forced-deep-linking" />

#### 強制ディープリンク

強制ディープリンクを使用すると、URIスキームをフォールバックとして利用し、アプリを開いてユーザーをディープリンクできます。

この方法は、アプリをインストール済みのほとんどのユーザーで有効です。ただしiOSでは、URIスキームによるアプリ起動に制限があります。そのため、URIスキーム（`af_dp`パラメータ）で指定したアクティビティへ強制的にディープリンクするため、OneLink URLに`af_force_deeplink=true`を追加する必要がある場合があります。 <Anchor target="_blank" href="/marketers/ja/docs/uri-scheme-fallback-for-ios">iOSでURIスキームをフォールバックとして使用する方法</Anchor>について詳しくはこちら。

</Accordion>

<Accordion title="OneLinkはApp Store Connectのイベントに対応していますか？">

はい。 App Store ConnectのイベントにOneLinkを設定できます。リダイレクト、アプリ起動、インストール、リエンゲージメントのアトリビューションは通常どおり機能します。

</Accordion>

<Accordion title="ChromeでOneLink URLを開くと空白ページが表示されるのはなぜですか？">

`<a>` HTMLタグに`target`属性を含めていないことを確認してください。 OneLink URLを`target="_blank"`属性付きの`<a>`タグ内に配置すると、Chrome（iOS／Androidの両方）で空白ページが開き、App StoreやGoogle Playへリダイレクトされません。

</Accordion>

<Accordion title="BraveでOneLinkを使ったリダイレクトはできますか？">

はい。ただしAndroidでは、Braveブラウザ上でOneLinkリンクをクリックした場合、ディファードディープリンクは機能しません。 iOSでは、クリック後に空白画面が表示され、その画面上でスクロールやタップなど何らかの操作をした場合にのみ、ディファードディープリンクが機能します。

</Accordion>

<Accordion title="OneLinkカスタムリンクは、他のリンクより読み込みに時間がかかりますか？">

**いいえ。** OneLinkカスタムリンクは、正常に機能して必要なリダイレクトを行うために、追加の処理時間や読み込み時間を必要としません。他のAppsFlyerリンクと同等の速度で動作します。

</Accordion>

<Accordion title="OneLinkを使用する場合、インストール単価を記録するにはどうすればよいですか？">

［**詳細パラメータ**］の［**インストール単価を有効にする**］をオンにすると、そのリンク経由の各インストールへ特定のCPI値を適用できます。

費用通貨を選択し、CPIを表す**数値のみ**（小数点以下最大4桁）を入力します。これにより、af\_cost\_currencyとaf\_cost\_valueパラメータがリンクへ追加されます。

> 👍 **Tip**
>
> SMSキャンペーンの費用が1,000通あたり20ドル（CPM）だとします。過去の実績からキャンペーンのコンバージョン率が5%である場合、算出されるCPIは0.40ドルです。インストール単価を0.40 USDに設定すると、SMSキャンペーンの最終的なROIを計測できます。

<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview">コストとROIの計測</Anchor>について詳しくはこちら。

</Accordion>

<Accordion title="リダイレクト時にパラメータが引き継がれないようにするにはどうすればよいですか？">

`af_r`、`af_ios_url`、`af_android_url`、`af_web_dp`では、アトリビューションリンクまたはOneLinkのパラメータがリダイレクト先ページへ引き継がれます。この動作を防ぐには、アトリビューションリンクに`af_param_forwarding=false`を追加します。

</Accordion>

<Accordion title="リダイレクト先URLで他のパラメータは保持したまま、AppsFlyerのPIDとCパラメータだけを削除するにはどうすればよいですか？">

場合によっては、1つのURLに複数のPIDが含まれることがあります。これは、AppsFlyerがリダイレクト先URLにPIDとCパラメータを追加する一方で、クライアント側でも独自のPIDパラメータを追加できるためです。たとえば、クライアントのWebサイトURLで「product ID」を「pid」として使用している場合があります。

通常、アトリビューションリンクに`af_param_forwarding=false`を追加すると、すべてのパラメータが削除されます。

ただし、リンクがデスクトップからクリックされる場合、クライアント側では重要なCRMパラメータを残したいことがあります。 AppsFlyerのPIDとCパラメータだけを削除し、その他のパラメータを保持するには、アトリビューションリンクに`af_base_params_forward=false`を追加します。

</Accordion>

<Accordion title="単一プラットフォーム向けのカスタムリンクは現在も利用できますか？">

いいえ。単一プラットフォーム向けのカスタムリンクは現在利用できません。

</Accordion>

<Accordion title="リンク保存後に短縮URL IDを変更できますか？">

<strong>いいえ。</strong>短縮URL IDを設定できるのは、リンク作成時のみです。

</Accordion>

<Accordion title="OneLinkカスタムリンクをラップしたり短縮したりできますか？">

**外部のURL短縮サービスを使用したりOneLinkカスタムリンクをラップしたりすると、Universal LinksやApp Linksによるアプリ起動機能が動作しなくなります。**

Universal LinksやApp Linksを有効にするには、OSがアプリに関連付けられたURLのドメインを認識する必要があります。ユーザーに表示するリンクを外部でラップ、短縮、リダイレクトすると、この認識ができなくなります。これには、bit.ly、AppsFlyer以外のブランドリンク、クリック計測が有効なメールサービスプロバイダー（ESP）の利用も含まれます。

**リダイレクトを正しく機能させたままリンクをラップ／短縮するには：**

* OneLinkカスタムリンクの作成時にAppsFlyerが生成する短縮URLを使用してください（bit.lyなど外部の短縮サービスは使用しないでください）。  
  **ヒント**！リンクに短いブランドドメインを設定すると、URLをさらに短くできます。 AppsFlyer管理画面でリンクを作成する場合は、URL IDをできるだけ短く編集することもできます。例：https://brand.com/a1b2/a （**brand.com**はブランドドメイン、**a1b2**は常に4文字のテンプレートID、**a**は1文字まで短く編集できるURL IDです。   
  メリット：
  * この方法では、OneLinkテンプレートに設定されたOneLinkサブドメインを使用するため、正しく機能します。
  * アトリビューションリンクを配布した後でも、ディープリンク設定を含むパラメータをその場で変更できます。
  * モバイル端末からのクリックはすべてAppsFlyer管理画面でカウントされるため、別のサービスを確認する必要がありません。
  * 短縮URLの末尾部分は、<Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain">ブランドドメイン</Anchor>としてカスタマイズできます。
* Universal LinksやApp Linksが機能しない場合のフォールバックとして<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">URIスキーム</Anchor>を使用し、リンクに`af_force_deeplink=true`パラメータを追加します。
* [ESPを利用する場合の対応方法](/docs/onelink-troubleshooting-and-faq#can-i-use-onelink-custom-links-in-emails)も参照してください。

</Accordion>

<Accordion title="メールでOneLinkカスタムリンクを使用できますか？">

<strong>はい。</strong>ただし、メールサービスプロバイダー（ESP）を利用する場合は、いくつか注意点があります。 ESPはクリックを計測するため、メール内に配置されたすべてのリンクをラップします。これにより、URLをクリックしたユーザーのアプリ起動／ディープリンクのフローが機能しなくなります。

これを防ぐには、次のいずれかの方法を使用します。

* ESPの設定でクリック計測を無効にします。  
  **（ヒント：通常はこの方法が最も簡単です。）**
* アトリビューションリンクに`af_esp=true`フラグを追加し、`af_dp`パラメータで指定したURIスキームを使ってアプリを強制的に開きます。この方法は、アプリをインストール済みのユーザーで有効です。
* Universal Linksによるアプリ起動とディープリンクについて、AppsFlyerのソリューションに対応しているESPを使用します。<Anchor target="_blank" href="/marketers/ja/docs/email-service-provider-esp-integration-guide">詳細はこちら</Anchor>。

</Accordion>

<Accordion title="ユーザーを地域ごとのアプリストアへリダイレクトするにはどうすればよいですか？">

OneLinkはユーザーのIPアドレスに基づいて、適切な地域のアプリストアへリダイレクトします。

</Accordion>

<Accordion title="OneLink URLが指定したドメインへユーザーをリダイレクトしないのはなぜですか？">

AppsFlyerでリダイレクト許可リストを有効にしているか確認してください。有効にしている場合、使用するWeb URLのドメインまたはサブドメインを許可リストへ登録する必要があります。<Anchor target="_blank" href="/marketers/ja/docs/set-up-your-domain-redirect-allowlist">リダイレクト許可リストの詳細はこちら</Anchor>

</Accordion>

<Accordion title="「探しているアプリは利用できません」というエラーが表示されるのはなぜですか？">

Google Playへリダイレクトされず「探しているアプリは利用できません」と表示される場合、次の原因が考えられます。

* アプリが現在Google Playで「保留中」のステータスになっている。上記のエラーメッセージを回避するには、リンクのリダイレクト先をGoogle PlayではなくWeb URLに設定します。アプリが承認されたら、リダイレクト先をGoogle Playへ戻すことができます。これらの設定変更は、<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">リンクのテンプレートページ</Anchor>で行います。
* アプリがサードパーティストアでのみ提供されている場合、AppsFlyerでGoogle Playのステータスが誤って設定されていることが原因の場合があります。この問題を解決するには、SettingsのMy Appsページで<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">Google Playのステータスを「Published out of store」に設定する必要があります</Anchor>。

</Accordion>

<Accordion title="m.onelink.meの短縮リンクが機能しないのはなぜですか？">

2024年6月をもって、旧バージョンの短縮リンク**m.onelink.me**は廃止されました。このサブドメインを引き続き使用しているリンクは、意図した遷移先へリダイレクトされなくなり、想定していたユーザー体験が中断される可能性があります。

</Accordion>

<Accordion title="既存リンクで、ブランドドメインとそのOneLinkサブドメインを手動で切り替えることはできますか？">

はい。ブランドドメインとOneLinkサブドメインが正しくマッピングされている場合に限り可能です。参照：<Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer">AppsFlyerでブランドドメインを設定する</Anchor>

**例**：  
OneLinkサブドメイン：**demo.onelink.me**  
テンプレートID：**A1r4**  
**demo.onelink.me**サブドメインにマッピングされているブランドドメイン：

* **app.simulatorapp.com**
* **click.simulatorapp.com**

OneLink管理画面で次のブランドリンクを作成したとします。  
**app.simulatorapp.com/A1r4/simulationlink**  
上記のブランドリンクは、別のブランドドメインリンクまたはOneLinkサブドメインリンクへ置き換えることができます。  
以下のリンクは機能的に同一で、どの環境でも同じように動作します。

* app.simulatorapp.com/A1r4/simulationlink
* demo.onelink.me/A1r4/simulationlink
* click.simulatorapp.com/A1r4/simulationlink

</Accordion>

<div id="onelink-parameter-faq" />

### OneLinkパラメータに関するよくある質問

<Accordion title="OneLinkカスタムリンクで必須のパラメータは何ですか？">

必須なのはメディアソース（**pid**）パラメータのみです。

</Accordion>

<Accordion title="短縮URLにパラメータを追加できますか？">

<strong>はい。</strong>任意のパラメータを短縮URLに追加できます。

**重要：** 短縮URLに追加したパラメータは、リンク内にすでに設定されているパラメータを上書きしません。

> 👍 **Tip**
>
> * 次のようなOneLinkカスタムリンクを作成したとします。
>   * **ロングURL：** https://onelink-sim.onelink.me/Il2C?pid=training&c=peaches
>   * **短縮URL：** https://onelink-sim.onelink.me/Il2C/70e6d165
> * 短縮URLに次のパラメータを追加します：https://onelink-sim.onelink.me/Il2C/70e6d165?c=bananas&af_adset=fruits
> * 短縮URLに追加した**af\_adset=fruits**パラメータは、アトリビューションに有効です。一方、ロングURLにはすでに**c**パラメータが存在するため、**c=bananas**パラメータは**有効になりません**。

</Accordion>

<Accordion title="カスタムメディアソース名には何を使用できますか？">

オウンドメディアの場合、連携済みパートナーが予約している名称でなければ、カスタムメディアソース名（PID値）は任意に設定できます。競合を避けるため、カスタムメディアソースには\_intサフィックス（例：googleadwords\_int）を使用しないでください。また、カスタムメディアソース名として*organic*を使用するとアトリビューションデータの整合性に影響する可能性があるため、使用しないことを推奨します。

有料メディアでOneLinkを使用する場合：

* OneLinkカスタムリンクのメディアソース値には、連携済みパートナー用に予約された**PID**値（**\_int**で終わる値）を使用します。カスタムメディアソース名として、*googleadwords*や*facebook*などのSRNメディアソースを使用しないでください。使用すると、アトリビューションデータの整合性に影響する可能性があります。
* OneLinkテンプレートに設定されているすべてのアプリで、そのパートナーがAppsFlyerと連携済みかつ有効（［**パートナーを有効化**］トグルがオン）であることを確認してください。

</Accordion>

<Accordion title="OneLinkにはどのアトリビューションパラメータを追加できますか？">

さまざまなアトリビューションパラメータを追加することで、より詳細なドリルダウン分析が可能になります。

| **アトリビューションパラメータ** | **説明** | **リンク上のパラメータ名** |
| --- | --- | --- |
| **キャンペーン** | キャンペーン名を設定し、オウンドメディア内の異なるキャンペーンを比較します。 | c |
| **広告セット** | 広告セット名を設定し、オウンドメディアの特定キャンペーン内で異なる広告セットを比較します。 | af\_adset |
| **広告名** | 広告名を設定し、オウンドメディアの特定の広告セット／キャンペーン内で異なるクリエイティブを比較します。 | af\_ad |
| **チャネル** | オウンドメディアで複数の配信チャネルを比較したい場合は、チャネル名を設定します。<br /><br />例：SMSメッセージを2社のSMSサービスプロバイダーへ振り分ける場合、channelパラメータでプロバイダーを指定します。その後、2社のコンバージョン率を比較できます。 | af\_channel |
| **サブスクライバーパラメータ** | 利用可能な5つのサブスクライバーパラメータのいずれかを使用して、分析に役立つ値を設定できます。<br /><br />**注意：** これらのパラメータは解析され、ローデータレポートに表示されるため、データの集計やフィルタリングに役立ちます。 | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |
| **カスタムパラメータ** | サブスクライバーパラメータと同様に、任意のパラメータ名と値を使用してフィールドを指定できます。任意の名前<br /><br />サブスクライバーパラメータとは異なり、カスタムパラメータはローデータ上で解析されず、ローデータレポートの**original url**列にのみ表示されます。 | カスタム  <br />（任意に指定） |

<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">AppsFlyerのアトリビューションリンク構造とパラメータ</Anchor>について詳しくはこちら。

</Accordion>

<Accordion title="OneLinkカスタムリンクに追加したカスタムパラメータはローデータで確認できますか？">

<strong>はい。</strong>カスタムパラメータはローデータの**original url**列に渡され、そこで確認できます。ローデータ内に個別の列は作成されません。

解析済みデータとして利用する場合は、ローデータレポートに個別の列が用意されているサブスクライバーパラメータ`af_sub1-5`を使用してください。

</Accordion>

<Accordion title="パラメータ名では大文字と小文字が区別されますか？">

<strong>はい。</strong>パラメータ名と値には小文字のみを使用してください。パラメータ名や値に大文字を使用したり、大文字・小文字の表記が統一されていなかったりすると、管理画面とローデータの両方でエラーやデータの不一致が発生する可能性があります。

</Accordion>

<div id="integrated-partner-faq" />

### 連携済みパートナーに関するよくある質問

<Accordion title="ソーシャルアプリの無料投稿でOneLinkを使用できますか？">

ソーシャルアプリの無料投稿では、投稿を目にする潜在ユーザーを端末別に事前ターゲティングできないため、OneLinkを利用したい場合があります。

ただし、iOS Universal Linksの制限や、一部ソーシャルアプリ側の制約により、OneLinkを使った基本的な端末判定、リダイレクト、アトリビューション、ディープリンクは複雑になる場合があります。状況によっては、ユーザーを正しくリダイレクトまたはディープリンクするために、ソーシャルアプリ向けランディングページやURIスキームの設定が必要です。

以下の表は、現在主要なソーシャルアプリでOneLinkを利用できる条件をまとめたものです。

<table><tbody><tr><td>ソーシャルアプリ</td><td>Android：アプリ未インストール</td><td>Android：ディープリンク</td><td>iOS：アプリ未インストール</td><td>iOS：ディープリンク</td></tr><tr><td> <strong>Facebook</strong>（ブースト投稿を含む）</td><td><span>✓\*\*†† </span></td><td><span>✓\*\*††</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Facebook Messenger</strong></td><td><span>✓\*\*†† </span></td><td> <span>✓\*\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Snapchat</strong></td><td><span>✓†† </span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Instagram</strong></td><td><span>✓†† </span></td><td><span>✓††</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>LinkedIn</strong></td><td><span>✓</span></td><td><span>✓\*\*</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td><strong>Reddit</strong></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td><strong>Slack</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>X（旧Twitter）</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓^</span> </td></tr><tr><td><strong>WeChat</strong></td><td><span>✓† </span></td><td><span>✓† </span></td><td><span>✓\*</span></td><td><span>✓\*† </span></td></tr><tr><td><strong>WhatsApp</strong></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="5"><p>\* <a href="./onelink-troubleshooting-and-faq#which-operating-systems-allow-uri-schemes-to-open-the-app">URIスキーム</a>、または<a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page" target="_blank">ソーシャルアプリ向けランディングページ</a>が設定されている場合。<strong>注意</strong>：FacebookとFacebook Messengerでは、URIスキームとソーシャルアプリ向けランディングページの両方を設定している場合、ソーシャルアプリ向けランディングページは表示されません。</p><p>\*\* URIスキームの設定が必要です。</p><p>^ Universal Linksを設定したソーシャルアプリ向けランディングページが必要です。</p><p><span>†</span> 外部ブラウザでリンクを開くようユーザーに求める場合があります。</p><p><span>†† AndroidソーシャルアプリのWebViewにおけるディープリンク／リダイレクトの制限。詳細は</span><a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection" target="_blank"><span>こちら</span></a><span>を参照してください。</span></p></td></tr></tbody></table>

</Accordion>

<Accordion title="広告ネットワーク（有料メディア）でOneLinkを使用できますか？">

<strong>はい。</strong>ただし、OneLinkは主にオウンドメディア向けであり、広告ネットワークでの利用が中心ではない点に注意してください。 広告ネットワークは通常アプリ内で広告を配信するため、ユーザーのプラットフォームやデバイスIDなどを把握しています。そのため、アプリ／プラットフォーム別のアトリビューションリンクで十分であり、OneLinkを使用する必要はありません。 ただし、広告ネットワーク側でユーザーのプラットフォームを事前に把握できない場合（広告ネットワーク自身がメールやSMSキャンペーンを実施する場合など）は、OneLinkが有効な選択肢になります。

> 🚧 **Important**
>
> 広告ネットワークでOneLinkを使用する場合は、OneLinkのロングURLを使用する必要があります。

**パートナー広告ネットワーク向けにOneLinkを設定するには：**

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">広告ネットワークのアトリビューションリンク設定手順</Anchor>に従い、表示されたら［**OneLinkを使用**］を選択します。

AndroidとiOSのパラメータをすべて正しく追加すると、OneLinkカスタムリンクがクリックされ、ユーザーが適切なプラットフォームへリダイレクトされた後、インストール時のポストバックで必要なパラメータが広告ネットワークへ送信されます。

> 👍 **Tip**
>
> 広告ネットワークは、ユーザーの端末プラットフォームに応じてIDFAまたはGAIDパラメータのいずれかを使用し、もう一方は無視します。

</Accordion>

<Accordion title="ソーシャルメディアアプリからiOSアプリを起動できない問題は、どうすれば解決できますか？">

Facebookなどのソーシャルメディアアプリでは、iOS Universal Linksによるアプリ起動がブロックされる場合があります。<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">ソーシャルアプリ向けランディングページ</Anchor>は、このようなアプリ起動の問題に対する推奨の解決策です。

ソーシャルアプリ向けランディングページを使用しない場合は、フォールバックとしてURIスキームを使用できます。ただし、以下の点に注意してください。

* URIスキームをフォールバックとして使用する場合、iOS固有の制限があります。
* Safariを含む多くのブラウザでは、URIスキームをフォールバックとして使用するために、URLへ`af_force_deeplink=true`パラメータを追加する必要があります。<Anchor target="_blank" href="/marketers/ja/docs/uri-scheme-fallback-for-ios">詳細はこちら</Anchor>。
* X（旧Twitter）はURIスキームをサポートしていません。アプリ起動の問題を回避するには、ソーシャルアプリ向けランディングページを使用してください。

</Accordion>

<Accordion title="InstagramでOneLinkを使用できますか？">

<strong>はい。</strong>ただし、以下の制限に注意してください。

* Instagramでは投稿本文のテキスト表示仕様上、キャプション内に入力したリンクはクリックできません。
* Androidアプリの起動とディープリンクは、特別な対応を行わなくてもサポートされます。一方、InstagramはiOSアプリの起動とディープリンクをサポートしていません。この問題には、次の2つの方法で対応できます。
  * **推奨：** <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">ソーシャルアプリ向けランディングページ</Anchor>を設定します。 Clustered PosterテンプレートとShowAndTellテンプレートが最適です。ソーシャルアプリ向けランディングページに加えて、OneLinkテンプレートにURIスキームを設定することも推奨します。
  * InstagramでOneLinkを使用する場合は、URIスキームと[強制ディープリンク](/docs/onelink-troubleshooting-and-faq#強制ディープリンク)を使用します。 InstagramでOneLinkに`af_force_deeplink=true`を使用する場合は、次の動作を把握しておいてください。

| アプリはインストール済み？ | クリックしたリンクにaf\_force\_deeplink=trueが含まれる？ | 結果 |
| --- | --- | --- |
| いいえ | はい | クリックするとアプリストアが開く |
| いいえ | いいえ | クリックするとアプリストアが開く |
| はい | はい | クリックするとアプリが開く |
| はい | いいえ | クリックするとアプリストアが開く |

</Accordion>

<Accordion title="X（旧Twitter）でOneLinkを使用できますか？">

はい。 XでOneLinkを使用できますが、**ソーシャルアプリ向けランディングページ（SALP）とUniversal Linksを組み合わせて設定することを強く推奨します。**

XのiOSアプリ内ブラウザでは、App StoreへのリダイレクトやURIスキームによるアプリ起動がブロックされるためです。そのため、URIスキームのみを設定したOneLinkでは、既存ユーザーのアプリを開くことができません。 SALPとUniversal Linksを組み合わせることで、アプリがインストール済みならアプリを開き、新規ユーザーなら必要に応じてApp Storeへ送るなど、ユーザーを適切に誘導できます。

</Accordion>

<Accordion title="WeChatでOneLinkを使ったリダイレクトはできますか？">

WeChatはAndroid／iOSのディープリンクを上書きし、ユーザーをWebページへリダイレクトします。 Webページから、ユーザーは［**オプション**］ボタンをタップし、ブラウザでページを開く操作を選択する必要があります。その結果、ユーザー体験が途切れ、コンバージョンファネルから離脱する可能性が高まります。

この問題に対応するため、OneLinkはWeChatからのクリックを識別し、オプションボタンをタップして［**ブラウザで開く**］を選択するよう案内する専用ランディングページを表示します。その後、OneLinkテンプレート設定で定義したリダイレクトURLが開きます。

<Image align="center" alt="WeChat_a.jpg" src="https://files.readme.io/49c03a10d458f6ce71fd6448e922294682ac9239775534c6264c29151ec1ea6d-30192900489105.jpg" />

ユーザーのWeChat言語設定が中国語の場合、OneLinkはローカライズされたランディングページを表示します。

<Image align="center" alt="WeChat_b.jpg" src="https://files.readme.io/502ef821a122459ab991f2a507c720f25fcac7129eb647a01290e8cabfa7a34e-30192887085841.jpg" />

</Accordion>

<Accordion title="アプリをインストール済みのAndroidユーザーがFacebook WebView上のリンクをクリックすると、アプリではなくWeb URLへリダイレクトされるのはなぜですか？">

通常、Facebook広告からアプリを開いたりディープリンクしたりすることは可能です。ただし、以下の条件に該当する場合、FacebookではOneLink URLから既存ユーザーのアプリを開くことができません。代わりに、アプリをインストール済みのユーザーを含むすべてのユーザーが、OneLinkテンプレートで定義されたURL、または**af\_android\_url**、**af\_r**、**af\_custom\_android\_url**のいずれかのパラメータ値で指定されたURLへ送られます。

* ユーザーがAndroidモバイル端末を使用している。
* Facebookアプリ内でリンクがクリックされている。
* リンク先がFacebook WebViewで開くHTMLページ（Webサイトまたはソーシャルアプリ向けランディングページ）である。
* HTMLページ内のリンクに、URIスキームを含む**af\_dp**パラメータと、OneLinkテンプレートまたはパラメータ（**af\_android\_url**、**af\_r**、**af\_custom\_android\_url**のいずれか）で設定したURLリダイレクトの両方が含まれている。

</Accordion>

<Accordion title="Meta Web Adsの有料キャンペーンで動画をクリックすると、iOSで空白ページが表示されるのはなぜですか？">

Meta Web Adsの有料キャンペーンで動画にOneLinkカスタムリンクを設定している場合、Facebookアプリ内のiOSユーザーをApp Storeへリダイレクトするには、ソーシャルアプリ向けランディングページ（SALP）が必要です。 SALPを設定していない場合、動画をクリックすると代わりに空白ページが表示されます。

</Accordion>

<div id="testing-faq" />

### テストに関するよくある質問

<Accordion title="ソーシャルアプリ向けランディングページをA/Bテストするにはどうすればよいですか？">

<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">ソーシャルアプリ向けランディングページ</Anchor>を使用すると、ソーシャルネットワークアプリ内でOneLinkを利用する際に、スムーズなアプリ起動のユーザー体験を提供できます。ファネルに1ステップ追加することで、コンバージョン率が下がるのではないかと懸念するかもしれません。しかし実際には、ランディングページがないとユーザージャーニーが途中で途切れやすく、コンバージョン率が非常に低くなる傾向があります。

効果に確信が持てない場合は、実際にテストしてみてください。

ソーシャルメディアアプリで、ソーシャルアプリ向けランディングページあり／なしのカスタムリンクを<Anchor target="_blank" href="/marketers/ja/docs/create-a-b-tests">A/Bテスト</Anchor>します。

**ソーシャルアプリ向けランディングページをA/Bテストするには：**

1. ソーシャルメディアアプリで使用する<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLinkリンクを作成</Anchor>し、Link1とします。このリンクにはソーシャルアプリ向けランディングページを設定しないでください。
2. **af\_adset**アトリビューションパラメータを追加します。
3. **af\_ad**アトリビューションパラメータを追加し、値を「no lp」に設定します。
4. ソーシャルメディアアプリ以外でLink1をテストし、リンクが正常に機能してアプリが正しく起動することを確認します。
5. Link1を複製し、Link2とします。
6. **af\_ad**アトリビューションパラメータの値を「using lp」に変更します。
7. Link2にのみ<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">ソーシャルアプリ向けランディングページを作成</Anchor>します。
8. **同じ**ソーシャルメディアアプリに、Link1とLink2をそれぞれ使用した2つの異なる投稿を公開します。  
   各リンクのクリック数が異なっていても問題ありません。重要なKPIは、各リンクの最終的なコンバージョン率です。
9. **十分なトラフィックが集まったら、A/Bテストの結果を確認します。**
   1. AppsFlyerの概要ダッシュボードを開き、［**集約パフォーマンスレポート**］テーブルまでスクロールします。
   2. Link1とLink2では、メディアソース、キャンペーン、広告セット名が同じです。対象の広告セットまでドリルダウンします。
   3. Link1またはLink2をクリックしたユーザーのコンバージョン率（およびその他のKPI）を比較します。

</Accordion>

<Accordion title="アプリ選択ダイアログを表示させないようにするにはどうすればよいですか？">

OneLinkのテスト時にアプリ選択ダイアログが表示される場合は、<Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing">アプリに署名</Anchor>してください。<Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing#debug-mode">デバッグアプリ</Anchor>の場合も同様です。アプリの署名に使用する証明書は、OneLinkでApp Linksを設定する際に<Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-for-deep-linking-and-deferred-deep-linking#generating-a-sha256-fingerprint">SHA256フィンガープリントを生成</Anchor>する際に使用する証明書と同じものです。

</Accordion>

<div id="deep-linking-faq" />

### ディープリンクに関するよくある質問

<Accordion title="どのディープリンク方式を実装すればよいですか？">

開発者は、ディープリンクにUnified Deep Linking（UDL）メソッドを実装してください。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">ディープリンクの設定手順</Anchor>を参照してください。

iOS Universal LinksとAndroid App Linksは**アプリを起動するための方法であり、ユーザーを実際にディープリンクするものではありません**（アプリ内の特定コンテンツへ遷移させる機能ではありません）。 URIスキームはアプリ起動とディープリンクの両方に使用できます（**af\_dp**カスタムリンクパラメータを使用）。ただし、設定上はアプリ起動用途にのみ使用することを推奨します。主な用途は、Universal LinksやApp Linksのフォールバック、およびAndroid 6.0より前のOSを使用するユーザーのアプリ起動です。

これらのいずれかの方法でアプリが起動すると、AppsFlyer SDKはカスタムアトリビューションリンクで指定された**deep\_link\_value**をアプリへ渡します。この値は、開発者が実装したUDLメソッドを通じて受け取る必要があります。

</Accordion>

<Accordion title="URIスキーム（af_dpパラメータ）をディープリンクに使用できますか？">

<strong>はい。</strong>ただし、推奨されません。理想的には、ディープリンクには**deep\_link\_value**を使用し、URIスキームは**af\_dp**パラメータを使って、ディープリンクせずにアプリを起動するフォールバックとして使用してください。ただし、すでにURIスキームでディープリンクする設定を実装し、URIパスの一部として追加パラメータを連結している場合（例：greatapp://param1/param2）は、既存の設定やコードを変更する必要はありません。URIスキームは引き続き機能します。

**カスタムパラメータは、カスタムリンク設定ページから追加することを推奨します**。

</Accordion>

<div id="ios-14-faq" />

### iOS 14に関するよくある質問

<Accordion title="iOS 14でもOneLinkのディープリンクは機能しますか？">

UDLメソッドを使用して広告ネットワークやオウンドメディアのキャンペーンからディープリンクされたiOS 14ユーザーについて、ユーザー体験への影響はありません。従来方式では、ディープリンクが正常に機能しない場合があります。

アトリビューション／レポートでは、利用可能な場合にAppsFlyerはIDFAまたはIDFVを使用します。 IDFAもIDFVも利用できない場合は、確率論的モデリングが使用されることがあります。 iOS 14.5以降では、確率論的モデリングは、オウンドメディア、クロスプロモーション、およびユーザー同意を得たWeb-to-appフローに限定されます。

</Accordion>

<Accordion title="iOS 14でもOneLinkのディファードディープリンクは機能しますか？">

UDLメソッドを使用して広告ネットワークやオウンドメディアのキャンペーンからディファードディープリンクされたiOS 14ユーザーについて、ユーザー体験への影響はありません。従来方式では、ディファードディープリンクが正常に機能しない場合があります。

アトリビューション／レポートでは、利用可能な場合にAppsFlyerはIDFAまたはIDFVを使用します。 IDFAもIDFVも利用できない場合は、確率論的モデリングが使用されることがあります。 iOS 14.5以降では、確率論的モデリングは、オウンドメディア、クロスプロモーション、およびユーザー同意を得たWeb-to-appフローに限定されます。広告ネットワークやオウンドメディアからディファードディープリンクを実装する場合は、AppsFlyer iOS SDK V6.1.0以降を使用することを推奨します。必要に応じてATT同意を取得でき、アトリビューションへの影響を抑え、より速いレスポンスを得られます。

</Accordion>

<div data-zendesk-anchors="onelink-troubleshooting-guide=onelink%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%AC%E3%82%A4%E3%83%89 01H7WPYJV9CQ1J6J3PFCEQFGB0=onelink%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%AC%E3%82%A4%E3%83%89 onelink-frequently-asked-questions=onelink%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7WPYJV9H52P659N8JPRX2TY=onelink%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F onelink-template-faq=onelink%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7WPYJV9TJRKHFZ77DFMKDDG=onelink%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F deep-linking=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF 01H7WPYJV9JSQ5FV73YCE3H5AF=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF onelink-link-faq=onelink%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7WPYJVAPNYAQ1SH4FBX4Z9F=onelink%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F fallback-urls=%E3%83%95%E3%82%A9%E3%83%BC%E3%83%AB%E3%83%90%E3%83%83%E3%82%AFurl 01H7WPYJVACCGVJD1Z7ZPVG2SQ=%E3%83%95%E3%82%A9%E3%83%BC%E3%83%AB%E3%83%90%E3%83%83%E3%82%AFurl forced-deep-linking=%E5%BC%B7%E5%88%B6%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF 01H7WPYJVA1W3HYYJJFQM01136=%E5%BC%B7%E5%88%B6%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF onelink-parameter-faq=onelink%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7WPYJVAGRVWHRVMZVQG1ZVE=onelink%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F integrated-partner-faq=%E9%80%A3%E6%90%BA%E6%B8%88%E3%81%BF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7WPYJVB8ZZSKFT1V01EN6QF=%E9%80%A3%E6%90%BA%E6%B8%88%E3%81%BF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F testing-faq=%E3%83%86%E3%82%B9%E3%83%88%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7WPYJVC1PJJDA0GGT1DVVCF=%E3%83%86%E3%82%B9%E3%83%88%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F deep-linking-faq=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7WPYJVCTM39HKCG9JN03BN6=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F ios-14-faq=ios-14%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7WPYJVCVCVWHJW4RH85KC40=ios-14%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F" />
