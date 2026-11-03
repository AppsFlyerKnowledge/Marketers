---
title: リダイレクト先ドメインの許可リストの設定
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
  created_at: '2024-05-15T11:31:00Z'
  edited_at: '2026-10-28T09:14:23Z'
  id: 25068636064529
  locale: ja
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ja/articles/25068636064529
---
> **概要：** リダイレクト先ドメインの許可リストを設定し、ユーザーを確認済みの信頼できるドメインにのみ誘導することで、データとブランドの信頼を守ります。

## <Image alt="Main redirect allowlist image.png" src="https://files.readme.io/a13b1c4641f4b265ef93ba9b65c57b0a7891336d6f6c21e94dd2ff5d83b948d6-30258741325713.png" width="1340px" />リダイレクト先の許可リストについて

リダイレクト先として許可するルートドメインやサブドメインを指定することで、不正なリダイレクト、フィッシング攻撃、不正行為からリンクを保護します。許可リストを有効にすると、AppsFlyerで作成したリンクは、リストに登録されたドメインのWeb URLにのみユーザーをリダイレクトします。それ以外の場合、ユーザーはアプリストアに移動します。リダイレクト先の許可リストは、<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">パートナー連携</Anchor>による単一プラットフォームの計測リンク、CTV・PC・コンソール向けの<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">直接計測リンク</Anchor>に適用されます。リダイレクト先の許可リストとWebリダイレクトのカスタマイズは、Zero、Growth、Enterpriseプランで利用できます。不正利用を防ぐため、Zeroプランではクレジットカードの登録が必要です（課金はされません）。

## リダイレクト先の許可リストの設定

許可リストは、手動またはCSVファイルで設定できます。設定前に、信頼できるドメインの一覧をセキュリティチームと確認することを推奨します。

<div id="manual-setup" />

<Accordion title="手動での設定">

**手動で設定するには、次の手順に従います。**

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。

