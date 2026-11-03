---
title: IDプロバイダー（IdP）を使用したSSO認証の設定
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - login security
    - SSO
    - SSO verification
    - SSO certificate
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-11-02T10:50:55Z'
  edited_at: '2026-10-28T09:13:49Z'
  id: 360015017198
  locale: ja
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ja/articles/360015017198
---
> **概要：** AppsFlyerをIDプロバイダー（IdP）と連携すると、アカウントのユーザーがシングルサインオン（SSO）でAppsFlyerにログインできます。 SSO認証の設定と有効化、および別のログイン方法を割り当てる適用除外ユーザーの追加（任意）について説明します。

## 注意事項

* AppsFlyerとIDプロバイダー（IdP）の両方で、同じメールアドレスを使ってユーザーを登録する必要があります。
* SSOの設定を管理・削除できるのは、<strong>［ログインセキュリティ］</strong>の権限が<strong>［管理］</strong>に設定された管理者のみです。
* デフォルトでは、アカウント全体でSSOによるログインが必須です。
* 管理者は適用除外ユーザーを追加し、SSOまたは割り当てた代替方法でログインできるように設定できます。
* 適用除外ユーザーが利用できる代替ログイン方法は、次のとおりです。
  * ユーザー名とパスワード
  * 認証アプリ（2FA）
* 適用除外ユーザーの代替ログイン方法として、SMSは利用できません。
* 適用除外ユーザーを追加しなかった場合、有効化後はすべてのユーザーにSSOでのログインが必須となります。

> 📘 **注意**
>
> SSOを有効にする前に、信頼できる管理者を少なくとも1名、適用除外ユーザーに追加することを推奨します。 SSOの設定に誤りがあっても、アカウントにログインできなくなる事態を防げます。

## SSO設定ページを開く

1. 上部のバーでアカウントメニュー（管理者のメールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. <strong>［ログインセキュリティの強化］</strong>で、<strong>［ログイン方法を設定］</strong>を選択します。
3. <strong>［ログインセキュリティ］</strong>ページで、<strong>［SSOを設定］</strong>をクリックします。

## SSOの設定

以下の手順に従い、IdPとAppsFlyerの両方でSSOを設定します。 設定のステータスは、SSOが設定済みの場合は<strong>［有効］</strong>、未設定または設定を削除した場合は<strong>［未設定］</strong>になります。

> 📘 **注意**
>
> * このガイドでは、以下のIdPの設定手順を詳しく説明します。そのほかのIdPについては、共通の設定手順の概要を説明します。
>   * JumpCloud
>   * Okta
>   * OneLogin
>   * Ping Identity

<div id="step-1-set-up-the-idp-platform" />

<Accordion title="手順1：IdP側の設定">

以下のIdPでSSO認証を設定する詳細な手順を参照してください。

* <Anchor target="_blank" href="/marketers/ja/docs/configure-appsflyer-sso-in-jumpcloud">JumpCloud</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/configure-appsflyer-sso-in-okta">Okta</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/configure-appsflyer-sso-in-onelogin">OneLogin</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/configure-appsflyer-sso-in-ping-identity">Ping Identity</Anchor>

#### そのほかのIdPの設定概要

そのほかのIdPの設定手順は、次のとおりです。

