---
title: Ping IdentityでのAppsFlyer SSOの設定
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - security
    - Marketers
    - authentication
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
  created_at: '2023-06-11T09:28:10Z'
  edited_at: '2026-10-28T09:13:43Z'
  id: 16062655361937
  locale: ja
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ja/articles/16062655361937
---
> **概要：** Ping IdentityをIDプロバイダー（IdP）として使用する場合の、SSOの設定方法を説明します。

AppsFlyerのSSOを設定するには、まずPing Identity側で設定を行います。次の手順に従ってください。

<div id="create-the-appsflyer-app-in-ping" />

<Accordion title="Ping IdentityでAppsFlyerアプリを作成する">

**前提条件：** 管理者権限のあるPing Identityアカウント。

1. Ping Identityの管理メニューで **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** に移動し、＋をクリックします。
2. 右側に開いたセクションで、次の設定を行います。
   * Ping Identityプラグインのアプリ一覧に表示する名前を入力します。
   * アプリの種類にSAML Applicationを選択します。
3. **Configure**をクリックします。 SAML Configurationが表示されます。
   * サービスプロバイダー（AppsFlyer）から認証を開始する場合は、**Import From URL**を選択します。
     * **Import URL：** <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">https://hq1.appsflyer.com/auth/sso-metadata</Anchor>
     * **ACS URLs：** AppsFlyerのアカウントIDを使用して、次のリンクを入力します。  
       <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-callback">https://hq1.appsflyer.com/auth/sso-callback</Anchor>
     * **Entity ID：** <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com/</Anchor>を入力します。  

       <Image alt="ping" src="https://files.readme.io/8b265666f05bc4f6ab984151d7d73653b9ea5dcb837898d17e96bf9c392fe638-16063467179921.png" width="419px" />
   * IdP（Ping Identity）から認証を開始する場合は、**Manually Enter**を選択します。
     * **ACS URLs：** AppsFlyerのアカウントIDを使用して、次のリンクを入力します。  
       `https://hq1.appsflyer.com/auth/sso-callback/<Enter your AppsFlyer account ID here>`
     * **Entity ID：** <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com/</Anchor>を入力します。
4. **Save**をクリックします。
5. **Configuration**タブで、次の設定を行います。
   1. **Download Metadata**をクリックします。
   2. 右上の編集アイコンをクリックし、次の項目を入力します。  

      <Image alt="ping" src="https://files.readme.io/386fab01b9389d88ea0c4870ba2ea8e33d9ab6e27322059be5e46efbf248714b-16063435689233.png" width="487px" />

      * **SIGNING KEY：**
        * **Sign Assertion & Response**を選択します。
        * **Signing Algorithm：RSA\_SHA256**を選択します。
      * **ENCRYPTION：**
        * **Enable Encryption**を選択します。
        * ALGORITHM：**AES\_256**を選択します。
      * **CERTIFICATE：**
        * **Import**を選択し、<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#obtaining-the-appsflyer-certificate-from-the-metadata-url">AppsFlyerの暗号化証明書</Anchor>をアップロードします。この証明書はAppsFlyerが署名したもので、リクエストの暗号化と署名の両方に使用されます。  
          **注意：** Amazonが署名したAppsFlyerの証明書もアップロードできます。この証明書の取得については、担当CSMにお問い合わせください。
        * **Enforced Signed Authn Request**を選択します。
6. **Save**をクリックします。
7. **Attribute Mappings**タブで編集アイコンをクリックし、**PingOne Mappings**の**Email Address**を選択します。  

   <Image alt="ping-identity" src="https://files.readme.io/b93ac5463868c8f5f7760b60492a30f7ae59c52b766e76ef57fbe42e00f4bf2b-16292200523025.png" width="620px" />
8. **Save**をクリックします。

</Accordion>

<div id="create-ping-groups" />

<Accordion title="Ping Identityのグループを作成する">

Ping IdentityのSAMLアプリを作成したら、ユーザーグループを作成し、ユーザーを追加します。

