---
title: OneLink｜CSVによるリンクの一括操作
metadata:
  keywords:
    - Marketers
    - bulk
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2023-04-13T11:31:43Z'
  edited_at: '2026-10-21T19:17:20Z'
  id: 14511403892369
  locale: ja
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ja/articles/14511403892369
---
> **概要：** OneLinkの［リンクの一括管理］ページでは、OneLinkのカスタムショートリンクを一括で作成・管理できます。

リンクを一括作成し、作成したリンクを表示・編集できます。リンクは管理しやすいコレクションとして整理され、新しいリンクの追加、ダウンロード、QRコード画像ファイルの生成などを、コレクション全体に対して一括で実行できます。

<div id="getting-started" />

## 利用開始

1. AppsFlyerで、［**Engage**］>［**リンクの一括管理**］に移動します。
2. 案内ページに、以下のいずれかのボタンが表示されます。
   1. ［**利用を開始**］：クリックして、最初のコレクションを作成します。
   2. ［**OneLinkテンプレートを作成**］：アカウントにOneLinkテンプレートが少なくとも1つあり、GrowthまたはEnterpriseプランを契約していることを確認してください。 <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">OneLinkテンプレート</Anchor>を参照してください。
   3. ［**アップグレード**］：リンクの一括管理は、EnterpriseまたはGrowthプランで利用できます。プランのアップグレードについては、CSMに連絡するか、[hello@appsflyer.com](mailto:hello@appsflyer.com)までお問い合わせください。

<div id="creating-your-first-collection" />

## 最初のコレクションの作成

1. ［**＋新しいコレクション**］をクリックします。
2. コレクション名を入力します。  
   後からすぐに識別できるよう、コレクションの用途が分かる名前を付けてください。
