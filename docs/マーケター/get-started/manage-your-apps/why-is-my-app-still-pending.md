---
title: アプリリリース後の必須作業について(アプリが未リリースのままの理由)
metadata:
  keywords:
    - Google Play
    - App Store
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2018-10-14T07:22:04Z'
  edited_at: '2026-10-14T09:32:46Z'
  id: 360001533885
  locale: ja
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ja/articles/360001533885
---
> **概要：** 概要：AppsFlyerの管理画面上で、各アプリが既にアプリストアに公開済みなのか、未リリースの状態なのか、ステータスを確認可能です。リリースのタイミングで重要な設定になるので注意してください。

AppsFlyerの管理画面に<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">新しいアプリを追加する</Anchor>際には、まず最初にアプリが未リリースなのか、既にストアにリリースされているのかを選択します。

未リリースアプリは、AppsFlyerの管理画面上ではリリース済みのアプリと同じように見えます。つまり、アクセス可能な管理画面があり、すべての計測機能が機能する状態です。ただし唯一の違いはアプリのロゴ画像で、未リリースアプリの場合実際のロゴではなくAppsFlyerのロゴが表示されます。

![Pending_App.png](https://files.readme.io/fd280ea8dbcd280aae0a1328d1523f52c51d2f30dc163e7a62deb424ae5bc8ed-360001789338.png)

## この設定の仕組み

AppsFlyerでは、1日に数回、アプリのリリース状況を自動でチェックしています。

AppsFlyerがアプリのステータスを確認した時点でまだストアにアプリが存在していなかった場合、そのアプリは管理画面上では未リリースアプリとして表示されます。アプリが最終的にiTunesやGooglePlayに申請され公開されると、ステータスが自動的にアップデートされ、アプリのロゴ画像はそのアプリのオリジナルのロゴ画像に変更されます。

管理画面上でのアプリのステータスは、データ収集と計測には影響しません。アプリがGooglePlay、もしくはAppStoreに公開されユーザーがアプリをインストールして使用すると、インストールとアプリ内イベントのデータが管理画面上に同じように表示されます。

## アプリステータスの更新

アプリのステータスをアクティブに変更するために、AppsFlyerはアプリストア上でのステータスを確認しています。もしも、アプリがGooglePlayやiTunesで公開されているにも関わらず、管理画面上ではまだ未リリースの状態で表示されていた場合には、アドミン権限であれば手動でステータスを確認、更新することが可能です。

**前提条件：**

**アプリのステータスを手動で更新するには：**

2. 未リリースのアプリの横にある、 **ステータスを更新**をクリックしてください。  
     

   ![app-refersh-status.png](https://files.readme.io/d995ea3ee3523a8f0d4854f9ec116efc33c892694d56334c483b7d9fa6da8d64-360001704577.png)

## ストアの国設定

アプリによっては、一部の国のみに限定してGooglePlayやiTunesにアプリを公開している場合があります。AppsFlyerがアプリのステータスを正しく確認、更新するためには、**正しいストアの国設定がそのアプリに対して行われていることが重要**です。

### iOS

管理画面に<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">iOSアプリを追加</Anchor>する際には、アプリが公開される(予定)のアプリストアの国を選択してください。間違った国を選択してしまった場合、AppsFlyerはアプリが公開されていてもステータスを更新することができなくなってしまいます。

Appleのアプリストアの国設定を変更するには：

1. AppsFlyer管理画面左メニュー **設定** > アプリ設定**へ移動します。**
2. **アプリストアの国設定**のセクションで、正しい国を選択してください。
3. スクロールダウンして、**設定を保存**をクリックしてください。
4. アプリがまだ未リリースと表示されている場合には、[もう一度**ステータスを更新**のボタンをクリックしてください。](/docs/why-is-my-app-still-pending#アプリステータスの更新)

### Android

管理画面に<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">Androidアプリを追加</Anchor>する際には、GooglePlayの国を選択するオプションはなく、デフォルトでUSに設定されます。もしもUSのGooglePlayストアにアプリを公開しない場合には、AppsFlyerがアプリのステータスを正しく確認、更新するために、正しいストアの国設定をそのアプリに対して行う必要があります。

GooglePlayの国設定を変更するには：

1. AppsFlyer管理画面左メニュー **設定** > アプリ設定**へ移動します。**
2. **アプリストアの国設定**のセクションで、正しい国を選択してください。
3. スクロールダウンして、**設定を保存**をクリックしてください。
4. アプリがまだ未リリースと表示されている場合には、[もう一度**ステータスを更新**のボタンをクリックしてください。](/docs/why-is-my-app-still-pending#アプリステータスの更新)

<div data-zendesk-anchors="whats-happening=%E3%81%93%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF h_01HKW8NT3DWZMYVDYR13BDZDCT=%E3%81%93%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF refreshing-the-app-status=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%81%AE%E6%9B%B4%E6%96%B0 h_01HKW8NT3DY227ASKYX1RC3V5T=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%81%AE%E6%9B%B4%E6%96%B0 store-country=%E3%82%B9%E3%83%88%E3%82%A2%E3%81%AE%E5%9B%BD%E8%A8%AD%E5%AE%9A h_01HKW8NT3DHSDAG9C9225TDNRE=%E3%82%B9%E3%83%88%E3%82%A2%E3%81%AE%E5%9B%BD%E8%A8%AD%E5%AE%9A h_01HKW8NT3DMWVGRB0RE3H3BQ36=ios h_01HKW8NT3D2V81Z1ZBVQKTYX8T=android" />
