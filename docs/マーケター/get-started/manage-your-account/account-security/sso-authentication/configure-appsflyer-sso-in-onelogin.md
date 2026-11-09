---
title: OneLoginでのAppsFlyer SSOの設定
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2023-05-04T07:41:06Z'
  edited_at: '2026-10-28T09:13:41Z'
  id: 15044997313041
  locale: ja
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ja/articles/15044997313041
---
> **概要：** OneLoginをIDプロバイダー（IdP）として使用する場合の、SSOの設定方法を説明します。

AppsFlyerのSSOを設定するには、まずOneLogin側で設定を行います。次の手順に従ってください。

<div id="create-the-appsflyer-app-in-oonelogin" />

<Accordion title="OneLoginでAppsFlyerアプリを作成する">

**前提条件：** 管理者権限のあるOneLoginアカウント。

1. OneLoginの管理コンソールで、**Applications**＞**<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>** に移動します。
2. 右上の**Add App**をクリックします。
3. **SAML Custom Connector (Advanced)** を検索して選択します。  

   <Image align="center" alt="onelogin_saml_app.png" src="https://files.readme.io/c1e5ec122e21f05e860486ad280ba9e692b3d05b05105d9c1ca700b8921ee6ab-15045173609745.png" width="601px" />
4. **Display Name**フィールドに、OneLoginプラグインのアプリ一覧に表示する名前を入力します。
5. ［任意］**App logo**：アプリ名の横に表示するロゴを追加します。
6. ［任意］説明を追加します。
7. **Save**をクリックします。画面上部に、設定が完了したことを示すメッセージが表示されます。
8. サイドメニューで**Configuration**タブに移動します。
9. 次の各項目を設定します。
   * **Audience (EntityID)：** <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com</Anchor>を入力します。
   * **ACS (Consumer) URL Validation**、**ACS (Consumer) URL：** OneLoginがユーザーの認証情報を送信するエンドポイントを入力します。<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">こちらのコールバックURLの設定説明</Anchor>に従って、該当するリンクを使用してください。
   * **Recipient：ACS (Consumer) URL**フィールドと同じURLを入力します。
   * **Login URL：** AppsFlyerの<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">ログインURL</Anchor>を入力します。
   * **SAML not valid before**、**SAML not valid on or after：** アサーション（認証結果を伝える情報）の有効期間を分単位で指定します。
   * **SAML initiator：** <Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">認証を開始する場所を選択します</Anchor>。
     * IdPから認証を開始する場合は、**OneLogin**を選択します。
     * AppsFlyerから認証を開始する場合は、**Service Provider**を選択します。
   * **SAML nameID format：** Emailを選択します。
   * **SAML issuer type：** Specificを選択します。
   * **SAML signature element：Both**を選択します。
   * **Encrypt assertion**：チェックボックスをオンにします。
   * **SAML encryption method：AES-256-CBC**を選択します。
10. **Save**をクリックします。
11. **Assertion encryption：** 
    1. <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">SSOメタデータのURL</Anchor>を開き、暗号化証明書の値をコピーします。
    2. **Configuration**タブに戻り、**SAML encryption**テキストボックスに貼り付けます。
    3. **Save**をクリックします。

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="IdPのSSOメタデータを取得する">

1. 対象アプリ（**Applications**＞**<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**）のサイドメニューで**SSO**を選択します。
2. **Issuer URL**をコピーして新しいタブに貼り付け、SSOメタデータをダウンロードします。

</Accordion>

<div id="create-onelogin-users" />

<Accordion title="OneLoginのユーザーを作成する">

1. 上部メニューで、**Users**＞<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/users">**Users**</Anchor>に移動します。
2. 右上の**New User**をクリックします。
3. ユーザーの**First name**、**Last name**、**Email**を入力します。
4. 右上の**Save User**をクリックし、**More Actions**＞**Change Password**を選択して、パスワードを設定します。
5. ユーザーのパスワードを設定し、**Update**をクリックします。

</Accordion>

<div id="assign-users-to-your-app" />

<Accordion title="ユーザーをアプリに割り当てる">

1. 対象ユーザーのサイドメニューで、**Application**タブに移動します。
2. **Applications**の横にある＋をクリックします。
3. 作成したAppsFlyerアプリを選択し、**Continue**をクリックします。  

   <Image align="center" alt="onelogin_assign_app.png" src="https://files.readme.io/a1769673f3f167f728a00fb1cccb951bd246798fd7327c51b021f73987bc8fb2-15552909316241.png" width="326px" />
4. 上部メニューで、**Applications**＞**<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>** に移動します。
5. 作成したアプリを選択します。
6. **Save**をクリックします。

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="AppsFlyerで設定を完了する">

IdP側の設定が完了したら、AppsFlyerに戻って<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">残りの設定を完了</Anchor>します。その後、<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">テスト</Anchor>して、正常に動作することを確認します。

</Accordion>

<div data-zendesk-anchors="h_01HF690GVE4FXXTMC5QWSJTY3C=create-the-appsflyer-app-in-oonelogin h_01HF690GVECMCVQAJFZ509MD50=get-idp-sso-metadata h_01HF690GVEKMV3TZ8MAD4HM635=create-onelogin-users h_01HF690GVEVEQ4GNJGXHKF5VT1=assign-users-to-your-app h_01HF690GVEWYEGR2Z9F22FQHGE=complete-the-process-in-appsflyer" />