3. OneLinkテンプレートを選択します。注意：コレクション内のすべてのリンクは、このテンプレートをもとに作成されます。
4. ［**保存して続行**］をクリックします。
5. CSVファイルをアップロードします。[サンプルCSV](https://cdn.appsflyer.com/onelink-bulk-links-mgmt/sample_file.csv)を参考にできます。  
     
   [アップロード形式](/docs/perform-onelink-bulk-actions-via-csv#upload-format)を参照し、CSVが要件を満たし、正常にアップロードできる形式であることを確認してください。 CSVファイルをアップロードすると、内容が検証されます。 無効な行がある場合は、ファイルの修正に役立つ検証結果レポートをCSV形式でダウンロードできます。 UIの案内に従い、修正したファイルをアップロードしてください。
6. ［**コレクションを作成**］をクリックします。

<div id="managing-your-bulk-links-with-collections" />

## コレクションによる一括リンク管理

一括作成したリンクは、コレクション単位で管理します。

* ページ上部の［**今月の一括リンク利用状況**］ウィジェットには、当月の上限に対するリンクリクエスト数（リンクの作成と更新を含む）が表示されます。
  * 現在、デフォルトの上限は月間20,000件のリンク作成です。

* ［**コレクション**］セクションでは、コレクションの作成や、既存のリンクコレクションに対する各種操作が可能です。
* コレクションが8個以上ある場合は、一覧を検索・フィルタリングできます。
* 各コレクションには、最大2,000個のリンクを含められます。

<div id="other-actions" />

## その他の操作

コレクションには、以下の操作も実行できます。

<div id="creating-a-new-collection" />

<Accordion title="新しいコレクションの作成">

[月間利用量](#コレクションによる一括リンク管理)が上限を超えていなければ、新しいコレクションを作成できます。

1. ［**新しいコレクション**］をクリックします。
2. 案内に従って操作します。
   1. 作成方法は、「[最初のコレクションの作成](/docs/perform-onelink-bulk-actions-via-csv#最初のコレクションの作成)」と同じです。

</Accordion>

<div id="downloading-a-collection-of-links" />

<Accordion title="コレクション内のリンクのダウンロード">

コレクションをダウンロードするには、以下の条件を満たしている必要があります。

* コレクションに有効なリンクがあること。
* コレクションに関連付けられたOneLinkテンプレートのモバイルアプリのうち、少なくとも1つへのアクセス権限があること。

コレクションをダウンロードするには：

1. AppsFlyerのサイドメニューから、［**Engage**］>［**リンクの一括管理**］を選択します。
2. 対象のコレクションの行で、リンクのダウンロードアイコン![links.png](https://files.readme.io/eb3548960149ec6d0274acf683f693773f4bb9800d624a6ed056c5a1b0b33343-21656949393937.png)をクリックします。
3. 出力するショートURLのドメインを選択します。
4. ［**ダウンロード**］をクリックします。

<div id="important" />

> 🚧 **重要**
>
> AppsFlyerは、ブランドドメインの利用をおすすめします。ブランドへの信頼感と認知度を高め、キャンペーンのパフォーマンス向上につながる可能性があります。<Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain">詳細はこちら</Anchor>

</Accordion>

<div id="downloading-a-collection-of-qr-codes" />

<Accordion title="コレクション内のQRコードのダウンロード">

コレクション全体のQRコード画像を作成できます。

1. AppsFlyerのサイドメニューから、［**Engage**］>［**リンクの一括管理**］を選択します。
2. 対象のコレクションの行で、QRコード画像のダウンロードアイコン<Image alt="generate qr.png" src="https://files.readme.io/23dbd4b2e3ed248e868ae7d5deee3cac383b0e018ae17204f9547f5707a428c9-21656949404561.png" width="22px" />をクリックします。
3. ［**QRコード画像を生成**］ダイアログで、以下を設定します。
   * **ドメイン：** ユーザーがQRコードを読み取った後に表示されるURLの、サブドメインまたはブランドドメインを選択します。
   * **QRコードの画像形式：** PNGまたはSVGを選択します。
   * **QRコードのファイル名形式：** QRコード画像のファイル名の先頭に使用する値を持つパラメータを選択します。各QRコード画像の用途を識別しやすいよう、ファイル名から内容を判断できるパラメータの値を使用してください。
4. ［**生成］をクリックします。** ［**QRコード画像をダウンロード**］パネルで、ファイルの生成状況を確認できます。
5. ZIPファイルをダウンロードするには、ダウンロードアイコン<Image alt="download-bulk.png" src="https://files.readme.io/8436aed2633bbed2f6cb65c00690711766c153c97042b5b157c199333e8723c2-21656949409041.png" width="18px" />をクリックします。

<div id="note" />

> 📘 **注意**
>
> * 生成が完了すると、ファイルはパネルから24時間ダウンロードできます。その後、自動的に削除されます。
> * 複数のQRコード画像ファイルをまとめて提供するため、ダウンロードファイルはZIP形式です。ブラウザでZIPファイルのダウンロード許可を求められた場合は、許可して続行してください。
> * QRコードの生成処理は、最大2件まで同時に実行できます。

</Accordion>

<div id="adding-links-to-a-collection" />

<Accordion title="コレクションへのリンクの追加">

リンクを追加するには、以下の条件を満たしている必要があります。

* コレクションに関連付けられたOneLinkテンプレートのモバイルアプリのうち、少なくとも1つへのアクセス権限があること。
* コレクション内の有効なリンクが2,000個未満であること。
* [月間利用量](#コレクションによる一括リンク管理)が上限を超えていないこと。

コレクションにリンクを追加するには、［**メニューオプション**］>［**コレクションにリンクを追加**］をクリックします。

* 「[最初のコレクションの作成](/docs/perform-onelink-bulk-actions-via-csv#最初のコレクションの作成)」の手順5以降に従って、リンクを追加します。

</Accordion>

<div id="editing-links-in-a-collection" />

<Accordion title="コレクション内のリンクの編集">

リンクを編集するには、以下の条件を満たしている必要があります。

* コレクションに有効なリンクがあること。
* コレクションに関連付けられたOneLinkテンプレートのモバイルアプリのうち、少なくとも1つへのアクセス権限があること。
* [月間利用量](#コレクションによる一括リンク管理)が上限を超えていないこと。

**コレクション内のリンクを編集するには：**

1. ［**メニューオプション**］>［**リンクを編集**］をクリックします。
2. コレクションのベースCSVをダウンロードします。このファイルには、コレクション内で編集可能なすべてのリンクが含まれます。
3. 最初の手順の案内に従って、リンクのパラメータを編集します。更新するリンクの［**Mark for update**］が［**true**］に設定されていることを確認します。
4. ［**次へ**］をクリックします。
5. 編集したCSVをアップロードします。[アップロード形式](/docs/perform-onelink-bulk-actions-via-csv#upload-format)を参照し、CSVが要件を満たし、正常にアップロードできる形式であることを確認してください。
   * CSVファイルをアップロードすると、内容が検証されます。
   * 無効な行がある場合は、ファイルの修正に役立つ検証結果レポートをCSV形式でダウンロードできます。 UIの案内に従い、修正したファイルをアップロードしてください。
6. ［**リンクを更新**］をクリックします。

<div id="notes" />

> 📘 **注意**
>
> * このリンクコレクションのQRコード画像をダウンロード済みの場合も、リンクのパラメータを更新した後、同じ画像を引き続き使用できます。QRコード自体は変わりません。
> * 一括編集でリンクを更新すると、リンクの有効期間（TTL）が365日延長されます。

</Accordion>

<div id="viewing-the-collection-history" />

<Accordion title="コレクションの履歴の表示">

コレクションの履歴を表示するには、［**メニューオプション**］>［**コレクションの履歴を表示**］をクリックします。

履歴ウィンドウには、以下の操作と、その実行日時・実行者が表示されます。

* **名前の変更：** コレクション名の変更内容。
* **リンクの追加：** コレクションにリンクを追加した日時。
* **リンクの更新**：コレクション内のリンクを編集・更新した日時。
* **コレクションの作成**：コレクションを作成した日時。
* **QRコードZIPのダウンロード**：コレクションのQRコード画像を生成・ダウンロードした日時。

**リンクの追加と更新**では、変更によって[利用量](#コレクションによる一括リンク管理)がどのように変わったかも確認でき、その変更の操作レポートをダウンロードできます。

* 操作レポートをダウンロードするには、コレクションに関連付けられたOneLinkテンプレートのモバイルアプリのうち、少なくとも1つへのアクセス権限が必要です。

</Accordion>

<div id="editing-the-collection-name" />

<Accordion title="コレクション名の編集">

コレクション名を編集するには、以下の条件を満たしている必要があります。

* コレクションに関連付けられたOneLinkテンプレートのモバイルアプリのうち、少なくとも1つへのアクセス権限があること。

コレクション名を編集するには：

1. 変更するコレクション名にカーソルを合わせます。
2. コレクション名の横の編集アイコンをクリックします。
3. 名前を編集したら、Enterキーを押すか、画面の他の場所をクリックします。

</Accordion>

<div id="deleting-empty-collections" />

<Accordion title="コレクションの削除">

コレクションを削除するには、関連付けられたOneLinkテンプレートのモバイルアプリのうち、少なくとも1つへのアクセス権限が必要です。

**コレクションを削除するには：**

1. AppsFlyerで、［**Engage**］>［**リンクの一括管理**］に移動します。
2. 削除するコレクションの横のアクションメニューをクリックし、［**コレクションを削除**］を選択します。

<div id="important-notes" />

> 📘 **重要な注意事項**
>
> * コレクションを本当に削除してよいか、確認してください。有効なリンクがあるコレクションを削除すると、リンクが機能しなくなり、クリックしたユーザーのアトリビューションやリダイレクトが正しく行われなくなります。**コレクションを削除すると、元に戻すことはできません。**
> * 削除したリンクの記録を残したい場合は、削除する前にコレクションをダウンロードできます。 **CSVファイルとしてダウンロードするには：**
>   確認メッセージの［**コレクションをダウンロード**］をクリックします。

<div id="empty-collections" />

### 空のコレクション

**コレクションが空になる理由として、以下が考えられます。**

* コレクション内のすべてのリンクの有効期間（TTL）が切れた。
* リンクが作成される前に、新しいコレクションの作成処理をキャンセルした、または処理を完了できなかった。

空のコレクションも、前述の方法で削除できます。

</Accordion>

<div id="general-information" />

## 一般情報

<div id="note-1" />

> 📘 **注意**
>
> 2023年4月より前に一括作成したリンクは、リンクの一括管理ページには表示されず、管理もできません。

<div id="upload-format" />

<Accordion title="アップロード形式">

CSVをエラーなくアップロードできるよう、ファイルが以下の要件を満たしていることを確認してください。

* CSV形式であること。
* ファイルサイズが4MB以下であること。
* 作成・更新するリンクに関する内容のみが含まれていること。
* 1つのリンクを1行に記載すること。
* **Custom Link ID**は、一意の値を設定する列で、リンクのショートURLのIDを指定できます。ショートURLのIDは、リンクの作成後には編集できません。 URL IDの詳細は、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#url-id">こちら</Anchor>を参照してください。
* 各列に1つのパラメータを記載すること（パラメータ列は最大35列）。
* 文字エンコーディングにUTF-8を使用すること。

</Accordion>

<div id="parameters-in-the-uploaded-csv" />

<Accordion title="アップロードするCSV内のパラメータ">

* CSVには、AppsFlyerのリンクで使用可能な任意のパラメータを含められます。アトリビューション用（c、af\_channel、af\_adsetなど）、リダイレクト・ディープリンク用（af\_ios\_url、af\_dp、deep\_link\_valueなど）の予約済みパラメータや、カスタムパラメータを使用できます。
* メディアソース（pid）パラメータは必須です。
* OneLinkテンプレートにURIスキームを設定済みでも、一括作成するリンクでは、CSVファイルにURIスキームを指定したaf\_dpパラメータを含める必要があります。

</Accordion>

<div id="faq" />

## よくある質問

<div id="qr-with-long-links-vs-short-links---is-there-any-difference" />

<Accordion title="ロングURLとショートURLでは、QRコードに違いはありますか？">

QRコードは、ロングURLでもショートURLでも機能します。ただし、ショートURL自体は変わらないため、ショートURLを使用すると、公開済みのQRコードを差し替えることなく、OneLink管理画面の［リンク管理］セクションからリンクのパラメータや動作を更新できます。

* **ショートURL：** ショートURLの設定でパラメータを変更しても、QRコードは変わりません。公開し直す必要はありません。
* **ロングURL（Smart Scriptなど）：** ロングURLのパラメータを変更すると、QRコードも変わります。一度公開したURLの内容を遠隔で更新することはできないため、新しいQRコードを生成して配布する必要があります。

</Accordion>

<div id="can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example" />

<Accordion title="QRコードを作成した後、例えば印刷後でも、そのリンクの動作を変更できますか？">

はい。編集可能なOneLinkショートURL（OneLinkのUIで作成したURLなど）をもとにしたQRコードであれば、変更できます。 **QRコードは、紐づくURLを視覚的に表現したもの**です。  URL自体を変更すると、対応するQRコードも変わります。例えば、mike.onelink.me/123A/shorturlのQRコードと、mike.onelink.me/123A/exampleのQRコードは異なります。

一方、OneLinkのショートURLはハッシュ化されたURLであり、パラメータやリダイレクトのルールはバックエンドで設定されるため、URLには表示されません。そのため、表示されるURLとQRコードを変えずに、バックエンドの設定を編集できます。

</Accordion>

<div id="what-options-are-available-for-generating-qr-codes-in-appsflyer" />

<Accordion title="AppsFlyerには、どのようなQRコードの生成方法がありますか？">

以下の方法があります。

* **AppsFlyer管理画面のOneLinkのUI：**
  * リンクの作成時にQRコードを自動生成
  * QRコードのカスタマイズが可能
  * SVGまたはPNGでエクスポートが可能
  * ショートURLを使用
* **QRコードの一括作成（リンクの一括管理ページ）：**
  * QRコードのカスタマイズが可能
  * SVGまたはPNGでエクスポートが可能
  * 内容が分かるファイル名の設定に対応
  * ショートURLを使用
* **Smart ScriptによるQRコードの生成：**
  * 動的に生成したロングURLを使用
  * 生成したURLに応じてQRコードを作成
  * QRコードのカスタマイズが可能
  * 複数のURLのQRコードを一括作成可能

</Accordion>

<div id="can-you-bulk-create-qr-codes" />

<Accordion title="QRコードを一括作成できますか？">

はい。リンクの一括管理ページの[QRコードの一括作成機能](/docs/perform-onelink-bulk-actions-via-csv)を使用すると、QRコードを一括作成できます。

</Accordion>

<div data-zendesk-anchors="getting-started=%E5%88%A9%E7%94%A8%E9%96%8B%E5%A7%8B h_01HKWSS511PMGTVEJN82SF5NX5=%E5%88%A9%E7%94%A8%E9%96%8B%E5%A7%8B creating-your-first-collection=%E6%9C%80%E5%88%9D%E3%81%AE%E3%82%B3%E3%83%AC%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90 h_01HKWSS511SD4DFH7TMZV1EETH=%E6%9C%80%E5%88%9D%E3%81%AE%E3%82%B3%E3%83%AC%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90 managing-your-bulk-links-with-collections=%E3%82%B3%E3%83%AC%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%82%88%E3%82%8B%E4%B8%80%E6%8B%AC%E3%83%AA%E3%83%B3%E3%82%AF%E7%AE%A1%E7%90%86 h_01HKWSS511XMB3CZ563SBZTEAC=%E3%82%B3%E3%83%AC%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%82%88%E3%82%8B%E4%B8%80%E6%8B%AC%E3%83%AA%E3%83%B3%E3%82%AF%E7%AE%A1%E7%90%86 other-actions=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%93%8D%E4%BD%9C h_01HKWSS5113EPY13J2KHMWGDS7=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%93%8D%E4%BD%9C h_01HKWSS511G8AREWDP05F6ZMER=creating-a-new-collection h_01HKWSS511DN9BSXFDNV053K63=downloading-a-collection-of-links h_01HKWSS511EDVWMAPHNGN711MG=%E9%87%8D%E8%A6%81 h_01HKWSS511SQR18RGSSKGTERCV=downloading-a-collection-of-qr-codes h_01HKWSS5112CT9HV7K81QSHMGM=%E6%B3%A8%E6%84%8F h_01HKWSS51125ZBCRQ087159YFH=adding-links-to-a-collection h_01HKWSS511AWCA4QV2NKVTTNKA=editing-links-in-a-collection h_01HKWSS512QYQBY0ZRE317528Z=%E6%B3%A8%E6%84%8F-1 h_01HKWSS512NZC3X8CPDDWB47JH=viewing-the-collection-history h_01HKWSS512RP5ATJWB38G88793=editing-the-collection-name h_01HKWSS512Q4MDFX75CK9VCREK=deleting-empty-collections h_01JQ69NF4SR7FT765JQP35B25G=%E9%87%8D%E8%A6%81%E3%81%AA%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85 empty-collections=%E7%A9%BA%E3%81%AE%E3%82%B3%E3%83%AC%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 h_01JQ69A1511N1GQFMBA2S748JK=%E7%A9%BA%E3%81%AE%E3%82%B3%E3%83%AC%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 general-information=%E4%B8%80%E8%88%AC%E6%83%85%E5%A0%B1 h_01HKWSS512JYNT3386P1KPZ452=%E4%B8%80%E8%88%AC%E6%83%85%E5%A0%B1 h_01HKWSS5123XVFKBZ892YCTFAC=%E6%B3%A8%E6%84%8F-2 h_01HKWSS5126A9XVE645CHCJD7X=upload-format h_01HKWSS512P7ZB213PCZ7JQTYP=parameters-in-the-uploaded-csv faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01K42S97K7KSKFC6BYEHPT0GZ5=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F qr-with-long-links-vs-short-links-%E2%80%93-is-there-any-difference=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVKGQZKAS1PZ3B9H20=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVTV0KP280D15JF7NB=can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example h_01K42Q4QQVV1RZZXZK2Y9W8R58=what-options-are-available-for-generating-qr-codes-in-appsflyer h_01K42Q4QQVZF4H8FYZCTJPR0RX=can-you-bulk-create-qr-codes" />
