---
title: JumpCloudでのAppsFlyer SSOの設定
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
  created_at: '2023-03-08T07:39:41Z'
  edited_at: '2026-10-28T09:13:36Z'
  id: 13563131567249
  locale: ja
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ja/articles/13563131567249
---
> **概要：** JumpCloudをIDプロバイダー（IdP）として使用する場合の、SSOの設定方法を説明します。

AppsFlyerのSSOを設定するには、まずJumpCloud側で設定を行います。次の手順に従ってください。

<div id="create-the-appsflyer-app-in-jumpcloud" />

<Accordion title="JumpCloudでAppsFlyerアプリを作成する">

**前提条件：** 管理者権限のあるJumpCloudアカウント。

1. JumpCloudの管理メニューで<Anchor target="_blank" href="https://console.jumpcloud.com/#/sso">SSO</Anchor>に移動し、**＋Add New Application**をクリックします。
2. アプリ一覧でAppsFlyerを検索し、**configure**をクリックします。
3. **New SSO**の**General Info**タブで、**Display label**フィールドにアプリ名を入力します。
4. ［任意］説明を追加します。
5. **SSO**タブで、次の設定を行います。
   1. **Upload Metadata：** <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">AppsFlyer SSOのメタデータ</Anchor>をXMLファイルでダウンロードし、ここにアップロードします。
   2. **ACS URLs：** <Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">ユーザーの認証方法</Anchor>に対応するコールバックURLを入力します。
   3. **Login URL：** AppsFlyerの<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">ログインURL</Anchor>を入力します。  

      <Image alt="jumpcloud_sso_tab2__1_.png" src="https://files.readme.io/3b45c98d191a35644c5479a0237e92908ca6f18416f6df2b6e0c84a30940307b-15934671100561.png" width="477px" />
6. **activate**をクリックします。
7. 公開証明書が作成されます。作成されたことを示す表示が、ページの右上に現れます。 **Download Certificate**をクリックします。この証明書は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">手順2のAppsFlyer側の設定</Anchor>で必要になります。

</Accordion>

<div id="create-jumpcloud-users" />

<Accordion title="JumpCloudのユーザーを作成する">

1. JumpCloudの管理メニューから<Anchor target="_blank" href="https://console.jumpcloud.com/#/users">Users</Anchor>に移動し、＋アイコンをクリックします。
2. **Manual user entry**を選択します。  
   <Image alt="cloud_jump_manual_user_entry.png" src="https://files.readme.io/d00299979fa5e036c464c8c6d360965d46e42d5042a31366ced7adc84914c0be-14947838808081.png" width="417px" />
3. 必須項目の**Username**と**Company Email**を入力し、**save user**をクリックします。
4. 自社で認められている方法に従って、ユーザーのパスワードを設定します。
5. 続けてユーザーを追加する場合は、**Save And Create Another**をクリックし、手順3を繰り返します。すべてのユーザーを追加したら、**Save**をクリックします。

</Accordion>

<div id="create-jumpcloud-groups" />

<Accordion title="JumpCloudのグループを作成してAppsFlyerアプリに割り当てる">

グループを作成し、ユーザーを追加します。

1. JumpCloudの管理メニューから<Anchor target="_blank" href="https://console.jumpcloud.com/#/groups/user">User Groups</Anchor>に移動し、＋アイコンをクリックします。
2. グループ名を入力します。
3. **Users**タブで、グループに追加するユーザーを選択します。
4. **Applications**タブで、作成したAppsFlyerアプリを選択します。
5. **save**をクリックします。

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="IdPのSSOメタデータを取得する">

1. JumpCloudの管理メニューで、**SSO**に移動します。
2. 設定したAppsFlyerアプリを選択し、右上の**Copy Metadata URL**をクリックします。コピーしたリンクは、次の手順で貼り付けます。

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="AppsFlyerで設定を完了する">

IdP側の設定が完了したら、AppsFlyerに戻って<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">残りの設定を完了</Anchor>します。その後、<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">テスト</Anchor>して、正常に動作することを確認します。

</Accordion>

<div data-zendesk-anchors="h_01HF99ZFBKPYCP8228VKWPCRHX=create-the-appsflyer-app-in-jumpcloud h_01HF99ZFBKXD6HQE44FDQVQZWK=create-jumpcloud-users h_01HF99ZFBK0T9JQVFNTX705V9M=create-jumpcloud-groups h_01HF99ZFBKDFKTFXEE8Q0MH6SY=get-idp-sso-metadata h_01HF99ZFBK40ZTFKKJNXP4N294=complete-the-process-in-appsflyer" />
