---
title: Firebase Dynamic LinksからAppsFlyerへの移行
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-06-19T09:27:37Z'
  edited_at: '2026-10-14T09:29:58Z'
  id: 16282289097105
  locale: ja
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/ja/articles/16282289097105
---
> **概要：** このステップバイステップガイドを使用して、Firebase Dynamic LinksからAppsFlyer OneLinkへスムーズに移行しましょう。

## ![53375 Firebase migration KB image.png](https://files.readme.io/b5340a5b30c160bca2b420052fd60b23f4bfe0de6d2868f91ad4342bee36c7df-30063560499345.png)

<div id="about-the-migration" />

## 移行について

Googleの<Anchor target="_blank" href="https://firebase.google.com/docs/dynamic-links">Firebase Dynamic Links</Anchor>は、 2025年8月25日に廃止されます。この日付をもって、Firebase Dynamic Links によって提供されるすべてのリンク (カスタムドメインと page.link サブドメインの両方でホストされているもの）が機能しなくなり、新しいリンクの作成が無効になります。Firebase Dynamic Linksを使用する場合は、キャンペーンによるユーザージャーニーの中断を防ぐために、できるだけ早く積極的な手順を実行してリンクを他の場所に移行することが不可欠です。

AppsFlyerのOneLinkは、アトリビューションやリダイレクト、ディープリンク機能を持つリンクを作成し、デバイス、オペレーティングシステム、チャネル、プラットフォームに関係なく、1つのリンクでオウンドメディアまたは有料メディアのユーザーをアプリユーザーにコンバージョンさせることが可能です。AppsFlyerと提携して、パーソナライズされたコンテキストに応じたユーザージャーニーを作成、ユーザーをアプリに誘導し、コンバージョンと収益を最大化します。Firebase Dynamic LinksからAppsFlyerに移行するには、以下の手順に従ってください。

<div id="migrate-from-firebase-to-appsflyer" />

## FirebaseからAppsFlyerへの移行

このセクションでは、FirebaseダイナミックリンクをAppsFlyer OneLinkに移行する方法について説明します。

**前提条件**

始める前に、次が必要です:

* Firebase ダイナミックリンク
* アプリ開発者

**AppsFlyerへ移行する：**

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="ステップ 1. AppsFlyerアカウントの作成">

* <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">AppsFlyerアカウントを作成</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/user-management">適切な権限を持つアカウントユーザーを追加</Anchor>します。

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="ステップ 2. アプリ追加">

* AppsFlyerに<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">アプリIDを追加</Anchor>します。
* （任意） アクティブユーザーの定義に合わせて、デフォルト90日間の<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>を変更します。

<Image align="center" alt="add" src="https://files.readme.io/7f7bab2277d0f45434618d28714c727ccbb9e414192b765dd22551bcbd5b0a37-16950840602769.png" />

</Accordion>

<div id="step-3-create-a-onelink-template" />

<Accordion title="ステップ 3. OneLinkテンプレートの作成">

**このステップでは、マーケターとアプリ開発者の両方の作業が必要です**。

テンプレートは、リンクとエンドユーザーのエクスペリエンスの作成に必須です。OneLink テンプレートは、さまざまなマーケティングキャンペーン用に作成するすべてのOneLinkリンクのリダイレクトロジックの基礎を形成します。

* <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートの作成</Anchor>
  * マーケティング担当者は、AppsFlyerの管理者ユーザーであるか、<Anchor target="_blank" href="/marketers/ja/docs/user-management">OneLinkテンプレートを追加 / 編集する権限</Anchor>を持っている必要があります。

</Accordion>

<div id="step-4-set-up-the-appsflyer-sdk" />

<Accordion title="ステップ 4. AppsFlyer SDKの実装">

**このステップではアプリ開発者の作業が必要です。**

アプリに実装するAppsFlyer SDKは、アプリとAppsFlyerプラットフォーム間の接続の役割を果たします。提供される機能：

* ディープリンク：UDL APIの実装が可能になります。
* アトリビューション：アプリのインストール、アプリ起動、アプリ内イベントなどを計測します。

以下の手順を使用して、AppsFlyer SDKをアプリと連携させます。

<div id="appsflyer-sdk-integration-steps" />

#### AppsFlyer SDKの連携手順

1. AppsFlyer SDKをアプリに実装します。  
   Android、iOSそれぞれの<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">SDK実装ガイド</Anchor>を参照してください。
2. AppsFlyerのスキームを使用して、計測したいアプリ内イベントをマッピングしてください。  
   これは、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">SDK</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>を介して行うことができます。
3. Firebase SDKを処理します。  
   AppsFlyerのみに切り替えるか、または数週間両方のSDKを同時に実行することができます。以下の表でこれらのオプションの内訳をご覧ください。  

| 任意 | 更新されたアプリ  <br />バージョンのリリース後 | 影響 |
| --- | --- | --- |
| Firebase SDKを削除（推奨） | AppsFlyerのみが新規インストールと更新ユーザーを記録します。  <br />Firebase は、ユーザーがアプリを更新するまで、ユーザーによって実行されたイベントを表示します。 | <ul><li>切り替えが素早く完了します。</li><li>重複アトリビューション無し</li><li>Firebase SDKがまだ残っているアプリのバージョンがあるかどうかを確認できます</li></ul> |
| 移行期間中はFirebase SDKを保持 | AppsFlyer と Firebase は新規インストールを属性化し、イベントを報告します。後日、Firebase SDKを削除します。 | <ul><li>データ検証が可能：AppsFlyerとFirebaseのデータを比較することができます。</li><li>二重アトリビューションにより、広告ネットワークで二重請求が発生する可能性があります。</li><li>作業量がより多いです。</li></ul> |

4. 作業範囲に含まれる他の全てのタスクが完了したあと、AppsFlyer SDKを含むアプリバージョンをアプリストアに更新します。AppsFlyerによる新規ユーザーのアトリビューションが開始します。   
   **注：**
   * iOS、Google Play、および関連する全てのAndroidの外部ストアのアプリを更新してください。
   * Androidアプリは、認識せずとも非公式のAPKサイトに存在している可能性があります（アプリのパッケージ名をウェブで検索して確認してください）。APKサイトは最新バージョンに更新するのに時間がかかるため、AppsFlyer SDKが実装されていない古いバージョンのアプリをインストールするオーガニックユーザーを生む可能性があります。
   * ストアでの更新版アプリの公開は、完全に完了するまでに数日かかる場合があります。この段階でインストールするユーザーは、以前のバージョンを引き続き使用できます。

</Accordion>

<div id="step-5-understand-parameter-mapping" />

<Accordion title="ステップ 5. パラメータのマッピング（開発者作業）">

**このステップではアプリ開発者の作業が必要です。**

Firebase Dynamic LinksパラメーターがAppsFlyerの対応するパラメーターにどのようにマッピングされるかを理解します。

マッピングを正しく行い、対応するパラメーターを理解することで、リンクで同じ結果が確実に得られます。

以下の表に、Firebaseのすべてのパラメーターと、対応するAppsFlyerパラメーターを示します。

この表は、AppsFlyer に移行するときに現在使用しているすべてのパラメーターの参考として使用してください。

<div id="note" />

> 📘 **注**
>
> Firebaseのパラメーターが表示されていない場合は、リンクにパラメーターを追加する必要がなく、OneLinkテンプレートの設定でAppsFlyerが対応しています。

<table><thead><tr><th>グループ</th><th>Firebase</th><th>AppsFlyer</th><th>説明</th></tr></thead><tbody><tr><td>モバイルパラメーター</td><td>リンク</td><td><ul><li>af_dp</li><li>deep_link_value</li></ul></td><td><ul><li> <strong>af_dp</strong>：iOSおよびAndroidアプリを起動するためのフォールバック方法として使用されるURIスキームの値</li><li> <strong>deep_link_value</strong>：アプリ起動時にユーザーを遷移させるアプリ内の特定画面を指示する値</li></ul></td></tr><tr><td> <br/>Androidパラメーター</td><td>afl</td><td>af_android_url</td><td>Androidユーザーをカスタマイズされたウェブページにリダイレクトできるようにします（遷移先のドメインは<a href="./set-up-your-domain-redirect-allowlist" target="_blank">リダイレクト許可リスト</a>に設定されている必要があります）</td></tr><tr><td rowspan="2">iOSパラメーター<br/><br/> </td><td>ifl</td><td>af_ios_url</td><td>iOS ユーザーをカスタマイズされた Web ページにリダイレクトできるようにします (ドメインは <a href="./set-up-your-domain-redirect-allowlist" target="_blank">リダイレクト許可リスト</a>に含まれている必要があります)</td></tr><tr><td>efr</td><td>af_force_deeplink</td><td>これがないと、このアプリを URI スキームで開けません。</td></tr><tr><td>他プラットフォームのURL</td><td>ofl</td><td>af_web_dp</td><td>デスクトップユーザーをウェブページにリダイレクトできるようになります。</td></tr><tr><td rowspan="3"> <br/>ソーシャルタグ<br/><br/> </td><td>st</td><td>af_og_title</td><td>ソーシャルメディア上の共有コンテンツのタイトルをカスタマイズするために使用します。</td></tr><tr><td>sd</td><td>af_og_description</td><td>ソーシャルメディア上の共有コンテンツの説明をカスタマイズするために使用します。</td></tr><tr><td>si</td><td>af_og_image</td><td>ソーシャルメディア上の共有コンテンツの画像をカスタマイズするために使用します。</td></tr><tr><td rowspan="5"><p>分析用のパラメーター <br/><br/><br/><br/> </p></td><td>utm_source</td><td>pid</td><td>Media Source</td></tr><tr><td>utm_medium</td><td>af_channel</td><td>広告が配信されるメディアソースチャネルを識別します。</td></tr><tr><td>utm_campaign</td><td>c</td><td>キャンペーン名</td></tr><tr><td>utm_term</td><td>af_keywords</td><td>テキストターゲットキャンペーンのためのキーワードリスト</td></tr><tr><td>utm_content</td><td>af_adset</td><td>キャンペーンに関連付けられた広告のコレクション</td></tr></tbody></table>

</Accordion>

<div id="step-6-create-onelink-links-with-mapped-parameters" />

<Accordion title="ステップ 6. マッピングされたパラメータを使用したOneLinkの作成">

マッピングされたパラメーターを使用して、OneLinkテンプレート上にOneLinkを作成できます。

リンクは、CSVファイル経由で<Anchor target="_blank" href="/marketers/ja/docs/perform-onelink-bulk-actions-via-csv">一括作成</Anchor>することも、<Anchor target="_blank" href="/marketers/ja/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor>を使用してプログラム的に作成することも、<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">AppsFlyer管理画面から個別に作成</Anchor>することも、<Anchor target="_blank" href="/marketers/ja/docs/user-invite-attribution">SDKで作成</Anchor>することも、手動で作成された<Anchor target="_blank" href="/marketers/ja/docs/understand-onelink-short-vs-long-urls">ロングリンク</Anchor>として作成することもできます。

次の表を使用して、用途に最適な方法を判断してください。

| Firebase | AppsFlyer | 以下の場合に使用してください | 備考 |
| --- | --- | --- | --- |
| Firebaseコンソール | <Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink管理画面</Anchor> | OneLinkリンクを1つずつ作成したい場合。OneLinkの機能と可能性を最大限に活用できます。 |  |
| ダイナミックリンクビルダーAPI | <Anchor target="_blank" href="/marketers/ja/docs/user-invite-attribution">SDK</Anchor> | ユーザーの招待や紹介などに使用する、プログラムで生成されたアプリ内リンクを作成したい場合 | <ul><li>iOS または Android 開発者が必要です</li></ul> |
| Firebase REST API | <Anchor target="_blank" href="/marketers/ja/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> | モバイルアプリの外部でプログラムによってリンクを作成したい場合 | <ul><li>開発者が必要です</li><li>無料プランでは利用できません</li></ul> |
| 手動リンク構築 | <Anchor target="_blank" href="/marketers/ja/docs/understand-onelink-short-vs-long-urls">ロングリンク</Anchor> | クエリパラメーターを使用してリンクを手動で作成したい場合ショートリンクが必要ない場合に使用します。例：リンクがボタンやバナーの背後に設置されている場合など |  |
|  | <Anchor target="_blank" href="/marketers/ja/docs/perform-onelink-bulk-actions-via-csv">OneLink一括作成</Anchor> | すべてのFirebaseダイナミックリンクを一括でAppsFlyerに移行したい場合<br /><br />エラーなくすべてのリンクをすばやく移動するには、これをお勧めします | <ul><li>[対応するFirebaseパラメータに従ってリンクパラメーターのキーと値をマッピング](/docs/migrate-from-firebase-dynamic-links-to-appsflyer#map-parameters)する前段階が必要です。</li><li>無料プランではご利用いただけません。</li></ul> |
|  | <Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">スマートバナー</Anchor> | モバイルウェブサイトにアプリへのディープリンクバナーを作成したい場合 |  |
|  | <Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors">スマートスクリプト</Anchor> | Web からアプリへのエクスペリエンスのために Web ページ内にロングリンクを動的に構築したい場合 |  |

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain">ブランドドメイン</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/using-firebase-and-google-tag-manager-with-appsflyer-overview">FirebaseとGoogleタグマネージャーのAppsFlyerでの利用—概要</Anchor>

<div data-zendesk-anchors="overview=%E7%A7%BB%E8%A1%8C%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01J7ZPPQ340PNQ70FZAQY4GBZ1=%E7%A7%BB%E8%A1%8C%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H8K961JHRXNQHBVN930XW70Q=%E7%A7%BB%E8%A1%8C%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 how-to-migrate-from-firebase-to-appsflyer=firebase%E3%81%8B%E3%82%89appsflyer%E3%81%B8%E3%81%AE%E7%A7%BB%E8%A1%8C 01H8K961JHCK0Z4GTTHCAKF98E=firebase%E3%81%8B%E3%82%89appsflyer%E3%81%B8%E3%81%AE%E7%A7%BB%E8%A1%8C h_01J5QWWGWGDBEF8RY3DZ5XAN3G=step-1-create-an-appsflyer-account h_01J5QWWGWGN17673GYFZWPNKQR=step-2-add-your-app h_01J5QWWGWGKJPRCG9N93B8KBYW=step-3-create-a-onelink-template h_01J5QWWGWGCQFHBQ9EC0QTPF4S=step-4-set-up-the-appsflyer-sdk appsflyer-sdk-integration-steps=appsflyer-sdk%E3%81%AE%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 h_01J5QXST2K890DV7QS6S9K3A01=appsflyer-sdk%E3%81%AE%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 h_01J5QWWGWGPRF5DRMMQ14BJCFA=step-5-understand-parameter-mapping 01H8K961JHBXVKXM0XQYY605EQ=%E6%B3%A8 h_01J5QWWGWG3ST19WDRZXN8FK8Q=step-6-create-onelink-links-with-mapped-parameters h_01HE7SZPKKQETH260G45V0D0HN=%E5%8F%82%E7%85%A7" />
