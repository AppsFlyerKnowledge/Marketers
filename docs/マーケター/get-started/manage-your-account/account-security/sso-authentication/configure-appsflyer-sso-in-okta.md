---
title: OktaでのAppsFlyer SSOの設定
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
  created_at: '2023-02-12T13:10:51Z'
  edited_at: '2026-10-28T09:13:38Z'
  id: 12934808889745
  locale: ja
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ja/articles/12934808889745
---
> **概要：** OktaをIDプロバイダー（IdP）として使用する場合の、SSOの設定方法を説明します。

AppsFlyerのSSOを設定するには、まずOkta側で設定を行います。次の手順に従ってください。

<div id="create-the-appsflyer-app-in-okta" />

<Accordion title="OktaでAppsFlyerアプリを作成する">

**前提条件：** 管理者権限のあるOktaアカウント。

1. Admin Consoleで**Applications**＞**Applications**に移動します。  
   <Image alt="Okta_side_menu___applications.png" src="https://files.readme.io/c218e729a7c00158e3804e7c7d884ec5b098e56628037ced54ad3c311470e038-13572360791825.png" width="241px" />
2. **Create App Integration**をクリックします。
3. **Create a new app integration**ダイアログで**SAML 2.0**を選択し、**Next**をクリックします。
4. **(1) General Settings**の**App name**フィールドに、Oktaプラグインのアプリ一覧に表示する名前を入力します。  
   <Image alt="Okta_app_name_and_icon__1_.png" src="https://files.readme.io/6998e7737b0aa5c4d70ad97ab41e17e471ddaf060e78c44fa2de41be1df17574-13572380565521.png" width="639px" />
