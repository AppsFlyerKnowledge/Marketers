---
title: 2要素認証（2FA）ログインの設定と利用
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
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
  created_at: '2020-06-22T10:25:26Z'
  edited_at: '2026-10-28T09:14:09Z'
  id: 360010178037
  locale: ja
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ja/articles/360010178037
---
> **概要：** 2要素認証（2FA）を使い、ログイン時のセキュリティを強化します。通常のログイン情報に加え、Google Authenticator、Microsoft Authenticator、またはSMSで認証します。

<div id="highlights" />

## 主な内容

* 2FAは、管理者が任意で有効にできる機能です。
* **Google AuthenticatorまたはMicrosoft Authenticator**と、**SMS認証**を選択できます。
* 有効化・無効化は、アカウントのすべてのユーザーに適用されます。
* 有効化した時点のユーザーはそのままログインできますが、次回ログイン時に2FAの設定を求められます。

<div id="-admin-managing-2fa" />

## ![admin.png](https://files.readme.io/d54680123b25ab7929285cebd778e0e74bd0d032df994b04d1bca106381c3dc6-360014518718.png) 管理者による2FAの管理

ユーザーの2FA設定を有効化、リセット、無効化できるのは、管理者のみです。

<div id="activate" />

<Accordion title="有効化">

管理者が**Google AuthenticatorまたはMicrosoft Authenticator**と**SMS認証**の両方を有効にした場合、ユーザーは希望する方法を選択できます。

<div id="note" />

> 📘 **注意**
>
> SMS認証は、通信事業者や国によってSMSの到達率が異なります。 SMSが届かずログインできなくなる事態を防ぐため、SMS認証と、Google AuthenticatorまたはMicrosoft Authenticatorの両方を有効にすることを強く推奨します。

**2FAを有効にするには、次の手順に従います。**

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. <strong>［ログインセキュリティの強化］</strong>セクションで、<strong>［ログイン方法を設定］</strong>をクリックし、<strong>［ログインセキュリティ］</strong>ページを開きます。
3. <strong>［2要素認証（2FA）］</strong>セクションで、<strong>［Google AuthenticatorまたはMicrosoft Authenticator］</strong>と<strong>［SMS認証］</strong>のいずれか、または両方をオンにします。

</Accordion>

<div id="reset" />

<Accordion title="リセット">

2FAを使用しているアカウントでは、ユーザーの2FAをリセットする必要が生じることがあります。リセット後の2FAログイン画面は、デフォルトで**Google AuthenticatorまたはMicrosoft Authenticator**の画面になります。

**ユーザーの2FAをリセットするには、次の手順に従います。**

1. メニューバーで、メールアドレスのドロップダウンをクリックします。
2. <strong>［ユーザー管理］</strong>を選択します。
3. <strong>［ユーザー］</strong>タブで、対象ユーザーの行の右端にあるメニュー<Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />をクリックします。
4. メニューから<strong>［2FAをリセット］</strong>を選択します。

**注意：** 管理者は、自分以外のユーザーの2FAをリセットできます（<Anchor target="_blank" href="/marketers/ja/docs/user-management#admin">アカウント所有者</Anchor>を含みます）。ほかに管理者がいない場合、アカウント所有者の2FAをリセットするには、AppsFlyerのCSチームにお問い合わせください。

</Accordion>

<div id="deactivate" />

<Accordion title="無効化">

2FAを無効にすると、アカウントのユーザーはユーザー名とパスワードのみでログインします。

**2FAを無効にするには、次の手順に従います。**

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. <strong>［ログインセキュリティの強化］</strong>セクションで、<strong>［ログイン方法を設定］</strong>をクリックし、<strong>［ログインセキュリティ］</strong>ページを開きます。
3. <strong>［2要素認証（2FA）］</strong>セクションで、<strong>［Google AuthenticatorまたはMicrosoft Authenticator］</strong>と<strong>［SMS認証］</strong>のいずれか、または両方をオフにします。
4. 無効化を確定します。

</Accordion>

<div id="account-users-using-google-or-microsoft-authenticator" />

## ユーザーによるGoogle AuthenticatorまたはMicrosoft Authenticatorの利用

初回は**Google AuthenticatorまたはMicrosoft Authenticator**の画面がデフォルトで表示されますが、次回以降は前回使用した2FAの認証方法が表示されます。

**Google AuthenticatorまたはMicrosoft Authenticator**を使用しない場合は、設定画面やログイン画面のリンクから、**SMS認証**の2FA画面に切り替えられます。

<div id="firsttime-setup" />

<Accordion title="初回設定">

2FAを初めて利用する前に、各ユーザーは**Google AuthenticatorまたはMicrosoft Authenticator**と、**QRコード**読み取りアプリをダウンロードする必要があります。これらのアプリは、**Google Play**（Android）または**App Store**（iOS）から入手できます。

**新規ユーザー**

1. メールの案内に従い、パスワードを作成します。
2. **AppsFlyer**にログインすると、2FAの設定ページに移動します。
3. 2FAを設定します。
   * **Google AuthenticatorまたはMicrosoft Authenticator**をダウンロードします。
   * QRコードを読み取ります。
   * **Google AuthenticatorまたはMicrosoft Authenticator**に表示される認証コードを入力します。
   * <strong>［認証］</strong>をクリックすると、<strong>［マイアプリ］</strong>ページに移動します。

**既存ユーザー**