* SAML 2.0プロトコルを使用してIdPにAppsFlyerアプリを作成し、[AppsFlyerの認証証明書](#the-authentication-certificate)をIdPに設定します。
* 作成したAppsFlyerアプリにユーザーを割り当てます。
* AppsFlyerに設定するIdPの証明書またはメタデータを取得します（[手順2：AppsFlyer側の設定→5. IdPメタデータの登録](#step-5-provide-idp-metadata)を参照）。

> 📘 **注意**
>
> * **重要** IdPにユーザーを割り当てる際は、各ユーザーのメールアドレスがAppsFlyerと同じになるよう、必ず同一のアドレスを使用してください。
> * <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">AppsFlyerのメタデータ</Anchor>には、次のものが含まれます。
>   * 暗号化証明書と署名証明書
>   * エンティティID
>   * コールバックURL

<div id="step-2-set-up-appsflyer" />

<Accordion title="手順2：AppsFlyer側の設定">

IdP側の設定が完了したら、以下の手順でAppsFlyerにSSO認証を設定します。

[SSO設定ページを開く方法](#sso設定ページを開く)を確認してください。

<div id="step-1-select-authentication-starting-point" />

<Accordion title="1. 認証を開始する場所を選択する">

1. ユーザーがどこからAppsFlyerにアクセスするかを選択します。この選択によって、認証の手順も決まります。
   * [IDプロバイダー（IdP）](#idプロバイダーidp)
   * [サービスプロバイダー（AppsFlyer）](#サービスプロバイダーappsflyer)
2. <strong>［次へ］</strong>をクリックします。

#### IDプロバイダー（IdP）

ユーザーはIdPの認証プラグインやWebページからログインし、認証後にAppsFlyerへ移動します。

> 📘 **注意**
>
> このオプションを選択すると、IdPとサービスプロバイダー（AppsFlyer）のどちらからでもログインできます。

#### サービスプロバイダー（AppsFlyer）

ユーザーは<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-callback">AppsFlyerのSSOログインページ</Anchor>で<strong>［SSOでログイン］</strong>をクリックし、メールアドレスを入力します。認証のためにIdPへ移動し、認証後にAppsFlyerのホームページへ戻ります。

[<Image alt="AppsFlyer_login_page.png" src="https://files.readme.io/fb80e44cf0cad29349ec85f75f65de73041b1787b278ae9d96449783580faeaa-17233244722577.png" width="257px" />](https://files.readme.io/fb80e44cf0cad29349ec85f75f65de73041b1787b278ae9d96449783580faeaa-17233244722577.png)

> 📘 **注意**
>
> このオプションを選択すると、サービスプロバイダー（AppsFlyer）からのみログインでき、IdPから直接ログインすることはできません。

<div id="step-3-select-certificate-type" />

<Accordion title="2. 証明書の種類を選択する">

AppsFlyerは、データの暗号化とSSOリクエストの署名に使用する公開鍵証明書を、2種類提供しています。

* **AppsFlyer署名証明書：** <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">AppsFlyerのメタデータURL</Anchor>から作成する、AppsFlyerの証明書。
* **CA署名証明書：Amazonが署名した**AppsFlyerの証明書。

**次の手順で選択します。**

* 証明書の種類を選択し、<strong>［次へ］</strong>をクリックします。

> 📘 **注意**
>
> AppsFlyerにIdPのSAML設定を登録し、IdPにAppsFlyerの最新SSOメタデータを登録して、双方の証明書の設定が完了すると、証明書が有効になります。具体的な手順は、以下で説明します。

</Accordion>

<div id="step-4-obtain-service-provider-appsflyer-metadata" />

<Accordion title="3. サービスプロバイダー（AppsFlyer）のメタデータを取得する">

1. AppsFlyerの最新SSOメタデータをコピーし、IdPのSAML設定に登録します。
   * **AppsFlyer署名証明書**を選択した場合は、以下のいずれかの情報をコピーします。
     * **メタデータURL：** メタデータURL全体の読み込みに対応するIdPでは、URLをコピーしてIdPに設定します。
     * **メタデータの構成要素：** メタデータURL全体の読み込みに対応しないIdPでは、**エンティティID**、**暗号化キー**（ダウンロード可能）、**Location URL**をそれぞれコピーし、IdPの対応する項目に設定します。
     * **XMLファイル：** AppsFlyerのSSOメタデータを、XMLファイルとしてダウンロードすることもできます。
   * **CA署名証明書**を選択した場合は、**メタデータの構成要素**をコピーします。
2. <strong>［次へ］</strong>をクリックします。

</Accordion>

<div id="step-5-provide-idp-metadata" />

<Accordion title="4. IdPメタデータを登録する">

以下の方法でIdPのSSOメタデータを登録し、メタデータの形式を検証します。**注意**：IdP証明書のデータは、メタ文字を含まない1行の形式である必要があります。

1. IdPメタデータの登録方法を選択します。
   * **URL：** IdPのメタデータURLを入力します。
   * **XMLファイル：** IdPのメタデータXMLファイルをアップロードします。
2. <strong>［検証］</strong>をクリックします。検証結果を示す確認メッセージが、ページ上部に表示されます。
3. <strong>［有効化］</strong>をクリックします。 SSO認証の有効化の結果を示す確認メッセージが、ページ上部に表示されます。

</Accordion>

<div id="5-add-exception-users" />

<Accordion title="5. 適用除外ユーザーを追加する">

適用除外ユーザーとは、SSOでのログインが必須ではないユーザーです。アカウント全体ではSSOでのログインが必須ですが、明示的に適用除外ユーザーに追加されたユーザーだけは、割り当てられた代替方法でもログインできます。

適用除外ユーザーの追加は任意です。適用除外ユーザーを追加しなかった場合、有効化後は全ユーザーにSSOでのログインが必須となります。

> 📘 **注意**
>
> SSOを有効にする前に、信頼できる管理者を少なくとも1名、適用除外ユーザーに追加してください。 SSOの設定に誤りがあっても、このユーザーが割り当てられた代替方法でログインし、設定を修正できます。

適用除外ユーザーを追加するには、次の手順に従います。

1. <strong>［適用除外ユーザーを追加］</strong>をクリックします。
2. <strong>［適用除外ユーザーの追加］</strong>ダイアログで、氏名またはメールアドレスを使ってユーザーを検索します。
3. 追加するユーザーを選択します。
4. <strong>［代替ログイン方法］</strong>のドロップダウンリストで、次のいずれかを選択します。
   * **ユーザー名とパスワード**
   * **認証アプリ**
5. 追加するユーザーごとに、手順2～4を繰り返します。
6. <strong>［適用除外ユーザーを追加］</strong>をクリックします。

### **複数のユーザーにログイン方法をまとめて設定する**

複数の適用除外ユーザーに同じ代替ログイン方法を設定するには、次の手順に従います。

1. 設定を変更するユーザーのチェックボックスを選択します。
2. <strong>［選択したユーザーのログイン方法を設定］</strong>をクリックします。
3. 次のいずれかを選択します。
   * **選択したすべてのユーザーにユーザー名とパスワードを適用**
   * **選択したすべてのユーザーに認証アプリを適用**

### **適用除外ユーザーを削除する**

適用除外ユーザーのリストからユーザーを削除するには、次の手順に従います。

* ユーザーの行の<strong>［削除］</strong>アイコンをクリックします。

そのユーザーは、リストからすぐに削除されます。

</Accordion>

<div id="6-activate-sso" />

<Accordion title="6. SSOを有効化する">

> 📘 **注意**
>
> SSOを有効にする前に、信頼できる管理者を少なくとも1名、適用除外ユーザーに追加することを推奨します。 SSOの設定に誤りがあっても、アカウントにログインできなくなる事態を防げます。

SSOを有効にするには、次の手順に従います。

1. <strong>［SSOを有効化］</strong>をクリックします。
2. <strong>［SSOを有効にしますか？］</strong>ダイアログで、SSOの設定内容を確認します。
3. <strong>［SSOを有効化］</strong>をクリックします。

設定に誤りがあると、ユーザーがAppsFlyerにログインできなくなることがあります。 SSOを有効にする前に、設定内容を確認してください。

適用除外ユーザーが追加されていない場合、確認ダイアログには、有効化後は全ユーザーにSSOでのログインが必須になることを示すメッセージが表示されます。

### **有効化の結果**

| **結果** | **説明** |
| --- | --- |
| SSOの有効化と、適用除外ユーザーの追加が完了 | SSOが有効になり、適用除外ユーザーも設定済みです。 |
| SSOは有効になったものの、一部の適用除外ユーザーが追加されなかった場合 | SSOは有効のままです。 <strong>［SSOを編集］</strong>から、適用除外ユーザーを追加・更新してください。 |
| SSOの有効化に失敗した場合 | SSOは有効にならず、設定のステータスは<strong>［未設定］</strong>に戻ります。 |

## **SSOの編集**

SSOの有効化後は、SSOの設定の編集と、適用除外ユーザーの管理ができます。

SSOの設定を編集するには、次の手順に従います。

1. <strong>［SAMLシングルサインオン（SSO）］</strong>セクションで、<strong>［編集］</strong>アイコンをクリックします。
2. 更新するセクションを開きます。
3. 必要な変更を行います。
4. **Save**をクリックします。
5. <strong>［変更を保存しますか？］</strong>ダイアログで、変更内容を確認します。
6. <strong>［変更を保存］</strong>をクリックします。

証明書の種類や認証を開始する場所を変更すると、AppsFlyerのメタデータも変更されます。変更を保存したら、サービスプロバイダー（AppsFlyer）の最新SSOメタデータをすぐにコピーし、IdPのSAML設定に登録してください。

### **適用除外ユーザーの編集**

適用除外ユーザーを編集するには、次の手順に従います。

1. SSOの編集ページで、<strong>［適用除外ユーザー］</strong>セクションを開きます。
2. <strong>［適用除外ユーザーを編集］</strong>をクリックします。
3. <strong>［適用除外ユーザーを編集］</strong>ダイアログで、ユーザーの追加・削除、または代替ログイン方法の更新を行います。
4. **Save**をクリックします。
5. <strong>［変更を保存しますか？］</strong>ダイアログで、<strong>［変更を保存］</strong>をクリックします。

登録済みの適用除外ユーザーには、現在の代替ログイン方法が表示されます。

</Accordion>

</Accordion>

<div id="step-3-test-the-sso-configuration" />

<Accordion title="手順3：SSO設定のテスト">

IdPとAppsFlyerの両方で設定が完了したら、IdPまたはサービスプロバイダー（AppsFlyer）の[URLコールバック方式](#single-signon-url-configuration)の**いずれか一方**で、AppsFlyerにログインできることを確認します（両方を使うものではありません）。

#### IdP経由の認証をテストする

IdPからログインする方式を設定した場合は、IdPのプラグインまたはWebページからAppsFlyerにアクセスできることを、次の手順で確認します。

1. AppsFlyerとIdPにログインしている場合は、両方からログアウトします。
2. ブラウザでシークレットモードのページを開きます。
3. IdPのWebページに移動します。 IdPにログインしていないため、認証の手順が表示されます。対象ユーザーでログインします。
4. AppsFlyerを検索して選択します。 AppsFlyerのホームページに移動します。この画面に移動できれば、正常に動作しています。

#### サービスプロバイダー（AppsFlyer）経由の認証をテストする

サービスプロバイダー（AppsFlyer）からログインする方式を設定した場合は、次の手順で、メールアドレスを使ってAppsFlyerにアクセスできることを確認します。

<Image alt="log_in_to_af_by_email2.png" src="https://files.readme.io/ae22ff9ba0216f54bee4cea82ed7d35cea656a68e30c0a0e4f549b1855ec7cfd-17233244746257.png" width="245px" />

1. AppsFlyerとIdPにログインしている場合は、両方からログアウトします。
2. ブラウザでシークレットモードのページを開きます。
3. <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">AppsFlyerのログインページ</Anchor>で、<strong>［SSOでログイン］</strong>をクリックします。
4. 対象ユーザーのメールアドレスを入力し、<strong>［続行］</strong>をクリックします。認証のため、IdPに移動します。
5. IdPで認証されると、ログイン済みの状態でAppsFlyerに戻ります。この画面に移動できれば、正常に動作しています。

</Accordion>

</Accordion>

</Accordion>

## SSO設定の管理

SSOの設定後も、設定の編集や削除ができます。

[SSO設定ページを開く方法](#sso設定ページを開く)を確認してください。

<div id="edit-sso" />

<Accordion title="SSOの編集">

このページでは、次の項目を編集できます。

* 認証を開始する場所
* 証明書の種類
* サービスプロバイダーのメタデータ
* IDプロバイダーのメタデータ
* 適用除外ユーザー

> 🚧 **重要**
>
> 証明書の種類や認証を開始する場所を変更すると、AppsFlyerのメタデータも変更されます。変更を保存したら、AppsFlyerからサービスプロバイダーの最新メタデータをすぐにコピーし、IDプロバイダー（IdP）のSAML設定に登録してください。

> 📘 **注意**
>
> 信頼できる管理者を少なくとも1名、適用除外ユーザーに追加してください。 SSOの設定に誤りがあっても、このユーザーが割り当てられた代替方法でログインし、設定を修正できます。

SSOの設定を編集するには、次の手順に従います。

1. <strong>［SAMLシングルサインオン（SSO）］</strong>セクションで、<strong>［編集］</strong>アイコンをクリックします。
2. 更新するセクションを開きます。
3. 必要な変更を行います。
4. **Save**をクリックします。
5. <strong>［変更を保存しますか？］</strong>ダイアログで、変更内容を確認します。
6. <strong>［変更を保存］</strong>をクリックします。

### 適用除外ユーザーの編集

適用除外ユーザーを編集するには、次の手順に従います。

1. <strong>［適用除外ユーザー］</strong>セクションを開きます。
2. <strong>［適用除外ユーザーを編集］</strong>をクリックします。
3. <strong>［適用除外ユーザーを編集］</strong>のユーザー一覧で、ユーザーの追加・削除、または代替ログイン方法の更新を行います。
4. **Save**をクリックします。
5. <strong>［変更を保存しますか？］</strong>ダイアログで、<strong>［変更を保存］</strong>をクリックします。

登録済みの適用除外ユーザーには、現在の代替ログイン方法が表示されます。

</Accordion>

<div id="remove-sso-configuration" />

<Accordion title="SSO設定の削除">

SSOの設定を削除するには、次の手順に従います。

1. <strong>［SAMLシングルサインオン（SSO）］</strong>セクションで、<strong>［削除］</strong>アイコンをクリックします。
2. 確認ダイアログで、設定の削除による影響を確認します。
3. <strong>［削除］</strong>をクリックします。

SSOの設定を削除すると、アカウントに保存されたSSOメタデータと設定が削除されます。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 名前 | 説明 |
| --- | --- |
| メールアドレス内の記号 | SSOでは、＋記号を含むメールアドレスには対応していません。<br /><br />例：my+customer@demo.com<br /><br />このようなアドレスを使用すると、ログインに失敗します。 |
| 適用除外ユーザー | 適用除外ユーザーは、管理者が明示的に追加する必要があります。 |
| 代替ログイン方法 | 代替ログイン方法として、**ユーザー名とパスワード**、または**認証アプリ**を利用できます。 |
| SMS認証 | 適用除外ユーザーの代替ログイン方法として、SMSは利用できません。 |
| 適用除外ユーザーがいない場合 | 適用除外ユーザーを追加しなかった場合、有効化後はすべてのユーザーにSSOでのログインが必須となります。 |
| 権限 | SSOの設定と適用除外ユーザーの管理を行うには、管理者の<strong>［ログインセキュリティ］</strong>の権限が<strong>［管理］</strong>に設定されている必要があります。 |
| 閲覧のみの権限 | <strong>［ログインセキュリティ］</strong>の権限が閲覧のみの管理者は、SSOページを表示できますが、SSOの設定や適用除外ユーザーを編集できません。 |
| 従来のUnforce SSO設定からの移行 | 従来のアカウント全体のUnforce SSO設定から移行したアカウントでは、ユーザー名とパスワードを使っていた既存ユーザーが、適用除外ユーザーに追加されます。新規ユーザーは、管理者が明示的に適用除外ユーザーに追加しない限り、SSOでログインする必要があります。 |
| 推奨する適用除外ユーザー | SSOを有効にする前に、信頼できる管理者を少なくとも1名、適用除外ユーザーに追加することを推奨します。 SSOの設定に誤りがあっても、アカウントにログインできなくなる事態を防げます。 |

</Accordion>

> 📄 **関連情報**
>
> <Anchor target="_blank" href="/marketers/ja/docs/sso-authentication-overview-and-faq">SSO認証の概要とよくある質問</Anchor>
>
> <Anchor target="_blank" href="/marketers/ja/docs/manage-exception-users-for-sso">SSOの適用除外ユーザーの管理について</Anchor>

<div data-zendesk-anchors="considerations=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85 h_01J7KK52TX8WGA3EK110R9M0GY=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85 h_01KSM8FMC9SCPBY2P56QPD6WJ2=%E6%B3%A8%E6%84%8F access-the-sso-configuration-page=sso%E8%A8%AD%E5%AE%9A%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E9%96%8B%E3%81%8F h_01J7X4Y5Y50EFAPVP6JY8WAMKN=sso%E8%A8%AD%E5%AE%9A%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E9%96%8B%E3%81%8F setting-up-sso-authentication=sso%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HCHG901V25TSRGRT9244384D=sso%E3%81%AE%E8%A8%AD%E5%AE%9A h_01J530X1930CMCF7XJM1XKPC74=%E6%B3%A8%E6%84%8F-1 01J530ZP34SQKHM5324DNFA25Y=step-1-set-up-the-idp-platform configuration-overview-for-other-idp-platforms=%E3%81%9D%E3%81%AE%E3%81%BB%E3%81%8B%E3%81%AEidp%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%A6%82%E8%A6%81 h_01HCHG901VPG0ZJ20XJBFPY7CD=%E3%81%9D%E3%81%AE%E3%81%BB%E3%81%8B%E3%81%AEidp%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%A6%82%E8%A6%81 h_01HCHG901VH2XZS9Q0KM9D26WX=%E6%B3%A8%E6%84%8F-2 h_01J5303SNTEVQNA4KZEMS2VG04=step-2-set-up-appsflyer h_01J4PGJ2T73313B1X6ECQ17S7Q=step-1-select-authentication-starting-point identity-provider-idp=id%E3%83%97%E3%83%AD%E3%83%90%E3%82%A4%E3%83%80%E3%83%BCidp h_01J4PHJ8FECGSAGQJGWREX3PKK=id%E3%83%97%E3%83%AD%E3%83%90%E3%82%A4%E3%83%80%E3%83%BCidp h_01J4PHSVS55G2M00S00KG06BB7=%E6%B3%A8%E6%84%8F-3 service-provider-appsflyer=%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%83%97%E3%83%AD%E3%83%90%E3%82%A4%E3%83%80%E3%83%BCappsflyer h_01J4PHTR1E9JV3SM0A7N4X3WJY=%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%83%97%E3%83%AD%E3%83%90%E3%82%A4%E3%83%80%E3%83%BCappsflyer h_01J4PJEQTBJ9P2SZBKGPF2696S=%E6%B3%A8%E6%84%8F-4 h_01J4PGJ2T76F7YTK42VBW8J1P6=step-3-select-certificate-type h_01J8CEE2BZN0THJ7DNSGRCGJNQ=%E6%B3%A8%E6%84%8F-5 h_01J4PGJ2T76PKE0V7NS7YXC4T5=step-4-obtain-service-provider-appsflyer-metadata h_01J4PGJ2T7SM8EGYZCW6D7AQN8=step-5-provide-idp-metadata h_01KSM7TN32SDETTPJRX5WPR707=5-add-exception-users h_01KSM8FMC91SDE8JQS12J7WXAG=%E6%B3%A8%E6%84%8F-6 add-login-methods-for-multiple-users=%E8%A4%87%E6%95%B0%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B3%E6%96%B9%E6%B3%95%E3%82%92%E3%81%BE%E3%81%A8%E3%82%81%E3%81%A6%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KSM7WDKE0PGCMFC6JCKTC107=%E8%A4%87%E6%95%B0%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B3%E6%96%B9%E6%B3%95%E3%82%92%E3%81%BE%E3%81%A8%E3%82%81%E3%81%A6%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B delete-an-exception-user=%E9%81%A9%E7%94%A8%E9%99%A4%E5%A4%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B h_01KSM7WDKFBFDN7TQVK4YWH3FR=%E9%81%A9%E7%94%A8%E9%99%A4%E5%A4%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B h_01KSM7TN324FN2QS5W6XBY91ES=6-activate-sso h_01KSM8H456C2SFE9E21HNAWFQM=%E6%B3%A8%E6%84%8F-7 activation-results=%E6%9C%89%E5%8A%B9%E5%8C%96%E3%81%AE%E7%B5%90%E6%9E%9C h_01KSM7YKYJ22W6TM1Q2EQGAAZ9=%E6%9C%89%E5%8A%B9%E5%8C%96%E3%81%AE%E7%B5%90%E6%9E%9C edit-sso::496a151=sso%E3%81%AE%E7%B7%A8%E9%9B%86 h_01KSM7YKYPNA5MZKMZH7K5R09S=sso%E3%81%AE%E7%B7%A8%E9%9B%86 edit-exception-users=%E9%81%A9%E7%94%A8%E9%99%A4%E5%A4%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E7%B7%A8%E9%9B%86 h_01KSM7YKYSVF5ZSMSYK5HPQJQ0=%E9%81%A9%E7%94%A8%E9%99%A4%E5%A4%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E7%B7%A8%E9%9B%86 h_01J5303SNTYMDMP2DW4GQCGEHK=step-3-test-the-sso-configuration testing-authentication-via-the-idp=idp%E7%B5%8C%E7%94%B1%E3%81%AE%E8%AA%8D%E8%A8%BC%E3%82%92%E3%83%86%E3%82%B9%E3%83%88%E3%81%99%E3%82%8B h_01HCHG901WXSQ2VPCH2NKE63SE=idp%E7%B5%8C%E7%94%B1%E3%81%AE%E8%AA%8D%E8%A8%BC%E3%82%92%E3%83%86%E3%82%B9%E3%83%88%E3%81%99%E3%82%8B testing-authentication-via-appsflyer=%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%83%97%E3%83%AD%E3%83%90%E3%82%A4%E3%83%80%E3%83%BCappsflyer%E7%B5%8C%E7%94%B1%E3%81%AE%E8%AA%8D%E8%A8%BC%E3%82%92%E3%83%86%E3%82%B9%E3%83%88%E3%81%99%E3%82%8B h_01HCHG901W6DJ3GN6E7WFR6RNK=%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%83%97%E3%83%AD%E3%83%90%E3%82%A4%E3%83%80%E3%83%BCappsflyer%E7%B5%8C%E7%94%B1%E3%81%AE%E8%AA%8D%E8%A8%BC%E3%82%92%E3%83%86%E3%82%B9%E3%83%88%E3%81%99%E3%82%8B manage-sso-configuration=sso%E8%A8%AD%E5%AE%9A%E3%81%AE%E7%AE%A1%E7%90%86 h_01J7WKPGTNPF10N4XMJG9ZDN87=sso%E8%A8%AD%E5%AE%9A%E3%81%AE%E7%AE%A1%E7%90%86 h_01J7X4P6B18HXJB99JYTVSC75N=edit-sso h_01KSMFXHV6501KFVD9SCCMJCF9=%E9%87%8D%E8%A6%81 h_01KSMFXHV6NJ4PKQ5117HB5B4H=%E6%B3%A8%E6%84%8F-8 edit-exception-users::6da5a820=%E9%81%A9%E7%94%A8%E9%99%A4%E5%A4%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E7%B7%A8%E9%9B%86-1 h_01KSMFSP2QXYEQWB2CM4YHTTS0=%E9%81%A9%E7%94%A8%E9%99%A4%E5%A4%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E7%B7%A8%E9%9B%86-1 h_01J7X4P6B1THTVR1M966JS4P99=remove-sso-configuration h_01K44S4WP3N8HG872PQX1CCES8=traits-and-limitations h_01HDPF69BTMRYR6E6VNMFR4JY4=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