5. ［任意］**App logo**：アプリ名の横に表示するロゴを追加します。
6. **Next**をクリックします。
7. **(2) Configure SAML Integration**で、次の各項目を設定します。 ![okta-create-saml-integration.png](https://files.readme.io/6c276dd54afd30e828b989fc6796de5eca46282ade015e7a34e0bd1cc95d7fb8-16870970396177.png)
   * **Single sign-on URL：** Oktaがユーザーの認証情報を送信するエンドポイントを入力します。<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">こちらのコールバックURLの設定説明</Anchor>に従って、該当するリンクを使用してください。
   * **Audience URI (SP Entity ID)：** <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com</Anchor>を入力します。
   * **Name ID format：** ユーザーを識別する形式として、**EmailAddress**を選択します。
   * **Application username：Okta username**を選択します。  
     **注意：** Oktaユーザーのメールアドレスは、AppsFlyerアカウントのメールアドレスと一致している必要があります。
8. **Show Advanced Settings**をクリックし、以下の画像の各項目に従って設定します。

   <Image alt="Okta_advanecd_settings__1_.png" src="https://files.readme.io/9a3461f700cc50a54237578a304206ed7693e30cdd516398089954321cd44af4-13572576788241.png" width="640px" />

   * **Assertion Encryption：Encrypted**（暗号化）または**Unencrypted**（暗号化なし）を選択します。   
     **注意：** アサーション（認証結果を伝える情報）はIdPが管理するため、**Encrypted**の選択を推奨します。
   * **Encryption certificate：** <Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#obtaining-the-appsflyer-certificate-from-the-metadata-url">AppsFlyerの暗号化証明書</Anchor>をアップロードします。この証明書はAppsFlyerが署名したもので、リクエストの暗号化と署名の両方に使用されます。
   * ［任意］**Signature certificate：** <Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#the-authentication-certificate">AppsFlyerの署名証明書</Anchor>をアップロードします。
9. ページの最下部までスクロールし、**Next**をクリックします。
10. **I’m an Okta customer adding an internal app**を選択し、**Finish**をクリックします。

</Accordion>

<div id="create-okta-users" />

<Accordion title="Oktaのユーザーを作成する">

OktaのSAMLアプリを作成したら、ユーザーを追加します。

1. Admin Consoleで、**Directory**＞**People**を選択します。

   <Image alt="Okta___directory___people.png" src="https://files.readme.io/d9c5da8787fdb81bf97bc0753b2f7794cdc59060e5026348428545064d138d18-13572579297169.png" width="226px" />
2. **Add Person**をクリックします。

   <Image alt="Okta___People___Add_person.png" src="https://files.readme.io/6bb8b854cf000259970d63b9eacb28bf6d4079d648939814aaa0e456a96c9bbe-13572600647697.png" width="524px" />
3. **Add Person**ダイアログで、次の設定を行います。

   <Image alt="Okta_Add_person__1_.png" src="https://files.readme.io/d6d7e198fab965872b5a01302a00bdbd0bfb5d561af372fc4390c9882a22a42c-13572617052689.png" width="620px" />

   * **User type**で、**User**を選択します。
   * 必須項目の**First name**、**Last name**、**Username**（メールアドレス）、**Primary email**を入力します。
   * **Password**では、ユーザー自身が設定するか、管理者が設定するかを選択できます。
4. 続けてユーザーを追加する場合は、**Save and Add Another**をクリックし、手順1～4を繰り返します。すべてのユーザーを追加したら、**Save**をクリックします。

</Accordion>

<div id="assign-users-to-your-app" />

<Accordion title="ユーザーをアプリに割り当てる">

1. Admin Consoleで、**Applications**＞**Applications**に戻ります。
2. **Browse App Catalog**で、作成したアプリを選択します。  
   <Image alt="Okta_side_menu___applications.png" src="https://files.readme.io/c218e729a7c00158e3804e7c7d884ec5b098e56628037ced54ad3c311470e038-13572360791825.png" width="233px" />
3. 選択したアプリの**Assignments**タブで、**Assign**＞**Assign to People**をクリックします。  
   ![Okta_sso_assign_to_people.png](https://files.readme.io/50930693a4a58ad8162b2ac81e476081c9b0288da4dab5b92bb41fece4aff586-14942267242769.png)
4. アプリに割り当てるユーザーを探し、**Assign**をクリックします。
5. すべてのユーザーについて、この操作を繰り返します。
6. すべてのユーザーを追加したら、**Done**をクリックします。追加したユーザーが、**People**に表示されます。

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="IdPのSSOメタデータを取得する">

1. Admin Consoleで、**Applications**＞**Applications**に戻ります。
2. **Browse App Catalog**で、対象のアプリを選択します。
3. **Sign On**タブをクリックします。
4. **SAML Signing Certificates**セクションで、有効な証明書の**Actions**＞**View IdP metadata**をクリックします。 <Image alt="okta_sso_view_idp_metadata.png" src="https://files.readme.io/a6d9f6753ead962713851bcc367abba6fad226d6e0a5f908055e44b1d3e1b2be-14942369009809.png" width="601px" />
5. 開いたタブのURLをコピーします。このURLは、次のAppsFlyer側の設定で使用します。

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="AppsFlyerで設定を完了する">

IdP側の設定が完了したら、AppsFlyerに戻って<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">残りの設定を完了</Anchor>します。その後、<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">テスト</Anchor>して、正常に動作することを確認します。

</Accordion>

<div id="see-also" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="https://developer.okta.com/docs/guides/build-sso-integration/openidconnect/main/">OktaのSSOドキュメント</Anchor>

<div data-zendesk-anchors="h_01HDNZYDQGGBMB9MJ97RF4BADM=create-the-appsflyer-app-in-okta h_01HDNZYDQGGFCA2KB9PDQY1ZTG=create-okta-users h_01HDNZYDQGC9MRQH92MM8W4FVE=assign-users-to-your-app h_01HDNZYDQGWRE9K6XG5EPYTYYX=get-idp-sso-metadata h_01HDNZYDQG6GNEP3TQMXVT5FTG=complete-the-process-in-appsflyer h_01HDP00WTAVP0X8FT51JC1JKKC=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