1. ユーザー名とパスワードで**AppsFlyer**にログインすると、2FAの設定ページに移動します。
2. 2FAを設定します。
   * **Google AuthenticatorまたはMicrosoft Authenticator**をダウンロードします。
   * QRコードを読み取ります。
   * **Google AuthenticatorまたはMicrosoft Authenticator**に表示される認証コードを入力します。
   * <strong>［認証］</strong>をクリックすると、<strong>［マイアプリ］</strong>ページに移動します。

</Accordion>

<div id="ongoing-use" />

<Accordion title="2回目以降の利用">

**2回目以降は、次の手順で利用します。**

1. ユーザー名とパスワードで**AppsFlyer**にログインすると、2FAのログインページに移動します。
2. スマートフォンで**Google AuthenticatorまたはMicrosoft Authenticator**を開き、認証コードを確認します。
3. 2FAページにコードを入力します。
4. <strong>［認証］</strong>をクリックすると、<strong>［マイアプリ］</strong>ページに移動します。

</Accordion>

<div id="account-users-using-sms-verification" />

## ユーザーによるSMS認証の利用

**SMS認証**を使用しない場合は、設定画面やログイン画面のリンクから、**Google AuthenticatorまたはMicrosoft Authenticator**の2FA画面に切り替えられます。

<div id="firsttime-sms-setup" />

<Accordion title="SMSの初回設定">

デフォルトの2FA認証方法は、**Google AuthenticatorまたはMicrosoft Authenticator**です。 **SMS認証**に切り替えるには、<strong>［SMS認証］</strong>リンクをクリックします。

**新規ユーザー**

1. メールの案内に従い、パスワードを作成します。
2. **AppsFlyer**にログインすると、2FAの設定ページに移動します。
3. 2FAを設定します。
   * 電話番号を数字のみで入力し（特殊文字は使用不可）、<strong>［コードを送信］</strong>をクリックします。
   * SMSの認証コードを入力し、**［認証］をクリックします。**

**既存ユーザー**

1. ユーザー名とパスワードで**AppsFlyer**にログインすると、2FAの設定ページに移動します。
2. 2FAを設定します。
   * 電話番号を数字のみで入力し（特殊文字は使用不可）、<strong>［コードを送信］</strong>をクリックします。
   * SMSの認証コードを入力し、<strong>［認証］</strong>をクリックします。

</Accordion>

<div id="ongoing-sms-use" />

<Accordion title="2回目以降のSMS認証の利用">

**2回目以降は、次の手順で利用します。**

1. ユーザー名とパスワードで**AppsFlyer**にログインすると、2FAのログインページに移動します。
2. 前回のログイン時にSMS認証を使用した場合は、**SMS認証**ページが表示されます。表示されない場合は、**Google AuthenticatorまたはMicrosoft Authenticator**の2FAページ下部にあるリンクをクリックします。
3. 電話番号が自動で表示されます。<strong>［コードを送信］</strong>をクリックします。
4. SMSで届いた認証コードを入力します。
5. <strong>［認証］</strong>をクリックします。

</Accordion>

<div data-zendesk-anchors="highlights=%E4%B8%BB%E3%81%AA%E5%86%85%E5%AE%B9 h_01HEHRKE8PY64KWVSSFR6T4F1Z=%E4%B8%BB%E3%81%AA%E5%86%85%E5%AE%B9 admin-managing-2fa=-%E7%AE%A1%E7%90%86%E8%80%85%E3%81%AB%E3%82%88%E3%82%8B2fa%E3%81%AE%E7%AE%A1%E7%90%86 h_01HEHRKE8PZA3H9SXPRD1FZ50S=-%E7%AE%A1%E7%90%86%E8%80%85%E3%81%AB%E3%82%88%E3%82%8B2fa%E3%81%AE%E7%AE%A1%E7%90%86 h_01HEHRKE8PV0ZADPXHNBBDMKAF=activate 01JCDTA1W486FEFRPT2VYJ2PVX=%E6%B3%A8%E6%84%8F h_01HEHRKE8P9N2W871ZEB1D3MYN=reset h_01HEHRKE8PEDWCNKMG1N4CFDMN=deactivate account-users-using-google-authenticator=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%82%88%E3%82%8Bgoogle-authenticator%E3%81%BE%E3%81%9F%E3%81%AFmicrosoft-authenticator%E3%81%AE%E5%88%A9%E7%94%A8 h_01HEHRKE8P1A2BARBDVMJPH1WY=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%82%88%E3%82%8Bgoogle-authenticator%E3%81%BE%E3%81%9F%E3%81%AFmicrosoft-authenticator%E3%81%AE%E5%88%A9%E7%94%A8 h_01HEHRKE8QQTX3Y9ZY1HZ6GBAG=firsttime-setup h_01HEHRKE8QHWHCMNB5M7S5YVYJ=ongoing-use account-users-using-sms-verification=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%82%88%E3%82%8Bsms%E8%AA%8D%E8%A8%BC%E3%81%AE%E5%88%A9%E7%94%A8 h_01HEHRKE8QZ245ZYBZ4FF814KN=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%82%88%E3%82%8Bsms%E8%AA%8D%E8%A8%BC%E3%81%AE%E5%88%A9%E7%94%A8 h_01HEHRKE8Q30QHGZ5QYMV4MR27=firsttime-sms-setup h_01HEHRKE8Q0229YE5QP5EJFSD8=ongoing-sms-use" />