![from account click security center Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. <strong>［リダイレクト先の許可リスト］</strong>セクションで、<strong>［リダイレクト先の許可リストを管理］</strong>をクリックします。

<Image alt="Manage redirect allowlist with arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="549px" />  

<strong>［リダイレクト先の許可リスト］</strong>ページが開きます。

3. <strong>［手動］</strong>タブで、<strong>［ドメイン名］</strong>フィールドにルートドメインまたはサブドメインを入力し、<strong>［ドメインをリストに追加］</strong>をクリックします。

<Image alt="Manually add domains.jpg" src="https://files.readme.io/95b37db2064ddba8c787d2dd5ac5ab2aa7698605f5c6eb3b4a59dd6324dee355-25103405228689.jpg" width="403px" />

* 英数字、ハイフン、ピリオドのみを使用してください。
* ドメインは、先頭と末尾が英字または数字で、最大253文字である必要があります。
* https://などの接頭辞は付けないでください。

許可リストの[仕様と制限事項](/docs/set-up-your-domain-redirect-allowlist#仕様と制限事項)も確認してください。

追加したドメインが、右側のリストに表示されます。

4. <strong>［リストを保存］</strong>をクリックします。

保存すると、約1時間以内にクリックに対して許可リストが適用されます。

</Accordion>

<div id="setup-via-csv-file" />

<Accordion title="CSVファイルでの設定">

**CSVファイルをアップロードして設定するには、次の手順に従います。**

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。  

![from account click security center Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. <strong>［リダイレクト先の許可リスト］</strong>セクションで、<strong>［リダイレクト先の許可リストを管理］</strong>をクリックします。  
<Image alt="Manage redirect allowlist with arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="530px" />  

<strong>［リダイレクト先の許可リスト］</strong>ページが開きます。

3. <strong>［CSVファイル］</strong>タブをクリックし、**CSVファイルの作成手順**に従って、ドメインの一覧を含むファイルを作成します。  
![CSV file upload.jpg](https://files.readme.io/2be73080048545f79e102e6f48df0db956e6739f156153c172c4fef5a2ea339f-25381979219345.jpg)

4. アップロード欄にCSVファイルをアップロードします。

* アップロード後にファイルが解析され、各値が検証されます。
* 有効な値は自動的に追加され、右側のリストに表示されます。
* 無効な値は追加されません。無効な値の情報は<strong>［アップロード状況］</strong>に表示されるため、内容を確認・修正して再アップロードしてください。詳細は、許可リストの[仕様と制限事項](/docs/set-up-your-domain-redirect-allowlist#仕様と制限事項)を参照してください。

5. <strong>［リストを保存］</strong>をクリックします。

保存すると、約1時間以内にクリックに対してリダイレクト先の許可リストが適用されます。

</Accordion>

<div id="edit-the-redirect-allowlist" />

<Accordion title="リダイレクト先の許可リストの編集">

許可リストのドメインは、いつでも追加・削除できます。

**ドメインを許可リストから削除するには、次の手順に従います。**

1. 右側のリストで削除するドメインにカーソルを合わせると、削除アイコンが表示されます。
2. 削除アイコンをクリックします。
3. <strong>［リストを保存］</strong>をクリックして、変更を保存します。

**注意：** 保存すると、約1時間以内に更新後の許可リストがクリックに適用されます。

</Accordion>

## 仕様と制限事項

| 項目 | 補足 |
| --- | --- |
| 設定 | <ul><li>リダイレクト先の許可リストにアクセスして管理できるのは、AdminロールとSecurityロールです。</li><li>許可リストはアカウント単位で設定され、アカウント内のすべてのアプリとAppsFlyerリンクに適用されます。</li><li>複数アカウントに所属するチームメンバーは、支払い方法が未登録のアカウントがある場合、リダイレクト先の許可リストを利用できません。</li><li>AppsFlyerリンクの作成を担当する社内メンバーや関係者に、許可リストが適用されることと、許可されたリダイレクト先ドメインを知らせてください。</li></ul> |
| 適用範囲 | <ul><li>許可リストは、作成時期にかかわらず、<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">パートナー連携</Anchor>による単一プラットフォームの計測リンク、CTV・PC・コンソール向けの<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">直接計測リンク</Anchor>など、**AppsFlyerで作成したすべてのリンク**に適用されます。</li><li>カスタムWebサイトやランディングページ、Google Play、App Store、そのほかのアプリストアを問わず、以下のリダイレクト設定に指定するURLのドメインを、許可リストに登録してください。許可リストは、次の設定によるリダイレクトに対応し、保護します。<ul><li>リンクパラメータ：<ul><li>`af_r`</li><li>`af_web_dp`</li><li>`af_ios_url`</li><li>`af_android_url`</li></ul></li><li>iOS、Android、デスクトップ向けのOneLinkテンプレートのリダイレクト設定。</li><li>値がWeb URLの`af_dp`にも対応しますが、この形式の値は推奨されません。このパラメータには、本来、アプリを開くための<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_dp">URIスキーム</Anchor>を設定します。</li></ul></li><li>**リンクのプレビューが代替表示になる場合：** AppsFlyerがSNS用のリンクプレビューを生成する際は、リダイレクトパラメータを許可リストと照合します。許可されていない場合、AppsFlyerはそのページのプレビューを取得せず、代替のプレビューを表示します。</li></ul> |
| ドメイン | <ul><li>許可リストには、少なくとも1件のドメインが必要です。</li><li>登録できるのはルートドメインまたはサブドメインのみで、特定のパスは指定できません。値に`https://`や`http://`のプロトコルは含めないでください。</li><li>ルートドメインを追加すると、その配下のすべてのサブドメインにも適用されます。<br />たとえば「website.com」を追加すると、「abc.website.com」と「xyz.website.com」も対象になります。</li><li>リダイレクト先として使用できるのは、外部からアクセスできる公開ドメインのみです。</li><li>リンクが意図したとおりにリダイレクトされるよう、AppsFlyerのドメイン（onelink.me、app.appsflyer.comなど）や、独自のリダイレクト機能を持つドメイン（bit.lyなど）は含めないでください。</li><li>許可リストには、ドメイン／サブドメインを最大250件追加できます。許可リストの画面に表示される件数から、登録済みのドメイン数を確認できます。</li></ul> |
| リダイレクト | リンクのリダイレクト先ドメインが許可されているか分からない場合は、次のいずれかを行います。<br /><br />許可リストに登録されていることを確認します。<br /><br />または<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/discover-your-campaign-link-parameters-and-behavior">Link Discovery</Anchor>ツールを使用します。リンクを入力した際に許可リストにないドメインがあると、<strong>［パラメータ］</strong>列の<strong>［リダイレクト］</strong>の下にアラートが表示されます。 |

<div data-zendesk-anchors="overview=%E3%83%AA%E3%83%80%E3%82%A4%E3%83%AC%E3%82%AF%E3%83%88%E5%85%88%E3%81%AE%E8%A8%B1%E5%8F%AF%E3%83%AA%E3%82%B9%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HYTJSH4YMAJ3CV88KZ9JD9XR=%E3%83%AA%E3%83%80%E3%82%A4%E3%83%AC%E3%82%AF%E3%83%88%E5%85%88%E3%81%AE%E8%A8%B1%E5%8F%AF%E3%83%AA%E3%82%B9%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 set-up-your-redirect-allowlist=%E3%83%AA%E3%83%80%E3%82%A4%E3%83%AC%E3%82%AF%E3%83%88%E5%85%88%E3%81%AE%E8%A8%B1%E5%8F%AF%E3%83%AA%E3%82%B9%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HY0BNRBEN91348744YME42SW=%E3%83%AA%E3%83%80%E3%82%A4%E3%83%AC%E3%82%AF%E3%83%88%E5%85%88%E3%81%AE%E8%A8%B1%E5%8F%AF%E3%83%AA%E3%82%B9%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HY04JEK8J3664HE8J9783S61=manual-setup h_01HY04JEK8Y51EG3H6WFKHYYH4=setup-via-csv-file h_01HY04JEK840Q4DZ2SRMTB7HRE=edit-the-redirect-allowlist traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