1. Ping Identityの管理メニューで**Identity**＞**<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/group">Groups</Anchor>** に移動し、＋をクリックします。  

   <Image alt="ping" src="https://files.readme.io/fcc2a3f035a285d96d7b7c3e83cfeed64e86cb0f0807e6acced75df89bd8dfc4-16292210866705.png" width="216px" />
2. 右側に開いたセクションでグループ名を入力し、**Save**をクリックします。
3. すべてのユーザーグループについて、手順1～2を繰り返します。

</Accordion>

<div id="create-ping-identity-users-and-assign-them-to-groups-and-roles" />

<Accordion title="Ping Identityのユーザーを作成し、グループとロールを割り当てる">

1. Ping Identityの管理メニューで**Identity**＞<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/user">**Users**</Anchor>に移動し、＋をクリックします。  

   ![ping](https://files.readme.io/802946a62c1df918b82cccc1cf0855ffea8167ed91aa6b0d6bce8973c37b4e75-16292200536081.png)
2. 右側に開いたセクションで、次の設定を行います。
   1. ユーザーの氏名とメールアドレスを入力します。
   2. **Administrator Population**を選択します。
   3. ユーザーのワンタイムパスワードを作成するか、**Generate Password**をクリックして自動生成します。ユーザーはPing Identityにログインした際に、パスワードを作成する必要があります。
   4. **Save**をクリックします。
3. **Groups**の編集ボタンをクリックし、ユーザーを追加するグループを選択して、**Save**をクリックします。
4. **Roles**タブ＞**Grant roles**をクリックし、ユーザーに割り当てるロールを選択して、**Save**をクリックします。

</Accordion>

<div id="provide-access-to-your-groups-and-activate-the-app" />

<Accordion title="グループにアクセスを許可してアプリを有効化する">

### グループにアクセスを許可する

1. Ping Identityの管理メニューで**Connections**＞**<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** に移動し、作成したアプリを選択します。  

   ![pi-applications.png](https://files.readme.io/6c8545bc5334747d7da6a090ca745c1b00cfedc3f48e59ccc304c814885cd183-16522614384785.png)
2. 右側に開いたセクションで**Access**タブを選択し、編集ボタンをクリックします。
3. 作成したグループを選択し、**Save**をクリックします。

### アプリを有効化する

1. Ping Identityの管理メニューで**Connections**＞**<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** に移動し、作成したアプリを選択します。
2. アプリを有効化します。  

   ![pi-appsflyer](https://files.readme.io/24c34f3426ae7b46301316937ae8485464e0b3810808e3bbcc1be843ba34a616-16523020816657.png)

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="AppsFlyerで設定を完了する">

IdP側の設定が完了したら、AppsFlyerに戻って<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">残りの設定を完了</Anchor>します。その後、<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">テスト</Anchor>して、正常に動作することを確認します。

</Accordion>

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="https://docs.pingidentity.com/r/en-us/pingfederate-112/pf_ident_provid_sso_config">Ping IdentityのSSO設定ドキュメント</Anchor>

<div data-zendesk-anchors="h_01HDP087XSDCY9W577GARNQ5GS=create-the-appsflyer-app-in-ping h_01HDP087XSRYXKE5TW7HYR3NYZ=create-ping-groups h_01HDP087XSKBVDREY0YZ27CG8T=create-ping-identity-users-and-assign-them-to-groups-and-roles h_01HDP087XSQPN3DAH8HAKMH3GS=provide-access-to-your-groups-and-activate-the-app provide-access-to-your-groups=%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%97%E3%81%AB%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E3%82%92%E8%A8%B1%E5%8F%AF%E3%81%99%E3%82%8B h_01HDP087XST1C28TEJXF3X8XK4=%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%97%E3%81%AB%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E3%82%92%E8%A8%B1%E5%8F%AF%E3%81%99%E3%82%8B activate-the-app=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96%E3%81%99%E3%82%8B h_01HDP087XSMBE3G6A4DSQ1WHBT=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96%E3%81%99%E3%82%8B h_01HDP087XS1S0XC5W74MK2AYY3=complete-the-process-in-appsflyer h_01HDP0ARX3NJZWBK0KC9Q64MG8=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
